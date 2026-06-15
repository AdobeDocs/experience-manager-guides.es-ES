---
title: API para rastrear el procesamiento posterior de una carpeta o un recurso
description: Obtenga información acerca de la API para rastrear el procesamiento posterior de una carpeta o un recurso
feature: Post-Processing Event Handler
role: Developer
level: Experienced
exl-id: f902fac1-2717-4696-a835-c4b0bb8add3d
TQID: https://experienceleague.adobe.com/Lyv-S5o-Z40bMqqIHhbxKrsmn9CCqHRnqnpiq91EjGU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 1d80ca88a3a6637a118657367b86b499675f6d0e
workflow-type: tm+mt
source-wordcount: 150
ht-degree: 13%

---

# API para rastrear el estado posterior al procesamiento de una carpeta o un recurso

El siguiente es un método POST que inicia un trabajo asincrónico para obtener el estado de los recursos.

## Buscar el estado de los recursos en las guías

**URL de solicitud**

`http://<aem-guides-server>:<port-number>bin/guides/v1/assets/status `

**Parámetros**

| Nombre | Tipo | Requerido | Descripción |
|----|----|--------|-----------|
| `path` | Cadena | Sí | Ruta de carpeta o recurso para el que se debe obtener el estado. |
| `excludedPaths` | Cadena | No | Rutas de carpeta que se excluirán de la lista anterior. |

```JSON
{ 

    "paths": [ 

        "/content/dam/status-fetch1", 

        "/content/dam/status-fetch2" 

    ], 

    "excludedPaths": [ 

        "content/dam/status-fetch1/excluded-folder" 

    ] 

} 
```

**Valores de respuesta**
jobId para sondear y obtener el estado del trabajo asincrónico.

```JSON
{ 

  "jobId": "akjhdfalkj1132", 

  "status": "WAITING", 

 

} 
```

## API de sondeo

Un método GET que obtiene el estado del trabajo asincrónico ejecutado por la API anterior.

**URL de solicitud**

`http://<aem-guides-server>:<port-number>bin/guides/v1/assets/status`

**Parámetros**

| Nombre | Tipo | Requerido | Descripción |
|----|----|--------|-----------|
| `jobId` | Cadena | Sí | El ID de trabajo devuelto por la API anterior |

**Valores de respuesta**

Lista de recursos y su estado.

```JSON
{ 

  "jobId": " akjhdfalkj1132", 

  "status": "SUCCESS", 

  "assets": [ 

    { 

      "path": "/content/dam/status-fetch1/a.dita", 

      "uuid": "GUID-1293914ansd", 

      "status": "SUCCESS", 

      "exists": true 

    }, 

    { 

      "path": "/content/dam/status-fetch1/b.dita", 

      "uuid": "GUID-1883241", 

      "status": "FAILURE", 

      "exists": true 

    } 

 

  ] 

} 
```

**Valores de estado:** CORRECTO, ERRÓNEO, PROCESANDO, PENDIENTE
