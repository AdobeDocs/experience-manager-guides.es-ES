---
title: Base de conocimiento
description: Obtenga información sobre cómo crear ajustes preestablecidos de la Base de conocimiento desde la consola Mapa. Configure el ajuste preestablecido de salida de la Base de conocimiento en AEM Guides.
feature: Publishing
role: User
exl-id: 31fdfd96-377c-406b-96ed-59a80bf6e03e
source-git-commit: 0d713f9ff4bd48aa90bce368d6ad7abf86ecbbf7
workflow-type: tm+mt
source-wordcount: '1260'
ht-degree: 2%

---

# Base de conocimiento {#knowledge-base}

Siga estos pasos para crear el ajuste preestablecido de **Knowledge Base** desde la consola Mapa:

1. [Abra un archivo de mapa DITA en la consola de mapas](./open-files-map-console.md).

   También puede obtener acceso al archivo de asignación desde el widget **Archivos recientes** en la [sección Información general](./intro-home-page.md#overview). El archivo de mapa seleccionado se abriría en la consola de mapas.
1. En la pestaña **Ajustes preestablecidos de salida**, seleccione el icono + para crear un ajuste preestablecido de salida.
1. Seleccione **Base de conocimiento** del menú desplegable Tipo en el cuadro de diálogo **Nuevo ajuste preestablecido de salida**.
1. En el campo **Destino**, seleccione un destino para la salida generada. Las opciones disponibles son: **Adobe Experience Manager**, **Salesforce** y **ServiceNow**.

   ![](./images/knowledge-base-preset-dialog-box.png){width="350" align="left"}

1. Seleccione la opción **Agregar al perfil de carpeta actual** para crear un ajuste preestablecido de salida dentro del perfil de carpeta actual. El ![icono de perfil de carpeta](images/global-preset-icon.svg) indica un ajuste preestablecido de nivel de perfil de carpeta.

   Obtenga más información sobre [Administrar ajustes preestablecidos de salida de perfil global y de carpeta](./web-editor-manage-output-presets.md).

1. Seleccione **Añadir**.

   Se crea el ajuste preestablecido de la Base de conocimiento.

## Configuración de Knowledge Base{#knowledge-base-configuration}


Las opciones de configuración preestablecidas de la base de conocimiento están organizadas en las fichas **General**, **Artículos** y el destino seleccionado (**AEM**/ **ServiceNow**/ **Salesforce**).

![](./images/kb-aem-preset.png){width="550" align="left"}

### General

Las siguientes opciones de configuración están disponibles en la ficha **General**:

| Opciones de Knowledge Base | Descripción |
| --- | --- |
| Aplicación de condiciones mediante | Seleccione una de las siguientes opciones:<br><br>* **Ninguna aplicada**: Seleccione esta opción si no desea aplicar ninguna condición en la salida publicada.<br>* **archivo DITAVAL**: seleccione los archivos DITAVAL para generar contenido personalizado. Puede seleccionar varios archivos DITAVAL mediante el cuadro de diálogo de exploración o escribiendo la ruta del archivo. Utilice el icono en forma de cruz situado cerca del nombre del archivo para eliminarlo. Los archivos DITAVAL se evalúan en el orden especificado, por lo que las condiciones especificadas en el primer archivo tienen prioridad sobre las condiciones coincidentes especificadas en archivos posteriores. Puede mantener el orden de los archivos añadiendo o eliminando archivos. Si el archivo DITAVAL se mueve a otra ubicación o se elimina, no se elimina automáticamente del ajuste preestablecido. Debe actualizar la ubicación en caso de que los archivos se muevan o eliminen. Puede pasar el ratón sobre el nombre del archivo para ver la ruta en el repositorio de Adobe Experience Manager donde está almacenado el archivo. Solo puede seleccionar archivos DITAVAL y se muestra un error si selecciona cualquier otro tipo de archivo.<br>* **Ajuste preestablecido de condición**: seleccione un ajuste preestablecido de condición en el menú desplegable para aplicar una condición al publicar la salida. La opción está visible si se ha añadido una condición presente en la ficha Ajustes preestablecidos de condición de la consola de mapa DITA. Para obtener más información acerca de los ajustes preestablecidos de condición, vea [Usar ajustes preestablecidos de condición](generate-output-use-condition-presets.md#id1825FL004PN). |
| Usar línea base | Si ha creado una Línea base para el mapa DITA seleccionado, seleccione esta opción para especificar la versión que desea publicar.<br><br>Ver [Trabajar con línea de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obtener más detalles. |
| Flujo de trabajo de generación posterior | Al elegir esta opción, se muestra una nueva lista desplegable Flujo de trabajo de generación posterior que contiene todos los flujos de trabajo configurados en Adobe Experience Manager. Debe seleccionar un flujo de trabajo que desee ejecutar una vez completada la generación de resultados.<br><br>**Nota**: Obtenga más información acerca de cómo [personalizar el flujo de trabajo de generación posterior a la salida](../cs-install-guide/customize-workflows.md#id17A6GI004Y4) en la sección Guía de instalación y configuración para Cloud Services. |

### Artículos

Esta pestaña muestra la vista de árbol o jerárquica del mapa. Elija los temas que desea publicar en una base de conocimientos. Expanda un nodo del índice y elija los temas que desea publicar.

### Target: Adobe Experience Manager/ServiceNow/Salesforce

Las opciones de configuración cambian según el destino seleccionado.


**Adobe Experience Manager**

Se muestran las siguientes opciones de configuración para **Adobe Experience Manager** como destino:


>[!NOTE]
>
>Solo puede utilizar el ajuste preestablecido de la Base de conocimiento de Adobe Experience Manager si el administrador lo ha configurado.

| Opciones de Adobe Experience Manager | Descripción |
| --- | --- |
| Usar ruta del artículo | Seleccione esta opción para ver la **ruta de acceso del artículo** de la carpeta que contiene las plantillas de la base de conocimiento. |
| Ruta de artículo | Este campo aparece si selecciona la opción **Usar ruta del artículo**. Examine para seleccionar el sitio de la base de conocimiento dentro del repositorio de Adobe Experience Manager donde se almacena el resultado. |
| Sitio | Utilice este campo para seleccionar la base de conocimiento de Adobe Experience Manager necesaria. Puede configurar las bases de conocimiento en el sitio de Adobe Experience Manager para almacenar el contenido en función de los permisos. Los artículos de este mapa DITA se pueden publicar en estas bases de conocimiento. |
| Categoría | Seleccione una categoría de la lista desplegable para publicar los temas del índice de esa categoría en el sitio de Adobe Experience Manager. |
| Plantilla de sección y plantilla de artículo | Estos son los componentes estructurales utilizados para organizar el contenido de la salida. Están predefinidas en la plantilla del sitio de Adobe Experience Manager. |
| Flujo de trabajo de generación posterior | Al elegir esta opción, se muestra una nueva lista desplegable Flujo de trabajo de generación de publicaciones que contiene todos los flujos de trabajo configurados en Adobe Experience Manager Debe seleccionar un flujo de trabajo que desee ejecutar después de completar el flujo de trabajo de generación de resultados.<br>Obtenga más información acerca de cómo [personalizar el flujo de trabajo de generación posterior a la salida](../install-guide/customize-workflows.md#id17A6GI004Y4) en la sección Guía de instalación y configuración. |

>[!TIP]
> 
>Seleccione el icono **Actualizar** para rellenar las respectivas plantillas en los campos según la plantilla de la Base de conocimiento que haya seleccionado.

**ServiceNow**

Se muestran las siguientes opciones de configuración para **ServiceNow** como destino:

| Opciones de ServiceNow | Descripción |
| --- | --- |
| Perfil de publicación | Utilice el menú desplegable para seleccionar entre los perfiles de conexión de ServiceNow que configura el administrador. Para obtener más información sobre cómo el administrador puede crear un perfil de publicación, vea la descripción de la característica **Configuración de Workspace** (que aparece como **Configuración** para **Local**) en la sección [Panel izquierdo](./web-editor-features.md#id2051EA0M0HS). |
| Base de conocimiento | Utilice este campo para seleccionar la base de conocimiento de ServiceNow necesaria. Puede configurar bases de conocimiento en el sitio ServiceNow para almacenar el contenido en función de los permisos. Los artículos de este mapa DITA se pueden publicar en estas bases de conocimiento. |
| Categoría y subcategoría | Las categorías son como árboles jerárquicos utilizados para buscar y clasificar artículos de la Base de conocimiento de ServiceNow. Agregue una categoría y subcategoría para publicar los temas y subtemas del índice en esa categoría y subcategoría del sitio ServiceNow. |

**Salesforce**

Se muestran las siguientes opciones de configuración para **Salesforce** como destino:

| Opciones de Salesforce | Descripción |
| --- | --- |
| Perfil de publicación | Utilice la lista desplegable para seleccionar entre los perfiles de conexión de Salesforce que configura el administrador. Para obtener más información sobre cómo el administrador puede crear un perfil de publicación, vea la descripción de la característica **Configuración de Workspace** (que aparece como **Configuración** para **Local**) en la sección [Barra de fichas](./web-editor-features.md#tab-bar). |
| Tipo de registro | Utilice la lista desplegable para seleccionar entre los tipos de registro configurados en Salesforce según la configuración de visibilidad en función del perfil de usuario. Los tipos de registro Salesforce son una forma de agrupar muchos registros de un tipo para ese objeto. Definen cómo se organiza la publicación. Por ejemplo, puede seleccionar el Tipo de registro de preguntas más frecuentes y publicar según el diseño de página de preguntas más frecuentes y los campos. |
| Campo de contenido de artículo | Puede tener diferentes campos y un diseño único para cada plantilla de tipo de registro. Utilice estos campos para introducir información específica según el tipo de artículo. Por ejemplo, puede ver el título, la respuesta y la ecuación de un artículo de preguntas frecuentes. |
| Categorías | Seleccione una categoría de la lista desplegable para publicar los temas del índice de esa categoría en el sitio de Salesforce. |

**Algunas opciones más**

También puede ver las siguientes opciones en los ajustes preestablecidos de Salesforce y ServiceNow:

| Opciones | Descripción |
| --- | --- |
| Elimine el encabezado del tema del cuerpo del artículo. | Seleccione esta opción para quitar el encabezado del tema del artículo en la salida publicada. |
| Cargar como borrador | Seleccione esta opción para cargar el tema y compartirlo como borrador antes de ponerlo a disposición de los usuarios. |
| Cargar imágenes | Seleccione esta opción si desea que las imágenes de los temas se incluyan en la salida publicada. |
| Cargar documentos vinculados | Seleccione esta opción para incluir los documentos vinculados en los temas de la salida publicada. |





**Tema principal:** [Explicación de los ajustes preestablecidos de salida](generate-output-understand-presets.md)
