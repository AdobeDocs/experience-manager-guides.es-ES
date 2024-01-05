---
title: Personalización sencilla
description: Ejemplo de personalización simple
source-git-commit: 8ee7782e3ac0f7797216f542a6db53f7053d5c69
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 0%

---


# Ejemplo de personalización simple

AEM Permítanos saber cómo integrar estas personalizaciones en nuestra aplicación Guías de.

Supongamos que queremos añadir este botón en una vista existente de la aplicación.
Para esto necesitamos 3 cosas básicas:

1. El `id` del JSON de vista al que queremos agregar nuestro componente.
2. El `target`, es decir, la ubicación en el JSON al que queremos agregar el nuevo componente. El `target` se define mediante una `key` y `value`. El par clave-valor puede ser cualquier atributo utilizado para definir el componente que pueda ayudar en la identificación única del mismo.
También podemos usar índices para hacer referencia al objetivo.
Tenemos 3 viewStates:  `APPEND`, `PREPEND`, `REPLACE`.
3. El JSON del componente recién creado y los métodos correspondientes.

AEM Supongamos que queremos añadir un botón al cuadro de herramientas de anotaciones utilizado en la revisión que abra el archivo en la vista de datos de.

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

1. el `id` del JSON en el que queremos insertar nuestro componente, es decir, `annotation_toolbox`
2. el objetivo es `addcomment` botón. Añadimos el botón después del `addcomment` mediante el botón viewState `append`.
3. Definimos el evento en el que se hace clic del botón en el controlador.

El JSON para &quot;annotation_toolbox&quot;  `.src/jsons/review_app/annotation_toolbox.json`

Antes de la personalización, el cuadro de herramientas de anotación tenía este aspecto:

![annotation-toolbox](imgs/annotation_toolbox.png "Cuadro de herramientas Anotación")

Después de la personalización, el cuadro de herramientas de anotación tiene este aspecto:

![custom-annotation-toolbox](imgs/customised_annotation_toolbox.png "Cuadro de herramientas de anotaciones personalizado")

## Adición de CSS

Para mantener la coherencia, proporcionamos el componente ya diseñado. El JSON insertado tendrá estilos inherentes aplicados La forma principal de administrar css es a través de la clave extraClass en las extensiones.

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

Puede colocar estilos personalizados con clases CSS agregando un archivo css a clientlibs. Durante la compilación también creamos [Viento De Cola](https://tailwindcss.com/docs/utility-first) salida para las clases de utilidades en tailwind. La configuración para lo mismo se puede encontrar en el `tailwind.config.js` en `./tailwind.config.js`
