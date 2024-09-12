---
title: API de REST para flujo de trabajo de conversión
description: Obtenga información acerca de las API de REST para el flujo de trabajo de conversión
exl-id: f091782e-ab54-4db4-9018-9bcbff9da7b2
feature: Rest API Conversion Workflow
role: Developer
level: Experienced
source-git-commit: 45ae1471fe0f0586764ede9dd96530b7f75f69ee
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 9%

---

# API de REST para flujo de trabajo de conversión {#id175UB30E05Z}

Las siguientes API de REST permiten convertir documentos de Word, HTML y InDesign al formato DITA.

## Convertir documentos de Word

Método de GET que convierte documentos de Word en formato DITA.

**URL de solicitud**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/conversion

| Nombre | Tipo | Requerido | Descripción |
|----|----|--------|-----------|
| ``operation`` | Cadena | Sí | Nombre de la operación a la que se llama. El valor de este parámetro es ``word2dita``. <br> **Nota:** El valor no distingue entre mayúsculas y minúsculas. |
| `inputFile` | Cadena | Sí | AEM Ruta absoluta de los archivos de Word de origen en el repositorio de la. |
| `destPath` | Cadena | Sí | Ruta absoluta de la ubicación de destino donde se guardarán los ficheros DITA convertidos. |
| `createRev` | Booleano | Sí | Especifique si se crea una revisión de los archivos \( `true`\) en el destino especificado o no \( `false`\). Esto solo se tiene en cuenta cuando la ubicación de destino contiene una versión existente de los archivos convertidos. |
| `style2tagMap` | Cadena | Sí | Ruta absoluta del archivo de asignación de estilos que se utilizará para la conversión. |

**Valores de respuesta**:
Devuelve una respuesta HTTP 200 \(Correcto\).

## Convertir documentos de HTML

Método de GET que convierte documentos de HTML en formato DITA.

**URL de solicitud**:

http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/conversion

**Parámetros**:

| Nombre | Tipo | Requerido | Descripción |
|----|----|--------|-----------|
| `operation` | Cadena | Sí | Nombre de la operación a la que se llama. El valor de este parámetro es ``html2dita``. <br> **Nota:** El valor no distingue entre mayúsculas y minúsculas. |
| `inputFile` | Cadena | Sí | Ruta absoluta de los archivos del HTML AEM de origen en el repositorio de la. |
| `destPath` | Cadena | Sí | Ruta absoluta de la ubicación de destino donde se guardarán los ficheros DITA convertidos. |
| `createRev` | Booleano | Sí | Especifique si se crea una revisión de los archivos \( `true`\) en el destino especificado o no \( `false`\). Esto solo se tiene en cuenta cuando la ubicación de destino contiene una versión existente de los archivos convertidos. |

**Valores de respuesta**:

Devuelve una respuesta HTTP 200 \(Correcto\).

## Convertir documentos de InDesign

Método de GET que convierte documentos de InDesign en formato DITA.

**URL de solicitud**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/conversion

**Parámetros**:

| Nombre | Tipo | Requerido | Descripción |
|----|----|--------|-----------|
| ``operation`` | Cadena | Sí | Nombre de la operación a la que se llama. El valor de este parámetro es ``idml2dita``. <br> **Nota:** El valor no distingue entre mayúsculas y minúsculas. |
| `inputFile` | Cadena | Sí | Ruta absoluta de los archivos de InDesign AEM de origen en el repositorio de la. |
| `destPath` | Cadena | Sí | Ruta absoluta de la ubicación de destino donde se guardarán los ficheros DITA convertidos. |
| `createRev` | Booleano | Sí | Especifique si se crea una revisión de los archivos \( `true`\) en el destino especificado o no \( `false`\). Esto solo se tiene en cuenta cuando la ubicación de destino contiene una versión existente de los archivos convertidos. |

**Valores de respuesta**:
Devuelve una respuesta HTTP 200 \(Correcto\).
