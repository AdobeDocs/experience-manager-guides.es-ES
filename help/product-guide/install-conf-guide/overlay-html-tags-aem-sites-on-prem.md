---
title: Superponga las etiquetas de HTML en la salida de AEM Sites no heredada
description: Configure el vídeo y la configuración de imagen para la salida de aem sites en función de la asignación de componentes principales
feature: Installation
role: Admin
level: Experienced
exl-id: af349df4-04bf-4b9b-885f-d8bca32a4484
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: e557051c-ff02-4ff8-9421-cf452af0edd5
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 0%
---
# Superposición de etiquetas de HTML en la salida de AEM Sites para aplicaciones locales

Puede añadir y personalizar etiquetas de HTML en la salida de AEM Sites generada mediante el ajuste preestablecido de AEM Sites basado en la asignación de componentes principales desde el Editor. Para personalizar las etiquetas de HTML, puede superponer el archivo `config.xml`. Por ejemplo, puede configurar los mapas de vídeo e imagen en la salida de AEM Sites.

Realice los siguientes pasos para superponer y actualizar el archivo `config.xml`:

1. Inicie sesión en AEM y abra el modo CRXDE Lite.

1. Vaya al archivo de configuración disponible en la siguiente ubicación:

   `/libs/fmdita/cq/xssprotection/config.xml`

1. Cree un nodo de superposición de la carpeta `xssprotection` dentro del nodo de aplicaciones.

1. Vaya al archivo de configuración disponible en el nodo `apps`:

   `/apps/fmdita/config/config.xml`

1. Actualice las siguientes etiquetas para los vídeos e imágenes. A continuación, guarde el archivo.

Vídeos:

```XML
    <tag name="video" action="validate">
    <attribute name="src">
      <regexp-list>
        <regexp name="anything"/>
      </regexp-list>
    </attribute>
    <attribute name="width">
       <regexp-list>
           <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="height">
       <regexp-list>
          <regexp name="anything"/>
       </regexp-list>
     </attribute>
     <attribute name="data">
       <regexp-list>
         <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="class">
       <regexp-list>
           <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="poster">
      <regexp-list>
        <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="controls">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    </tag>
    <tag name="source" action="validate">
      <attribute name="src">
        <regexp-list>
           <regexp name="anything"/>
        </regexp-list>
      </attribute>
    </tag>
```

Mapas de imagen:

```XML
        <tag name="map" action="validate">
    <attribute    name="name">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    </tag>
    <!-- Image & image related tags -->
    <tag name="img" action="validate">
    <attribute name="src" onInvalid="removeTag">
        <regexp-list>
            <regexp name="onsiteURL"/>
            <regexp name="offsiteURL"/>
        </regexp-list>
    </attribute>
    <attribute name="name"/>
    <attribute name="alt"/>
    <attribute name="height"/>
    <attribute name="width"/>
    <attribute name="border"/>
    <attribute name="align"/>
    <attribute name="usemap">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="hspace">
        <regexp-list>
            <regexp name="number"/>
        </regexp-list>
    </attribute>
    <attribute name="vspace">
        <regexp-list>
            <regexp name="number"/>
        </regexp-list>
    </attribute>
    </tag>
    <tag name="area" action="validate">
    <attribute name="shape">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="coords">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="href">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
   </tag>
```




Más información sobre las prácticas recomendadas de [Seguridad](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/introduction/security).
