---
title: Configurar la ubicación de salida base para la salida de publicación para los servicios locales
description: Configurar la ubicación de salida base para la salida de publicación para los servicios locales
feature: Output Generation
role: Admin
level: Experienced
exl-id: ae1d805a-7b79-4b76-8be2-a19c5552530c
TQID: https://experienceleague.adobe.com/qf1UZh14gvlc7ZHUUBaDlHe1U3zDvzGlGjYavYKITWY
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: d6596f3f-92a7-43ec-b444-237db6adad05id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 112
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
