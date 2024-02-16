---
title: Notas de versión | Novedades de las guías de Adobe Experience Manager, versión de julio de 2023
description: Conozca las funciones nuevas y mejoradas de la versión de julio de 2023 de las guías de Adobe Experience Manager as a Cloud Service
exl-id: 4b907729-4fbf-48ed-a2e1-014bd1101c73
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 0%

---

# Novedades de la versión de julio de 2023 de Adobe Experience Manager Guides as a Cloud Service

Este artículo cubre las funciones nuevas y mejoradas de la versión de julio de 2023 de las guías de Adobe Experience Manager (más adelante denominadas *AEM Guías de as a Cloud Service*).

Para obtener más información sobre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en esta versión, consulte [Notas de versión](release-notes-2023-7-0.md).

## Conectarse a un origen de datos e insertar datos en los temas

AEM Ahora puede conectarse rápidamente a sus fuentes de datos utilizando conectores predeterminados desde las guías de la interfaz de usuario de la interfaz de usuario de la interfaz de usuario de la interfaz de usuario de Gmail. AEM La conexión a una fuente de datos le permite mantener la información sincronizada con la fuente y cualquier actualización de los datos se refleja automáticamente, lo que convierte a las guías en un auténtico centro de contenido. Esta función le ayuda a ahorrar tiempo y esfuerzo para agregar o copiar manualmente los datos.

AEM Ahora, Guías de la permite al administrador configurar los conectores listos para usar para las bases de datos JIRA y SQL (MySQL, PostgreSQL, SQL Server, SQLite). También pueden agregar otros conectores ampliando las interfaces predeterminadas.

Una vez añadidos, puede ver los conectores configurados en la sección **Fuentes de datos** Panel en el editor web.

![](assets/code-snippet-generator.png){width="300" align="left"}

Puede crear un generador de fragmentos de contenido para recuperar los datos de una fuente de datos conectada. A continuación, puede insertar los datos en los temas y editarlos.

Una vez creado un generador de fragmentos de contenido, puede volver a utilizarlo para insertar los datos en cualquier tema. Para obtener más información, consulte [Inserción de un fragmento de contenido desde la fuente de datos](../user-guide/web-editor-content-snippet.md).



## Panel Revisar para mostrar los proyectos de revisión y las tareas de revisión activas

AEM Ahora, Guías de la hace que sus comentarios sean más fluidos. Proporciona el panel Revisiones dentro del Editor web. El panel Revisiones muestra todos los proyectos de revisión y las tareas de revisión activas dentro de los proyectos de revisión de los que forma parte.

Como autor, esta función le ayuda a abrir fácilmente las tareas de revisión, ver los comentarios y dirigirlos rápidamente en una vista centralizada.
![](assets/active-review-task-comments.png){width="800" align="left"}
Para obtener más información, consulte **Revisar** descripción de funciones dentro de [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS) sección.


## Mejoras en la colección de mapas

Una colección de mapas ayuda a organizar varias asignaciones y a publicarlas por lotes. Se han realizado muchas mejoras en la colección de mapas:

- Ahora, también puede agregar ajustes preestablecidos de salida de PDF nativo a una colección de mapas y utilizarlos para generar la salida de PDF.
- Puede ver los ajustes preestablecidos de perfil global y de carpeta creados por el administrador y utilizarlos para generar la salida del PDF.
- Ahora, no solo puede seleccionar un ajuste preestablecido individual, sino que también puede activar todos los ajustes preestablecidos de perfil de carpeta para un mapa DITA de una sola vez.
  ![](assets/edit-map-collection.png){width="800" align="left"}

Para obtener más información, consulte [Usar la colección de mapas para generar resultados](../user-guide/generate-output-use-map-collection-output-generation.md).

## Capacidad para acceder a archivos de HTML temporales al generar la salida del PDF nativo

AEM Ahora, Guías de le permite descargar los archivos de HTML temporales creados al generar la salida de PDF nativa. En la configuración del ajuste preestablecido de salida, seleccione la opción para descargar los archivos temporales.  AEM A continuación, Guías le permite descargar los archivos temporales creados al generar la salida mediante ese ajuste preestablecido.

Esta función permite obtener una mejor perspectiva del proceso de generación con acceso a estilos y diseños provisionales y le ayuda a corregir o cambiar los estilos CSS según sus necesidades.

![](assets/native-pdf-advanced-settings.png){width="800" align="left"}

Para obtener más información, consulte [Crear un ajuste preestablecido de salida de PDF](../web-editor/native-pdf-web-editor.md#create-output-preset).

## Publicación basada en microservicios para generar HTML5 y salida personalizada

AEM El nuevo microservicio de publicación le permite ejecutar grandes cargas de trabajo de publicación simultáneamente en guías de publicación as a Cloud Service y aprovechar la plataforma Adobe I/O Runtime sin servidor líder del sector. Ahora, con el microservicio, también puede generar el HTML 5 y la salida personalizada.
Puede ejecutar varias solicitudes de publicación y obtener un rendimiento mejorado para generar estos formatos de salida.
Para obtener más información, consulte [AEM Configuración de la publicación basada en microservicios para las guías de la as a Cloud Service](../knowledge-base/publishing/configure-microservices.md).

## AEM Consulte los detalles de la versión de las guías de la comunidad en Acerca de la información

AEM Ahora, junto con el **Acerca de** AEM Para obtener más información, también puede ver los detalles de la versión de las Guías de. Puede ver los detalles de la versión actual en la **Acerca de** de la opción **Ayuda** AEM en la página Navegación de la.

![](assets/about-aem-help.png)(width=&quot;800&quot; align=&quot;left&quot;)
