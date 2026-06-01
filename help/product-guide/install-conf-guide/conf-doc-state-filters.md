---
title: Configurar filtros de estado del documento
description: Obtenga información sobre cómo configurar los filtros de estado del documento
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 6dee8479-770f-48d7-9939-5035388d16d8
source-git-commit: 4d8a6cd1e683af7ac3496464a2e0ed930eb9e8fc
workflow-type: tm+mt
source-wordcount: '208'
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

**Tema principal:**&#x200B;[&#x200B; Personalizar editor web](customize-overview.md)
