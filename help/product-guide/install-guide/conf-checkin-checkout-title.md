---
title: Configurar título para los iconos Proteger y Desproteger
description: Obtenga información sobre cómo configurar el título de los iconos Proteger y Desproteger
exl-id: a8888a17-e819-4fa2-bb6f-cafe1002803a
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/NytwQkk18-M0MpxxBP3OWg3WFJf6Oy3N5dBaiKlc6Gg
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9baid: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 165
ht-degree: 0%

---

# Configurar el título de los iconos Proteger y Desproteger

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
