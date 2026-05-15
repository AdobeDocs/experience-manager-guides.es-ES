---
title: Lista
description: Lista
role: User, Admin
exl-id: 333b5e24-efba-4a51-8f68-83b5d1d7daec
TQID: https://experienceleague.adobe.com/2mjVuKodk-Jn7tGoiF1fNpCnTd1VqK57oATMiN2gd0o
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 58
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
