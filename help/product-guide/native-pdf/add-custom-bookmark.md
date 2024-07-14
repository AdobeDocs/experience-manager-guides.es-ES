---
title: Función nativa de PDF Publish | Añadir un marcador personalizado en la salida del PDF
description: Aprenda a crear hojas de estilo de uso y a crear estilos para el contenido.
exl-id: 6e6dbba3-da41-4066-b7b2-735a3d92b70a
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---

# Añadir un marcador personalizado en la salida del PDF

Por lo general, la tabla de contenido de un mapa DITA se duplica como marcadores en la salida final del PDF. Esta tabla de contenido se crea a partir de los títulos de temas o secciones del mapa DITA. A veces, es posible que desee añadir un marcador personalizado a un contenido en particular en la salida del PDF para facilitar la navegación. Esto se puede lograr agregando un atributo `outputclass` en el elemento y aplicándole el atributo siguiente:

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

En la salida del PDF, la tabla *Contact list* se agrega en el segundo nivel de la lista de marcadores del PDF, como se muestra a continuación:

<img src="./assets/custom-bookmark-in-pdf-output.png" width="500">

>[!NOTE]
>
>Debe elegir el nivel correcto en el que se agrega el marcador personalizado. Si especifica un número menor que el marcador del tema principal, el marcador personalizado toma la posición del marcador principal y todos los demás marcadores se muestran como secundarios. Esto puede dar lugar a una estructura de marcadores inesperada.
