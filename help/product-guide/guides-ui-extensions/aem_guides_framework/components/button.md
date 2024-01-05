---
title: Botón
description: Botón
source-git-commit: 2e1cb576fa3b0a765304508e5f7962a154f1a72c
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 5%

---


# Botón

Para mostrar un botón utilizamos el componente, botón.
El componente de botón de la JUI representa un HTML `<button/>`.

```js title="buttonJSON.js"
const buttonJSON = {
  "component": "button",//tells the component name
  "label": "Yes, login",//tells the text for the button
  "variant": "cta",//tells the variants for the button which  provides default styles
  "on-click": "done",//tells what function to run after user clicks the button
};
```

Esto producirá un botón con una etiqueta de `Yes, login`. Las otras propiedades incluyen, entre otras, variant, label y on-click.
> **_NOTA:_**  El `on-<events>` es la sintaxis para invocar los comandos en los controladores.

El botón procesado tendrá este aspecto:

![botón](imgs/yes_login_button.png "Botón")
