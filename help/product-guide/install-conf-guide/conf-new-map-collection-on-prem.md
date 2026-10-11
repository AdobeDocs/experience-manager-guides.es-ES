---
title: Configuración de la nueva colección de mapas para instalación local
description: Obtenga información sobre cómo configurar la nueva colección de mapas para in situ
feature: Configuration
role: Admin
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 2%
---
# Configuración de la nueva colección de mapas para instalación local

Los siguientes pasos explican cómo habilitar la colección de mapas New en su entorno On-Premise.

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete **com.adobe.fmdita.config.ConfigManager**.

1. Habilite la configuración **Habilitar nuevas colecciones de mapas** (enable.new.map.collections).

   ![](assets/new-map-collection.png){width="800"}

1. Seleccione **Guardar**.
