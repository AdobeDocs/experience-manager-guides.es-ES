---
title: Creación del proyecto de traducción
description: Obtenga información sobre la creación de proyectos de traducción de API
feature: Post-Processing Event Handler
role: Developer
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
subfeature_v2:
  - id: e0bef973-8c57-4760-9b12-ec950a3c7247
    internal-label: Post processing event handler
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 14%
---

# Creación del proyecto de traducción

>[!NOTE]
>
> Para obtener las definiciones de extremo de API de REST más recientes y los detalles relacionados, vea la documentación de Swagger en `https://<aem-author-url>/libs/fmdita/clientlibs/api-docs/index.html` (reemplace `<aem-author-url>` por la URL de su servidor de AEM). Dado que este artículo está programado para archivarse en octubre de 2026, recomendamos utilizar la documentación de Swagger a partir de ahora para obtener la información de API más actualizada.

Un método POST que le ayuda a crear un proyecto de traducción al aceptar los detalles necesarios del proyecto.

## URL de solicitud

`http://<aem-guides-server>:<port-number>/bin/guides/v1/translation/project/create`

## Tipo de solicitud

PUBLICAR

## Parámetros de solicitud

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `type` | Cadena | newTranslationProject, xliffTranslationProject, newMultiLingualTranslationProject, addToExistingProject, newScopingTranslationProject |
| `versionDetails`, `versionSelector` | Cadena | Línea base, última versión, versionAsOfDate |
| `language` | Cadena | Idiomas separados por comas &quot;de&quot;, &quot;fr&quot; |
| `map.id` | Cadena | GUID del mapa de origen que se va a traducir |
| `map.path` | Cadena | Ruta del mapa de origen que se va a traducir |
| `referenceType` | Cadena | Indirecto, directo |
| `fileType` | Cadena | Mapa, Tema, Otros |
| `documentState` | Cadena | puede ser una de las listas asignadas por el usuario en el perfil del mapa |
| `translationStatus` | Cadena | Desincronizado, Sincronizado, Actualizado, Desactualizado, En curso, Copia faltante, NINGUNO, N/A |

>[!NOTE]
>
>Puede usar `map.id` o `map.path` al crear un proyecto de traducción.

## Solicitar ejemplo

```JSON
{
  "title": "Test Project 1 on Dec 5",
  "type": "newTranslationProject",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en",
      "path": "/content/dam/ajay-test/lang/en/m2.ditamap"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "latestVersion"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": [] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
   ]
```

## Valores de respuesta

```JSON
{
  "executionId": "5c13c571-3407-46d5-8f45-50ea9e05a212",
  "path": "/content/projects/test_project_1_ondec5"
}
```

**Códigos de respuesta**

- 200 Correctos
- 400 Entrada no válida
- 401 Acceso no autorizado
- Error de servidor interno 500

## Solicitudes de ejemplo

### Adición a un proyecto existente

```json
{
  "title": "Add to existing Project",
  "type": "addToExistingProject",
  "path": "/content/projects/test_project_1_existing",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "versionAsOfDate",
      "version": "2025-12-05T10:30:00+01:30"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": [] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
  ]
}
```

### Agregar a un proyecto existente con Línea base

```json
{
  "title": "Add to existin project Project with baseline",
  "type": "addToExistingProject",
  "path": "/content/projects/existing_project_path",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "baseline",
      "version": "test1"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": ["Direct"] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
  ]
}
```

## Estado de creación del proyecto de traducción

Una API de GET que rastrea el estado de traducción de un proyecto de traducción recién creado.

## URL de solicitud

`http://<aem-guides-server>:<port-number>/bin/guides/v1/translation/project/creationstatus`

## Tipo de solicitud

GET

## Parámetros de solicitud

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `path` | Cadena | Ruta del proyecto |
| `languageStatusMap` | Cadena | Para cada idioma solicitado, devuelve el estado de finalización: En curso, Completado, Fallido, Omitido |


## Solicitar ejemplo

```json
{
  "path": "/content/projects/test_project_1_ondec5",
  "languageStatusMap": {
    "de": "Completed"
  }
}
```
