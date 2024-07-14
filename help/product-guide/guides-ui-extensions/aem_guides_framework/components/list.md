---
title: Lista
description: Lista
role: User, Admin
exl-id: 333b5e24-efba-4a51-8f68-83b5d1d7daec
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
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

Normalmente itemConfig es un `widget`. Para obtener más información sobre los widgets, ve a [Widgets](../Widgets/basic-widget.md)

La lista procesada tendrá este aspecto:

![lista](./imgs/list.png "Lista")
