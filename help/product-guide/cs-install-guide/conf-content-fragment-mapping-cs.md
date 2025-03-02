---
title: Configure la asignación basada en JSON entre un tema y un modelo de fragmento de contenido.
description: Obtenga información sobre cómo configurar la asignación basada en JSON entre un tema y un modelo de fragmento de contenido.
exl-id: 438e2964-b9c7-462a-a68c-8031bd97911c
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 97d7776c81e7776d0248d6711ae5d05c46c44239
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 0%

---

# Creación de una asignación entre un tema y un fragmento de contenido



Adobe Experience Manager Guides le permite crear una asignación basada en JSON entre un tema y un modelo de fragmento de contenido. Puede utilizar la asignación basada en JSON para publicar contenido presente en algunos o todos los elementos de un tema en un fragmento de contenido.

>[!NOTE]
> 
> Si utiliza la versión 4.6 o versiones posteriores y no necesita crear esta asignación, puede arrastrar los elementos del tema a los campos presentes en el modelo de fragmento de contenido.
> Más información sobre cómo [publicar fragmentos de contenido](../user-guide/publish-content-fragment.md).


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

Puede publicar todo el tema con la asignación predeterminada. Seleccione la asignación `Full Topic` del cuadro de diálogo desplegable **Generar fragmento de contenido** y tenga el campo &quot;topicData&quot; en el modelo de fragmento de contenido.
