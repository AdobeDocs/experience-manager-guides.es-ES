---
title: Uso de Markdown en DITA AEM Guides
description: Migración y uso de Markdown en DITA AEM Guides
author: Pulkit Nagpal(punagpal)
exl-id: a94c0129-df40-4b61-ac60-679b2ffe7e86
TQID: https://experienceleague.adobe.com/z41KjrBkAeDaH-iKXOFLH44qOQElziip1FqcRhnKaUI
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 281
ht-degree: 0%

---

# Uso de Markdown en AEM Guides

## Opciones disponibles

Existen dos opciones para utilizar archivos Markdown en AEM Guides:

- Opción 1: Importe el Markdown existente en AEM Guides y utilícelo directamente dentro del mapa de datos para publicarlo

- Opción 2 : convertir archivos Markdown existentes en DITA

Hablemos de cada opción :

### Opción 1: Importe el Markdown existente en AEM Guides y utilícelo directamente dentro del mapa para publicarlo

Tiene una configuración más sencilla y una implementación más rápida. Sin embargo, la utilización limitada de la funcionalidad de AEM Guides como la reutilización del contenido.

El usuario debe agregar el atributo `format="markdown" ` o `format="mdita"` para que los motores de publicación entiendan el tipo de archivo y publiquen en consecuencia.

Archivo de muestra: [Markdown Ditamap](https://acrobat.adobe.com/id/urn:aaid:sc:AP:da31137e-be84-44fb-8974-d038eeff0283)

![captura de pantalla para referencia](../../assets/authoring/markdown_map.png)


#### Publicación en PDF y salida web

AEM Guides ofrece la opción Web (Html5/Sitio de AEM) y PDF (Native-PDF/DITA-OT) para publicar un mapa de datos con contenido Markdown

### Opción 2 : Convertir Markdown a formato DITA

Uso completo de la funcionalidad de AEM Guides, que permite la reutilización de contenido, la traducción de procesamiento condicional, la línea de base, etc. Pero necesitaría esfuerzos iniciales para convertir `.md` al formato `.dita`.

Markdown to DITA se puede convertir con herramientas externas como Adobe FrameMaker y DITA-OT.


Para Adobe FrameMaker, consulte: [Import markdown](https://www.adobe.com/in/products/framemaker/features.html#import-markdown)

Para DITA-OT, consulte: [Markdown como entrada](https://www.dita-ot.org/dev/topics/markdown-input.html)

Archivo de muestra convertido mediante Adobe FrameMaker : [Markdown en ejemplo DITA](https://acrobat.adobe.com/id/urn:aaid:sc:AP:874881f3-ba43-410c-abc6-2df899536d79)

#### Publicación en PDF y salida web

Una vez que los archivos Markdown se convierten en DITA, el usuario puede publicar sin problemas la salida en cualquier formato disponible en AEM Guides.

Formatos disponibles en AEM Guides: [Formatos de salida](../../../../user-guide/generate-output-understand-presets.md)
