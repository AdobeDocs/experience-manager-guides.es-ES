---
title: Función nativa de PDF Publish | Aplicar un estilo personalizado a las entradas del índice y al contenido del tema
description: Aprenda a crear hojas de estilo de uso y a crear estilos para el contenido.
exl-id: f65c9683-a1fc-432a-854b-83e8f39d7dae
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: db4c823e592e249e1d828a7071fc0848a5e68c0f
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 0%

---

# Aplicar un estilo personalizado a las entradas del índice y al contenido del tema

A veces, es posible que desee aplicar un estilo personalizado a las entradas de la tabla de contenido o a un tema en particular. Esto se puede lograr asociando un atributo `outputclass` con el elemento `<topicref>` del mapa DITA. Además, si desea aplicar un formato personalizado a todo un tema, también puede hacerlo ampliando la definición de estilo del atributo en CSS.

Veamos un ejemplo de un nuevo tema que desee enviar para su revisión. Para facilitar la identificación del tema actualizado, debe agregar un atributo `outputclass` al elemento `<topicref>` en el mapa DITA y, a continuación, definir un estilo personalizado para el mismo en CSS.

En el ejemplo siguiente, al tema *Historial de vuelos* se le ha asignado un atributo `outputclass` con el valor `new-topic`.

<img src="./assets/new-topic-attribute-in-map.png" width="500">

La definición de clase de `new-topic` en un archivo CSS puede permitirle definir el estilo para los siguientes elementos:
* La entrada principal del índice o mini-índice
* Título del tema en el contenido principal
* Todo el contenido del tema, incluido el título

Veamos cómo se puede definir cada uno de estos escenarios en CSS. En la siguiente definición CSS de la clase `new-topic`, se ha cambiado el color del texto.

```css
…
.new-topic {
  color: #CC5309
}
…
```

Esta definición controla el color del texto del índice y el título del tema. La siguiente salida de PDF muestra los diferentes colores aplicados en la entrada del índice:

<img src="./assets/pdf-output-toc-entry.jpg" width="500">

El título del tema también está diseñado con el mismo color.

<img src="./assets/pdf-output-topic-title.jpg" width="500">

Si desea que la entrada del índice y el título del tema tengan estilos diferentes, puede definirlos por separado como se muestra a continuación:

```css
...
/*for styling TOC entry */
.new-topic {
  color: #CC3509
}

/* for styling topic's title */
.new-topic.title {
  color: #092ACC
}
...
```

Por último, también puede aplicar estilos a todo el contenido del tema. Para ello, debe agregar un sufijo &quot;`-content`&quot; al nombre de clase. En el ejemplo siguiente, se ha agregado una barra de cambios en todo el contenido del tema:

```css
...
/* for styling the topic's content */
.new-topic-content {
  -ro-change-bar-color: #A609CC;
}
...
```

Utilizando los atributos de estilo anteriores, se agrega una barra de cambios a la izquierda del tema *Historial de vuelo*, como se muestra a continuación:

<img src="./assets/pdf-output-topic-content.jpg" width="500">

## Quitar filas vacías del índice

Si no ha definido el título de ningún tema, aparecerán filas vacías en la tabla de contenido para dichos temas.

Para quitar las filas vacías del índice y del mini índice, agregue el siguiente estilo en `layout.css`:

```css
.toc-body a:empty,
.chaptoc-body a:empty {
    display: none;
} 
```

