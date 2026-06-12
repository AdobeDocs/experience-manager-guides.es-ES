---
title: Configurar el valor predeterminado para la vista de etiquetas
description: Obtenga información sobre cómo configurar el valor predeterminado para la vista de etiquetas
exl-id: 52214459-74b8-47ec-982b-6176145348a8
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/5Dh86YzZVL8vKnHpDPLNijpDxISnpbgkcfCIbUNxZTo
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 214
ht-degree: 0%

---

# Configurar el valor predeterminado para la vista de etiquetas {#id223GN0M0NDC}

AEM Guides le permite configurar el estado predeterminado de la vista Etiquetas en el Editor Web, lo que le ayuda a mantener activada o desactivada la vista Etiquetas de forma predeterminada en la sesión de un nuevo usuario.Siga estos pasos para configurar el valor predeterminado de la Vista de etiquetas:

1. Descargue el archivo de configuración de la interfaz de usuario iniciando sesión en Adobe Experience Manager como administrador.
1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.
1. Seleccione **Guías** de la lista de herramientas y haga clic en **Perfiles de carpeta**.
1. Haga clic en el mosaico **Perfil global**.
1. Seleccione la ficha **Configuración del editor XML** y haga clic en el icono **Editar** de la parte superior.
1. En la sección **Configuración de la interfaz de usuario del editor XML**, haga clic en el icono **Descargar** para descargar el archivo `ui_config.json` en su sistema local.
1. En el archivo `ui_config.json`, cambie el estado de vista de etiquetas predeterminado cambiando la sección defaultValues como se muestra a continuación:

   ```json
   "defaultValues":
                   {
                   "tagsView": true
                   }
   ```

1. Guarde el archivo y cárguelo.

>[!NOTE]
>
> La preferencia del usuario en el Editor Web para habilitar/deshabilitar la Vista de etiquetas tiene prioridad sobre este valor predeterminado. Por lo tanto, si un usuario habilita la Vista de etiquetas desde el Editor web, permanecerá habilitada incluso en todas las sesiones.

**Tema principal:**&#x200B;[&#x200B; Personalizar editor web](conf-web-editor.md)
