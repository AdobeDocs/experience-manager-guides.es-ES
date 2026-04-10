---
title: Configuración de la replicación de DITA Assets
description: Obtenga información sobre cómo configurar la replicación de recursos de datos
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 453da51a42984b912547570f2e1de70806b41171
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 3%

---

# Configuración de la replicación de recursos DITA

Las siguientes pestañas proporcionan instrucciones para configurar la función de replicación de recursos DITA en función de la configuración de Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Siga las instrucciones indicadas en [Anulaciones de configuración](../install-conf-guide/download-install-config-override.md) para crear el archivo de configuración.

1. En el archivo de configuración, proporcione los siguientes detalles (propiedad):

   | PID | Clave de propiedad | Valor de propiedad |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `publish.replicate` | **Valor predeterminado:** &quot;true&quot; |

>[!TAB Local]

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete *com.adobe.fmdita.config.ConfigManager*.

1. Configure la configuración `Replicate DITA assets` según sus necesidades. La configuración está habilitada de forma predeterminada.


   ![](assets/dita-assets-replication.png){width="350" align="left"}


1. Seleccione **Guardar**.

>[!ENDTABS]
