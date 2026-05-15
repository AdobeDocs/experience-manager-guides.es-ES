---
title: Personalización sencilla
description: Ejemplo de personalización simple
role: User, Admin
exl-id: 7f19f0b0-2a1b-4a8b-b28c-3918a1bc9096
TQID: https://experienceleague.adobe.com/IFKRQlzewz3NcnX-xruXzInQMiEzwEmhe-4knxXPrJM
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 296
ht-degree: 0%

---

# Ejemplo de personalización simple

Descubra cómo integrar estas personalizaciones en nuestra aplicación de AEM Guides.

Supongamos que queremos añadir este botón en una vista existente de la aplicación.
Para esto necesitamos 3 cosas básicas:

1. El `id` del JSON de vista al que queremos agregar nuestro componente.
2. El `target`, es decir, la ubicación en el JSON al que queremos agregar el nuevo componente. `target` se ha definido con `key` y `value`. El par clave-valor puede ser cualquier atributo utilizado para definir el componente que pueda ayudar en la identificación única del mismo.
También podemos usar índices para hacer referencia al objetivo.
Tenemos 3 viewStates: `APPEND`, `PREPEND`, `REPLACE`.
3. El JSON del componente recién creado y los métodos correspondientes.

Supongamos que queremos agregar un botón al cuadro de herramientas de anotaciones utilizado en la revisión que abra el archivo en AEM.

```typescript
export default {
  id: 'annotation_toolbox', 
  view: {
    items: [
      {
        component: 'button',
        icon: 'linkOut',
        title: 'Open topic in Assets view',
        'on-click': 'openTopicInAEM',
        target: {
          key: 'value',
          value: 'addcomment',
          viewState: VIEW_STATE.APPEND

        },
      },
    ],
  },
  controller: {
    openTopicInAEM: function (args) {
        const topicIndex = tcx.model.getValue(tcx.model.KEYS.REVIEW_CURR_TOPIC)
        const {allTopics = {}} = tcx.model.getValue(tcx.model.KEYS.REVIEW_DATA) || {}
        tcx.appGet('util').openInAEM(allTopics[topicIndex])
    },
  },
}
```

En el ejemplo anterior tenemos:

1. el `id` del JSON en el que queremos insertar nuestro componente, por ejemplo: `annotation_toolbox`
2. el destino es el botón `addcomment`. Agregamos nuestro botón después del botón `addcomment` usando viewState `append`.
3. Definimos el evento en el que se hace clic del botón en el controlador.

El JSON para &quot;annotation_toolbox&quot; `.src/jsons/review_app/annotation_toolbox.json`

Antes de la personalización, el cuadro de herramientas de anotación tenía este aspecto:

![cuadro de herramientas de anotaciones](imgs/annotation_toolbox.png "Cuadro de herramientas de anotaciones")

Después de la personalización, el cuadro de herramientas de anotación tiene este aspecto:

![cuadro de herramientas de anotaciones personalizado](imgs/customised_annotation_toolbox.png "Cuadro de herramientas de anotaciones personalizado")

## Adición de CSS

Para mantener la coherencia, proporcionamos el componente ya diseñado. El JSON insertado tendrá estilos inherentes aplicados
La forma principal de administrar css es mediante la clave extraClass en las extensiones.

```js
{    
    "view":{
        items:[
            {
                compoenent:"button",
                extraClass:"underline bg-red",
            }
        ]
    }
}
```

Puede colocar estilos personalizados con clases CSS agregando un archivo css a clientlibs. Durante la compilación también creamos la salida [Tailwind](https://tailwindcss.com/docs/utility-first) para las clases de utilidades en tailwind. La configuración para lo mismo se puede encontrar en `tailwind.config.js` de la extensión en `./tailwind.config.js`
