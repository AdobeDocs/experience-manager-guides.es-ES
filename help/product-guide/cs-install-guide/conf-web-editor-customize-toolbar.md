---
title: Personalizar barra de herramientas
description: Aprenda a personalizar la barra de herramientas
exl-id: ba82af48-9357-4f29-90ce-6793366ab432
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 0%

---

# Personalizar barra de herramientas {#id172FB00L0V6}

De forma predeterminada, el editor web incluye las funciones editoriales más comunes que requiere cualquier editor DITA. Las funciones como la inserción de elementos de tipo lista \(numerada o con viñetas\), referencia cruzada, referencia de contenido, tabla, párrafo y formato de caracteres están disponibles en el editor. Además de estos elementos básicos, puede personalizar el Editor Web para insertar elementos que se utilizan en el entorno de creación.

Existen dos formas de personalizar la barra de herramientas del Editor Web:

- Añadir una nueva funcionalidad a la barra de herramientas

- Elimine cualquier funcionalidad existente de la barra de herramientas


## Añadir una función en la barra de herramientas

Añadir una funcionalidad al editor web implica dos tareas principales: añadir un icono para la función en la variable *ui\_config.json* y añadir la funcionalidad de fondo en JavaScript.

Siga estos pasos para agregar una función a la barra de herramientas del Editor Web:

1. Para descargar el archivo de configuración de la interfaz de usuario, inicie sesión en Adobe Experience Manager como administrador.

