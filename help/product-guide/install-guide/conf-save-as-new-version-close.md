---
title: Configurar mensaje para guardar como nueva versión al cerrar
description: Obtenga información sobre cómo configurar el mensaje para guardar como una nueva versión al cerrar
exl-id: 1b8c3eaa-a654-4563-9541-18a59b7d306c
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Configurar mensaje para guardar como nueva versión al cerrar {#id222HBI00XXA}

Cuando el usuario intenta cerrar un archivo que se abre en el Editor Web utilizando **Cerrar** en la pestaña del archivo o en el **Cerrar** opción en el menú Opciones, aparece un cuadro de diálogo si el archivo tiene datos sin guardar o una versión sin guardar. Se solicitará al usuario que guarde el archivo como una nueva versión si la versión no está guardada.

El **Guardar como nueva versión** La casilla de verificación no está activada de forma predeterminada y debe activarla desde configMgr. Realice los siguientes pasos para habilitar la opción de forma predeterminada en el Editor web:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** paquete.

1. Seleccione el **Pedir una nueva versión al cerrar** opción.

1. Haga clic en **Guardar**.


Cuando se selecciona esta opción, la variable **Guardar como nueva versión** La casilla de verificación está seleccionada de forma predeterminada en el cuadro de diálogo.

Para obtener más información, consulte *Escenarios de archivo, cerrar y guardar* de la guía as a Cloud Service Uso de guías de Adobe Experience Manager.

**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
