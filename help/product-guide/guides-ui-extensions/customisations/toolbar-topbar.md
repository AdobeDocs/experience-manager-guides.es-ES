---
title: Barra superior y barra de herramientas
description: Personalizar la barra superior y la barra de herramientas
role: User, Admin
exl-id: 7065c9b8-67ac-4f6d-8124-daa547f2dc3b
source-git-commit: 4f41609368b64415993b93be27162b069e7b2e32
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 0%

---

# Personalizar la barra superior y la barra de herramientas

Para personalizar `topbar` y `toolbar`, se usarán los identificadores: `topbar` o `toolbar`, y se seguirá la misma vista, estructura de controlador.

A continuación se muestra un ejemplo trivial de personalización de la barra de herramientas. En este caso, se ha eliminado el botón `Insert Numbered List` y se ha reemplazado el botón `Insert Paragraph` por nuestro propio componente mediante un controlador en el que se puede hacer clic personalizado.

Para acceder a la funcionalidad expuesta en el objeto `proxy`, necesitaremos acceder a él mediante `this.proxy.getValue`, por ejemplo, para recuperar un valor.

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
        init: function() {
            console.log(this.proxy.getValue("canUndo"))
            this.proxy.subscribeAppEvent({
              key: "editor.preview_rendered",
              next: async function (e) {
                console.log(this.proxy.getValue("canUndo"))
              }.bind(this)
            })
        },
        INSERT_P(){
            this.next("AUTHOR_INSERT_ELEMENT",  "p" )
        }
    }
}
```
