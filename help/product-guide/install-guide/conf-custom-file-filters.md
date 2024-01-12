---
title: Configurar filtros para cuadro de diálogo de exploración de archivos
description: Obtenga información sobre cómo configurar filtros para el cuadro de diálogo de exploración de archivos
exl-id: 1ef09820-3b18-4762-b177-4d40926e21f0
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 0%

---

# Configurar filtros para cuadro de diálogo de exploración de archivos {#id20CIL7009GN}

Mientras trabaja en el Editor Web, debe utilizar el cuadro de diálogo de exploración de archivos para insertar elementos como imagen, referencia o referencia de clave. El cuadro de diálogo de exploración de archivos predeterminado no ofrece ninguna opción de filtrado de archivos. Puede añadir sus propios filtros para acceder a los archivos necesarios de forma fácil y rápida.

Realice los siguientes pasos para agregar las opciones de filtrado de archivos personalizadas al cuadro de diálogo de exploración de archivos:

1. AEM Inicie sesión en la aplicación y abra el modo CRXDE Lite.

1. Vaya al archivo de configuración predeterminado disponible en la siguiente ubicación:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Cree una copia del archivo de configuración predeterminado en la siguiente ubicación:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Vaya a y abra `ui_config.json` archivo en el `apps` nodo para editar.

1. En el `ui_config.json` , añada la definición de los filtros que desea añadir.

   El siguiente fragmento de código muestra cómo agregar dos opciones de filtrado: archivos DITA y archivos de imagen.

   ```json
   "browseFilters": [
       {
         "title": "DITA Files",
         "property": "jcr:content/metadata/dita_class",
         "operation": "exists"
       },
       {
         "title": "Image Files",
         "property": "jcr:content/metadata/dc:format",
         "value": [        
           "image/jpeg",
           "image/gif",
           "image/png"
         ]
       }
   ]
   ```

   En el fragmento de código anterior, el primer filtro es para archivos DITA. La definición del filtro toma los siguientes parámetros:

   - **título:**   El nombre para mostrar del filtro. Este título aparece como la opción de filtrado en el cuadro de diálogo de exploración de archivos.

   - **propiedad:**   Propiedad que debe coincidir en los metadatos del archivo. Por ejemplo, para permitir solo los archivos que tienen el `dita_class` metadatos en su propiedad, el filtro de propiedad toma &quot;`jcr:content/metadata/dita_class`&quot; como su valor.

   - **operación:**   Especifique &quot;`exists`&quot; para coincidir con la existencia del valor especificado en el parámetro de propiedad.

   El segundo filtro es para archivos de imagen. Los parámetros son similares al primer filtro, excepto el parámetro `value` parámetro. El `value` El parámetro toma una matriz de tipos de imagen como valor. Todos los tipos de archivo especificados en el parámetro value se buscan y se muestran en el cuadro de diálogo de exploración de archivos; el resto de tipos de archivo se omiten.

1. Guarde el *ui\_config.json* y vuelva a cargar el editor web.

   Al iniciar el cuadro de diálogo de exploración de archivos, se muestran las opciones de filtro configuradas en el archivo ui\_config.json.

   ![](assets/file-browse-custom-filters.png){width="300" align="left"}
