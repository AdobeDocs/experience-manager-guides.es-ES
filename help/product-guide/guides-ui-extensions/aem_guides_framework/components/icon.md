---
title: Icono
description: Icono
role: User, Admin
exl-id: 5ba41c77-7329-49fc-bce5-02682261ea8e
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 6%

---

# Icono

Para mostrar un icono utilizamos el componente, icono.
El componente de área de texto en la JUI representa un HTML `<icon/>`.

Los iconos disponibles en [Adobe Spectrum Icons](https://spectrum.adobe.com/page/icons/) son compatibles con nuestra aplicación.

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
