---
title: Configurar la ubicación de salida base para la salida de publicación para los servicios locales
description: Configurar la ubicación de salida base para la salida de publicación para los servicios locales
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: ab6f1f09de2ef758d7f05ba0a49194ac9f387dea
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


