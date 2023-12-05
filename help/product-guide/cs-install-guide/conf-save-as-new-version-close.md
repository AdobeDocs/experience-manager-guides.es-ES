---
title: Configurar mensaje para guardar como nueva versión al cerrar
description: Obtenga información sobre cómo configurar el mensaje para guardar como una nueva versión al cerrar
exl-id: 9029b671-8ff8-45eb-b27e-ab89bd09e7ed
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 1%

---

# Configurar mensaje para guardar como nueva versión al cerrar {#id222HBI00XXA}

Cuando el usuario intenta cerrar un archivo que se abre en el Editor Web utilizando **Cerrar** en la pestaña del archivo o en el **Cerrar** opción en el menú Opciones, aparece un cuadro de diálogo si el archivo tiene datos sin guardar o una versión sin guardar. Se solicitará al usuario que guarde el archivo como una nueva versión si la versión no está guardada.

Siga las instrucciones que se indican en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar una solicitud de que se guarde como una nueva versión al cerrar:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.savenewversion` | Boolean \( true/ false\). <br>  **Valor predeterminado**: true |

Cuando esta configuración está habilitada, la variable **Guardar como nueva versión** La casilla de verificación está seleccionada de forma predeterminada en el cuadro de diálogo.

Para obtener más información, consulte *Escenarios de archivo, cerrar y guardar* de la guía as a Cloud Service Uso de guías de Adobe Experience Manager.

**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
