---
title: Configurar el guardado automático de archivos en el Editor web
description: Obtenga información sobre cómo configurar el guardado automático de archivos en el Editor Web
exl-id: 23fe404c-c76d-43ba-9b28-c49ab1e524de
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 1%

---

# Configurar el guardado automático de archivos en el Editor web {#id199CC0J0M5Z}

Una de las funciones más comunes del editor basado en explorador es la capacidad de guardar datos después de un período de tiempo específico. AEM El Editor web de las guías de la aplicación también admite el guardado automático de archivos de temas y mapas en el intervalo de tiempo especificado. Cuando se activa esta función, se guarda la copia de trabajo del tema o del mapa. No se crea una nueva versión del tema o del mapa. Para crear una nueva versión, debe hacer clic en el icono Guardar revisión de la barra de herramientas del Editor Web.

La función de guardado automático no está activada de forma predeterminada y debe activarla desde configMgr. Realice los siguientes pasos para habilitar la función de guardado automático en el editor web:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** paquete.

1. En el *XmlEditorConfig* configuración, seleccione la **Guardar automáticamente** opción.

1. En el **Intervalo de guardado automático** , especifique el intervalo de tiempo en segundos para almacenar en déclencheur la función de guardado automático.

1. Haga clic en **Guardar**.


**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
