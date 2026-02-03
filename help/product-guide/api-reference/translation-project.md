---
title: Creación del proyecto de traducción
description: Obtenga información sobre la creación de proyectos de traducción de API
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: 41dd3dee5f9d64fb5c58b5b302cc9759e48e3631
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 17%

---

# Creación del proyecto de traducción

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



