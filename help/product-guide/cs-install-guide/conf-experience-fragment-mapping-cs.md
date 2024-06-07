---
title: Configure la asignación basada en JSON entre un tema y una plantilla de fragmento de experiencia.
description: Obtenga información sobre cómo configurar la asignación basada en JSON entre un tema y una plantilla de Fragmento de experiencia.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: f252537d15d7e8f8651dddb0ae635905705e4adf
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Creación de una asignación entre un tema y un fragmento de experiencia

Guías de Adobe Experience Manager proporciona la función para crear una asignación basada en JSON entre un tema y una plantilla de fragmento de experiencia. Puede utilizar esta asignación para publicar contenido presente en algunos o todos los elementos de un tema en un Fragmento de experiencia.

1. Para descargar *experienceFragmentMapping.json*, inicie sesión en Adobe Experience Manager como administrador.
1. Seleccione el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.
1. Seleccione Guías de la lista de herramientas y seleccione la **Perfiles de carpeta**.
1. Seleccione el mosaico de perfil que desea configurar. Puede configurar la asignación para el perfil global o de nivel de carpeta. Por ejemplo, seleccione la opción **Perfil global** mosaico.
1. Seleccione el **Configuración del editor XML** y seleccione la pestaña **Editar** en la parte superior.
1. Seleccione el **Descargar** para descargar el *experienceFragmentMapping.json*  en su sistema local. A continuación, puede realizar cambios en el archivo y luego cargarlo.

1. Debe seguir las siguientes validaciones:

   1. Debe ser un archivo JSON
   2. Debe contener una matriz que contenga al menos un objeto y cada objeto debe contener lo siguiente:


      `"template": string `

      `"mapping": array`

      Cada objeto de asignación debe contener lo siguiente:

      `"name": string`

      `"class": string`

      `"resourceType": string`

      `"attributeMap": array`


1. Guarde el archivo y cárguelo.

Guías del Experience Manager convierte el tema completo en HTML, que luego se puede asignar a los componentes principales utilizados en el Fragmento de experiencia. Por ejemplo, el contenido de una `<p>` La etiqueta se puede asignar para crear un componente de texto en el Fragmento de experiencia.
* `name`: especifique el elemento HTML. Por ejemplo, `<div>`, `<img>`
* `class`: especifique la etiqueta de elemento DITA correspondiente al elemento HTML. Por ejemplo, `<p>` `<image>`
* `resourceType`: especifique el tipo de recurso aplicable al componente utilizado en el fragmento de experiencia. Por ejemplo, `wcm/foundation/components/text` es el resourceType para wcm `text` componente.
* `attributeMap`: proporcione información adicional al componente, como si un componente de texto debe representarse como `RichText` o contiene el `fileReference` de un componente de imagen.




Archivo de muestra:

```
[
  {
    "template": "default",
    "mapping": [
      {
        "name": "#element",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      }
    ]
  },
  {
    "template": "/conf/we-retail/settings/wcm/templates/experience-fragment-web-variation",
    "mapping": [
      {
        "name": "div",
        "class": "title",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "h1, h2, h3, h4, h5, h6",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "div",
        "class": "p",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "img",
        "class": "image",
        "resourceType": "wcm/foundation/components/image",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "fileReference"
          }
        ]
      },
      {
        "name": "#element",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      }
    ]
  }
]
```



Al publicar los fragmentos de experiencias desde el editor web, seleccione la opción `Template` en el menú desplegable de **Generar Fragmento De Experiencia** para ver la asignación disponible para la plantilla en el **Asignación** field. Si no hay ninguna asignación personalizada para una plantilla, se muestra la asignación predeterminada. Puede utilizar la asignación predeterminada para publicar todo el tema como un Fragmento de experiencia.

Para obtener más información, consulte [Publicar fragmentos de experiencias](../user-guide/publish-experience-fragment.md).

