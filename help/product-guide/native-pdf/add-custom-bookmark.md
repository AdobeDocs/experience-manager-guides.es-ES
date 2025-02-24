---
title: Función de publicación nativa de PDF | Añadir un marcador personalizado en la salida de PDF
description: Aprenda a crear hojas de estilo de uso y a crear estilos para el contenido.
exl-id: 6e6dbba3-da41-4066-b7b2-735a3d92b70a
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 1c96f25c3b970d04d23e8faf94a8f39095f6bd2c
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---

# Añadir un marcador personalizado en la salida de PDF

Por lo general, la tabla de contenido de un mapa DITA se replica como marcadores en la salida final de PDF, incluido el título **Contenido** que abre la página de tabla de contenido cuando se selecciona. Esta tabla de contenido se crea a partir de los títulos de temas o secciones del mapa DITA.

A veces, es posible que desee agregar un marcador personalizado a un contenido en particular en la salida de PDF para facilitar la navegación. Esto se puede lograr agregando un atributo `outputclass` en el elemento y aplicándole el atributo siguiente:

`bookmark-level: 3`

En este caso, `bookmark-level` es un atributo y el número `3` es el valor que indica el nivel en la jerarquía de marcadores donde se agrega el marcador. En el ejemplo siguiente, el tema de primer nivel &quot;Contactos&quot; tiene una tabla, &quot;Lista de contactos&quot; en la que se ha agregado un atributo `outputclass` con el valor `custom-bookmark`.


<img src="./assets/custom-bookmark-attribute.png" width="500">

La siguiente definición de la clase `custom-bookmark` se agrega en el archivo CSS:

```css
…
/*Adding a custom bookmark*/
.custom-bookmark{
    bookmark-level: 2
}
…
```

En la salida de PDF, la tabla *Contact list* se agrega en el segundo nivel de la lista de marcadores de PDF, como se muestra a continuación:

![](assets/custom-bookmark-in-pdf-output.png) {width="300" align="left"}

>[!NOTE]
>
>Debe elegir el nivel correcto en el que se agrega el marcador personalizado. Si especifica un número menor que el marcador del tema principal, el marcador personalizado toma la posición del marcador principal y todos los demás marcadores se muestran como secundarios. Esto puede dar lugar a una estructura de marcadores inesperada.

**Quitando el título de contenido de los marcadores de salida de PDF**

Si no desea incluir el título **Contents** en la salida de PDF, puede eliminarlo colocando **Contents** dentro del elemento `<p>` en lugar del elemento `<h1>`.

El proceso paso a paso para eliminar el título de Contenido de los marcadores es el siguiente:

1. Abra la plantilla de PDF que esté utilizando para la salida de PDF.
2. Abra la **página de índice** dentro de **diseños de página**.
La página del índice se muestra a la derecha.
3. Cambie al modo **Source** y cambie el elemento donde Contents se encuentra desde `<h1>` a `<p>`.

Antes del cambio:

```
<h1 class="toc-title">Contents</h1>
```

Después del cambio:

```
<p class="toc-title">Contents</p>
```

Guarde los cambios y vuelva a generar la salida.





