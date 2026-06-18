---
title: Configurar la solicitud para proteger un archivo al cerrar
description: Obtenga información sobre cómo configurar el mensaje para proteger un archivo al cerrar
exl-id: d184c97f-8405-4bcd-963d-635f17584897
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/mK01xE-ysqIXm9YL5xkvp1dz1-3hGr63kvt-cePEHSA
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 196
ht-degree: 1%

---

# Configurar la solicitud para proteger un archivo al cerrar {#id222HC040PE8}

Cuando el usuario intenta cerrar un archivo que está abierto en el Editor con el botón **Cerrar** de la ficha del archivo o con la opción **Cerrar** del menú Opciones, aparece un cuadro de diálogo si el archivo tiene datos sin guardar o una versión sin guardar. Se solicitará al usuario que desbloquee el archivo si está bloqueado.

La casilla de verificación **Desbloquear el archivo** no está habilitada de manera predeterminada y debe habilitarla desde configMgr. Realice los siguientes pasos para habilitar la opción de forma predeterminada en el Editor:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Seleccione la opción **Pedir protección al cerrar**.

1. Haga clic en **Guardar**.


Cuando esta configuración está habilitada, la casilla de verificación **Desbloquear el archivo** está seleccionada de forma predeterminada en el cuadro de diálogo.

Para obtener más información, consulte la sección *Cerrar archivo y guardar escenarios* en la guía Usar Adobe Experience Manager Guides as a Cloud Service.

**Tema principal:**[ Editor personalizado](conf-web-editor.md)
