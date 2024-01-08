---
title: Base de conocimiento
description: Aprenda a crear ajustes preestablecidos de la base de conocimiento desde el editor web y el panel de mapas. AEM Configure el ajuste preestablecido de salida de la Base de conocimiento en las Guías de.
source-git-commit: 899b493709ee7f1fb31789e4afc3e985fa2505f7
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 1%

---

# Base de conocimiento {#knowledge-base}

Puede crear el **Base de conocimiento** ajuste preestablecido desde el editor web:

En el panel Repositorio, abra el fichero de mapa DITA en **Vista de mapa**, luego en el **Output** , seleccione el icono + para crear un ajuste preestablecido de salida y, a continuación, seleccione **Base de conocimiento** desde el **Tipo** menú desplegable en **Nuevo ajuste preestablecido de salida** diálogo. Puede asignar un nombre al ajuste preestablecido y elegir el destino para generar la salida utilizando **Adobe Experience Manager**, **Salesforce**, o **ServiceNow**.




## Configuración de Knowledge Base{#knowledge-base-configuration}


En el editor web, las siguientes configuraciones se han organizado en la variable **General** y **Artículos** pestañas. También puede configurar los ajustes de la variable específica **Base de conocimiento** ha seleccionado como objetivo, **Adobe Experience Manager**, **Salesforce**, o **ServiceNow**.


### General

