---
title: Área de texto
description: Área de texto
role: User, Admin
exl-id: 4c576acc-fa6a-4c41-9b92-443ba51dc8ee
source-git-commit: 08d379acc98dac425f1c84b0ac2226b0e34f6d8b
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 3%

---

# Campo de texto y área de texto

Para tomar el texto como entrada, utilizamos los componentes, el campo de texto y el área de texto.
El componente de área de texto en la JUI representa un HTML `<textarea/>`.

```js title="textArea.js"
const textAreaJSON =  {
    "component": "textarea", //tells the component name
    "id": "input_name", // can be used to give a unique identifier to a component
    "data": "@name", // the variable storing the inputted text
    "on-keyup": {
        "name": "submitName",
        "eventArgs": {
            "keys": [
            "ENTER"
            ]
        }
    },
},
```

En este caso, `on-keyup` es la sintaxis para invocar los comandos de los controladores.
Esto producirá un área de texto donde al presionar ENTRAR se llamará al evento `submitName`

El área de texto procesada tendrá este aspecto:

![área de texto](./imgs/text_area.png "Área de texto")
