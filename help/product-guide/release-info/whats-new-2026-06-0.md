---
title: Notas de versión | Novedades de la versión 2026.06.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las funciones nuevas y mejoradas de la versión 2026.06.0 de Adobe Experience Manager Guides
role: Leader
source-git-commit: f3f30400f776f746427e257e2c937ff3413aa9ac
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 0%

---

# Novedades de la versión 2026.06.0 (junio de 2026)

Este artículo cubre las funciones nuevas y mejoradas introducidas con la versión 2026.06.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener la lista de problemas corregidos en esta versión, vea [Problemas corregidos en la versión 2026.06.0](fixed-issues-2026-06-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2026.06.0](../release-info/upgrade-instructions-2026-06-0.md).


## Nueva recopilación de mapas (Beta) para administrar mapas y publicar salidas

>[!NOTE]
>
> Esta función está disponible actualmente como función de Beta y está desactivada de forma predeterminada. Para habilitarlo en su entorno, póngase en contacto con el equipo de éxito del cliente.

La nueva colección de mapas (Beta) reúne la administración de la colección de mapas y las actividades de generación de resultados en una sola interfaz. Desde una ubicación, puede administrar mapas y ajustes preestablecidos, generar y publicar salidas, ver el historial de generación y publicación, y mucho más. Al unir las tareas de publicación relacionadas, resulta más fácil trabajar con colecciones de mapas y rastrear la actividad de salida en varios mapas y sus idiomas asociados.

![](assets/new-maps-collection.png)

Para obtener más información, vea [Usar nueva colección de asignaciones para la generación de resultados (Beta)](../user-guide/generate-output-use-new-map-collection-output-generation.md).

## Presentación de un nuevo motor de publicación para PDF nativo

Ya está disponible un nuevo motor de publicación, *Native PDF engine v2*, para Native PDF en Experience Manager Guides. Incluye mejoras de procesamiento y correcciones para los problemas del motor nativo de PDF v1. Debido a que se ha actualizado el comportamiento de procesamiento, la salida de PDF generada con *motor de PDF nativo v2* puede diferir de la salida generada con el motor de publicación nativo de PDF existente, *motor de PDF nativo v1*.

Por ejemplo, el texto de los PDF generados puede parecer ligeramente distinto debido a las actualizaciones en las fuentes principales utilizadas por *Motor de PDF nativo v2*. Del mismo modo, las imágenes pueden parecer más nítidas debido a las mejoras en la interpolación de imágenes y el comportamiento de procesamiento.

Aprenda a [habilitar el motor nativo de PDF v2](../native-pdf/conf-new-pdf-engine.md) en su entorno.

Para obtener información sobre **Motor PDF nativo v2**, vea [Trabajar con el motor PDF nativo v2](../native-pdf/new-pdf-engine.md).


## Mejoras del editor

### Compatibilidad con el estilo de cita AMA

Experience Manager Guides ahora admite el estilo de citas de la American Medical Association (AMA), ampliando el marco de citas existente para cumplir con los estándares de documentación requeridos por los clientes en los sectores de salud, regulación y ciencias de la vida.

Cuando se selecciona AMA como estilo de cita en **configuración de Workspace**, las citas se formatean automáticamente según las directrices de AMA, incluida la representación numérica de superíndice, la numeración secuencial y el orden preciso de las listas de referencias. La opción **Analizar cita** en el editor está disponible exclusivamente cuando se selecciona AMA, lo que permite a los autores agregar y analizar citas sin cambiar de contexto.

El estilo de cita AMA es compatible con los formatos de salida nativos de PDF y AEM Sites. Para configurar el estilo de cita, vaya a **Configuración de Workspace** y seleccione AMA en las opciones de estilo de cita. Para obtener detalles, vea [Trabajar con citas](../user-guide/web-editor-apply-citations.md).


### Ahora se admite la compatibilidad con fuentes de datos externas y citas en el nuevo editor

