---
title: Configurar mensaje para guardar como nueva versión al cerrar
description: Obtenga información sobre cómo configurar el mensaje para guardar como una nueva versión al cerrar
exl-id: 1b8c3eaa-a654-4563-9541-18a59b7d306c
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/VdnwN--C-0kLd-vo5RDFLNXNBKzU7wofWZJsvPuVGAA
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
source-wordcount: 213
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

Para obtener más información, consulte la sección *Cerrar archivo y guardar escenarios* en la guía Usar Adobe Experience Manager Guides as a Cloud Service.

**Tema principal:**&#x200B;[&#x200B; Personalizar editor web](conf-web-editor.md)
