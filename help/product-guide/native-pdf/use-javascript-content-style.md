---
title: Función de publicación nativa de PDF | Usar JavaScript para trabajar con contenido o estilo
description: Aprenda a crear hojas de estilo de uso y a crear estilos para el contenido.
exl-id: 2f301f6a-0d1c-4194-84c2-0fddaef8d3ec
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 1%

---

# Usar JavaScript para trabajar con contenido o estilo

La función Publicación de PDF nativo permite ejecutar JavaScript para manipular el contenido o el estilo aplicados al contenido antes de que se genere el PDF final. Esta función le proporciona un control completo sobre cómo se genera la salida final. Por ejemplo, es posible que desee agregar información de aviso legal a la salida del PDF, que reside en otro PDF. Con JavaScript, puede añadir la información de aviso legal una vez que el PDF se haya creado para el contenido base, pero antes de que se genere el PDF final.\
Para admitir la ejecución de JavaScript, la función de publicación de PDF nativo le ofrece las siguientes funciones de devolución de llamada:

* `window.pdfLayout.onBeforeCreateTOC(callback)`: Esta función de llamada de retorno se ejecuta antes de que se genere la tabla de contenido.
* `window.pdfLayout.onBeforePagination(callback)`: Esta función de llamada de retorno se ejecuta después de generar la TDC, pero antes de que se añadan saltos de página en el PDF.
* `window.pdfLayout.onAfterPagination(callback)`: Esta función de llamada de retorno se ejecuta después de añadir la tabla de contenido y los saltos de página en el PDF.

>[!NOTE]
>
>Internamente, se mantiene una secuencia de ejecución para estas funciones de rótulo. En primer lugar, se ejecuta onBeforeCreateTOC, seguido de onBeforePagination y, por último, se ejecuta onAfterPagination.

En función del tipo de contenido o modificación de estilo que desee realizar, puede elegir qué función de llamada de retorno utilizar. Por ejemplo, si desea agregar contenido, se recomienda hacerlo antes de generar la TDC. Del mismo modo, si desea realizar algunas actualizaciones de estilo, se pueden realizar antes o después de la paginación.

En el ejemplo siguiente, la posición de los títulos de las figuras cambia de arriba a abajo de las imágenes. Para ello, debe habilitar la opción de ejecución de JavaScript en el ajuste preestablecido. Para ello, realice los siguientes pasos:

1. Abra la programación para editarla.
1. Vaya a la **Avanzadas** pestaña.
1. Seleccione el **Habilitar JavaScript** opción.
1. Guarde el ajuste preestablecido y cierre.

A continuación, cree un archivo JavaScript con el siguiente código y guárdelo en la carpeta Recursos de la plantilla:

```css
...
/*
* DITA only allows the figure title to be placed above images 
* This JavaScript code is used to move the figure title below the image
* */
window.addEventListener('DOMContentLoaded', function () {
    window.pdfLayout.onBeforeCreateTOC(function() {
        var titleNodes = document.querySelectorAll('.fig > .title')
        for (var i = 0; i < titleNodes.length; i++) {
            var titleNode = titleNodes[i]
            var figNode = titleNode.parentNode
            var imageNode = figNode.querySelector('.image')
            if(imageNode && imageNode.parentNode !== figNode) {
              imageNode = imageNode.parentNode
            }
            if (figNode && imageNode && imageNode.parentNode === figNode) {
                figNode.insertBefore(imageNode, titleNode)
            }
        }
    })
});
...
```

>[!NOTE]
>
>El `window.addEventListener('DOMContentLoaded', function ()` se debe llamar a la función antes de utilizar las funciones de llamada de retorno.

A continuación, se debe llamar a esta secuencia de comandos desde un archivo de plantilla que se utiliza para generar la salida del PDF. Para nuestro ejemplo, lo añadiremos en la plantilla del índice. Asegúrese de que la variable `<script>` se añade dentro de un `<div>` dentro de `<body>` etiqueta. Si lo agrega en el `<head>` o fuera del `<body>` , el script no se ejecutará.

<img src="./assets/js-added-resources-template.png" width="500">

La salida generada con este código y la plantilla muestran el título de la figura debajo de la imagen:

<img src="./assets/fig-title-below-image.png" width="500">

## Agregar una marca de agua a la salida del PDF para los borradores de documentos {#watermark-draft-document}

También puede utilizar JavaScript para agregar marcas de agua condicionales. Estas marcas de agua se agregan al documento cuando se cumple la condición definida.\
Por ejemplo, puede crear un archivo JavaScript con el siguiente código para crear una marca de agua en la salida del PDF del documento que aún no está aprobado. Esta marca de agua no aparece si genera el PDF para el documento en el estado de documento &quot;Aprobado&quot;.

```css
...
/*
* This file can be used to add a watermark to the PDF output
* */

window.addEventListener('DOMContentLoaded', function () {
    var watermark = 'Draft'
    var metaTag = document.getElementsByTagName('meta')
    css = "@page {\n  @left-middle {\n    content: \"".concat(watermark, "\";\n    z-index: 100;\n    font-family: sans-serif;\n    font-size: 80pt;\n    font-weight: bold;\n    color: gray(0, 0.3);\n    text-align: center;\n    transform: rotate(-54.7deg);\n    position: absolute;\n    left: 0;\n    top: 0;\n    width: 100%;\n    height: 100%;\n  }\n}")
    head = document.head || document.getElementsByTagName('head')[0], style = document.createElement('style');
    style.appendChild(document.createTextNode(css));
    window.pdfLayout.onBeforePagination(function () {
        for (let i = 0; i < metaTag.length; i++) {
            if (metaTag[i].getAttribute('name') === 'docstate' && metaTag[i].getAttribute('value') !== 'Approved') {
                head.appendChild(style);
            }
        }
    })
});
...
```

La salida del PDF generada con este código muestra una marca de agua *Borrador* en la portada del documento:

<img src="./assets/draft-watermark.png" width="500">
