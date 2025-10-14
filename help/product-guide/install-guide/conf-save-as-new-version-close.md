---
title: Configurar mensaje para guardar como nueva versión al cerrar
description: Obtenga información sobre cómo configurar el mensaje para guardar como una nueva versión al cerrar
exl-id: 1b8c3eaa-a654-4563-9541-18a59b7d306c
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Configurar mensaje para guardar como nueva versión al cerrar {#id222HBI00XXA}

Cuando el usuario intenta cerrar un archivo que está abierto en el Editor Web con el botón **Cerrar** de la ficha del archivo o con la opción **Cerrar** del menú Opciones, aparece un cuadro de diálogo si el archivo tiene datos sin guardar o una versión sin guardar. Se solicitará al usuario que guarde el archivo como una nueva versión si la versión no está guardada.

La casilla de verificación **Guardar como nueva versión** no está habilitada de forma predeterminada y debe habilitarla desde configMgr. Realice los siguientes pasos para habilitar la opción de forma predeterminada en el Editor web:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Seleccione la opción **Pedir nueva versión al cerrar**.

1. Haga clic en **Guardar**.


Cuando se selecciona esta opción, la casilla de verificación **Guardar como nueva versión** está seleccionada de forma predeterminada en el cuadro de diálogo.

Para obtener más información, consulte la sección *Cerrar archivo y guardar escenarios* en la guía as a Cloud Service sobre el uso de Adobe Experience Manager Guides.

**Tema principal:**&#x200B;[&#x200B; Personalizar editor web](conf-web-editor.md)
