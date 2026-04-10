---
title: Configurar filtros para cuadro de diálogo de exploración de archivos
description: Obtenga información sobre cómo configurar filtros para el cuadro de diálogo de exploración de archivos
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 0%

---

# Configurar filtros para cuadro de diálogo de exploración de archivos

Mientras trabaja en el Editor Web, debe utilizar el cuadro de diálogo de exploración de archivos para insertar elementos como imagen, referencia o referencia de clave. El cuadro de diálogo de exploración de archivos predeterminado no ofrece ninguna opción de filtrado de archivos. Puede añadir sus propios filtros para acceder a los archivos necesarios de forma fácil y rápida.

Las siguientes pestañas proporcionan instrucciones para añadir las opciones de filtrado de archivos personalizadas al cuadro de diálogo de exploración de archivos en función de la configuración de Experience Manager Guides: Cloud Service o Local.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Para descargar el archivo de configuración de la interfaz de usuario, inicie sesión en Adobe Experience Manager como administrador.

1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.
1. Seleccione **Guías** de la lista de herramientas y haga clic en **Perfiles de carpeta**.
1. Haga clic en el mosaico **Perfil global**.
1. Seleccione la ficha **Configuración del editor XML** y haga clic en el icono **Editar** de la parte superior
1. Haga clic en el icono **Descargar** para descargar el archivo ui\_config.json en su sistema local. A continuación, puede realizar cambios en el archivo y luego cargarlo.
1. En el archivo `ui_config.json`, agregue la definición de los filtros que desea agregar.

   El siguiente fragmento de código muestra cómo agregar dos opciones de filtrado: archivos DITA y archivos de imagen.

   ```
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

   title
:   El nombre para mostrar del filtro. Este título aparece como la opción de filtrado en el cuadro de diálogo de exploración de archivos.

   propiedad
:   Propiedad que debe coincidir en los metadatos del archivo. Por ejemplo, para permitir solo los archivos que tienen los metadatos `dita_class` en su propiedad, el filtro de propiedad toma &quot; `jcr:content/metadata/dita_class`&quot; como su valor.

   operación
:   Especifique &quot;`exists`&quot; para que coincida con la existencia del valor especificado en el parámetro de propiedad.

   El segundo filtro es para archivos de imagen. Los parámetros son similares al primer filtro excepto el parámetro `value`. El parámetro `value` toma una matriz de tipos de imagen como valor. Todos los tipos de archivo especificados en el parámetro value se buscan y se muestran en el cuadro de diálogo de exploración de archivos; el resto de tipos de archivo se omiten.

1. Guarde el archivo *ui\_config.json* y cárguelo. A continuación, vuelva a cargar el editor web.

   Al iniciar el cuadro de diálogo de exploración de archivos, se muestran las opciones de filtro configuradas en el archivo ui\_config.json.

   ![](assets/file-browse-custom-filters.png)

>[!TAB Local]

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

   - **título:**   El nombre para mostrar del filtro. Este título aparece como la opción de filtrado en el cuadro de diálogo de exploración de archivos.

   - **propiedad:**   Propiedad que debe coincidir en los metadatos del archivo. Por ejemplo, para permitir solamente los archivos que tienen los metadatos `dita_class` en su propiedad, el filtro de propiedad toma &quot;`jcr:content/metadata/dita_class`&quot; como su valor.

   - **operación:**   Especifique &quot;`exists`&quot; para que coincida con la existencia del valor especificado en el parámetro de propiedad.

   El segundo filtro es para archivos de imagen. Los parámetros son similares al primer filtro excepto el parámetro `value`. El parámetro `value` toma una matriz de tipos de imagen como valor. Todos los tipos de archivo especificados en el parámetro value se buscan y se muestran en el cuadro de diálogo de exploración de archivos; el resto de tipos de archivo se omiten.

1. Guarde el archivo *ui\_config.json* y vuelva a cargar el Editor web.

   Al iniciar el cuadro de diálogo de exploración de archivos, se muestran las opciones de filtro configuradas en el archivo ui\_config.json.

   ![](assets/file-browse-custom-filters.png){width="300" align="left"}

>[!ENDTABS]


**Tema principal:**[ Personalizar editor web](customize-overview.md)
