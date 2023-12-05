---
title: Función de publicación nativa de PDF | Aplicar estilo personalizado en entradas del índice y contenido del tema
description: Aprenda a crear hojas de estilo de uso y a crear estilos para el contenido.
exl-id: f65c9683-a1fc-432a-854b-83e8f39d7dae
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---

# Aplicar un estilo personalizado a las entradas del índice y al contenido del tema

A veces, es posible que desee aplicar un estilo personalizado a las entradas de la tabla de contenido o a un tema en particular. Esto se puede lograr asociando una `outputclass` con el atributo `<topicref>` en el mapa DITA. Además, si desea aplicar un formato personalizado a todo un tema, también puede hacerlo ampliando la definición de estilo del atributo en CSS.

Veamos un ejemplo de un nuevo tema que desee enviar para su revisión. Para facilitar la identificación del tema actualizado, debe agregar una `outputclass` atribuir a `<topicref>` en el mapa DITA y, a continuación, defina un estilo personalizado para el mismo en el CSS.

En el ejemplo siguiente, la variable *Historial de vuelos* se ha asignado un al tema `outputclass` atributo con el valor de `new-topic`.

<img src="./assets/new-topic-attribute-in-map.png" width="500">

La definición de clase del `new-topic` en un archivo CSS puede permitir definir el estilo para los siguientes elementos:
* La entrada principal del índice o mini-índice
* Título del tema en el contenido principal
* Todo el contenido del tema, incluido el título

Veamos cómo se puede definir cada uno de estos escenarios en CSS. En la siguiente definición CSS de `new-topic` , se ha cambiado el color del texto.

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

Por último, también puede aplicar estilos a todo el contenido del tema. Para ello, debe añadir un sufijo &quot;`-content`&quot; al nombre de clase. En el ejemplo siguiente, se ha agregado una barra de cambios en todo el contenido del tema:

```css
...
/* for styling the topic's content */
.new-topic-content {
  -ro-change-bar-color: #A609CC;
}
...
```

Con los atributos de estilo anteriores, se agrega una barra de cambios a la izquierda del *Historial de vuelo* como se muestra a continuación:

<img src="./assets/pdf-output-topic-content.jpg" width="500">
