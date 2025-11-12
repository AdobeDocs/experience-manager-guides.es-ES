---
title: Preguntas frecuentes sobre el rendimiento y la escalabilidad de la publicación en Adobe Experience Manager Guides
description: Obtenga información acerca de las preguntas más frecuentes sobre Rendimiento y escalabilidad de la publicación en Adobe Experience Manager Guides.
source-git-commit: d128860bdff78c100ba348b54a237b237171635f
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 0%

---

# Preguntas frecuentes

A continuación se muestra una lista de respuestas a las preguntas más frecuentes que proporciona información detallada sobre cómo administra Adobe Experience Manager Guides los flujos de trabajo de publicación, el comportamiento de escalado y el rendimiento de la infraestructura. Está diseñado para usuarios empresariales, administradores y equipos de documentación que utilizan Experience Manager Guides para realizar publicaciones a gran escala. En el diagrama se explica el flujo de trabajo general de Experience Manager Guides Publishing Architecture.

![](images/IO_runtime.drawio.png){align="left"}


## ¿Cuántas solicitudes de publicación puede ejecutar Experience Manager Guides al día?

El número de solicitudes de publicación que Experience Manager Guides puede procesar por día depende del tamaño y el tipo de contenido. Según la configuración, el sistema permite un trabajo de publicación por núcleo de procesador. En la configuración actual, se pueden ejecutar 20 trabajos de publicación en paralelo (2 pods × 10 núcleos cada uno).

A medida que el entorno de producción se escala automáticamente, este número puede aumentar a 40 trabajos de publicación simultáneos cuando los pods se escalan hasta 4.

## ¿Cuántas solicitudes de publicación se pueden ejecutar simultáneamente antes de que se pongan en cola?

- Mínimo (predeterminado): 20 trabajos de publicación (2 pods)
- Máximo (escalado): 40 trabajos de publicación (4 pods)

Este número puede variar en función de la carga general del servidor. Si se están ejecutando otros trabajos de Sling en segundo plano, comparten núcleos de procesamiento, lo que reduce potencialmente la concurrencia a menos de 20.

## ¿Afecta la ejecución de varias solicitudes de publicación a otras funcionalidades de la aplicación, como la edición de archivos .dita?

Puede tener algún impacto en el rendimiento, pero suele ser mínimo. La mayoría de los procesamientos intensos se producen en el tiempo de ejecución de E/S (servicio de publicación sin servidor), mientras que la instancia de AEM realiza principalmente operaciones de E/S para la generación de dependencias y el sondeo de estado. Como resultado, la utilización de CPU en AEM sigue siendo baja y las experiencias de creación y edición no se ven muy afectadas.

## ¿Cómo gestiona Experience Manager Guides archivos y gráficos de gran tamaño, como archivos SVG o archivos .dita que superen los 500 KB?

Todos los archivos grandes se comprimen y almacenan en el JCR (repositorio de contenido Java). El tiempo de ejecución de E/S recupera el paquete zip completo antes de iniciar la publicación. Incluso cuando se gestionan varios archivos grandes (por ejemplo, 500 KB cada uno), esto no afecta significativamente a la velocidad de descarga o transferencia debido al empaquetado optimizado y al manejo paralelo de E/S.

## ¿Cuál es la infraestructura y configuración de publicación que utiliza Experience Manager Guides?

Experience Manager Guides utiliza microservicios en contenedores y sin servidor para la publicación. Cada nueva versión del servicio de publicación se presenta como una imagen Docker, implementada automáticamente en el entorno de nube de Adobe. Este diseño garantiza:

- Sin mantenimiento de infraestructura dedicado para los clientes
- Adaptación automática para gestionar la demanda de publicación
- Actualizaciones rápidas y tiempo de inactividad mínimo

## Si la cola de publicación o el sistema de administración se bloquean debido a una sobrecarga, ¿se verán afectadas otras funcionalidades de AEM?

No, el Experience Manager Guides está diseñado con una arquitectura tolerante a errores. Si la cola de publicación se sobrecarga, las solicitudes se vuelven a intentar automáticamente y los pods se escalan automáticamente para gestionar la carga adicional. Más allá de un determinado umbral, la restricción de carga se aplica para mantener la estabilidad. Otras áreas de aplicación (creación, revisión, administración de recursos) no se ven afectadas.

## ¿Hay una herramienta de monitorización o acceso al registro disponible para identificar cuándo Experience Manager Guides está bajo carga pesada (similar a la monitorización Jenkins)?

