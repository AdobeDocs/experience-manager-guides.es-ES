---
title: Personalizar barra de herramientas
description: Aprenda a personalizar la barra de herramientas
exl-id: 14a82c7e-5c07-43a8-bd9e-b221d80f6d05
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 5778ed2855287d1010728e689abbe6020ad56574
workflow-type: tm+mt
source-wordcount: '951'
ht-degree: 0%

---

# Personalizar barra de herramientas {#id172FB00L0V6}

De forma predeterminada, el editor web incluye las funciones editoriales más comunes que requiere cualquier editor DITA. Las funciones como la inserción de elementos de tipo lista \(numerada o con viñetas\), referencia cruzada, referencia de contenido, tabla, párrafo y formato de caracteres están disponibles en el editor. Además de estos elementos básicos, puede personalizar el Editor Web para insertar elementos que se utilizan en el entorno de creación.

>[!NOTE]
>
> Al migrar de la IU antigua a la nueva IU de AEM Guides (aplicable a partir de las versiones 2502 y 5.0 de AEM Guides), las actualizaciones de `ui_config` deben convertirse a configuraciones de IU más flexibles y modulares. Este marco de trabajo ayuda a adoptar cambios sin problemas en la barra de herramientas del editor y en otros widgets de destino según corresponda. Para obtener más información, vea [Información general sobre Convert UI Config](https://experienceleague.adobe.com/en/docs/experience-manager-guides-learn/videos/advanced-user-guide/conver-ui-config).

Existen dos formas de personalizar la barra de herramientas del Editor Web:

- Añadir una nueva funcionalidad a la barra de herramientas

- Elimine cualquier funcionalidad existente de la barra de herramientas


## Añadir una función en la barra de herramientas

Agregar una funcionalidad al Editor web implica dos tareas principales: agregar un icono para la característica en el archivo *ui\_config.json* y agregar la funcionalidad en segundo plano en JavaScript.

**Agregar un icono en la barra de herramientas**

Siga estos pasos para agregar una función a la barra de herramientas del Editor Web:

1. Inicie sesión en AEM y abra el modo CRXDE Lite.

1. Vaya al archivo de configuración predeterminado disponible en la siguiente ubicación:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Cree una copia del archivo de configuración predeterminado en la siguiente ubicación:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Vaya y abra el archivo `ui_config.json` en el nodo `apps` para editarlo.

1. En el archivo `ui_config.json`, agregue la definición de la nueva característica en la sección de barras de herramientas. Normalmente, puede crear un nuevo grupo de botones de barra de herramientas y agregarle uno o más botones de barra de herramientas. O bien, puede agregar un nuevo botón de barra de herramientas dentro de un grupo existente. Se requieren los siguientes detalles para crear un nuevo grupo de barras de herramientas:

   - **type:**Especifique `blockGroup` como el valor `type`. Este valor indica que está creando un grupo de bloques que contendría uno o más grupos de barras de herramientas.

   - **extraclass:** Nombre de la clase o clases separadas por espacio.

   - **elementos:** Especifique la definición de todos los grupos en la barra de herramientas. Cada grupo puede contener uno o varios iconos de la barra de herramientas. Para definir iconos dentro de un grupo de barras de herramientas, debe definir de nuevo el atributo `type` dentro de `items` y establecer su valor en `buttonGroup`. Especifique uno o varios nombres de clase en la propiedad `extraclass`. Especifique el nombre de la característica en la propiedad `label`. El siguiente fragmento del archivo `ui_config.json` muestra la definición del bloque de barra de herramientas principal, seguida de la definición `buttonGroup`:

     ```json
     "toolbar": {    
       "type": "blockGroup",    
       "extraclass": 
       "toolbar operations",    
         "items": [      
           {        
             "type": "buttonGroup",        
             "extraclass": "left-controls",        
             "label": "Left Controls",        
             "items": [
     ```

     En la colección `items`, debe especificar la definición de uno o más iconos de la barra de herramientas.
Debe definir las siguientes propiedades para añadir un icono de la barra de herramientas:

   - **tipo:** Especifique `button` como el valor `type`. Este valor indica que está agregando un botón de barra de herramientas.

   - **icono:** Especifique el nombre del icono de Coral que desea utilizar en la barra de herramientas.

   - **variante:** Especifique `quiet` como el valor `variant`.

   - **título:** Especifique la información del objeto para el icono.

   - **al hacer clic:** Especifique el nombre del comando definido para la característica en el archivo JavaScript. Si el comando requiere parámetros de entrada, especifique el nombre del comando como:

     ```JavaScript
     "on-click": {"name": "AUTHOR_INSERT_ELEMENT", "args": "simpletable"}
     ```

   - **mostrar u ocultar:** Si está definiendo la propiedad `show`, especifique los modos en que se mostrará el icono. Los valores posibles son - `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(mostrar en todos los modos\) o `false` \(ocultar en todos los modos\).

   En lugar de `show`, también puede definir la propiedad `hide`. Los valores posibles son los mismos que en la propiedad `show` con la única diferencia de que el icono no se muestra en el modo especificado.

1. Cree una carpeta *clientlib* y agregue su JavaScript a esta carpeta.

1. Actualice la propiedad categories de la carpeta *clientlib* asignándole el valor de *apps.fmdita.xml\_editor.page\_overrides*.

1. Guarde el archivo *ui\_config.json* y vuelva a cargar el Editor web.


**Muestras de código JavaScript**

En esta sección se proporcionan dos ejemplos de código JavaScript que le ayudarán a empezar a añadir funcionalidades personalizadas. El siguiente ejemplo muestra el número de versión de AEM Guides cuando un usuario hace clic en el icono Mostrar versión de la barra de herramientas.

Agregue el siguiente código a un archivo JavaScript:

```JavaScript
/**
* This file contains an example to show AEM Guides version 
* number when a user clicks on the Show Version icon in the toolbar. 
* Step 1. Create a clientlib folder and add save a file with your *JavaScript code into this folder. A code sample is shared below.
* Step 2: Update the categories property of the clientlib folder by *assigning it the value of 
* "apps.fmdita.xml_editor.page_overrides".
* Step 3: Add the feature in the ui_config.json file as shown after the *sample code. Save the ui_config.json file and reload the Web Editor
 */

(function (window) {
  "use strict";

  window.addEventListener('DOMContentLoaded', function () {
    fmxml.ready(function () {
      fmxml.eventHandler.subscribe({
        key: 'user.alert',
        next: function next() {
          alert("AEM Guides version x.x");
        }
      });
    });
  });
})(window);
```

Añada la función en el archivo ui\_config.json como:

```json
 {
      "type": "button",
      "icon": "alert",
      "title": "About AEM Guides",
      "variant": "quiet",

  "show": "true",
      "on-click": "user.alert"
  } 
```

En el ejemplo siguiente se muestra cómo cambiar el estado de un documento de un archivo activo a &quot;En revisión&quot;.

```JavaScript
/**
* This file contains an example to set the document state of an active *open documen to "In-Review". 
* Step 1. Create a clientlib folder and add save a file with your *JavaScript code into this folder. A code sample is shared below.
* Step 2: Update the categories property of the clientlib folder by *assigning it the value of 
* "apps.fmdita.xml_editor.page_overrides".
* Step 3: Add the feature in the ui_config.json file as shown after the *sample code. Save the ui_config.json file and reload the Web Editor
 */

(function (window) {
  "use strict";

  //Wait for the page has been completely loaded 

  window.addEventListener('DOMContentLoaded', function () {

    //Wait for the xml editor to start
    fmxml.ready(function () {

      //Subscribe to 'user.docstate.to.in-review' event
      fmxml.eventHandler.subscribe({
        key: 'user.docstate.to.in-review',
        next: function next() {
          var docstate = "In-Review"; // New docstate name
          var filePath = fmxml.curEditor.filePath; 
// Get the file path of active open file
          if (filePath) {
            //Call API to change the doc state
            $.ajax({
              type: 'POST',
              url: '/bin/fmdita/states',
              data: {
                paths: filePath,
                operation: "setdocstates",
                docstate: docstate
              }
            }).fail(function (xhr, textStatus, errorThrown) {
              console.error("Cannot update docstate to " + docstate);
            }).success(function (data) {
              console.log('docstate updated to ' + docstate);
            });
          }
        }
      });
    });
  });
})(window);
```

Añada la función en el archivo ui\_config.json como:

```json
 {
      "type": "button",
      "icon": "actions",
      "title": "Change document state to In-Review",
      "variant": "quiet",
      "show": "true",
      "on-click": "user.docstate.to.in-review"
    } 
```

## Eliminación de una función de la barra de herramientas

A veces es posible que no desee proporcionar todas las características disponibles actualmente en el Editor Web, en ese caso puede quitar la característica no deseada de la barra de herramientas del Editor Web.

Realice los siguientes pasos para eliminar cualquier función no deseada de la barra de herramientas:

1. Inicie sesión en AEM y abra el modo CRXDE Lite.

1. Vaya al archivo de configuración predeterminado disponible en la siguiente ubicación:.

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Cree una copia del archivo de configuración predeterminado en la siguiente ubicación:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Vaya y abra el archivo `ui_config.json` en el nodo `apps` para editarlo.
El archivo `ui_config.json` tiene tres secciones:

- **barras de herramientas:**   Esta sección contiene la definición de todas las funciones disponibles en la barra de herramientas del editor, como Insertar/Quitar lista numerada, \(archivo\) Cerrar, Guardar, Comentarios y más.

- **accesos directos:**   Esta sección contiene la definición de los métodos abreviados de teclado asignados a una función concreta del editor.

- **plantillas:**   Esta sección contiene la estructura predefinida de los elementos DITA que puede utilizar en el documento. De forma predeterminada, la sección de plantillas contiene definiciones de plantilla para un párrafo, tabla simple, tabla y elementos de cuerpo. Puede crear una definición de plantilla para cualquier elemento añadiendo una estructura XML válida para el elemento deseado. Por ejemplo, si desea agregar un elemento `p` con cada nuevo elemento `li` en una lista, puede agregar el siguiente código al final de la sección de plantillas para lograrlo:

```HTML
"li": "<li><p></p></li>"
```

1. En la sección de barras de herramientas, quite la entrada de la función que no desee exponer a los usuarios.

1. Guarde el archivo *ui\_config.json* y vuelva a cargar el Editor web.


**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
