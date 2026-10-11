---
title: Configure la asignación basada en JSON entre un tema y un modelo de fragmento de contenido.
description: Obtenga información sobre cómo configurar la asignación basada en JSON entre un tema y un modelo de fragmento de contenido.
exl-id: 21446bcb-e7df-4823-acc3-1fdc7473f0d1
feature: Output Generation
role: Admin
level: Experienced
hidefromtoc: 'yes'
TQID: 'https://experienceleague.adobe.com/RQfBAqnFbJwbscxdqkuPFf8N8HnXXy-Z-SuiwlleofY'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
    internal-label: Profiles
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 0%
---
# Creación de una asignación entre un tema y un fragmento de contenido

AEM Guides proporciona la función para crear una asignación basada en JSON entre un tema y un modelo de fragmento de contenido. Puede utilizar esta asignación para publicar contenido presente en algunos o todos los elementos de un tema en un fragmento de contenido.

1. Para descargar *contentFragmentMapping.json*, inicie sesión en Adobe Experience Manager como administrador.
1. Seleccione el enlace de Adobe Experience Manager en la parte superior y elija **Herramientas**.
1. Seleccione Guías de la lista de herramientas y seleccione **Perfiles de carpeta**.
1. Seleccione el mosaico **Perfil global**.
1. Seleccione la ficha **Configuración del editor XML** y seleccione el icono **Editar** de la parte superior.
1. Seleccione el icono **Descargar** para descargar el archivo *contentFragmentMapping.json* en su sistema local. A continuación, puede realizar cambios en el archivo y luego cargarlo.

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

Puede publicar todo el tema con la asignación predeterminada. Seleccione la asignación `Full Topic` del menú desplegable en el cuadro de diálogo **Publicar como fragmento de contenido** y tenga el campo &quot;topicData&quot; en el modelo de fragmento de contenido.
