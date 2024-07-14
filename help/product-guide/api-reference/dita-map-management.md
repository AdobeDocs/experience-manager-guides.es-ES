---
title: API de REST para trabajar con mapas DITA
description: Obtenga información acerca de la API de REST para trabajar con mapas DITA
exl-id: 6277e52d-1b05-4dd7-8d2b-4b94f329e2d7
feature: Rest API DITA Map
role: Developer
level: Experienced
source-git-commit: 7c529e98334999cf2b5e9ee18a27278d24318437
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---

# API de REST para trabajar con mapas DITA {#id175UB30E05Z}

La siguiente API de REST permite trabajar con mapas DITA en AEM Guides.

## Descargar mapa DITA con dependientes

Método de GET que descarga un mapa DITA con todos sus dependientes, como temas referenciados, submapas, imágenes y DTD utilizados en el mapa y los temas.

**URL de solicitud**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/exportditamap

**Parámetros**:
|Nombre|Tipo|Descripción|Requerida|
----|----|--------|-----------
AEM |`ditamap`|Cadena|Sí|Ruta absoluta del archivo de mapa DITA en el repositorio de la.|
|`baseline`|Cadena|No|Título de la línea de base que se usa para recuperar el contenido con versiones. <br> **Nota:** El valor distingue entre mayúsculas y minúsculas. |

**Valores de respuesta**:
Un archivo .zip cuyo contenido se escribe en el flujo de salida de la respuesta.

## Iniciar exportación para mapa DITA con dependientes

Método de POST que inicia una exportación para un mapa DITA con todos sus dependientes, como temas referenciados, submapas, imágenes y DTD utilizados en el mapa y los temas. El estado se puede consultar más adelante y la URL de descarga se puede recuperar una vez completada.

**URL de solicitud**:
http:*//&lt;aem-guides-server\>: &lt;port-number\>/bin/dxml/async-export*

**Parámetros**:
|Nombre|Tipo|Descripción|Requerida|
----|----|--------|-----------
AEM |`ditamap`|Cadena|Sí|Ruta absoluta del archivo de mapa DITA en el repositorio de la.|
|`baseline`|Cadena|No|Título de la línea de base que se usa para recuperar el contenido con versiones. <br> **Nota:** El valor distingue entre mayúsculas y minúsculas.|
|`flatFS`|Booleano|No|\(Opcional\) Si se establece en true, se devuelve una estructura plana de archivos en el archivo ZIP. Por ejemplo, si el mapa DITA hace referencia a contenido de varias carpetas, todos los ficheros a los que se hace referencia se extraerán en una sola carpeta. En caso de que haya archivos con el mismo nombre, se cambiará el nombre de esos archivos añadiendo un sufijo numérico. Todas las referencias \(en el mapa DITA y en los temas\) se gestionan automáticamente, ya que se actualizan en función de la nueva ubicación de los archivos en la estructura de carpetas plana. Si se establece en false, la estructura de carpetas se mantiene tal como está en el archivo ZIP. Si el mapa DITA hace referencia a ficheros de varias ubicaciones, todas esas ubicaciones se crearán también en el fichero ZIP. Al restaurar el archivo ZIP, se crea la estructura de carpetas exacta en la ubicación de destino. <br>: el valor predeterminado de este parámetro es false.|

**Valores de respuesta**:
|Elemento|Descripción|
|-------|-----------|
|`status`|Estado de retorno de la operación realizada. Las opciones posibles son: INICIADO, FALLIDO, EN CURSO, CORRECTO, FALTANTE, ELIMINADO|
|`jobId`|ID único del trabajo. Se puede utilizar más adelante para consultar el estado.|
|errorMessage|Mensaje de error del trabajo en caso de error \(si el estado es FAILED, MISSING o DELETED\).|
|`filePath`|Ruta de archivo del ZIP. Solo está presente cuando se completa el trabajo y el estado es CORRECTO. Se puede usar para descargar el archivo ZIP.|

## Consultar estado de exportación de mapa DITA

Método de GET que recupera el estado de exportación de un mapa DITA con todos sus dependientes. Se puede sondear a intervalos si el estado es STARTED o INPROGRESS hasta que finalice \(correctamente o con un error\).

**URL de solicitud**:
http:*//&lt;aem-guides-server\>: &lt;port-number\>/bin/dxml/async-export*

**Parámetros**
|Nombre|Tipo|Descripción|Requerida|
----|----|--------|-----------
|`jobId`|Cadena|Sí|Id. de trabajo recuperado cuando se inició el trabajo de exportación.|

**Valores de respuesta**:
|Elemento|Descripción|
|-------|-----------|
|`status`|El estado del trabajo de exportación. Las opciones posibles son: INICIADO, FALLIDO, EN CURSO, CORRECTO, FALTANTE, ELIMINADO|
|`jobId`|ID único del trabajo. Se puede utilizar más adelante para consultar el estado.|
|`errorMessage`|El mensaje de error del trabajo en caso de error \(si el estado es FAILED, MISSING o DELETED\).|
|`filePath`|Ruta de archivo del ZIP. Solo está presente cuando se completa el trabajo y el estado es CORRECTO. Se puede usar para descargar el archivo ZIP.|
