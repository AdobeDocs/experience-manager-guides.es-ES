---
title: Configurar la omisión de vínculos de igual a igual para Línea de base V1 en Local
description: Obtenga información sobre cómo habilitar o deshabilitar el omitido de vínculos de igual a igual para Línea de base V1 en Local
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 1%

---

# Configurar la omisión de vínculos de igual a igual para la línea de base antigua en local

Los siguientes pasos explican cómo habilitar la omisión de vínculos de igual a igual para la línea de base antigua en su entorno local.

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete **com.adobe.fmdita.config.ConfigManager**.

1. Habilite la opción **Omitir vínculos de igual a igual para Línea de base V1** (guides.baseline.v1.skip.peer.links). Esta configuración está deshabilitada de forma predeterminada.

1. Seleccione **Guardar**.
