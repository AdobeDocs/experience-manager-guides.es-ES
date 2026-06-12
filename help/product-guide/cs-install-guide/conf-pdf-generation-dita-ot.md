---
title: Configuración de la generación de PDF de tema único
description: Obtenga información sobre cómo configurar la generación de PDF de un solo tema
exl-id: 5b66fd3b-6450-49ce-b06e-d2d5bab37990
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/DinL1ZwovhmP61iQOQkW6XR-ALahlONxOU4e5UXpSGY
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9baid: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 271
ht-degree: 0%

---

# Configuración de la generación de PDF de tema único {#id22ADC70M0XA}

Con AEM Guides, puede generar el PDF de temas individuales o un archivo de mapa completo. Puede publicar los temas en formato PDF utilizando PDF nativo o el método DITA-OT. Utilice el método nativo de PDF para generar una salida de PDF con numerosas funciones basadas en los estándares de medios paginados CSS3 y CSS del W3C. Se puede utilizar el método DITA-OT para generar una salida de PDF para un mapa desde el tablero de mapas.

>[!NOTE]
>
> PDF nativo es el método predeterminado para generar un PDF en la versión actual de AEM Guides.

Para activar la generación antigua de PDF mediante DITA-OT desde el modo de vista previa del tema, realice los siguientes pasos:

1. Inicie sesión en Adobe Experience Manager como administrador y descargue el archivo de configuración de la interfaz de usuario.

1. Para ello, haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.
1. Seleccione **Guías** de la lista de herramientas y haga clic en **Perfiles de carpeta**.
1. Haga clic en el mosaico **Perfil global**.
1. Seleccione la ficha **Configuración del editor XML** y haga clic en el icono **Editar** de la parte superior
1. Haga clic en el icono **Descargar** para descargar el archivo ui\_config.json en su sistema local. A continuación, puede realizar cambios en el archivo y luego cargarlo.
1. En el archivo `ui_config.json`, busque la siguiente configuración:

   ```
   {
                           "component": "button",
                           "variant": "action",
                           "quiet": true,
                           "icon": "filePDF",
                           "title": "Download as PDF",
                           "on-click": "EDITOR_SAVE_AS_PDF"
                           }
   ```

   y reemplácelo por

   ```
   {
                           "component": "button",
                           "icon": "filePDF",
                           "variant": "action",
                           "quiet": true, "title": "Export as PDF",
                           "on-click": "DOWNLOAD_TOPIC_PDF",
                           "show" : ["@isPreviewMode", "@isXmlMode"]
                           }
   ```

1. Guarde el archivo y cárguelo.

Después de realizar los pasos anteriores, si elige el mismo perfil de carpeta en Preferencias de usuario en el Editor web, verá la opción de generación de PDF en el modo de vista previa de un tema.

**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
