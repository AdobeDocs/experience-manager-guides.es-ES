---
title: Configurar la solicitud para proteger un archivo al cerrar
description: Obtenga información sobre cómo configurar el mensaje para proteger un archivo al cerrar
exl-id: d184c97f-8405-4bcd-963d-635f17584897
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 1%

---

# Configurar la solicitud para proteger un archivo al cerrar {#id222HC040PE8}

Cuando el usuario intenta cerrar un archivo que se abre en el Editor Web utilizando **Cerrar** en la pestaña del archivo o en el **Cerrar** opción en el menú Opciones, aparece un cuadro de diálogo si el archivo tiene datos sin guardar o una versión sin guardar. Se solicitará al usuario que desbloquee el archivo si está bloqueado.

El **Desbloquear el archivo** La casilla de verificación no está activada de forma predeterminada y debe activarla desde configMgr. Realice los siguientes pasos para habilitar la opción de forma predeterminada en el Editor web:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** paquete.

1. Seleccione el **Pedir registro de entrada al cerrar** opción.

1. Haga clic en **Guardar**.


Cuando esta configuración está habilitada, la variable **Desbloquear el archivo** La casilla de verificación está seleccionada de forma predeterminada en el cuadro de diálogo.

Para obtener más información, consulte *Escenarios de archivo, cerrar y guardar* de la guía as a Cloud Service Uso de guías de Adobe Experience Manager.

**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
