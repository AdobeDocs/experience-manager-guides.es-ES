---
title: Área de texto
description: Área de texto
source-git-commit: 2e1cb576fa3b0a765304508e5f7962a154f1a72c
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

Aquí, `on-keyup` es la sintaxis para invocar los comandos en los controladores.
Esto producirá un textArea en el que al pulsar INTRO se invocará el evento `submitName`

El área de texto procesada tendrá este aspecto:

![área de texto](./imgs/text_area.png "Área de texto")
