---
title: Configurar filtros para cuadro de diálogo de exploración de archivos
description: Obtenga información sobre cómo configurar filtros para el cuadro de diálogo de exploración de archivos
exl-id: 1ef09820-3b18-4762-b177-4d40926e21f0
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/7AzojwFiEQkwYtDnwsHhmMOwSCG3vWgsZW5oXZRsTFw
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 323
ht-degree: 0%

---

# Configurar filtros para cuadro de diálogo de exploración de archivos {#id20CIL7009GN}

Mientras trabaja en el editor, debe utilizar el cuadro de diálogo de exploración de archivos para insertar elementos como imagen, referencia o referencia de clave. El cuadro de diálogo de exploración de archivos predeterminado no ofrece ninguna opción de filtrado de archivos. Puede añadir sus propios filtros para acceder a los archivos necesarios de forma fácil y rápida.

Realice los siguientes pasos para agregar las opciones de filtrado de archivos personalizadas al cuadro de diálogo de exploración de archivos:

1. Inicie sesión en AEM y abra el modo CRXDE Lite.

1. Vaya al archivo de configuración predeterminado disponible en la siguiente ubicación:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Cree una copia del archivo de configuración predeterminado en la siguiente ubicación:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Vaya y abra el archivo `ui_config.json` en el nodo `apps` para editarlo.

1. En el archivo `ui_config.json`, agregue la definición de los filtros que desea agregar.

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

   - **título:** El nombre para mostrar del filtro. Este título aparece como la opción de filtrado en el cuadro de diálogo de exploración de archivos.

   - **propiedad:** Propiedad que debe coincidir en los metadatos del archivo. Por ejemplo, para permitir solamente los archivos que tienen los metadatos `dita_class` en su propiedad, el filtro de propiedad toma &quot;`jcr:content/metadata/dita_class`&quot; como su valor.

   - **operación:** Especifique &quot;`exists`&quot; para que coincida con la existencia del valor especificado en el parámetro de propiedad.

   El segundo filtro es para archivos de imagen. Los parámetros son similares al primer filtro excepto el parámetro `value`. El parámetro `value` toma una matriz de tipos de imagen como valor. Todos los tipos de archivo especificados en el parámetro value se buscan y se muestran en el cuadro de diálogo de exploración de archivos; el resto de tipos de archivo se omiten.

1. Guarde el archivo *ui\_config.json* y vuelva a cargar el Editor.

   Al iniciar el cuadro de diálogo de exploración de archivos, se muestran las opciones de filtro configuradas en el archivo ui\_config.json.

   ![](assets/file-browse-custom-filters.png){width="300"}
