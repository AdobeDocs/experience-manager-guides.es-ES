---
title: Controlador de eventos del proceso de conversión
description: Obtenga información acerca del controlador de eventos del proceso de conversión
exl-id: 8033935d-2113-4e39-ab74-b7431b89f948
feature: Conversion Process Event Handler
role: Developer
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# Controlador de eventos del proceso de conversión {#id175UB30E05Z}

AEM Las guías de datos exponen el evento com/adobe/fmdita/conversion/complete que se utiliza para realizar cualquier operación posterior al procesamiento una vez completado el proceso de conversión de un documento. Este evento se activa cada vez que se migra un documento no DITA al formato de archivo DITA. Por ejemplo, si ejecuta un proceso de conversión de Word a DITA o de InDesign a DITA, se llama a este evento una vez finalizado el proceso de conversión.

AEM Es necesario crear un controlador de eventos de tipo para leer las propiedades disponibles en este evento y realizar un procesamiento posterior.

Los detalles del evento se explican a continuación:

**Nombre del evento**:

```HTTP
com/adobe/fmdita/conversion/complete 
```

**Parámetros**:\
|Nombre|Tipo|Descripción| |----|----|-----------| |`status`|Cadena|Estado de devolución de la operación realizada. Las opciones posibles son: - SUCCESS: El proceso de conversión se completó correctamente. <br> - COMPLETADO CON ERRORES: el proceso de conversión se ha completado, pero con algunos errores. <br>- FALLIDO: Error en el proceso de conversión debido a un error grave.| |`filePath`AEM |Cadena|Ruta absoluta del archivo de origen \(que se va a convertir\) en el repositorio de.| |`outputPath`|Cadena|Ruta absoluta de la ubicación de destino donde se guardarán los archivos DITA convertidos.| |`logPath`|Cadena|Ruta absoluta del nodo donde se guardará el registro de conversión.|
