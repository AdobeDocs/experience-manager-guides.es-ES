---
title: Configurar nueva línea base para On-Premise
description: Obtenga información sobre cómo habilitar o deshabilitar la nueva línea de base para On-Premise
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
source-git-commit: 4abf673f636ffd20d087c99b5112d8504929a6ee
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 1%
---
# Configurar nueva línea base para local

>[!IMPORTANT]
>
> Implemente las configuraciones del sistema mediante código en lugar de aplicarlas manualmente en el entorno de tiempo de ejecución.

Los siguientes pasos explican cómo habilitar la nueva línea de base en su entorno local.

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete **com.adobe.fmdita.config.ConfigManager**.

1. Habilite la opción **Habilitar línea de base más rápida (v2)**. También puede buscar con el nombre de configuración exacto `enable.baseline.v2`.

1. Seleccione **Guardar**.

>[!NOTE]
>
>Después de habilitar esta función, debe migrar las líneas base existentes a la nueva línea base. Para obtener instrucciones paso a paso y un vídeo de introducción, vea [Nueva línea de base en Experience Manager Guides](../user-guide/web-editor-baseline-v2.md).

