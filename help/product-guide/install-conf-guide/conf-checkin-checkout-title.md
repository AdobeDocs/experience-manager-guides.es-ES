---
title: Configurar título para los iconos Proteger y Desproteger
description: Obtenga información sobre cómo configurar el título de los iconos Proteger y Desproteger
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 3032b49e-73d1-44d0-88b4-7e6e9444cac6
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---

# Configure el título de los iconos Proteger y Desproteger para Local

AEM Guides permite configurar el título de los iconos Proteger y Desproteger en el Editor. Siga estos pasos para configurar el título de los iconos Proteger y Desproteger:

1. Descargue el archivo de configuración de la interfaz de usuario iniciando sesión en Adobe Experience Manager como administrador.
1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.
1. Seleccione **Guías** de la lista de herramientas y haga clic en **Perfiles de carpeta**.
1. Haga clic en el mosaico **Perfil global**.
1. Seleccione la ficha **Configuración del editor XML** y haga clic en el icono **Editar** de la parte superior.
1. En la sección **Configuración de la interfaz de usuario del editor XML**, haga clic en el icono **Descargar** para descargar el archivo `ui_config.json` en su sistema local.
1. En el archivo `ui_config.json`, cambie el título en la sección &quot;barra superior&quot;. Puede cambiar los siguientes valores:

   ```json
   //Change title to "Check out" instead of "Lock"
           "title": "Check out"
   
   //Change title to "Check in" instead of "@checkOutBy
            "title": "Check in"
   ```

1. Guarde el archivo y cárguelo.
