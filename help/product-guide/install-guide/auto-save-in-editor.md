---
title: Configurar el guardado automático de archivos en el Editor web
description: Obtenga información sobre cómo configurar el guardado automático de archivos en el Editor Web
exl-id: 23fe404c-c76d-43ba-9b28-c49ab1e524de
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/-VGsv3zHE6oACLVpnYm24-rX9-H6uUGyz3SEsP2ILBE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 204
ht-degree: 0%

---

# Configurar el guardado automático de archivos en el Editor web {#id199CC0J0M5Z}

Una de las funciones más comunes del editor basado en explorador es la capacidad de guardar datos después de un período de tiempo específico. El editor web de AEM Guides también admite el guardado automático de archivos de temas y mapas en el intervalo de tiempo especificado. Cuando se activa esta función, se guarda la copia de trabajo del tema o del mapa. No se crea una nueva versión del tema o del mapa. Para crear una nueva versión, debe hacer clic en el icono Guardar revisión de la barra de herramientas del Editor Web.

La función de guardado automático no está activada de forma predeterminada y debe activarla desde configMgr. Realice los siguientes pasos para habilitar la función de guardado automático en el editor web:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. En la configuración de *XmlEditorConfig*, seleccione la opción **Guardar automáticamente**.

1. En el campo **Intervalo de guardado automático**, especifique el intervalo de tiempo en segundos para almacenar en déclencheur la característica de guardado automático.

1. Haga clic en **Guardar**.


**Tema principal:**&#x200B;[&#x200B; Personalizar editor web](conf-web-editor.md)
