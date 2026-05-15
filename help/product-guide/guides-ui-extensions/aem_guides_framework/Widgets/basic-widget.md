---
title: Widgets
description: Comprender los widgets
role: User, Admin
exl-id: 96e960df-d595-4d58-8ad4-27057f857bac
TQID: https://experienceleague.adobe.com/SssVShlzFB3kjQCV-cNAOZVYb0TYSQ1CjtWoax2Q-LU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 86
ht-degree: 0%

---

# Widgets

Se pueden combinar varios componentes básicos, como se describe en la sección Componentes, para crear un widget.
Los widgets se pueden utilizar para crear un nuevo componente &quot;más complejo&quot; o para dar estructura a los elementos de un componente.

¡Vamos a sumergirnos en el concepto de widget!

Empezaremos por hacer un widget simple para mostrar una lista de idiomas.

```js title="basicWidget.js"
const widgetJSON =  {
    "component": "div", 
    "id": "widget_languages", 
    "items": [ // adding components to the widget
        {
            "component": "div",
            "items": [
                {
                    "component": "icon",
                    "icon": "info"
                },
                {
                    "component": "label",
                    "label": "List of some languages"
                }
            ]
        },
        {
            "component": "list",
            "data": "@languages"
        }
    ]
},
```

Aquí, `@languages` es una matriz definida en el modelo de `widget_languages` como: [&quot;inglés&quot;, &quot;francés&quot;, &quot;hindi&quot;, &quot;español&quot;, &quot;urdu&quot;]

El widget básico procesado tendrá este aspecto:

![widget_básico](imgs/basic_widget.png "widget básico")
