---
title: Widgets
description: Comprender los widgets
role: User, Admin
exl-id: 96e960df-d595-4d58-8ad4-27057f857bac
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '87'
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
