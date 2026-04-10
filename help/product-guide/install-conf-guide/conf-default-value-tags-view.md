---
title: Configurar el valor predeterminado para la vista de etiquetas
description: Obtenga información sobre cómo configurar el valor predeterminado para la vista de etiquetas
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Configurar el valor predeterminado para la vista de etiquetas {#id223GN0M0NDC}

AEM Guides le permite configurar el estado predeterminado de la vista Etiquetas en el Editor Web, lo que le ayuda a mantener activada o desactivada la vista Etiquetas de forma predeterminada en la sesión de un nuevo usuario. Realice los siguientes pasos para configurar el valor predeterminado de la vista Etiquetas:

1. Descargue el archivo de configuración de la interfaz de usuario iniciando sesión en Adobe Experience Manager como administrador.
1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.
1. Seleccione **Guías** de la lista de herramientas y haga clic en **Perfiles de carpeta**.
1. Haga clic en el mosaico **Perfil global**.
1. Seleccione la ficha **Configuración del editor XML** y haga clic en el icono **Editar** de la parte superior.
1. En la sección **Configuración de la interfaz de usuario del editor XML**, haga clic en el icono **Descargar** para descargar el archivo `ui_config.json` en su sistema local.
1. En el archivo `ui_config.json`, cambie el estado de vista de etiquetas predeterminado cambiando la sección defaultValues como se muestra a continuación:

   ```
   "defaultValues":
               {
               "tagsView": true
               }
   ```

1. Guarde el archivo y cárguelo.

>[!NOTE]
>
> La preferencia del usuario en el Editor Web para habilitar/deshabilitar la Vista de etiquetas tiene prioridad sobre este valor predeterminado. Por lo tanto, si un usuario habilita la Vista de etiquetas desde el Editor web, permanecerá habilitada incluso en todas las sesiones.

**Tema principal:**[ Personalizar editor web](customize-overview.md)
