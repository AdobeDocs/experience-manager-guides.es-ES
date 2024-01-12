---
title: Configurar el valor predeterminado para la vista de etiquetas
description: Obtenga información sobre cómo configurar el valor predeterminado para la vista de etiquetas
exl-id: 52214459-74b8-47ec-982b-6176145348a8
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Configurar el valor predeterminado para la vista de etiquetas {#id223GN0M0NDC}

AEM Las guías de usuario le permiten configurar el estado predeterminado de la vista Etiquetas en el Editor Web, lo que le ayuda a mantener la vista Etiquetas activada o desactivada de forma predeterminada en la sesión de un nuevo usuario. Realice los siguientes pasos para configurar el valor predeterminado de la vista Etiquetas:

1. Descargue el archivo de configuración de la interfaz de usuario iniciando sesión en Adobe Experience Manager como administrador.
1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.
1. Seleccionar **Guías** en la lista de herramientas y haga clic en **Perfiles de carpeta**.
1. Haga clic en **Perfil global** mosaico.
1. Seleccione el **Configuración del editor XML** y haga clic en la pestaña **Editar** en la parte superior.
1. En el **Configuración de IU del Editor XML** , haga clic en **Descargar** para descargar el `ui_config.json` en su sistema local.
1. En el `ui_config.json` , cambie el estado de vista de etiquetas predeterminado cambiando la sección defaultValues como se muestra a continuación:

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

**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
