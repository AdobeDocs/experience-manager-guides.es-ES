---
title: Uso de Markdown en DITA AEM Guides
description: Migración y uso de Markdown en DITA AEM Guides
source-git-commit: dfda0ec4fe7301182299f6ab46d2772629ab6df7
workflow-type: tm+mt
source-wordcount: '256'
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


#### Publish a PDF y salida web

AEM Guides AEM ofrece la opción Web (Html5/Sitio de la) y PDF (PDF nativo/DITA-OT) para publicar un mapa de datos con contenido de Markdown

### Opción 2 : Convertir Markdown a formato DITA

Uso completo de la funcionalidad de AEM Guides, que permite la reutilización de contenido, la traducción de procesamiento condicional, la línea de base, etc. Pero necesitaría esfuerzos iniciales para convertir `.md` al formato `.dita`.

Markdown to DITA se puede convertir con herramientas externas como Adobe FrameMaker y DITA-OT.


Para Adobe FrameMaker, consulte: [Import markdown](https://www.adobe.com/in/products/framemaker/features.html#import-markdown)

Para DITA-OT, consulte: [Markdown como entrada](https://www.dita-ot.org/dev/topics/markdown-input.html)

Archivo de muestra convertido mediante Adobe FrameMaker : [Markdown en ejemplo DITA](https://acrobat.adobe.com/id/urn:aaid:sc:AP:874881f3-ba43-410c-abc6-2df899536d79)

#### Publish a PDF y salida web

Una vez que los archivos Markdown se convierten en DITA, el usuario puede publicar sin problemas la salida en cualquier formato disponible en AEM Guides.

Formatos disponibles en AEM Guides: [Formatos de salida](../../../../user-guide/generate-output-understand-presets.md)
