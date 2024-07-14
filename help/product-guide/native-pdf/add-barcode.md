---
title: Función nativa de PDF Publish | Añadir código de barras
description: Aprenda a añadir códigos de barras.
exl-id: 206bdcf9-2bcd-4bf1-815a-c97cdf0dc415
source-git-commit: d525775afeeb89754762ff514126b1c3a3307b3f
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 1%

---

# Añadir un código de barras a la salida del PDF

Un código de barras es un patrón de datos que las máquinas pueden leer. Los clientes pueden escanear códigos de barras con un escáner de códigos de barras o con la cámara de su smartphone. La información de codificación, como los detalles del producto, los números de inventario o las direcciones URL del sitio web, puede resultar útil. Añadir códigos de barras le ayuda a capturar los datos fácilmente, mejora la experiencia del cliente y facilita una mejor administración y seguridad de los datos.

Puede crear un estilo para el código de barras. y utilizarlo para insertar un código de barras en un diseño de página. Puede aplicar el estilo a un código de barras de ejemplo en el diseño de página deseado.


Este tutorial le ayuda a añadir códigos de barras en la salida del PDF.

## Pasos para generar un código de barras

Para generar un código de barras, realice los siguientes pasos:

### Actualice el CSS de la plantilla para procesar un valor de código de barras

