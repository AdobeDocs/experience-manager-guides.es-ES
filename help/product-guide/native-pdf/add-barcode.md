---
title: Función de publicación nativa de PDF | Añadir código de barras
description: Aprenda a añadir códigos de barras.
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 1%

---

# Añadir un código de barras a la salida del PDF

Los códigos de barras son útiles para incluir información que las máquinas pueden procesar fácilmente. Del mismo modo, los códigos QR se utilizan para los vínculos que los lectores pueden abrir con sus dispositivos móviles.

Este tutorial le ayuda a añadir códigos de barras en la parte superior de cada página en la salida del PDF.

## Pasos para generar un código de barras

Para generar un código de barras, realice los siguientes pasos:

### Añadir un ID de recurso al mapa DITA

Añada un elemento de ID de recurso al mapa DITA. El ID de recurso sirve como entrada principal para generar el código de barras.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<map id="GUID-3c330691-4dac-4020-904a-d2d6246aeeb1-en">
  <title>Barcode Sample</title>
  <topicmeta>
    <resourceid id="7a5bda1c-b1db-4fd8-8763-a731e2e8abba">
    </resourceid>
  </topicmeta>
  <topicref href="GUID-139f6c64-bea3-4f17-8b22-ee131557e249-en.dita" type="topic">
  </topicref>
</map>  
```

También puede editar el ID del recurso en el modo Autor.

<img src="./assets/barcode-map.png" alt="Salida de muestra con código de barras" width="700" border="2px solid blue">


### Añada un marcador de posición de código de barras en el encabezado de plantilla

Modifique la `Common.plt` archivo en el **Básico** para agregar un código de barras después del título del proyecto.

```html
...
  <div data-region="header">
    <p class="chapter-header"><span data-field="project-title" data-format="default">Project Title</span> </p>
    <p><span class="barcode" data-field="metadata" data-format="default" data-subtype="//resourceid/@id">Resource ID (barcode)</span></p>
  </div>
} 
...
```


### Actualice el CSS de la plantilla para procesar un valor de código de barras

Modifique la `content.css` para procesar un código de barras durante la generación del PDF. Se admiten varios tipos de código de barras como qrcode y pdf417.  Para obtener más información, consulte [Tipos de códigos de barras](#barcode-types).



```css
...
.barcode {
  -ro-replacedelement: barcode;
  -ro-barcode-type: code128;
}
...
```

Una vez realizados los pasos anteriores, puede generar la salida del PDF con un código de barras.

La siguiente captura de pantalla muestra un código de barras de muestra en una salida de PDF.

<img src="./assets/barcode-output-sample.png" alt="Salida de muestra con código de barras" width="700">


## Tipos de códigos de barras {#barcode-types}

| Tipo | Atributo CSS | Atributo(s) adicional(es) |
| ------------------------------- | ----------------------- | -------------------------- |
| Código QR | qrcode |                            |
| PDF417 | pdf417 |                            |
| Matriz de datos | data-matrix |                            |
| Código azteca | aztec-code |                            |
| Matriz de cuadrícula | grid-matrix |                            |
| Maxicode | modo maxicode-4 |                            |
| Micro QR | microqr |                            |
| Código uno | código uno |                            |
| Bloque de código F | codablockf |                            |
| GS1 Databar Limited | databar-limited |                            |
| Barra de datos GS1 omnidireccional | barra de datos omnidireccional |                            |
| EAN-13 | ean-13 |                            |
| GS1-128 (EAN-128) | code128 | -ro-barcode-encoding: gs1; |
| ITF-14 | itf14 |                            |
| UPC-A | upc-a |                            |
| Código 128 | code128 |                            |
| Intercalado 2 de 5 | code2of5 intercalado |                            |
| POSTNET | postnet |                            |
| Código postal neerlandés | kixcode |                            |
| Korea Post | corea-post |                            |
| Deutsche Post Leitcode | dp-leitcode |                            |
| Australia Post | auspost |                            |
| Logmars | logmars |                            |
| Farmacode | código de farmacia |                            |
| OneCode de USPS (correo inteligente) | usps-onecode |                            |


