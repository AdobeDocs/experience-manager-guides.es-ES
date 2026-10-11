---
title: API de REST para flujo de trabajo de conversión
description: Obtenga información acerca de las API de REST para el flujo de trabajo de conversión
exl-id: f091782e-ab54-4db4-9018-9bcbff9da7b2
feature: Rest API Conversion Workflow
role: Developer
level: Experienced
TQID: 'https://experienceleague.adobe.com/EG-ugDPVpviaEI1SXHOaFLPfChkzqQ8tSkPV-LZ-X3o'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
    internal-label: APIs
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
subfeature_v2:
  - id: d3b388b7-b49d-4f87-b444-9b6f7fc2ef0c
    internal-label: REST API Conversion Workflow
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 9%
---
# API de REST para flujo de trabajo de conversión {#id175UB30E05Z}

Las siguientes API de REST permiten convertir documentos de Word, HTML y InDesign al formato DITA.

## Convertir documentos de Word

Método GET que convierte documentos de Word en formato DITA.

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

Método GET que convierte documentos de HTML en formato DITA.

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

Método GET que convierte documentos de InDesign en formato DITA.

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
