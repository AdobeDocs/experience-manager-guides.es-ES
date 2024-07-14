---
title: Notas de versión | Adobe Experience Manager Guides as a Cloud Service, versión de abril de 2023
description: Lanzamiento de Adobe Experience Manager Guides as a Cloud Service en abril de 2023
exl-id: 269e3a13-584d-4cff-a18a-d4fa89646a5a
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# Novedades de la versión de abril de 2023 de Adobe Experience Manager Guides as a Cloud Service

Este artículo cubre las funciones nuevas y mejoradas de la versión de abril de 2023 de Adobe Experience Manager Guides (más adelante denominadas *AEM Guides as a Cloud Service*).

Para obtener más información sobre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en esta versión, consulte el artículo [Notas de la versión](release-notes-2023-4-0.md).

## Compatibilidad de metadatos avanzada en la publicación de PDF

AEM Guides ahora proporciona compatibilidad avanzada con los metadatos asignados a los metadatos en la salida del PDF. Las opciones de metadatos incluyen información sobre el documento y su contenido, como el nombre del autor, el título del documento, las palabras clave, la información de copyright y otros campos de datos.

<img src="assets/pdf-metadata.png" alt=" metadatos pdf nativos">

XMP Puede importar un archivo de y AEM Guides puede elegir la información del archivo. También tiene la opción de proporcionar los nombres y valores de los metadatos mediante la lista desplegable. También puede agregar metadatos personalizados escribiendo directamente en el campo de nombre.


## Panel de vista de esquema mejorada

AEM Guides proporciona un panel de vista de esquema mejorado en el que se obtiene la vista jerárquica de los elementos utilizados en el documento.

<img src="assets/select-element-content-outline-view_cs.png" alt=" metadatos pdf nativos">

La vista Esquema proporciona las siguientes mejoras:

* El menú desplegable Opciones de vista se muestra en la parte superior del panel Vista de esquema. Si un elemento tiene un ID, un atributo y un texto, puede seleccionarlos en la lista desplegable para mostrarlos junto con el elemento. Los atributos que se pueden mostrar en el panel Vista de esquema están determinados por la configuración de Atributos de visualización que ha configurado el administrador en **Configuración del editor**.

* Con la función de búsqueda, puede buscar un elemento por su nombre, ID, texto o valor de atributo.


## Publicación basada en microservicios para AEM Guides as a Cloud Service

AEM Guides as a Cloud Service proporciona la función para ejecutar grandes cargas de trabajo de publicación simultáneamente con publicaciones basadas en microservicios y aprovechar la plataforma sin servidor de Adobe I/O Runtime líder en el sector.

Ahora, en la versión de abril, puede ejecutar varias solicitudes de publicación simultáneamente y generar salidas de PDF masivas de forma muy eficaz mediante la publicación de PDF nativos basada en microservicios.
Para obtener más información, consulte [Configurar la nueva publicación basada en microservicios para AEM Guides as a Cloud Service](../knowledge-base/publishing/configure-microservices.md).
