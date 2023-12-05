---
title: Configurar título para los iconos Proteger y Desproteger
description: Obtenga información sobre cómo configurar el título de los iconos Proteger y Desproteger
exl-id: a8888a17-e819-4fa2-bb6f-cafe1002803a
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---

# Configurar el título de los iconos Proteger y Desproteger

AEM Guías de la aplicación le permite configurar el título para los iconos Proteger y Desproteger en el Editor Web. Siga estos pasos para configurar el título de los iconos Proteger y Desproteger:

1. Descargue el archivo de configuración de la interfaz de usuario iniciando sesión en Adobe Experience Manager como administrador.
1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.
1. Seleccionar **Guías** en la lista de herramientas y haga clic en **Perfiles de carpeta**.
1. Haga clic en **Perfil global** mosaico.
1. Seleccione el **Configuración del editor XML** y haga clic en la pestaña **Editar** en la parte superior.
1. En el **Configuración de IU del Editor XML** , haga clic en **Descargar** para descargar el `ui_config.json` en su sistema local.
1. En el `ui_config.json` , cambie el título en la sección &quot;barra superior&quot;. Puede cambiar los siguientes valores:

   ```json
   //Change title to "Check out" instead of "Lock"
           "title": "Check out"
   
   //Change title to "Check in" instead of "@checkOutBy
            "title": "Check in"
   ```

1. Guarde el archivo y cárguelo.
