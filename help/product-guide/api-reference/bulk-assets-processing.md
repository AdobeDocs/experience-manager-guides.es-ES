---
title: API para iniciar el procesamiento masivo de recursos
description: Obtenga información acerca de la API para iniciar el procesamiento masivo de recursos
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: 8671a26bfee2d9e3b4e70a8f2615568c08c0a370
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 12%

---

# API para iniciar el procesamiento masivo de recursos

Un método POST que inicia el procesamiento masivo de recursos para una ruta de acceso especificada. Esta API admite el procesamiento de recursos basado en JCR y en base a datos. Inicia un trabajo asincrónico que procesa todos los recursos de la ruta dada y sus subrutas. Al iniciarse, la API devuelve un ID de procesamiento único, que se puede utilizar para realizar un seguimiento del estado del trabajo.

**URL de solicitud**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process`

**Parámetros de solicitud**

| Nombre | Tipo | Requerido | Descripción |
|----|----|--------|-----------|
| `path` | Cadena | Sí | Ruta absoluta de la carpeta o el recurso en el repositorio de AEM que se va a procesar. |
| `excludedPaths` | Cadena | No | Lista de rutas que se excluirán del procesamiento |
| `type` | Cadena | Sí | Tipo de procesamiento que se va a realizar. Por ejemplo: ASSET_PROCESSING. |
| `filter` | Objeto | No | Filtros aplicados a los recursos seleccionados |

**Filtrar campos de objeto**

| Nombre | Tipo | Descripción |
|----|----|-----------|
| fileTypes | Cadena | Tipos de recursos que procesar. Valores permitidos: DITATOPIC, DITAMAP, MARKDOWN, HTML/CSS, DITAVAL, OTROS. |
| startTime | Entero | Límite inferior para la hora de creación del recurso |
| endTime | Entero | Límite superior del tiempo de creación del recurso |

**Ejemplo de solicitud**

```JSON
{
  "path": "/content/dam/status-fetch1",
  "excludedPaths": [
    "content/dam/status-fetch1/excluded-folder"
  ],
  "type": "ASSET_PROCESSING",
  "filter": {
        "fileTypes": ["DITAMAP", "DITATOPIC"],
        "startTime": 1758876933000
        "endTime": 1764932039000
    }
}
```

**Valores de respuesta**

processingId para sondear y obtener el estado del trabajo asincrónico.

```JSON
{
  "processingId": "akjhdfalkj1132"
}
```

**Códigos de respuesta**

- 200 Correctos
- 400 Entrada no válida
- 401 Acceso no autorizado
- Error de servidor interno 500

## Comprobar estado del trabajo

Método de GET que recupera el estado actual de un trabajo de procesamiento de recursos iniciado anteriormente.

**URL de solicitud**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/status`

**Parámetros de solicitud**

| Nombre | Tipo | Requerido | Descripción |
|----|----|--------|-----------|
| `processingId` | Cadena | Sí | ID único del trabajo cuyo estado se está consultando. |

**Ejemplo de respuesta**

```JSON
{
  "processingId": "string",
  "path": "string",
  "excludedPaths": ["string"],
  "status": "WAITING",
  "triggeredCount": 0,
  "startedAt": 0,
  "completedAt": 0,
  "hasLogs": true,
  "createdBy": "string",
  "type": "ASSET_PROCESSING",
  "migrationSet": {
    "totalFiles": 0,
    "calculationStatus": "WAITING"
  },
  "eta": {
    "value": 0,
    "unit": "string"
  },
  "comments": "string",
  "restartable": true,
  "resumable": true,
  "cancellable": true
}
```

**Códigos de respuesta**

- 200 Correctos
- 400 Entrada no válida
- 401 Acceso no autorizado
- Error de servidor interno 500

## Ver registros de trabajos

Método de GET que recupera los registros de un ID de trabajo determinado. Esta API recupera los registros del trabajo de procesamiento de recursos. El ID de procesamiento es obligatorio. La API proporciona parámetros de desplazamiento y límite, así como una estrategia de seguimiento.

