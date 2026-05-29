---
title: Configurar nuevo editor
description: Obtenga información sobre cómo habilitar o deshabilitar el nuevo editor
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 2%

---

# Configurar nuevo editor para local

>[!IMPORTANT]
>
> Implemente las configuraciones del sistema mediante código en lugar de aplicarlas manualmente en el entorno de tiempo de ejecución.

Los siguientes pasos explican cómo habilitar el nuevo editor en su entorno On-Premise.

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete **com.adobe.fmdita.config.ConfigManager**.

1. Habilite la configuración **Habilitar editor 2.0** (`enable.markup.editor`).

1. Seleccione **Guardar**.

