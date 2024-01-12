---
title: Configurar el guardado automático de archivos en el Editor web
description: Obtenga información sobre cómo configurar el guardado automático de archivos en el Editor Web
exl-id: 4d99c3d8-cf6a-4cf3-aaec-9009a0376c1e
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 1%

---

# Configurar el guardado automático de archivos en el Editor web {#id199CC0J0M5Z}

Una de las funciones más comunes del editor basado en explorador es la capacidad de guardar datos después de un período de tiempo específico. AEM El Editor web de guías de recursos también admite el guardado automático de archivos de temas y mapas en el intervalo de tiempo especificado. Cuando se activa esta función, se guarda la copia de trabajo del tema o del mapa. No se crea una nueva versión del tema o del mapa. Para crear una nueva versión, debe hacer clic en el icono Guardar revisión de la barra de herramientas del Editor Web.

La función de guardado automático no está activada de forma predeterminada y debe habilitarla mediante el archivo de configuración.

Siga las instrucciones que se indican en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar el intervalo de tiempo de guardado automático y guardado automático del archivo:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.autosave` | Boolean \(true/false\).<br> **Valor predeterminado**: false |
| `xmleditor.autosaveinterval` | Especifique el intervalo de tiempo en segundos para almacenar en déclencheur la función de guardado automático. |

**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
