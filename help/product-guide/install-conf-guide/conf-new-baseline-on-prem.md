---
title: Configurar nueva línea base para On-Premise
description: Obtenga información sobre cómo habilitar o deshabilitar la nueva línea de base para On-Premise
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 1%

---

# Configurar nueva línea base para local

>[!IMPORTANT]
>
> Implemente las configuraciones del sistema mediante código en lugar de aplicarlas manualmente en el entorno de tiempo de ejecución.

Los siguientes pasos explican cómo habilitar la nueva línea de base en su entorno local.

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete **com.adobe.fmdita.config.ConfigManager**.

1. Habilite la opción **Habilitar línea de base más rápida (v2)**. También puede buscar con el nombre de configuración exacto `enable.baseline.v2`.

1. Seleccione **Guardar**.

>[!NOTE]
>
>Después de habilitar esta función, debe migrar las líneas base existentes a la nueva línea base. Para obtener instrucciones paso a paso y un vídeo de introducción, vea [Nueva línea de base (Beta) en Experience Manager Guides](../user-guide/web-editor-baseline-v2.md).