1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.
1. Seleccionar **Guías** en la lista de herramientas y haga clic en **Perfiles de carpeta**.
1. Haga clic en **Perfil global** mosaico.
1. Seleccione el **Configuración del editor XML** y haga clic en **Editar** en la parte superior
1. Haga clic en **Descargar** para descargar el archivo ui\_config.json en su sistema local. A continuación, puede realizar cambios en el archivo y luego cargarlo.
1. En el `ui_config.json` , agregue la definición de la nueva función en la sección barras de herramientas. Guarde el archivo y cárguelo.

   Normalmente, puede crear un nuevo grupo de botones de barra de herramientas y agregarle uno o más botones de barra de herramientas. O bien, puede agregar un nuevo botón de barra de herramientas dentro de un grupo existente. Se requieren los siguientes detalles para crear un nuevo grupo de barras de herramientas:

   **type**: especifique `blockGroup` como el `type` valor. Este valor indica que está creando un grupo de bloques que contendría uno o más grupos de barras de herramientas.

   **extraclase**: Nombre de la clase o clases separadas con espacio.

   **items**: especifique la definición de todos los grupos en la barra de herramientas. Cada grupo puede contener uno o varios iconos de la barra de herramientas. Para definir iconos dentro de un grupo de barras de herramientas, debe definir de nuevo la variable `type` dentro del atributo `items`y establezca su valor en `buttonGroup`. Especifique uno o varios nombres de clase en la variable `extraclass` propiedad. Especifique el nombre de la función en la `label` propiedad. El siguiente fragmento de la `ui_config.json` archivo muestra la definición del bloque de barra de herramientas principal, seguido del `buttonGroup` definición:

       &quot;
       &quot;barra de herramientas&quot;: {
       &quot;type&quot;: &quot;blockGroup&quot;,
       &quot;extraclass&quot;:
       &quot;operaciones de la barra de herramientas&quot;,
       &quot;elementos&quot;: [
       {
       &quot;type&quot;: &quot;buttonGroup&quot;,
       &quot;extra class&quot;: &quot;left-controls&quot;,
       &quot;label&quot;: &quot;Controles izquierdos&quot;,
       &quot;elementos&quot;: [
       &quot;
   
   Dentro de `items` , debe especificar la definición de uno o más iconos de la barra de herramientas.

   Debe definir las siguientes propiedades para añadir un icono de la barra de herramientas:

   **type**: especifique `button` como el `type` valor. Este valor indica que está agregando un botón de barra de herramientas.

   **icono**: especifique el nombre del icono de Coral que desee utilizar en la barra de herramientas.

   **variante**: especifique `quiet` como el `variant` valor.

   **title**: especifique la información del objeto para el icono.

   **al hacer clic**: especifique el nombre del comando definido para la función en el archivo JavaScript. Si el comando requiere parámetros de entrada, especifique el nombre del comando como:

       &quot;Javascript
       &quot;on-click&quot;: {&quot;name&quot;: &quot;AUTHOR_INSERT_ELEMENT&quot;, &quot;args&quot;: &quot;simpletable&quot;}
       &quot;
   
   **mostrar u ocultar**: Si está definiendo la variable `show` y, a continuación, especifique los modos en los que se muestra el icono. Los valores posibles son: `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(mostrar en todos los modos\), o `false` \(ocultar en todos los modos\).

   En lugar de `show`, también puede definir la variable `hide` propiedad. Los valores posibles son los mismos que en `show` con la única diferencia de que el icono no se muestra en el modo especificado.

   AEM En el siguiente ejemplo se muestra el número de versión de las guías de la aplicación cuando el usuario hace clic en el icono Mostrar versión de la barra de herramientas.

   Añada el siguiente código a un archivo JavaScript:

   ```Javascript
   $(document).ready(setTimeout(function() {
                           fmxml.commandHandler.subscribe({
                           key: 'user.alert',
                           next: function() {
                           alert("AEM Guides version x.x")
                           }
                           })
                           }, 1000))
   ```

   Añada la función en la *ui\_config.json* archivo como:

   ```Javascript
   "type": "button",
   "icon": "alert","variant": "quiet","title": "About AEM Guides","show": "true","on-click": "user.alert"
   ```

1. Crear un *clientlib* y agregue el JavaScript a esta carpeta.

1. Actualice la propiedad categories del *clientlib* asignándole el valor de. *apps.fmdita.xml\_editor.page\_overrides*.

1. Guarde el *ui\_config.json* y vuelva a cargar el editor web.


## Eliminación de una función de la barra de herramientas

A veces es posible que no desee proporcionar todas las características disponibles actualmente en el Editor Web, en ese caso puede quitar la característica no deseada de la barra de herramientas del Editor Web.

Realice los siguientes pasos para eliminar cualquier función no deseada de la barra de herramientas:

1. Para descargar el archivo de configuración de la interfaz de usuario, inicie sesión en Adobe Experience Manager como administrador.

1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.
1. Seleccionar **Guías** en la lista de herramientas y haga clic en **Perfiles de carpeta**.
1. Haga clic en **Perfil global** mosaico.
1. Seleccione el **Configuración del editor XML** y haga clic en **Editar** en la parte superior
1. Haga clic en **Descargar** para descargar el archivo ui\_config.json en su sistema local. A continuación, puede realizar cambios en el archivo y luego cargarlo.

   El `ui_config.json` El archivo tiene tres secciones:

   1. **barras de herramientas**: Esta sección contiene la definición de todas las funciones disponibles en la barra de herramientas del editor, como Insertar/Quitar lista numerada, \(archivo\) Cerrar, Guardar, Comentarios y más.

   1. **atajos**: Esta sección contiene la definición de los métodos abreviados de teclado asignados a una función concreta del editor.

   1. **templates**: esta sección contiene la estructura predefinida de elementos DITA que puede utilizar en el documento. De forma predeterminada, la sección de plantillas contiene definiciones de plantilla para un párrafo, tabla simple, tabla y elementos de cuerpo. Puede crear una definición de plantilla para cualquier elemento añadiendo una estructura XML válida para el elemento deseado. Por ejemplo, si desea agregar un `p` con cada elemento nuevo `li` en una lista, puede añadir el siguiente código al final de la sección templates para conseguirlo:

   ```css
   "li": "<li><p></p></li>"
   ```

1. En la sección de barras de herramientas, quite la entrada de la función que no desee exponer a los usuarios.

1. Guarde el *ui\_config.json* y vuelva a cargar el editor web.


**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
