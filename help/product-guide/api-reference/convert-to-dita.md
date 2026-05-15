---
title: API de REST para flujo de trabajo de conversión
description: Obtenga información acerca de las API de REST para el flujo de trabajo de conversión
exl-id: f091782e-ab54-4db4-9018-9bcbff9da7b2
feature: Rest API Conversion Workflow
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/EG-ugDPVpviaEI1SXHOaFLPfChkzqQ8tSkPV-LZ-X3o
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552eid: c6d09140-3c91-45d3-b7ed-b681af752f43
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 402
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
| `inputFile` | Cadena | Sí | Ruta absoluta de los archivos de origen de Word en el repositorio de AEM. |
| `destPath` | Cadena | Sí | Ruta absoluta de la ubicación de destino donde se guardarán los ficheros DITA convertidos. |
| `createRev` | Booleano | Sí | Especifique si se crea una revisión de los archivos \( `true`\) en el destino especificado o no \( `false`\). Esto solo se tiene en cuenta cuando la ubicación de destino contiene una versión existente de los archivos convertidos. |
| `style2tagMap` | Cadena | Sí | Ruta absoluta del archivo de asignación de estilos que se utilizará para la conversión. |

**Valores de respuesta**:
Devuelve una respuesta HTTP 200 \(Correcto\).

## Convertir documentos de HTML

Método de GET que convierte documentos de HTML en formato DITA.

**URL de solicitud**:

http://*<aem-guides-server\>*: *<port-number\>*/bin/fmdita/conversion

**Parámetros**:

| Nombre | Tipo | Requerido | Descripción |
|----|----|--------|-----------|
| `operation` | Cadena | Sí | Nombre de la operación a la que se llama. El valor de este parámetro es ``html2dita``. <br> **Nota:** El valor no distingue entre mayúsculas y minúsculas. |
| `inputFile` | Cadena | Sí | Ruta absoluta de los archivos HTML de origen en el repositorio de AEM. |
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
| `inputFile` | Cadena | Sí | Ruta absoluta de los archivos InDesign de origen en el repositorio de AEM. |
| `destPath` | Cadena | Sí | Ruta absoluta de la ubicación de destino donde se guardarán los ficheros DITA convertidos. |
| `createRev` | Booleano | Sí | Especifique si se crea una revisión de los archivos \( `true`\) en el destino especificado o no \( `false`\). Esto solo se tiene en cuenta cuando la ubicación de destino contiene una versión existente de los archivos convertidos. |

**Valores de respuesta**:
Devuelve una respuesta HTTP 200 \(Correcto\).
