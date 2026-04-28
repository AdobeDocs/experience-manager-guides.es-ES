---
title: Configuración de la replicación de DITA Assets para servicios locales
description: Obtenga información sobre cómo configurar la replicación de recursos de datos para servicios locales
feature: Output Generation
role: Admin
level: Experienced
exl-id: 49fd9dfe-e1a5-4388-abbd-ec5d45669b45
source-git-commit: ccaf2ead1a9a24ab822298c6b9ef6866a1c32e8c
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 2%

---

# Configuración de la replicación de recursos DITA

Siga estos pasos para configurar la función de procesamiento de recursos:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete *com.adobe.fmdita.config.ConfigManager*.

1. Configure la configuración `Replicate DITA assets` según sus necesidades. La configuración está habilitada de forma predeterminada.


   ![](assets/dita-assets-replication.png){width="350" align="left"}


1. Seleccione **Guardar**.