Modifique el archivo `layout.css` para procesar un código de barras durante la generación del PDF. Se admiten varios tipos de código de barras como qrcode y pdf417.  Para obtener más información, vea [Tipos de código de barras](#barcode-types).



```css
...
.barcode { 
-ro-replacedelement: barcode;   
-ro-barcode-type: code128;   
-ro-barcode-size: 100%;   
-ro-barcode-content: content();   
object-fit: contain;   
margin-top: 2mm;
 
}
...
```

### Utilice el estilo CSS para generar el código de barras.

Puede generar el código de barras de diferentes maneras. Algunos de los ejemplos son los siguientes:

**Ejemplo 1**

Agregue un marcador de posición de código de barras en el encabezado de la plantilla y aplique el estilo:

1. Editar **plantillas** > **diseños de página**
1. Seleccione un diseño de página. Por ejemplo, puede seleccionar el diseño de página BackCover, que contiene el encabezado o pie de página.
1. Añada el siguiente intervalo a la ubicación en la que desea insertar el código de barras.

   `<span class="barcode">Sample barcode</span></p>`.

   >[!NOTE]
   >
   > Utilice el mismo nombre de clase que definió en `layout.css`.

1. Reemplace `<Sample barcode>` por el valor que desea que lea el analizador de códigos de barras.

Puede ver el código de barras al generar el PDF de salida mediante la plantilla, que incluye el diseño de página. Una vez realizados los pasos anteriores, puede generar la salida del PDF con un código de barras.

La siguiente captura de pantalla muestra un código de barras de muestra en una salida de PDF.

<img src="./assets/barcode-output-sample.png" alt="Salida de muestra con código de barras" width="700" border="2px">

**Ejemplo 2**

Modifique el archivo `Common.plt` en la plantilla **Básico** para agregar un código de barras después del título del proyecto.

Para crear un código de barras para un número ISBN, agregue un número ISBN. A continuación, utilice el número ISBN para generar el código de barras.

```html
...

  <div data-region="header">
    <p class="chapter-header"><span data-field="project-title" data-format="default">Project Title</span> </p>
    <p><span class="barcode">978-1-56619-909-4</span></p>
  </div>
} 
...
```

**Ejemplo 3**

Para crear un código de barras utilizando los metadatos de asignación:

Utilice cualquier metadato presente en el elemento `<topicmeta>` de un mapa DITA para mostrarlo como código de barras. Asegúrese de utilizar la sintaxis XPath correcta. Por ejemplo, puede agregar un(a) `<resourceid>` en el(la) `<topicmeta>` de un mapa DITA.

En el ejemplo siguiente, el ID de recurso sirve como entrada principal para generar el código de barras.

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



Puede utilizar el ID de recurso en un diseño de página de la siguiente manera:


```html
  <div data-region="header">
    <p class="chapter-header"><span data-field="project-title" data-format="default">Project Title</span> </p>
    <p><span class="barcode" data-field="metadata" data-format="default" data-subtype="//resourceid/@id">Resource ID (barcode)</span></p>
  </div>
} 
```

## Tipos de códigos de barras {#barcode-types}

Algunos de los códigos de barras más utilizados son los siguientes:

| Tipo | -ro-barcode-type | Detalles adicionales |
| ---| --- | --- |
| Código QR | qrcode | La simbología del código de barras QR según ISO/IEC 18004:2015. |
| Código 128 | code128 | La simbología del código de barras 128 definida en la norma ISO/IEC 15417:2007. |
| Código 32 | code32 | Código 32, también conocido como &quot;Código Farmacéutico italiano&quot;. |
| Código 49 | code49 | Código 49 según ANSI/AIM-BC6-2000. |
| Código 11 | code11 |                            |
| Código 93 | code93 |                            |
| Código16k | code16k |                            |
| PDF417 | pdf417 | Las simbologías de código de barras PDF 417/MicroPDF417 según ISO/IEC 15438:2006 e ISO/IEC 24728:2006. |
| Código 3 de 9 | code39 | El código 3 de 9 simbología de código de barras según la norma ISO/IEC 16388:2007. |
| MSI Plessey | mezquindad |                            |
| Código de canal | channelcode | Código de canal según ANSI/AIM BC12-1998. |
| Codabar | codabar | Código de barras de Codabar simbología según BS EN 798:1996. |
| EAN-8 | ean-8 | Código de barras según la norma BS EN 797:1996. |
| EAN-13 | ean-13 | Código de barras según la norma BS EN 797:1996. |
| UPC-A | upc-a | Código de barras UPC simbología según BS EN 797:1996. |
| UPC-E | upc-e | Código de barras UPC simbología según BS EN 797:1996. |
| Complemento Ean/UPC | complemento | Símbolo de código de barras complementario EAN/UPC según BS EN 797:1996. |
| Teléfono | telefonear | También conocido como Alpha de teléfono. |
| Barra de datos GS1/Barra de datos 14 | databar | Barra de datos GS1 según ISO/IEC 24724:2011. |
| Barra de datos GS1 expandida / Barra de datos 14 expandida | expandido por la barra de datos | Barra de datos GS1 expandida según ISO/IEC 24724:2011. |
| GS1 Databar Limited | databar-limited | GS1 DataBar Limited según ISO/IEC 24724:2011. |
| POSTNET (Técnica de codificación numérica postal) | postnet | La simbología del código de barras POSTNET (Postal Numeric Encoding Technique) utilizada por el servicio postal de Estados Unidos. |
| Número de farmacia (PZN-8) | pzn8 | Una simbología basada en el código 39 utilizada por la industria farmacéutica en Alemania. |
| Farmacode | código de farmacia |                            |
| Bloque de código F | codablockf | Simbología según AIM Europe &quot;Uniform Symbology Specification Codablock F&quot;, 1995. |
| Logmars | logmars | El estándar LOGMARS (Aplicaciones Logísticas de Símbolos Automatizados de Marcado y Lectura) utilizado por el Departamento de Defensa de los Estados Unidos. |
| Runas aztecas | runas aztecas | Simbología del código de barras de Aztec Runes según ISO/IEC 24778:2008 Anexo A. |
| Código azteca | aztec-code | Código Azteca simbología de código de barras Según ISO/IEC 24778:2008. |                            |
| Matriz de datos | data-matrix | Simbología de código de barras ECC 200 según ISO/IEC 16022:2006. |
| Código uno | código uno |                            |
