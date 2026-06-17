---
title: Función de publicación nativa de PDF | Aplicar estilo personalizado en entradas del índice y contenido del tema
description: Aprenda a crear hojas de estilo de uso y a crear estilos para el contenido.
exl-id: f65c9683-a1fc-432a-854b-83e8f39d7dae
feature: Output Generation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/cqknNhuPThhuNTsLZzwnrUzPJguIPs4J-3rX6PVR2V8
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: febac97b369bad427f0f650f2cdc69b0ca6c9f69
workflow-type: tm+mt
source-wordcount: 460
ht-degree: 0%

---

# Aplicar un estilo personalizado a las entradas del índice y al contenido del tema

Puede aplicar estilos personalizados a entradas del índice, encabezados de tema o temas individuales utilizando el atributo `outputclass` en elementos de mapa compatibles, como `<topicref>` y `<topichead>`. Para aplicar formato personalizado a todo un tema, amplíe la definición de estilo del atributo `outputclass` en CSS.

## Aplicar estilo a un tema al que se hace referencia mediante `<topicref>`

Puede aplicar un elemento `outputclass` en un elemento `<topicref>` para aplicar estilo a la entrada del índice, al título del tema o al contenido completo del tema en el PDF generado.

Por ejemplo, para identificar un tema que requiere revisión, agregue un atributo outputclass al elemento `<topicref>` correspondiente en el mapa DITA y defina los estilos asociados en el CSS.

En el ejemplo siguiente, al tema *Historial de vuelos* se le ha asignado un atributo `outputclass` con el valor `new-topic`.

<img src="./assets/new-topic-attribute-in-map.png" width="500">

La clase `new-topic` se puede usar para definir estilos para:

* La entrada principal del índice o mini-índice
* Título del tema en el contenido principal
* Todo el contenido del tema, incluido el título

La siguiente definición de CSS cambia el color del texto para la entrada del índice y el título del tema:

```css
.new-topic {
  color:#CC5309
}
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
  color:#CC3509
}

/* for styling topic's title */
.new-topic.title {
  color:#092ACC
}
...
```

Para aplicar estilos a todo el contenido del tema, agregue el sufijo `-content` al nombre de clase. En el siguiente ejemplo se agrega una barra de cambios al contenido del tema:

```css
...
/* for styling the topic's content */
.new-topic-content {
  -ro-change-bar-color:#A609CC;
}
...
```

Utilizando los atributos de estilo anteriores, se agrega una barra de cambios a la izquierda del tema *Historial de vuelo*, como se muestra a continuación:

<img src="./assets/pdf-output-topic-content.jpg" width="500">

## Aplicar estilos a `topichead` elementos

Puede usar el atributo `outputclass` en un elemento `<topichead>` para aplicar estilos diferentes a la entrada del índice y al encabezado generado para `topichead`.

Por ejemplo, si define los siguientes `topichead` en su mapa DITA:

```xml
<topichead navtitle="Getting Started" outputclass="new-topichead">
    ...
</topichead>
```

La clase `new-topichead` se aplica a la entrada topichead del índice y al encabezado generado para el encabezado topichead.

Si desea aplicar un estilo diferente al encabezado, defina una clase independiente para él, de forma similar a como `<topicref>` admite estilos independientes para la entrada del índice y el título del tema:

```css
...
/* Style for the topichead TOC entry */
.new-topichead {
  color: #CC5309;
}

/* Style for the topichead heading */
.new-topichead.title {
  color: #092ACC;
}...
```

Si desea aplicar estilo al contenido asociado con el encabezado del tema, anexe el sufijo `- content` al nombre de clase:

```css
.new-topichead-content {
    border-left: 2px solid #cccccc;
    padding-left: 8px;
}
```



## Quitar filas vacías del índice

Si no ha definido el título de ningún tema, aparecerán filas vacías en la tabla de contenido para dichos temas.

Para quitar las filas vacías del índice y del mini índice, agregue el siguiente estilo en `layout.css`:

```css
.toc-body a:empty,
.chaptoc-body a:empty {
    display: none;
} 
```

