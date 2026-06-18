---
title: Configurar el valor predeterminado para la vista de etiquetas
description: Obtenga información sobre cómo configurar el valor predeterminado para la vista de etiquetas
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: d54e3a3c-9f61-43cf-a925-12e4ce948a55
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 0%

---

# Configurar el valor predeterminado para la vista de etiquetas {#id223GN0M0NDC}

AEM Guides le permite configurar el estado predeterminado de la Vista de etiquetas en el Editor, lo que le ayuda a mantener activada o desactivada la Vista de etiquetas de forma predeterminada en la sesión de un nuevo usuario.Siga estos pasos para configurar el valor predeterminado de la Vista de etiquetas:

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
> La preferencia del usuario en el Editor para habilitar/deshabilitar la Vista de etiquetas tiene prioridad sobre este valor predeterminado. Por lo tanto, si un usuario habilita la Vista de etiquetas desde el Editor, permanecerá habilitada incluso en todas las sesiones.

**Tema principal:**&#x200B;[&#x200B; Editor personalizado](customize-overview.md)
