---
title: Widgets de procesamiento
description: Cómo funciona el procesamiento en los widgets JUI
role: User, Admin
exl-id: 381cc7b9-c957-40be-9db4-8347eefe2fa7
TQID: https://experienceleague.adobe.com/-VznRFHuyxLqumy55MssEvPMMHIIt2BelCe7C6zBqR8
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

# Widgets de procesamiento

Podemos procesar un widget haciendo referencia a él con su `id`

Para procesar el widget `widget_languages` en cualquier lugar de la aplicación, podemos usar la sintaxis simple:

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

Aquí `@files` hay una lista de objetos de archivo que contienen campos

```typescript
- fileName: string
- contributors: Array<String>
```
