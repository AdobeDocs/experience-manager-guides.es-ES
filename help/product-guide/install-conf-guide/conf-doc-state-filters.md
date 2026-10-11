---
title: Configurar filtros de estado del documento
description: Obtenga información sobre cómo configurar los filtros de estado del documento
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 6dee8479-770f-48d7-9939-5035388d16d8
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
source-wordcount: '218'
ht-degree: 0%
---
# Configuración de filtros de estado de documento para Cloud Service

Adobe Experience Manager Guides proporciona la función para buscar un archivo en función de su estado de documento actual. Puede utilizar el filtro de búsqueda para buscar archivos desde la interfaz del repositorio y examinar los archivos.

Realice los siguientes pasos para configurar los filtros de estado del documento:

1. Inicie sesión en Adobe Experience Manager como administrador.
1. Seleccione el enlace de Adobe Experience Manager en la parte superior y elija **Herramientas**.
1. Seleccione **Guías** de la lista de herramientas y luego seleccione **Perfiles de carpeta**.
1. Abra el mosaico **Perfil global**. También puede seleccionar un mosaico de perfil de carpeta específico si desea que estos cambios se apliquen únicamente a esa carpeta en lugar de globalmente.
1. Vaya a **Configuración del editor XML**.
1. Seleccione el icono **Editar** de la parte superior.
1. Seleccione el icono **Descargar** para descargar el archivo `ui\_config.json` en su sistema local.
En el archivo `ui\_config.json` descargado, consulte la siguiente sección:

   ```
   "repositoryFilters": [
       {
       "title": "Document state",
       "property": "jcr:content/metadata/docstate",
       "children": [
           {
           "title": "Draft",
           "value": "Draft"
           },
           {
           "title": "Edit",
           "value": "Edit"
           },
           {
           "title": "In-Review",
           "value": "In-Review"
           },
           {
           "title": "Approved",
           "value": "Approved"
           },
           {
           "title": "Reviewed",
           "value": "Reviewed"
           },
           {
           "title": "Done",
           "value": "Done"
           }
       ]
       }
   ]
   ```

   Este fragmento representa los filtros de estado de documento predeterminados disponibles en Experience Manager Guides.

1. Puede personalizar los valores de filtro en función del flujo de trabajo de su organización. Por ejemplo, para agregar un estado de documento personalizado **Pendiente**, inserte la siguiente entrada en `children`:

   ```
   {
       "title": "Pending",
       "value": "Pending"
   }
   ```

1. Una vez actualizado, guarde el archivo y cárguelo.

Los filtros configurados se muestran en el panel **Filtros** del Repositorio en la página de inicio.

**Tema principal:**&#x200B;[&#x200B; Editor personalizado](customize-overview.md)
