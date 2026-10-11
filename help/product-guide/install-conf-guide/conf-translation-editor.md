---
title: Configurar la función de traducción en el editor
description: Aprenda a configurar la función de traducción en el editor
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 22d7e1c7-2059-43fb-b7aa-3ae4a6072678
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
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
