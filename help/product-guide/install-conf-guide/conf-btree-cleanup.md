---
title: Configurar trabajo de limpieza del almacén de referencia
description: Configurar trabajo de limpieza del almacén de referencia
feature: Output Generation
role: Admin
level: Experienced
exl-id: 58f98313-fc91-43b3-9553-aa5ab4946925
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
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
source-wordcount: '247'
ht-degree: 3%
---
# Configurar limpieza del almacén de referencia

Configure el trabajo de limpieza del almacén de referencia y administre la configuración de `Guides BTree deletion` para mantener el sistema optimizado y el almacenamiento limpio.

## Configurar trabajo de limpieza del almacén de referencia

Las siguientes pestañas proporcionan instrucciones para configurar el trabajo de limpieza del almacén de referencia en función de la configuración de Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md) para crear el archivo de configuración.

1. En el archivo de configuración, proporcione los siguientes detalles (propiedad):

   | PID | Clave de propiedad | Valor de propiedad |
   |---|---|---|
   | `com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob` | `cronExpression` | **Valor predeterminado:** &quot;0 0 0 * * ?&quot; |

>[!TAB Local]

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete *com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob*.

1. Actualice la expresión cron para configurar la frecuencia de ejecución del trabajo del programador de limpieza del almacén de referencia.

1. Configure el Planificador de limpieza de la tienda de referencia como se muestra a continuación.

   ![](assets/btree-cleanup-config.png)

1. Seleccione **Guardar**.

>[!ENDTABS]

## Configuración de las guías Configuración de habilitación de eliminación de árbol B

Las siguientes pestañas proporcionan instrucciones para habilitar la configuración en función de la configuración de Experience Manager Guides: Cloud Service o Local.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md) para crear el archivo de configuración.

1. En el archivo de configuración, proporcione los siguientes detalles (propiedad):

   | PID | Clave de propiedad | Valor de propiedad |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `btree.deletion.enabled` | **Valor predeterminado:** &quot;True&quot; |

>[!TAB Local]

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete *com.adobe.fmdita.config.ConfigManager*.
1. Habilite la opción **Eliminación del árbol b de guías habilitada** (btree.delete.enabled).

   ![](assets/btree-cleanup-setting.png)

1. Seleccione **Guardar**.

>[!ENDTABS]
