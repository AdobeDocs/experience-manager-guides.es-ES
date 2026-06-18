---
title: Configurar la función de traducción en el editor
description: Aprenda a configurar la función de traducción en el editor
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 22d7e1c7-2059-43fb-b7aa-3ae4a6072678
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 0%

---

# Configuración de la función de traducción en el Editor para Cloud Service

El editor proporciona una potente función de traducción para traducir el contenido a varios idiomas.

Puede usar la pestaña **Administrar** del Editor para traducir el contenido. Esta pestaña está disponible de forma predeterminada.

Para ocultar la ficha **Administrar** en el Editor, realice los siguientes pasos:

1. Inicie sesión en **Adobe Experience Manager** como administrador.
1. Haz clic en el vínculo **Adobe Experience Manager** de la parte superior y elige **Herramientas**.
1. Seleccione **Guías** de la lista de herramientas y haga clic en **Perfiles de carpeta**.
1. Haga clic en el mosaico **Perfil global**.
1. Haga clic en **Configuración del editor XML**.
1. Haz clic en el icono **Editar** de la parte superior.
1. Descargar el archivo de `ui\_config.json`.Elimine el siguiente fragmento de código del archivo descargado:

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

**Tema principal:**[ Editor personalizado](customize-overview.md)
