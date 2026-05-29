---
title: Configurar la inicialización de la copia de destino en el flujo de trabajo de traducción para local
description: Obtenga información sobre cómo habilitar o deshabilitar la inicialización de la copia de destino en el flujo de trabajo de traducción para in situ
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 1%

---

# Configurar la inicialización de la copia de destino en el flujo de trabajo de traducción para local

Los siguientes pasos explican cómo habilitar la inicialización de la copia de destino en el flujo de trabajo de traducción para su entorno local.

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete **com.adobe.fmdita.config.ConfigManager**.

1. Habilite o deshabilite la opción **Inicializar copia de idioma de destino con contenido de origen** ( translation.workflow.propagate.source.content) según sus necesidades. Esta configuración solo es aplicable cuando el flujo de trabajo de traducción heredada está deshabilitado.

1. Seleccione **Guardar**.
