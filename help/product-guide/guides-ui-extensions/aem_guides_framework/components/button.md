---
title: Botón
description: Botón
role: User, Admin
exl-id: 40e3f254-f94e-4f43-8ff5-2e6e1eb1cb6f
TQID: https://experienceleague.adobe.com/pmhyi9TN4gFF0opdy2SsTEUr4l1uLZMwhIwmUPMJSA0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 62
ht-degree: 4%

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

Esto producirá un botón con la etiqueta `Yes, login`. Las otras propiedades incluyen, entre otras, variant, label y on-click.
> **_NOTE:_** `on-<events>` es la sintaxis para invocar los comandos en los controladores.

El botón procesado tendrá este aspecto:

![botón](imgs/yes_login_button.png "Botón")
