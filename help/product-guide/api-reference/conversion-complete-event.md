---
title: Controlador de eventos del proceso de conversión
description: Obtenga información acerca del controlador de eventos del proceso de conversión
exl-id: 8033935d-2113-4e39-ab74-b7431b89f948
feature: Conversion Process Event Handler
role: Developer
level: Experienced
TQID: 'https://experienceleague.adobe.com/VhlUaVSMTZpfyh5MiJI0WHFpc46s41xjLbuLMUnKH58'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
subfeature_v2:
  - id: bb416568-e09c-46e3-b3e9-fa7154401215
    internal-label: Conversion process event handler
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 3%
---
# Controlador de eventos del proceso de conversión {#id175UB30E05Z}

AEM Guides expone el evento com/adobe/fmdita/conversion/complete que se utiliza para realizar operaciones posteriores al procesamiento una vez completado el proceso de conversión de un documento. Este evento se activa cada vez que se migra un documento no DITA al formato de archivo DITA. Por ejemplo, si ejecuta un proceso de conversión de Word a DITA o de InDesign a DITA, se llama a este evento una vez finalizado el proceso de conversión.

Debe crear un controlador de eventos AEM para leer las propiedades disponibles en este evento y realizar un procesamiento posterior.

Los detalles del evento se explican a continuación:

**Nombre del evento**:

```HTTP
com/adobe/fmdita/conversion/complete 
```

**Parámetros**:

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `status` | Cadena | Estado de devolución de la operación realizada. Las opciones posibles son: - SUCCESS: El proceso de conversión se completó correctamente. <br> - COMPLETADO CON ERRORES: el proceso de conversión se completó, pero con algunos errores. <br> - ERROR: error en el proceso de conversión debido a un error grave. |
| `filePath` | Cadena | Ruta absoluta del archivo de origen \(a convertir\) en el repositorio de AEM. |
| `outputPath` | Cadena | Ruta absoluta de la ubicación de destino donde se guardarán los ficheros DITA convertidos. |
| `logPath` | Cadena | Ruta absoluta del nodo donde se guardará el registro de conversión. |
