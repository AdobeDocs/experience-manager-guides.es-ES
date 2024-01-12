---
title: Icono
description: Icono
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 6%

---

# Icono

Para mostrar un icono utilizamos el componente, icono.
El componente de área de texto en la JUI representa un HTML `<icon/>`.

Iconos disponibles en [Iconos de espectro de Adobe](https://spectrum.adobe.com/page/icons/) son compatibles con nuestra aplicación.

```js title="icon.js"
const iconJSON =  {
    "component": "icon", //tells the component name
    "icon": "info", // name of the icon to be used
    "size": "S", // size of the icon
    "title": "Information" // tooltip corresponding to the icon.
},
```

también se pueden añadir iconos a los botones.

El icono procesado tendrá este aspecto:

![icono](./imgs/info_icon.png "Icono")
