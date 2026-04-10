---
title: Configurar la ubicación de salida base para la salida de publicación para los servicios locales
description: Configurar la ubicación de salida base para la salida de publicación para los servicios locales
feature: Output Generation
role: Admin
level: Experienced
exl-id: ae1d805a-7b79-4b76-8be2-a19c5552530c
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 1%

---

# Configurar la ubicación de salida base para publicar la salida para los servicios locales

Realice los siguientes pasos para configurar la ubicación de salida base:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete *com.adobe.fmdita.config.ConfigManager*.

1. Actualice la propiedad **Base Output Location** para especificar la ruta predeterminada en el repositorio de AEM donde se guardará PDF después de la publicación. Además, si se introduce una ruta no válida, se revertirá automáticamente a la ruta predeterminada: /content/dam/fmdita-output.

1. Haga clic en **Guardar**.
