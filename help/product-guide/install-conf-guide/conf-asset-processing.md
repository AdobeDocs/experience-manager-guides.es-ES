---
title: Configurar el procesamiento de recursos para Cloud Service
description: Obtenga información sobre cómo configurar el procesamiento de recursos para Cloud Service
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 3%

---

# Configurar la función de procesamiento de recursos

Las siguientes pestañas proporcionan instrucciones para configurar la función de procesamiento de recursos en función de la configuración de Experience Manager Guides: Cloud Service o Local.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md) para crear el archivo de configuración.

1. En el archivo de configuración, proporcione los siguientes detalles (propiedad):

   | PID | Clave de propiedad | Valor de propiedad |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `enable.asset.processing.scheduler` | **Valor predeterminado:** &quot;true&quot; |

>[!TAB Local]

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete *com.adobe.fmdita.config.ConfigManager*.

1. Configure la configuración `Enable Guides asset processing scheduled job` según sus necesidades. La configuración está habilitada de forma predeterminada.

1. Seleccione **Guardar**.

>[!ENDTABS]