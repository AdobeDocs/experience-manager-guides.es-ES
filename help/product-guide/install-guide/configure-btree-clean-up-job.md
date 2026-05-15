---
title: Configurar el trabajo de limpieza del árbol B para los servicios locales
description: Configurar el trabajo de limpieza del árbol B para los servicios locales
feature: Output Generation
role: Admin
level: Experienced
exl-id: ff6f968c-3440-4757-882a-676711ad05c3
TQID: https://experienceleague.adobe.com/qvOHGtHbgKS3xUv0pEXKTqeWblIDj8JKJwik8heXwPo
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 156
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
