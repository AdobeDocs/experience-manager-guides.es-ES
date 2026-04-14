---
title: Configurar el guardado automático de archivos en el Editor web
description: Obtenga información sobre cómo configurar el guardado automático de archivos en el Editor Web
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 142a588a-3d26-48ee-a3fe-23882922243c
source-git-commit: 9c53ac725618db1164b0ed310a47b258a7224778
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 1%

---

# Configurar el guardado automático de archivos en el Editor web {#id199CC0J0M5Z}

Una de las funciones más comunes del editor basado en explorador es la capacidad de guardar datos después de un período de tiempo específico. El Editor web de AEM Guides también admite el guardado automático de archivos de tema y asignación en el intervalo de tiempo especificado. Cuando se activa esta función, se guarda la copia de trabajo del tema o del mapa. No se crea una nueva versión del tema o del mapa. Para crear una nueva versión, debe hacer clic en el icono Guardar revisión de la barra de herramientas del Editor Web.

La característica de guardado automático no está habilitada de manera predeterminada y debe habilitarla usando el archivo de configuración de Cloud Service y de `configMgr` para local

Las siguientes pestañas proporcionan instrucciones para habilitar la función de guardado automático en el Editor web en función de la configuración de Experience Manager Guides: Cloud Service o Local.

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
