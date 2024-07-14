---
title: Barra superior y barra de herramientas
description: Personalizar la barra superior y la barra de herramientas
role: User, Admin
exl-id: 7065c9b8-67ac-4f6d-8124-daa547f2dc3b
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 0%

---

# Personalizar la barra superior y la barra de herramientas

Para personalizar `topbar` y `toolbar`, se usarán los identificadores: `topbar` o `toolbar`, y se seguirá la misma vista, estructura de controlador.

A continuación se muestra un ejemplo trivial de personalización de la barra de herramientas. En este caso, se ha eliminado el botón `Insert Numbered List` y se ha reemplazado el botón `Insert Paragraph` por nuestro propio componente mediante un controlador en el que se puede hacer clic personalizado.

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
