---
title: Barra superior y barra de herramientas
description: Personalizar la barra superior y la barra de herramientas
source-git-commit: 5962414dfc065543b946cac1468a5f62013073cf
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 0%

---


# Personalizar la barra superior y la barra de herramientas

Para personalizar la variable `topbar` y `toolbar`, se utilizarán los id: `topbar` o `toolbar`y siguen la misma vista, estructura del controlador.

A continuación se muestra un ejemplo trivial de personalización de la barra de herramientas. Aquí, se ha eliminado el `Insert Numbered List` y se ha sustituido el `Insert Paragraph` con su propio componente mediante un controlador en el que se hace clic personalizado.

```js title = toolbar_customisation.js
const toolbarExtend = {
    id: "toolbar",
    view: {
        items: [
            {
                component: "div",
                target: {
                    key:"title",value: "Insert Numbered List",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                {
                    "component": "button",
                    "icon": "textParagraph",
                    "variant": "action",
                    "quiet": true,
                    "title": "Insert Paragraph",
                    "on-click": "INSERT_P"
                },

                target: {
                    key:"title",value: "Insert Paragraph",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
        ]
    },
    controller: {

        INSERT_P(){
            this.next("AUTHOR_INSERT_ELEMENT",  "p" )
        }
    }
}
```
