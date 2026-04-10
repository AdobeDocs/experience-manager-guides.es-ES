---
title: Anulaciones de configuración para Cloud Service
description: Obtenga información sobre cómo configurar las anulaciones de configuración
feature: Installation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
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

