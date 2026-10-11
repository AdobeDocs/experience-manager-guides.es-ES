---
title: Configurar el trabajo de limpieza del árbol B para los servicios locales
description: Configurar el trabajo de limpieza del árbol B para los servicios locales
feature: Output Generation
role: Admin
level: Experienced
exl-id: ff6f968c-3440-4757-882a-676711ad05c3
TQID: 'https://experienceleague.adobe.com/qvOHGtHbgKS3xUv0pEXKTqeWblIDj8JKJwik8heXwPo'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 2%
---
# Configurar limpieza de árbol B

Configure el trabajo de limpieza del árbol B y administre la configuración de `Guides B-tree deletion` para mantener el sistema optimizado y el almacenamiento limpio.

## Configurar trabajo de limpieza del árbol B

Siga estos pasos para configurar el trabajo de limpieza del árbol B:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete *com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob*.

1. Actualice la expresión cron para configurar la frecuencia de ejecución del trabajo del programador de limpieza de árbol B.

1. Configure el planificador de limpieza de árbol B como se muestra a continuación.

   ![](assets/btree-cleanup-config.png)

1. Seleccione **Guardar**.


## Configuración de las guías Configuración de habilitación de eliminación de árbol B

Siga estos pasos para habilitar la configuración:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete *com.adobe.fmdita.config.ConfigManager*.
1. Habilite la configuración `Guides btree deletion enabled`.

   ![](assets/btree-cleanup-setting.png)

1. Seleccione **Guardar**.
