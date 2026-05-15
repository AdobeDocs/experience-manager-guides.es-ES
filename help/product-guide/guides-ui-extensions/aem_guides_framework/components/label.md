---
title: Etiqueta
description: Etiqueta
role: User, Admin
exl-id: aceefb08-3198-4c3a-90ec-ac1cdde28582
TQID: https://experienceleague.adobe.com/fYBih0o2nCF66z8OgoFJ0Xqt2oN8aY7ZomqfgljZIyA
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 45
ht-degree: 6%

---

# Etiqueta

Para mostrar cualquier texto o cadena, utilizamos el componente, la etiqueta.
El componente de etiqueta de la JUI representa un HTML `<label/>`.

A continuación se muestra un ejemplo para añadir una etiqueta estática

```js title="staticLabel.js"
const staticLabelJSON =  {
    "component": "label", //tells the component name
    "label": "This is an example label", // the string to be displayed
}
```

Debajo de JSON se muestra una cadena dinámica:

```js title="dynamicLabel.js"
const labelJSON =  {
    "component": "label", //tells the component name
    "label": "@name", // the variable storing the text to be displayed
},
```

La etiqueta procesada tendrá este aspecto:

![etiqueta](./imgs/label.png "Etiqueta")
