---
title: Configurar nuevo editor
description: Obtenga información sobre cómo habilitar o deshabilitar el nuevo editor
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
source-wordcount: '79'
ht-degree: 2%
---
# Configurar nuevo editor para local

>[!IMPORTANT]
>
> Implemente las configuraciones del sistema mediante código en lugar de aplicarlas manualmente en el entorno de tiempo de ejecución.

Los siguientes pasos explican cómo habilitar el nuevo editor en su entorno On-Premise.

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete **com.adobe.fmdita.config.ConfigManager**.

1. Habilite la configuración **Habilitar editor 2.0** (`enable.markup.editor`).

1. Seleccione **Guardar**.

