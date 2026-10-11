---
title: Configurar el guardado automático de archivos en el Editor
description: Obtenga información sobre cómo configurar el guardado automático de archivos en el Editor
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 142a588a-3d26-48ee-a3fe-23882922243c
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 1%
---
# Configurar el guardado automático de archivos en el Editor {#id199CC0J0M5Z}

Una de las funciones más comunes del editor basado en explorador es la capacidad de guardar datos después de un período de tiempo específico. El Editor de AEM Guides también admite el guardado automático de archivos de tema y asignación en el intervalo de tiempo especificado. Cuando se activa esta función, se guarda la copia de trabajo del tema o del mapa. No se crea una nueva versión del tema o del mapa. Para crear una nueva versión, debe hacer clic en el icono Guardar revisión de la barra de herramientas del editor.

La característica de guardado automático no está habilitada de manera predeterminada y debe habilitarla usando el archivo de configuración de Cloud Service y de `configMgr` para local

Las siguientes pestañas proporcionan instrucciones para habilitar la función de guardado automático en el Editor en función de la configuración de Experience Manager Guides: Cloud Service o Local.

>[!BEGINTABS]

>[!TAB Cloud Service]

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar el intervalo de tiempo de guardado automático y guardado automático del archivo:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.autosave` | Booleano \(true/false\).<br> **Valor predeterminado**: false |
| `xmleditor.autosaveinterval` | Especifique el intervalo de tiempo en segundos para almacenar en déclencheur la función de guardado automático. |  |

>[!TAB Local]

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. En la configuración de *XmlEditorConfig*, seleccione la opción **Guardar automáticamente**.

1. En el campo **Intervalo de guardado automático**, especifique el intervalo de tiempo en segundos para almacenar en déclencheur la característica de guardado automático.

1. Haga clic en **Guardar**.

>[!ENDTABS]
