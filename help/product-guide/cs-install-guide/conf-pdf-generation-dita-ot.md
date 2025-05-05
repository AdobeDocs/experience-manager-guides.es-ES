---
title: Configuración de la generación de PDF de tema único
description: Obtenga información sobre cómo configurar la generación de PDF de un solo tema
exl-id: 5b66fd3b-6450-49ce-b06e-d2d5bab37990
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Configuración de la generación de PDF de tema único {#id22ADC70M0XA}

Con AEM Guides, puede generar el PDF de temas individuales o un archivo de mapa completo. Los temas se pueden publicar en formato de PDF utilizando el PDF nativo o el método DITA-OT. Utilice el método de PDF nativo para generar una salida de PDF con numerosas funciones basada en los estándares de medios paginados CSS3 y CSS del W3C. Se puede utilizar el método DITA-OT para generar una salida de PDF para un mapa desde el tablero de mapas.

>[!NOTE]
>
> El PDF nativo es el método predeterminado para generar un PDF en la versión actual de AEM Guides.

Para activar la generación del PDF antiguo mediante DITA-OT desde el modo de vista previa del tema, realice los pasos siguientes:

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

Después de realizar los pasos dados anteriormente, si elige el mismo perfil de carpeta de Preferencias de usuario en el Editor Web, verá la opción de generación de PDF en el modo de vista previa de un tema.

**Tema principal:**&#x200B;[ Personalizar editor web](conf-web-editor.md)
