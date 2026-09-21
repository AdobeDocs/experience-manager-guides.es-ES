---
title: Uso de MCP con Adobe Experience Manager Guides
description: Aprenda a utilizar el protocolo de contexto de modelo (MCP) con AEM Guides para trabajar con temas, mapas, líneas de base e informes a través de un asistente de IA
feature: Authoring
role: User
source-git-commit: 864884f26389d256b0e054e3c0b7400b89f6d6ce
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 0%
---

# Uso del servidor MCP de Adobe Experience Manager Guides

El Protocolo de contexto de modelo (MCP) es una forma estándar en la que los asistentes de IA se conectan a herramientas y datos externos, en lugar de que usted cambie el contexto para operar esas herramientas usted mismo.

El servidor MCP de Adobe Experience Manager Guides lleva esto a Experience Manager Guides. Permite a un asistente de IA habilitado para MCP, como Anthropic Claude, conectarse a su entorno de Experience Manager Guides y actuar en su nombre, bajo sus propios permisos de AEM. Una vez conectado, puede trabajar con sus mapas, temas, líneas de base e informes en Experience Manager Guides as a Cloud Service utilizando un lenguaje natural sencillo.

Este artículo explica por qué MCP es útil para Experience Manager Guides, qué cubre el servidor MCP, con qué aplicaciones funciona y cómo utilizarlo.

## Por qué MCP para Experience Manager Guides es útil

Los equipos de documentación suelen dedicar un tiempo considerable a tareas repetitivas que requieren mucha navegación, como buscar temas en un mapa grande, comprobar estados de documentos, rastrear vínculos rotos, crear líneas de base para una versión o exportar informes. Con el servidor MCP de Experience Manager Guides, puede pedir a un asistente de IA que los gestione directamente, sin cambiar a la interfaz de usuario de Experience Manager Guides.

Por ejemplo:

- En lugar de abrir un mapa y comprobar el estado de cada tema uno a uno, pida al asistente que enumere los temas y sus estados.
- En lugar de iniciar manualmente un informe de vínculos rotos y esperar en la interfaz de usuario de Experience Manager Guides, pida al asistente que ejecute el informe y le indique cuándo ha terminado.
- En lugar de desplazarse a la pantalla de línea de base, pida al asistente que cree una línea de base para un mapa específico.

## Servidor MCP proporcionado por Experience Manager Guides

Experience Manager Guides expone las funcionalidades de MCP para trabajar con contenido de Experience Manager Guides y flujos de trabajo relacionados. Según los permisos de AEM, el servidor MCP proporciona acceso a las siguientes capacidades:

* **Temas y mapas**: Trabaje con temas y mapas a lo largo del ciclo de vida del contenido, desde la creación y visualización de contenido hasta su actualización, control de versiones, bloqueo y eliminación.
* **Líneas bases**: trabaje con líneas bases creando, enumerando, exportando, duplicando, reconstruyendo y etiquetándolas.
  >[!NOTE]
  >
  > Tanto para Cloud Service como para entornos locales, las capacidades de línea de base solo están disponibles cuando [se ha habilitado la nueva línea de base](../user-guide/web-editor-baseline-v2.md).
* **Informes**: obtenga información sobre el contenido al obtener acceso a listas de temas y metadatos, identificar vínculos rotos y revisar el uso multimedia.
* **Sistema**: Para comprender el estado del sistema, compruebe las versiones de los paquetes, el estado del paquete y los diagnósticos del entorno.

Si no tiene permiso para realizar una acción en AEM, no puede realizar la misma acción a través de MCP.

Las herramientas exactas disponibles pueden cambiar con el tiempo. En lugar de depender de una lista fija, pídale al asistente que le muestre lo que está disponible:

`List all Experience Manager Guides tools available and describe what they do.`


## Aplicaciones compatibles

El servidor MCP de Experience Manager Guides es un servidor MCP remoto que puede conectarse con clientes MCP compatibles. En función de su entorno, conecte su cliente MCP y autentique en el servidor MCP de Experience Manager Guides. Para obtener más información, vea [Configurar el servidor MCP de Experience Manager Guides](./configure-aem-guides-mcp.md).

## Uso del servidor MCP de Experience Manager Guides

Una vez conectado, describa lo que desee en lenguaje sencillo. El asistente selecciona la herramienta adecuada y rellena sus parámetros, como la ruta del mapa o el nombre de la línea de base.

>[!IMPORTANT]
>
> Las solicitudes que implican varios pasos o tardan tiempo en finalizarse, como exportaciones, compilaciones de línea de base y actualizaciones masivas, funcionan mejor con un modelo lógico. Estos se ejecutan en segundo plano: el asistente inicia el trabajo y, a continuación, comprueba su estado hasta que el resultado o un vínculo de descarga estén listos.

### Ejemplos de peticiones

Las siguientes indicaciones ilustran solicitudes típicas, cada una de las cuales activa una herramienta diferente:

1. **Comprobar estados de temas en un mapa**

   > Enumera todos los temas del mapa en `/content/dam/docs/user-guide.ditamap` y muestra sus títulos y estados de documento.

1. **Crear una línea de base**

   > Crear una línea de base estática de `/content/dam/docs/user-guide.ditamap` titulada &quot;Versión 3.2&quot;.

1. **Ejecutar un informe**

   > Ejecute el informe de vínculos rotos para la guía del usuario y deme el vínculo de descarga cuando esté listo.

## Gestión de expectativas

- **Validar el resultado**: el asistente puede cometer errores, como elegir el mapa o tema incorrecto. Revise un informe o una nueva línea de base antes de utilizarlo.
- **Mejora con el tiempo**: a medida que el asistente mejora, las tareas que reciben algunas indicaciones hoy pueden recibirlas más tarde.
- **Todavía realiza la llamada**: el asistente puede indicarle el estado de un tema o enumerar los vínculos rotos, pero decidir si el contenido está listo para publicarse sigue dependiendo del revisor o del editor.
- **Tenga cuidado con la aprobación automática**: algunos clientes de MCP, incluido Claude, le permiten aprobar automáticamente las acciones en lugar de confirmar cada una de ellas. Esto es aceptable para acciones de solo lectura, como ejecutar un informe. Para las acciones que crean, cambian o bloquean contenido, confirme cada una de ellas para que pueda revisarlas antes de que surta efecto.

Si tiene alguna pregunta sobre Experience Manager Guides MCP, póngase en contacto con el equipo de éxito del cliente de Adobe.


