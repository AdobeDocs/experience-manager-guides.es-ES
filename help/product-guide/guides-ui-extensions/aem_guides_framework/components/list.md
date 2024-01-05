---
title: Lista
description: Lista
source-git-commit: dfd4c898d3c093bfee1a8a6efff4e395efd20c60
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 5%

---

# Lista

Para mostrar una lista, se utiliza la lista de componentes.

```js title="list.js"
const listJSON =  {
    "component": "list", //tells the component name
    "data": "@languages", // an array of list items
},
```

En este caso, el lenguaje es una simple matriz de cadenas. `languages = ["English", "Hindi", "French"]`
Si queremos procesar una lista de objetos, podemos especificar la estructura utilizando la configuración del elemento.

```js title="list.js"
const listJSON =  {
    "component": "list", //tells the component name
    "data": "@projects", // an array of list items
    "itemConfig": { // used to define the structure of the list items.
    "component": "widget",
    "id": "checkbox_label"
    }
},
```

Normalmente itemConfig es una `widget`. Para obtener más información sobre los widgets, vaya a [Widgets](../Widgets/basic-widget.md)

La lista procesada tendrá este aspecto:

![lista](./imgs/list.png "Lista")
