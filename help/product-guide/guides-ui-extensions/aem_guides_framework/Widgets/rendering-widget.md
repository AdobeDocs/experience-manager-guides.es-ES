---
title: Widgets de procesamiento
description: Cómo funciona el procesamiento en los widgets JUI
source-git-commit: f9a72e44fe1a3d90180ff728189a24ea9c7b1b1a
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 0%

---

# Widgets de procesamiento

Podemos procesar un widget haciendo referencia a él mediante su `id`

Para procesar el widget `widget_languages` en cualquier parte de la aplicación podemos usar la sintaxis simple:

```json
{
    "component": "widget",
    "id": "widget_languages"
}
```

Los widgets también se pueden utilizar para procesar elementos complejos, como Deseo procesar la lista de colaboradores para cada archivo.
En este caso, el widget se puede construir de la siguiente manera:

```js title="fileContributorsWidget.js"
const widgetJSON =  {
    component: "div", 
    id: "file_contributors", 
    items: [ // adding components to the widget
        {
            component: "div",
            items: [
                {
                    component: "icon",
                    icon: "file"
                },
                {
                    component: "label",
                    label: "@fileName"
                }
            ]
        },
        {
            component: "list",
            data: "@contributors",
            itemConfig: {
                component: "label"
            }
        }
    ]
},
```

Ahora para procesar una lista de colaboradores para cada archivo, escribimos la lista como:

```js title="fileContributorsList.js"
const listJSON = {
    component: "list"
    data: "@files"
    itemConfig: {
        component: "widget",
        id: "file_contributors"
    }
}
```

Aquí `@files` es una lista de objetos de archivo que contienen campos

```typescript
- fileName: string
- contributors: Array<String>
```