El nuevo editor ahora admite dos funciones existentes de Experience Manager Guides: la capacidad de conexión con fuentes de datos externas y el uso de citas en los documentos.

Los autores pueden seguir utilizando fuentes de datos externas configuradas al crear o actualizar contenido en el nuevo editor. Las citas también son compatibles, por lo que los autores pueden agregar y administrar referencias en su contenido sin cambiar de editor.

## Revisar mejoras

### Sincronizar la finalización de tareas de revisión entre la IU de revisión y la bandeja de entrada de AEM (Beta)

>[!NOTE]
>
> Esta función está disponible actualmente como función de Beta y está desactivada de forma predeterminada. Para habilitarlo en su entorno, póngase en contacto con el equipo de éxito del cliente.

Ahora puede mantener sincronizada la finalización de las tareas de revisión entre la interfaz de usuario de revisión y la bandeja de entrada de AEM. Cuando esta función está habilitada, al completar una tarea en la interfaz de usuario de revisión se elimina de la bandeja de entrada AEM y al completarla desde la bandeja de entrada AEM, se marca como completada en la interfaz de usuario de revisión. Esto ayuda a evitar completar la misma tarea dos veces y facilita el flujo de trabajo de revisión. Los autores y los iniciadores de tareas pueden seguir revisando los comentarios y reasignando tareas cuando sea necesario realizar una revisión adicional. Cuando se reasigna una tarea, se genera una nueva notificación en la bandeja de entrada de AEM para el revisor, lo que permite que el ciclo de revisión continúe sin problemas.

Para obtener más información, vea [Completar la tarea de revisión como revisor](../user-guide/review-complete-review-tasks.md).

## Mejoras en el contenido de aprendizaje

En esta versión están disponibles las siguientes mejoras para la función de contenido Aprendizaje y formación sobre productos:

- Los autores ahora pueden hacer que una comprobación de conocimientos sea obligatoria para los alumnos antes de que avancen en un curso. Se ha introducido una nueva opción **Requerir comprobación de conocimientos para continuar** para la comprobación de conocimientos en los cursos. Cuando está activado, los alumnos deben intentar una comprobación de conocimientos antes de continuar con el contenido del curso siguiente. Esto ayuda a garantizar que las comprobaciones de conocimientos requeridas se completen en puntos designados del curso. Para obtener más información, vea [Otras opciones en el menú Insertar](../learning-content/lc-other-insert-options.md).
- Ahora puede utilizar campos de entrada de texto multilínea al crear contenido de aprendizaje. Esta mejora facilita la captura de respuestas del alumno más largas al admitir saltos de línea y ajuste de texto dentro de un solo campo, sin depender de scripts personalizados. Más información acerca de [Otras opciones en el menú Insertar](../learning-content/lc-other-insert-options.md).
- Las plantillas de salida SCORM ahora admiten la asignación de diferentes diseños de página a diferentes tipos de temas dentro de un curso. Esto le permite configurar diseños específicos para lecciones, cuestionarios, páginas de información general y otros tipos de temas directamente desde la configuración de la plantilla de salida.

  Esto permite que cada tipo de tema utilice un diseño adecuado para su contenido y estructura, en lugar de aplicar el mismo diseño en todas las páginas del curso. Para obtener más información sobre la configuración de diseños de página para plantillas de salida SCORM, vea [Configurar perfiles de carpeta](../lc-config-guide/lc-folder-profile.md).
- Experience Manager Guides ahora admite la publicación directa de contenido SCORM en Adobe Learning Manager (ALM). Después de configurar un perfil de publicación de ALM, los autores pueden generar una salida de SCORM y cargarla directamente en Adobe Learning Manager sin descargar e importar manualmente el paquete.

  Para obtener más información, vea [Configurar el ajuste preestablecido de SCORM](../learning-content/config-scorm-preset.md).


