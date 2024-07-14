---
title: Configuración de filtros de texto
description: Obtenga información sobre cómo configurar filtros de texto
exl-id: 180e4ab5-5259-4a00-ac3c-bb1d6814ce0d
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 0%

---

# Configuración de filtros de texto {#id21BPD0FK0XA}

AEM Guides AEM proporciona la función para buscar texto en los archivos presentes en la ruta seleccionada del repositorio de. Puede utilizar el filtro para buscar archivos desde el panel del repositorio o para examinar archivos. Mientras trabaja en el Editor Web, debe utilizar el cuadro de diálogo de exploración de archivos para insertar elementos como imagen, referencia o referencia de clave.

AEM De forma predeterminada, se pueden utilizar algunos filtros mejorados para buscar los archivos en el repositorio de. Puede filtrar todos los ficheros DITA o no DITA presentes en la ruta seleccionada. También se pueden buscar valores específicos en los atributos de elementos DITA. También puede buscar archivos que el usuario especificado haya desprotegido.

>[!NOTE]
>
> También puede configurar el perfil global y añadir más filtros para la búsqueda.

Siga estos pasos para configurar los filtros de texto:

1. Inicie sesión en Adobe Experience Manager como administrador.
1. Haz clic en el vínculo **Adobe Experience Manager** de la parte superior y elige **Herramientas**.
1. Seleccione **Guías** de la lista de herramientas y haga clic en **Perfiles de carpeta**.
1. Haga clic en el mosaico **Perfil global**.
1. Haga clic en **Configuración del editor XML**.
1. Haz clic en el icono **Editar** de la parte superior.
1. Descargue el archivo ui\_config.json.
1. Configure los filtros en el archivo. También puede añadir filtros personalizados como se muestra en el ejemplo siguiente:

   En el siguiente fragmento de código se muestra cómo añadir opciones de filtrado Archivos DITA, Elementos DITA, Elementos DITA y Extraído por archivos. También contiene un filtro personalizado: Etiquetas.

   ```json
   [
     {
       "title": "DITA files",
       "property": "jcr:content/metadata/dita_class",
       "operation": "like",
       "children": [
         {
           "title": "DITA Topics",
           "value": "- topic/topic",
           "checked": true
         },
         {
           "title": "DITA Maps",
           "value": "- map/map",
           "checked": true
         }
       ]
     },
     {
       "title": "DITA elements",
       "property": "jcr:content/ditameta",
       "widgetId": "dita_filter",
       "operation": "like"
     },
     {
       "title": "Checked out by",
       "property": "jcr:content/cq:drivelock",
       "operation": "like",
       "itemConfig": {
         "component": "textfield",
         "placeholder": "Checked out by"
       },
       "children": [
         {
           "title": "Check out"
         }
       ]
     },
     {
       "title": "Tags",
       "property": "jcr:content/metadata/cq:tags",
       "itemConfig": {
         "component": "textfield",
         "placeholder": "Enter Tag"
       },
       "children": [
         {
           "title": "Tags"
         }
       ]
     }
   ]
   ```

   En el fragmento de código anterior, el primer filtro es para archivos DITA. La definición del filtro toma los siguientes parámetros:

   - **Título:** El nombre para mostrar del filtro. Este título aparece como la opción de filtrado en el cuadro de diálogo de exploración de archivos.

   - **Propiedad:** Propiedad que debe coincidir en los metadatos del archivo. Por ejemplo, para permitir solo aquellos archivos que tienen los metadatos dita\_class en su propiedad, el filtro de propiedad toma &quot;jcr:content/metadata/dita\_class&quot; como su valor.

   - **Operación** Especifique &quot;existe&quot; para que coincida con la existencia del valor especificado en el parámetro de propiedad

1. Cargue el archivo ui\_config.json actualizado que contiene los filtros agregados.

Los filtros configurados están disponibles en el panel Filtros.

**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