No, actualmente no tiene acceso a las herramientas de monitorización interna. Para los equipos internos de Adobe, la monitorización se puede realizar utilizando:

- Splunk para el registro y el seguimiento de errores
- CLI de Kubernetes (K8s) para comprobar el rendimiento y el comportamiento de escalado a nivel de pod

Si se observa una degradación del rendimiento, los clientes deben ponerse en contacto con el Soporte técnico de Adobe para iniciar una investigación y un análisis.

## ¿Qué procesamiento se realiza antes de enviar una solicitud de publicación al microservicio?

Cuando se almacena en déclencheur una solicitud de publicación desde la pestaña Ajustes preestablecidos en la consola Mapa, se producen los siguientes pasos:

1. El sistema acepta la solicitud y valida los ajustes preestablecidos de línea base y condicionales.
2. AEM agrega todos los recursos y dependencias DITA que cumplen los requisitos.
3. Estos recursos están agrupados en un paquete zip.
4. El servicio de publicación sin servidor activa un contenedor de Docker, descarga los recursos, ejecuta la operación de publicación y vuelve a colocar los artefactos de salida generados en Experience Manager Guides.

Este flujo de trabajo garantiza una ejecución de publicación fiable, aislada y escalable.

## ¿Cuánto tiempo tarda un mapa en empezar a publicarse en el contenedor de microservicios y cuáles son los factores que definen este tiempo?

Una solicitud de publicación suele tardar unos minutos en enviarse al contenedor del microservicio. Este tiempo inicial se utiliza para la agregación de dependencias en AEM.

Una vez recibida la solicitud en el servicio de publicación sin servidor, el tiempo total de publicación depende de lo siguiente:

- Tamaño del mapa DITA
- Número de temas y recursos de medios
- Complejidad del contenido condicional y las reglas de formato

Las asignaciones más grandes o más complejas pueden tardar proporcionalmente más en publicarse.

## ¿Puede Experience Manager Guides priorizar las solicitudes de publicación en la cola (en lugar de las solicitudes recibidas por primera vez)?

Actualmente, todos los trabajos de publicación se tratan de forma equitativa y siguen un modelo de First-Come, First-Serve (FCFS). Actualmente no hay ningún mecanismo de priorización disponible.

Sin embargo, en futuras versiones, la lógica de priorización (por ejemplo, basada en el tamaño del trabajo o la importancia empresarial) podría introducirse como parte de las mejoras de optimización de colas.

## ¿Cómo gestiona Experience Manager Guides el escalado automático para las solicitudes de publicación?

La infraestructura de publicación de Experience Manager Guides admite el escalado automático en función de la carga. Al publicar, la demanda aumenta:

- Los pods (contenedores) adicionales se giran automáticamente.
- Cada pod puede procesar varios trabajos de publicación en paralelo.
- Una vez que la carga disminuye, los pods se reducen para optimizar el coste y el rendimiento.

Esto garantiza una alta disponibilidad, un rendimiento coherente y un tiempo de cola mínimo durante la carga máxima.

## ¿Qué sucede si un trabajo de publicación falla o se agota el tiempo de espera?

Si una solicitud de publicación falla debido a un problema transitorio (por ejemplo, interrupción de la red, tiempo de espera del servicio):

- se vuelve a intentar automáticamente en función de la lógica de reintento configurada en el servicio de publicación.
- los registros y los mensajes de error se capturan en el servidor con fines diagnósticos.
- Puede ver el estado del error y reintentar la publicación manualmente desde la consola Mapa si es necesario.

## ¿Puede monitorizar o rastrear el progreso de un trabajo de publicación?

Sí, Experience Manager Guides proporciona actualizaciones de estado de trabajos en tiempo real en la pestaña Ajustes preestablecidos de la consola Mapa, que incluye:

- Inicio y hora de finalización del trabajo
- Fase actual (compresión, envío, publicación o carga de resultados)
- Notificaciones de error (si las hay)

Esto le ayuda a comprender el progreso del trabajo e identificar posibles retrasos.

## ¿Qué prácticas recomendadas pueden mejorar el rendimiento de la publicación en Experience Manager Guides?

Para garantizar una velocidad de publicación óptima, siga estas prácticas recomendadas:

- Evite archivos de imagen grandes innecesarios o temas sin referencia
- Usar líneas de base para limitar el ámbito de publicación
- Mantenga las jerarquías de mapas DITA manejables y bien organizadas
- Programar una publicación intensiva durante las horas de menor actividad
- Utilice filtros condicionales de forma eficaz para reducir la carga de procesamiento




