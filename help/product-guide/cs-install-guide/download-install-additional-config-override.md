---
title: Anulaciones de configuración
description: Obtenga información sobre cómo configurar las anulaciones de configuración
exl-id: dc5f81f7-5b0a-4d12-a944-ba66b0239d5c
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 0%

---

# Anulaciones de configuración {#id216IFC003XA}

Para realizar cualquier actualización de la configuración, se debe utilizar el siguiente método genérico:

1. Acceda al repositorio de Git de Cloud Manager.

1. Cree un nuevo archivo JSON en la siguiente ubicación:

   src/main/content/jcr\_root/apps/fmditaCustom/config/

1. Asigne un nombre al archivo en el siguiente formato:

   $\{PID\}.cfg.json

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


**Tema principal:**[ Descargar e instalar](download-install.md)
