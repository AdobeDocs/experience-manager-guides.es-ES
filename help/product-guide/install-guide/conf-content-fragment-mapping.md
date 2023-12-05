---
title: Configure la asignación basada en JSON entre un tema y un modelo de fragmento de contenido.
description: Obtenga información sobre cómo configurar la asignación basada en JSON entre un tema y un modelo de fragmento de contenido.
exl-id: 21446bcb-e7df-4823-acc3-1fdc7473f0d1
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# Creación de una asignación entre un tema y un fragmento de contenido

AEM Guías de proporciona la función para crear una asignación basada en JSON entre un tema y un modelo de fragmento de contenido. Puede utilizar esta asignación para publicar contenido presente en algunos o todos los elementos de un tema en un fragmento de contenido.

1. Para descargar *contentFragmentMapping.json*, inicie sesión en Adobe Experience Manager como administrador.
1. Seleccione el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.
1. Seleccione Guías de la lista de herramientas y seleccione la **Perfiles de carpeta**.
1. Seleccione el **Perfil global** mosaico.
1. Seleccione el **Configuración del editor XML** y seleccione la pestaña **Editar** en la parte superior.
1. Seleccione el **Descargar** para descargar el *contentFragmentMapping.json*  en su sistema local. A continuación, puede realizar cambios en el archivo y luego cargarlo.

1. Debe seguir las siguientes validaciones:

   1. Debe ser un archivo JSON
   2. Debe contener una matriz que contenga al menos un objeto y cada objeto debe contener lo siguiente:


      `"name": string `

      `"mapping": array`

      Cada objeto de asignación debe contener lo siguiente:

      `"modelField": string`

      `"xpath": string`

      `"outputType": string`
1. Guarde el archivo y cárguelo.

Archivo de muestra:

```
[
  {
    "mapping": [
      {
        "modelField": "title",
        "xpath": "/topic[1]/title[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "shortdesc",
        "xpath": "/topic[1]/shortdesc[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "topicData",
        "xpath": "/topic[1]/body[1]",
        "outputType": "outerHTML"
      }
    ],
    "name": "Full Topic"
  },
  {
    "mapping": [
      {
        "modelField": "title",
        "xpath": "/topic[1]/title[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "shortdesc",
        "xpath": "/topic[1]/shortdesc[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "heroImage",
        "xpath": "/topic[1]/body[1]/p[1]/image[1]",
        "outputType": "outerHTML"
      },
      {
        "modelField": "dataTable",
        "xpath": "/topic[1]/body[1]/table[1]",
        "outputType": "outerHTML"
      }
    ],
    "name": "Sample Example with XPath"
  }
]
```

Puede publicar todo el tema con la asignación predeterminada. Seleccione el `Full Topic` asignación desde el menú desplegable en **Publicar como fragmento de contenido** y tengan el campo &quot;topicData&quot; en el modelo de fragmento de contenido.
