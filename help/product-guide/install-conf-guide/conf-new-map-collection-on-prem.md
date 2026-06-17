---
title: Configuración de la nueva colección de mapas para instalación local
description: Obtenga información sobre cómo configurar la nueva colección de mapas para in situ
feature: Configuration
role: Admin
level: Experienced
source-git-commit: da97ff167c70034dc1801792e7ccdf82d733c688
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 2%

---

# Configuración de la nueva colección de mapas para instalación local

Los siguientes pasos explican cómo habilitar la colección de mapas New en su entorno On-Premise.

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete **com.adobe.fmdita.config.ConfigManager**.

1. Habilite la configuración **Habilitar nuevas colecciones de mapas** (enable.new.map.collections).

   ![](assets/new-map-collection.png){width="800"}

1. Seleccione **Guardar**.