| Opciones de Knowledge Base | Descripción |
| --- | --- |
| Aplicación de condiciones mediante | Seleccione una de las siguientes opciones:<br><br>* **Ninguno aplicado**: seleccione esta opción si no desea aplicar ninguna condición en la salida publicada.<br>* **Archivo DITAVAL**: seleccione los archivos DITAVAL para generar contenido personalizado. Puede seleccionar varios archivos DITAVAL mediante el cuadro de diálogo de exploración o escribiendo la ruta del archivo. Utilice el icono en forma de cruz situado cerca del nombre del archivo para eliminarlo. Los archivos DITAVAL se evalúan en el orden especificado, por lo que las condiciones especificadas en el primer archivo tienen prioridad sobre las condiciones coincidentes especificadas en archivos posteriores. Puede mantener el orden de los archivos añadiendo o eliminando archivos. Si el archivo DITAVAL se mueve a otra ubicación o se elimina, no se elimina automáticamente del ajuste preestablecido. Debe actualizar la ubicación en caso de que los archivos se muevan o eliminen. Puede pasar el ratón sobre el nombre del archivo para ver la ruta en el repositorio de Adobe Experience Manager donde está almacenado el archivo. Solo puede seleccionar archivos DITAVAL y se muestra un error si selecciona cualquier otro tipo de archivo.<br>* **Ajuste preestablecido de condición**: Seleccione un ajuste preestablecido de condición en la lista desplegable para aplicar una condición al publicar la salida. La opción está visible si se ha añadido una condición presente en la ficha Ajustes preestablecidos de condición de la consola de mapa DITA. Para obtener más información sobre los ajustes preestablecidos de condición, consulte [Usar ajustes preestablecidos de condición](generate-output-use-condition-presets.md#id1825FL004PN). |
| Usar línea base | Si ha creado una Línea base para el mapa DITA seleccionado, seleccione esta opción para especificar la versión que desea publicar.<br><br>Ver [Trabajar con línea base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obtener más información. |
| Flujo de trabajo de generación posterior | Al elegir esta opción, se muestra una nueva lista desplegable Flujo de trabajo de generación posterior que contiene todos los flujos de trabajo configurados en Adobe Experience Manager. Debe seleccionar un flujo de trabajo que desee ejecutar una vez completada la generación de resultados.<br><br>**Nota**: Obtenga más información acerca de cómo [personalizar flujo de trabajo de generación posterior a la salida](../cs-install-guide/customize-workflows.md#id17A6GI004Y4) de la Guía de instalación y configuración para Cloud Service. |

### ServiceNow

| Opciones de ServiceNow | Descripción |
| --- | --- |
| Publicar perfil | Utilice el menú desplegable para seleccionar entre los perfiles de conexión de ServiceNow que configura el administrador. Para obtener más información sobre cómo el administrador puede crear un perfil de publicación, consulte **Configuración del editor** descripción de la función en [Panel izquierdo](./web-editor-features.md#id2051EA0M0HS) sección. |
| Base de conocimiento | Utilice este campo para seleccionar la base de conocimiento de ServiceNow necesaria. Puede configurar bases de conocimiento en el sitio ServiceNow para almacenar el contenido en función de los permisos. Los artículos de este mapa DITA se pueden publicar en estas bases de conocimiento. |
| Categoría y subcategoría | Las categorías son como árboles jerárquicos utilizados para buscar y clasificar artículos de la Base de conocimiento de ServiceNow. Agregue una categoría y subcategoría para publicar los temas y subtemas del índice en esa categoría y subcategoría del sitio ServiceNow. |

### Salesforce

| Opciones de Salesforce | Descripción |
| --- | --- |
| Publicar perfil | Utilice la lista desplegable para seleccionar entre los perfiles de conexión de Salesforce que configure su administrador. Para obtener más información sobre cómo el administrador puede crear un perfil de publicación, consulte **Configuración del editor** descripción de la función en [Panel izquierdo](./web-editor-features.md#id2051EA0M0HS) sección. |
| Tipo de registro | Utilice la lista desplegable para seleccionar entre los tipos de registro configurados en Salesforce según la configuración de visibilidad basada en el perfil de usuario. Los tipos de registro de Salesforce son una forma de agrupar muchos registros de un tipo para ese objeto. Definen cómo se organiza la publicación. Por ejemplo, puede seleccionar el Tipo de registro de preguntas más frecuentes y publicar según el diseño de página de preguntas más frecuentes y los campos. |
| Campo de contenido de artículo | Puede tener diferentes campos y un diseño único para cada plantilla de tipo de registro. Utilice estos campos para introducir información específica según el tipo de artículo. Por ejemplo, puede ver el título, la respuesta y la ecuación de un artículo de preguntas frecuentes. |
| Categorías | Seleccione una categoría del menú desplegable para publicar los temas del índice de esa categoría en el sitio de Salesforce. |

También puede ver las siguientes opciones en los ajustes preestablecidos de Salesforce y ServiceNow: | Opciones | Descripción | | — | — | |Quitar el encabezado del tema del cuerpo del artículo.|Seleccione esta opción para quitar el encabezado del tema del artículo en la salida publicada. | |Cargar como borrador | Seleccione esta opción para cargar el tema y compartirlo como borrador antes de ponerlo a disposición de los usuarios.| |Cargar imágenes| Seleccione esta opción si desea que las imágenes de los temas se incluyan en la salida publicada.| |Cargar documentos vinculados| Seleccione esta opción para incluir los documentos vinculados en los temas de la salida publicada.|


### Adobe Experience Manager

>[!NOTE]
>
>Puede utilizar el ajuste preestablecido de la Base de conocimiento de Adobe Experience Manager si el administrador lo ha configurado. Para obtener más información, consulte [Publicación basada en artículos desde el editor web](../install-guide/configure-article-based-publishing.md) de la Guía de instalación y configuración.

| Opciones de Adobe Experience Manager | Descripción |
| --- | --- |
| Usar ruta del artículo | Seleccione esta opción para ver el **Ruta del artículo** de la carpeta que contiene las plantillas de Knowledge Base. |
| Ruta de artículo | Este campo aparece si selecciona la opción **Usar ruta del artículo**. Examine para seleccionar el sitio de la base de conocimiento dentro del repositorio de Adobe Experience Manager donde se almacena el resultado. |
| Sitio | Utilice este campo para seleccionar la base de conocimiento de Adobe Experience Manager necesaria. Puede configurar las bases de conocimiento en el sitio de Adobe Experience Manager para almacenar el contenido en función de los permisos. Los artículos de este mapa DITA se pueden publicar en estas bases de conocimiento. |
| Categoría | Seleccione una categoría del menú desplegable para publicar los temas del índice de esa categoría en el sitio de Adobe de Experience Manager. |
| Plantilla de sección y plantilla de artículo | Estos son los componentes estructurales utilizados para organizar el contenido de la salida. Están predefinidas en la plantilla del sitio de Adobe Experience Manager. |
| Flujo de trabajo de generación posterior | Al elegir esta opción, se muestra una nueva lista desplegable Flujo de trabajo de generación de publicaciones que contiene todos los flujos de trabajo configurados en Adobe Experience Manager Debe seleccionar un flujo de trabajo que desee ejecutar después de completar el flujo de trabajo de generación de resultados.<br>Obtenga más información sobre cómo [personalizar flujo de trabajo de generación posterior a la salida](../install-guide/customize-workflows.md#id17A6GI004Y4) de la Guía de instalación y configuración. |
>[!TIP]
> 
>Seleccionar **Actualizar** ![icono de actualización](images/navtitle-refresh-icon.svg) para rellenar las respectivas plantillas en los campos según la plantilla de la Base de conocimiento que haya seleccionado.

### Artículos

Esta pestaña muestra la vista de árbol o jerárquica del mapa. Elija los temas que desea publicar en una base de conocimientos. Expanda un nodo del índice y elija los temas que desea publicar.

**Tema principal:** [Explicación de los ajustes preestablecidos de salida](generate-output-understand-presets.md)