**URL de solicitud**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/logs`

**Parámetros de solicitud**

| Nombre | Tipo | Requerido | Descripción |
|----|----|--------|-----------|
| `processingId` | Cadena | Sí | ID único del trabajo cuyos registros se van a ver. |
| `offset` | Entero | No | El punto de partida (número de línea) desde el que se deben leer los registros. Se utiliza para que la paginación omita las primeras N líneas. |
| `limit` | Entero | No | Número máximo de líneas de registro que se van a recuperar. |
| `tail` | Entero | No | Número de líneas de registro que se recuperarán del final. |


**Ejemplo de respuesta**

```JSON
{
  "lines": [
    "string"
  ],
  "limit": 0,
  "offset": 0,
  "hasMore": true
}
```

**Códigos de respuesta**

- 200 Correctos
- 400 Entrada no válida
- 401 Acceso no autorizado
- 500 Error interno del servidor


## Descargar registros de trabajo

Método de GET que descarga el archivo de registro de un trabajo determinado como ZIP.

**URL de solicitud**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/logs/download`

**Parámetros de solicitud**

| Nombre | Tipo | Requerido | Descripción |
|----|----|--------|-----------|
| `processingId` | Cadena | Sí | ID único del trabajo cuyo archivo de registro debe descargarse. |


**Ejemplo de respuesta**

```JSON
{
  "logFilePaths": [
    "string"
  ]
}
 
```

**Códigos de respuesta**

- 400 Entrada no válida
- 401 Acceso no autorizado
- 500 Error interno del servidor

## Cancelar trabajo

Una API de POST que cancela una solicitud de procesamiento masivo de recursos en curso. Si no se encuentra el trabajo, la API devuelve un error.

**URL de solicitud**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/cancel`

**Parámetros de solicitud**

| Nombre | Tipo | Requerido | Descripción |
|----|----|--------|-----------|
| `processingId` | Cadena | Sí | ID único del trabajo cuyo estado se está consultando. |


**Códigos de respuesta**

- 200 Correctos
- 400 Entrada no válida
- 401 Acceso no autorizado
- 500 Error interno del servidor


## Reanudar trabajo

Una API de POST que reinicia una solicitud de procesamiento masivo de recursos que se ha cancelado o que ha dado error. Reanuda el procesamiento desde el último punto de comprobación. Si el trabajo no se encuentra o se está ejecutando, la API devuelve un error.

**URL de solicitud**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/resume`

**Parámetros de solicitud**

| Nombre | Tipo | Requerido | Descripción |
|----|----|--------|-----------|
| `processingId` | Cadena | Sí | ID único del trabajo cuyo estado se está consultando. |


**Códigos de respuesta**

- 200 Correctos
- 400 Entrada no válida
- 401 Acceso no autorizado
- 500 Error interno del servidor

## Ver historial de trabajos

Una API de GET que devuelve las últimas &quot;N&quot; ejecuciones de posprocesamiento de recursos.

**URL de solicitud**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/history`

**Parámetros de solicitud**

Ninguna. Esta solicitud de GET recupera el historial de trabajos sin requerir parámetros de entrada.

**Ejemplo de respuesta**

```JSON
{
  "executionHistory": [
    {
      "processingId": "165f1de6-68c4-4dcd-9223-2b7242b62306",
      "path": "/content/dam/22858",
      "status": "SUCCESS",
      "triggeredCount": 6,
      "startedAt": 1761291362776,
      "completedAt": 1761291364026,
      "hasLogs": true,
      "createdBy": "user",
      "type": "ASSET_PROCESSING",
      "migrationSet": {
        "totalFiles": 6,
        "calculationStatus": "SUCCESS"
      },
      "eta": {
        "value": 0,
        "unit": "SECONDS"
      },
      "comments": "",
      "filter": {
        "fileTypes": [],
        "filterProcessedAssets": false
      },
      "cancellable": false,
      "resumable": false,
      "restartable": true
    }
  ]
}
```



