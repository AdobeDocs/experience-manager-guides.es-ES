---
title: Configurar el trabajo de limpieza del árbol B para Cloud Services
description: Configurar el trabajo de limpieza del árbol B para Cloud Services
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# Configurar limpieza de árbol B

Configure el trabajo de limpieza del árbol B y administre la configuración de `Guides BTree deletion` para mantener el sistema optimizado y el almacenamiento limpio.

## Configurar trabajo de limpieza del árbol B

Las siguientes pestañas proporcionan instrucciones para configurar el trabajo de limpieza del árbol B en función de la configuración de Experience Manager Guides: Cloud Service o On-Premise.

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

1. Actualice la expresión cron para configurar la frecuencia de ejecución del trabajo del programador de limpieza de árbol B.

1. Configure el planificador de limpieza de árbol B como se muestra a continuación.

   ![](assets/btree-cleanup-config.png){align="left"}

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
1. Habilite la configuración `Guides btree deletion enabled`.

   ![](assets/btree-cleanup-setting.png){align="left"}

1. Seleccione **Guardar**.

>[!ENDTABS]