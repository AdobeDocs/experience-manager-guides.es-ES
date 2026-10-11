---
title: Anulaciones de configuración para Cloud Service
description: Obtenga información sobre cómo configurar las anulaciones de configuración
feature: Installation
role: Admin
level: Experienced
exl-id: baf48913-ced7-444f-a125-661c0213d847
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: e557051c-ff02-4ff8-9421-cf452af0edd5
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 0%
---
# Anulaciones de configuración para Cloud Service {#id216IFC003XA}

Para realizar cualquier actualización de la configuración en Experience Manager Guides as a Cloud Service, se debe utilizar el siguiente método genérico:

1. Acceda al repositorio de Git de Cloud Manager.

1. Cree un nuevo archivo JSON en la siguiente ubicación:

   `src/main/content/jcr\_root/apps/fmditaCustom/config/`

1. Asigne un nombre al archivo en el siguiente formato:

   `$\{PID\}.cfg.json`

   En este caso, el PID es el ID de proceso de la configuración.

1. Agregue propiedades en el archivo JSON con el siguiente formato:

   ```
   {
      "aem.adminuname": "updatedUserjson",
      "valid.characters": "[-a-zA-Z0-9_@$]",
      "dita.serialization": true
   }
   ```

1. Confirme los cambios y ejecute la canalización de Cloud Manager para implementar la configuración actualizada.
