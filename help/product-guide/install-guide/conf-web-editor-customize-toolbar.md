---
title: Personalizar barra de herramientas
description: Aprenda a personalizar la barra de herramientas
exl-id: 14a82c7e-5c07-43a8-bd9e-b221d80f6d05
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 0%

---

# Personalizar barra de herramientas {#id172FB00L0V6}

De forma predeterminada, el editor web incluye las funciones editoriales más comunes que requiere cualquier editor DITA. Las funciones como la inserción de elementos de tipo lista \(numerada o con viñetas\), referencia cruzada, referencia de contenido, tabla, párrafo y formato de caracteres están disponibles en el editor. Además de estos elementos básicos, puede personalizar el Editor Web para insertar elementos que se utilizan en el entorno de creación.

Existen dos formas de personalizar la barra de herramientas del Editor Web:

- Añadir una nueva funcionalidad a la barra de herramientas

- Elimine cualquier funcionalidad existente de la barra de herramientas


## Añadir una función en la barra de herramientas

Añadir una funcionalidad al editor web implica dos tareas principales: añadir un icono para la función en la variable *ui\_config.json* y añadir la funcionalidad de fondo en JavaScript.

**Añadir un icono en la barra de herramientas**

Siga estos pasos para agregar una función a la barra de herramientas del Editor Web:

1. AEM Inicie sesión en la aplicación y abra el modo CRXDE Lite.

1. Vaya al archivo de configuración predeterminado disponible en la siguiente ubicación:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Cree una copia del archivo de configuración predeterminado en la siguiente ubicación:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Vaya a y abra `ui_config.json` archivo en el `apps` nodo para editar.

1. En el `ui_config.json` , agregue la definición de la nueva función en la sección barras de herramientas. Normalmente, puede crear un nuevo grupo de botones de barra de herramientas y agregarle uno o más botones de barra de herramientas. O bien, puede agregar un nuevo botón de barra de herramientas dentro de un grupo existente. Se requieren los siguientes detalles para crear un nuevo grupo de barras de herramientas:

   - **type:**Especificar `blockGroup` como el `type` valor. Este valor indica que está creando un grupo de bloques que contendría uno o más grupos de barras de herramientas.

   - **extraclase:** Nombre de la clase o clases separadas con espacio.

   - **elementos:** Especifique la definición de todos los grupos en la barra de herramientas. Cada grupo puede contener uno o varios iconos de la barra de herramientas. Para definir iconos dentro de un grupo de barras de herramientas, debe definir de nuevo la variable `type` dentro del atributo `items`y establezca su valor en `buttonGroup`. Especifique uno o varios nombres de clase en la variable `extraclass` propiedad. Especifique el nombre de la función en la `label` propiedad. El siguiente fragmento de la `ui_config.json` archivo muestra la definición del bloque de barra de herramientas principal, seguido del `buttonGroup` definición:

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

     Dentro de `items` , debe especificar la definición de uno o más iconos de la barra de herramientas.
Debe definir las siguientes propiedades para añadir un icono de la barra de herramientas:

   - **tipo:** Especificar `button` como el `type` valor. Este valor indica que está agregando un botón de barra de herramientas.

   - **icono:** Especifique el nombre del icono de Coral que desee utilizar en la barra de herramientas.

   - **variante:** Especificar `quiet` como el `variant` valor.

   - **título:** Especifique la información del objeto para el icono.

   - **al hacer clic:** Especifique el nombre del comando definido para la función en el archivo JavaScript. Si el comando requiere parámetros de entrada, especifique el nombre del comando como:

     ```JavaScript
     "on-click": {"name": "AUTHOR_INSERT_ELEMENT", "args": "simpletable"}
     ```

   - **mostrar u ocultar:** Si está definiendo la variable `show` y, a continuación, especifique los modos en los que se muestra el icono. Los valores posibles son: `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(mostrar en todos los modos\), o `false` \(ocultar en todos los modos\).

   En lugar de `show`, también puede definir la variable `hide` propiedad. Los valores posibles son los mismos que en `show` con la única diferencia de que el icono no se muestra en el modo especificado.

1. Crear un *clientlib* y agregue el JavaScript a esta carpeta.

1. Actualice la propiedad categories del *clientlib* asignándole el valor de. *apps.fmdita.xml\_editor.page\_overrides*.

1. Guarde el *ui\_config.json* y vuelva a cargar el editor web.


**Ejemplos de código JavaScript**

En esta sección se proporcionan dos ejemplos de código JavaScript que le ayudarán a empezar a añadir funcionalidades personalizadas. AEM En el siguiente ejemplo se muestra el número de versión de las guías de la aplicación cuando un usuario hace clic en el icono Mostrar versión de la barra de herramientas.

Añada el siguiente código a un archivo JavaScript:

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

1. AEM Inicie sesión en la aplicación y abra el modo CRXDE Lite.

1. Vaya al archivo de configuración predeterminado disponible en la siguiente ubicación:.

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Cree una copia del archivo de configuración predeterminado en la siguiente ubicación:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Vaya a y abra `ui_config.json` archivo en el `apps` nodo para editar.
El `ui_config.json` El archivo tiene tres secciones:

- **barras de herramientas:**   Esta sección contiene la definición de todas las funciones disponibles en la barra de herramientas del editor, como Insertar/Quitar lista numerada, \(archivo\) Cerrar, Guardar, Comentarios y más.

- **métodos abreviados:**   Esta sección contiene la definición de los métodos abreviados de teclado asignados a una función concreta del editor.

- **plantillas:**   Esta sección contiene la estructura predefinida de los elementos DITA que puede utilizar en el documento. De forma predeterminada, la sección de plantillas contiene definiciones de plantilla para un párrafo, tabla simple, tabla y elementos de cuerpo. Puede crear una definición de plantilla para cualquier elemento añadiendo una estructura XML válida para el elemento deseado. Por ejemplo, si desea agregar un `p` con cada elemento nuevo `li` en una lista, puede añadir el siguiente código al final de la sección templates para conseguirlo:

```HTML
"li": "<li><p></p></li>"
```

1. En la sección de barras de herramientas, quite la entrada de la función que no desee exponer a los usuarios.

1. Guarde el *ui\_config.json* y vuelva a cargar el editor web.


**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
