---
title: Personalizar barra de herramientas
description: Aprenda a personalizar la barra de herramientas
exl-id: ba82af48-9357-4f29-90ce-6793366ab432
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 5778ed2855287d1010728e689abbe6020ad56574
workflow-type: tm+mt
source-wordcount: '1013'
ht-degree: 0%

---

# Personalizar barra de herramientas {#id172FB00L0V6}

De forma predeterminada, el editor web incluye las funciones editoriales más comunes que requiere cualquier editor DITA. Las funciones como la inserción de elementos de tipo lista \(numerada o con viñetas\), referencia cruzada, referencia de contenido, tabla, párrafo y formato de caracteres están disponibles en el editor. Además de estos elementos básicos, puede personalizar el Editor Web para insertar elementos que se utilizan en el entorno de creación.

>[!NOTE]
>
> Al migrar de la IU antigua a la nueva IU de AEM Guides (aplicable a partir de las versiones 2502 y 5.0 de AEM Guides), las actualizaciones de `ui_config` deben convertirse a configuraciones de IU más flexibles y modulares. Este marco de trabajo ayuda a adoptar cambios sin problemas en la barra de herramientas del editor y en otros widgets de destino según corresponda. Para obtener más información, vea [Información general sobre Convert UI Config](https://experienceleague.adobe.com/es/docs/experience-manager-guides-learn/videos/advanced-user-guide/conver-ui-config).

Existen dos formas de personalizar la barra de herramientas del Editor Web:

- Añadir una nueva funcionalidad a la barra de herramientas

- Elimine cualquier funcionalidad existente de la barra de herramientas


## Añadir una función en la barra de herramientas

Agregar una funcionalidad al Editor web implica dos tareas principales: agregar un icono para la característica en el archivo *ui\_config.json* y agregar la funcionalidad en segundo plano en JavaScript.

Siga estos pasos para agregar una función a la barra de herramientas del Editor Web:

1. Para descargar el archivo de configuración de la interfaz de usuario, inicie sesión en Adobe Experience Manager como administrador.

1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.
1. Seleccione **Guías** de la lista de herramientas y haga clic en **Perfiles de carpeta**.
1. Haga clic en el mosaico **Perfil global**.
1. Seleccione la ficha **Configuración del editor XML** y haga clic en el icono **Editar** de la parte superior
1. Haga clic en el icono **Descargar** para descargar el archivo ui\_config.json en su sistema local. A continuación, puede realizar cambios en el archivo y luego cargarlo.
1. En el archivo `ui_config.json`, agregue la definición de la nueva característica en la sección de barras de herramientas. Guarde el archivo y cárguelo.

   Normalmente, puede crear un nuevo grupo de botones de barra de herramientas y agregarle uno o más botones de barra de herramientas. O bien, puede agregar un nuevo botón de barra de herramientas dentro de un grupo existente. Se requieren los siguientes detalles para crear un nuevo grupo de barras de herramientas:

   **tipo**:   Especifique `blockGroup` como el valor `type`. Este valor indica que está creando un grupo de bloques que contendría uno o más grupos de barras de herramientas.

   **extraclase**:   Nombre de la clase o clases separadas con espacio.

   **elementos**:   Especifique la definición de todos los grupos en la barra de herramientas. Cada grupo puede contener uno o varios iconos de la barra de herramientas. Para definir iconos dentro de un grupo de barras de herramientas, debe definir de nuevo el atributo `type` dentro de `items` y establecer su valor en `buttonGroup`. Especifique uno o varios nombres de clase en la propiedad `extraclass`. Especifique el nombre de la característica en la propiedad `label`. El siguiente fragmento del archivo `ui_config.json` muestra la definición del bloque de barra de herramientas principal, seguida de la definición `buttonGroup`:

       &quot;
       &quot;barra de herramientas&quot;: &lbrace;
       &quot;type&quot;: &quot;blockGroup&quot;,
       &quot;extraclass&quot;:
       &quot;operaciones de barra de herramientas&quot;,
       &quot;elementos&quot;: &lbrack;
       &lbrace;
       &quot;type&quot;: &quot;buttonGroup&quot;,
       &quot;extraclass&quot;: &quot;left-controls&quot;,
       &quot;label&quot;: &quot;Controles izquierdos&quot;,
       &quot;elementos&quot;: &lbrack;
       &quot;
   
   En la colección `items`, debe especificar la definición de uno o más iconos de la barra de herramientas.

   Debe definir las siguientes propiedades para añadir un icono de la barra de herramientas:

   **tipo**:   Especifique `button` como el valor `type`. Este valor indica que está agregando un botón de barra de herramientas.

   **icono**:   Especifique el nombre del icono de Coral que desee utilizar en la barra de herramientas.

   **variante**:   Especifique `quiet` como el valor `variant`.

   **título**:   Especifique la información del objeto para el icono.

   **clic**:   Especifique el nombre del comando definido para la función en el archivo JavaScript. Si el comando requiere parámetros de entrada, especifique el nombre del comando como:

       &quot;Javascript
       &quot;al hacer clic&quot;: {&quot;name&quot;: &quot;AUTHOR_INSERT_ELEMENT&quot;, &quot;args&quot;: &quot;simpletable&quot;}
       &quot;
   
   **mostrar u ocultar**:   Si está definiendo la propiedad `show`, especifique los modos en que se mostrará el icono. Los valores posibles son - `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(mostrar en todos los modos\) o `false` \(ocultar en todos los modos\).

   En lugar de `show`, también puede definir la propiedad `hide`. Los valores posibles son los mismos que en la propiedad `show` con la única diferencia de que el icono no se muestra en el modo especificado.

   El siguiente ejemplo muestra el número de versión de AEM Guides cuando el usuario hace clic en el icono Mostrar versión de la barra de herramientas.

   Agregue el siguiente código a un archivo JavaScript:

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

   Agregue la característica en el archivo *ui\_config.json* como:

   ```Javascript
   "type": "button",
   "icon": "alert","variant": "quiet","title": "About AEM Guides","show": "true","on-click": "user.alert"
   ```

1. Cree una carpeta *clientlib* y agregue su JavaScript a esta carpeta.

1. Actualice la propiedad categories de la carpeta *clientlib* asignándole el valor de *apps.fmdita.xml\_editor.page\_overrides*.

1. Guarde el archivo *ui\_config.json* y vuelva a cargar el Editor web.


## Eliminación de una función de la barra de herramientas

A veces es posible que no desee proporcionar todas las características disponibles actualmente en el Editor Web, en ese caso puede quitar la característica no deseada de la barra de herramientas del Editor Web.

Realice los siguientes pasos para eliminar cualquier función no deseada de la barra de herramientas:

1. Para descargar el archivo de configuración de la interfaz de usuario, inicie sesión en Adobe Experience Manager como administrador.

1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.
1. Seleccione **Guías** de la lista de herramientas y haga clic en **Perfiles de carpeta**.
1. Haga clic en el mosaico **Perfil global**.
1. Seleccione la ficha **Configuración del editor XML** y haga clic en el icono **Editar** de la parte superior
1. Haga clic en el icono **Descargar** para descargar el archivo ui\_config.json en su sistema local. A continuación, puede realizar cambios en el archivo y luego cargarlo.

   El archivo `ui_config.json` tiene tres secciones:

   1. **barras de herramientas**:   Esta sección contiene la definición de todas las funciones disponibles en la barra de herramientas del editor, como Insertar/Quitar lista numerada, \(archivo\) Cerrar, Guardar, Comentarios y más.

   1. **métodos abreviados**:   Esta sección contiene la definición de los métodos abreviados de teclado asignados a una función concreta del editor.

   1. **plantillas**:   Esta sección contiene la estructura predefinida de los elementos DITA que puede utilizar en el documento. De forma predeterminada, la sección de plantillas contiene definiciones de plantilla para un párrafo, tabla simple, tabla y elementos de cuerpo. Puede crear una definición de plantilla para cualquier elemento añadiendo una estructura XML válida para el elemento deseado. Por ejemplo, si desea agregar un elemento `p` con cada nuevo elemento `li` en una lista, puede agregar el siguiente código al final de la sección de plantillas para lograrlo:

   ```css
   "li": "<li><p></p></li>"
   ```

1. En la sección de barras de herramientas, quite la entrada de la función que no desee exponer a los usuarios.

1. Guarde el archivo *ui\_config.json* y vuelva a cargar el Editor web.


**Tema principal:**&#x200B;[ Personalizar editor web](conf-web-editor.md)
