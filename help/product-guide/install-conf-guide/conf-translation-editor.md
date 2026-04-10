---
title: Configuración de la función de traducción en el editor web
description: Obtenga información sobre cómo configurar la función de traducción en el editor web
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 0%

---

# Configuración de la función de traducción en el editor web de Cloud Service

El editor web proporciona una potente función de traducción para traducir el contenido a varios idiomas.

Puede usar la ficha **Administrar** del Editor web para traducir el contenido. Esta pestaña está disponible de forma predeterminada.

Para ocultar la ficha **Administrar** en el Editor web, realice los siguientes pasos:

1. Inicie sesión en **Adobe Experience Manager** como administrador.
1. Haz clic en el vínculo **Adobe Experience Manager** de la parte superior y elige **Herramientas**.
1. Seleccione **Guías** de la lista de herramientas y haga clic en **Perfiles de carpeta**.
1. Haga clic en el mosaico **Perfil global**.
1. Haga clic en **Configuración del editor XML**.
1. Haz clic en el icono **Editar** de la parte superior.
1. Descargar el archivo de `ui\_config.json`. Quite el siguiente fragmento de código del archivo descargado:

   ```json
   {
       "component":"tab",
       "id":"workflow",
       "title":"Manage",
       "on-click":"APP_MODE_CHANGE",
       "items":
       [
           {
               "component":"label",
               "label":"Manage"
           }
       ]
   },
   ```

1. Cargue el archivo ui\_config.json actualizado.

Tenga en cuenta que el filtro **Administrar** ya no está disponible.

**Tema principal:**[ Personalizar editor web](customize-overview.md)
