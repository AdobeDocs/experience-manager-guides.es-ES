---
title: Configurar filtros de estado del documento
description: Obtenga información sobre cómo configurar los filtros de estado del documento
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 4942b914ff278ebcf09d00da32d6f9c7cc4d7ff9
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 0%

---

# Configurar filtros de estado del documento

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

       &quot;
       &quot;repositoryFilters&quot;: &lbrack;
       &lbrace;
       &quot;title&quot;: &quot;Estado del documento&quot;,
       &quot;property&quot;: &quot;jcr:content/metadata/docstate&quot;,
       &quot;hijos&quot;: &lbrack;
       &lbrace;
       &quot;título&quot;: &quot;Borrador&quot;,
       &quot;value&quot;: &quot;Borrador&quot;
       ,
       &lbrace;
       &quot;título&quot;: &quot;Editar&quot;,
       &quot;valor&quot;: &quot;Editar&quot;
       ,
       &lbrace;
       &quot;título&quot;: &quot;En revisión&quot;,
       &quot;valor&quot;: &quot;En revisión&quot;
       ,
       &lbrace;
       &quot;title&quot;: &quot;Approved&quot;,
       &quot;valor&quot;: &quot;Aprobado&quot;
       ,
       &lbrace;
       &quot;título&quot;: &quot;Revisado&quot;,
       &quot;valor&quot;: &quot;Revisado&quot;
       ,
       &lbrace;
       &quot;título&quot;: &quot;Listo&quot;,
       &quot;valor&quot;: &quot;Listo&quot;
       
       &rbrack;
       
       &rbrack;
       &quot;
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

**Tema principal:**&#x200B;[&#x200B; Personalizar editor web](conf-web-editor.md)
