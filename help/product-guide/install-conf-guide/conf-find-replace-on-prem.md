---
title: Configuración de Buscar y reemplazar (vista de Source) para instalación local
description: Obtenga información sobre cómo configurar Buscar y reemplazar (vista de Source) para local
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
source-wordcount: '84'
ht-degree: 2%
---
# Configuración de Buscar y reemplazar (vista de Source) para instalación local

En los pasos siguientes se explica cómo habilitar Buscar y reemplazar (vista de Source) en el entorno local.

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete **com.adobe.fmdita.config.ConfigManager**.

1. Habilite el valor **Habilitar búsqueda y reemplazo de marcado** (enable.markup.findreplace).

1. Seleccione **Guardar**.
