---
title: Configurar el trabajo de limpieza del árbol B para los servicios locales
description: Configurar el trabajo de limpieza del árbol B para los servicios locales
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: e1b332b100cc8e3937557e4617d66352c1a0dc3c
workflow-type: tm+mt
source-wordcount: '145'
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

   ![](assets/btree-cleanup-config.png){align="left"}

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

   ![](assets/btree-cleanup-setting.png){align="left"}

1. Seleccione **Guardar**.

