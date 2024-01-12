---
title: Área de texto
description: Área de texto
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
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
