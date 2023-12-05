---
sidebar_position: 3
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '62'
ht-degree: 0%

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
