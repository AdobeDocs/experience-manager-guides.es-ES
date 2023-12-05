---
title: Notas de versión | Novedades de la versión 4.2.1 de las guías de Adobe Experience Manager
description: Conozca las funciones nuevas y mejoradas de las versiones 4.2.1 de las guías de Adobe Experience Manager
exl-id: 441aa7ec-d88c-42cb-83f0-d0f6e58bfa41
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 0%

---

# Novedades de la versión 4.2.1 de las guías de Adobe Experience Manager (mayo de 2023)

Este artículo cubre las funciones nuevas y mejoradas de la versión 4.2.1 de las guías de Adobe Experience Manager (más adelante denominadas *AEM Guías de*).

Para obtener más información sobre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en esta versión, consulte la [Notas de versión](release-notes-4.2.1.md) artículo.

## AEM Vaya del Editor Web a la página principal de la

AEM Ahora puede navegar fácilmente desde el Editor Web a la página Navegación de la.

![](assets/web-editor-launch-page.png){width="800" align="left"}

* Haga clic en **Guías** icono (![](assets/aem-guides-icon.png) AEM ), para volver a la página Navegación de la.


Para obtener más información, consulte [AEM Página de navegación de](../user-guide/web-editor-launch-editor.md#id2056BG00RZJ).

## Compatibilidad de metadatos avanzada en la publicación de PDF

AEM Guías de ahora proporciona soporte avanzado para los metadatos asignados a los metadatos en la salida del PDF. Las opciones de metadatos incluyen información sobre el documento y su contenido, como el nombre del autor, el título del documento, las palabras clave, la información de copyright y otros campos de datos.

<img src="assets/pdf-metadata.png" alt=" metadatos pdf nativos">

XMP AEM Puede importar un archivo de y las guías de usuario pueden seleccionar la información del archivo. También tiene la opción de proporcionar los nombres y valores de los metadatos mediante la lista desplegable. También puede agregar metadatos personalizados escribiendo directamente en el campo de nombre.

Para obtener más información, consulte **Metadatos** descripción de funciones en [Crear un ajuste preestablecido de salida de PDF](../web-editor/native-pdf-web-editor.md).

### Panel de vista de esquema mejorada

AEM Guías proporciona un panel de vista de esquema mejorado en el que se obtiene la vista jerárquica de los elementos utilizados en el documento.

<img src="assets/select-element-content-outline-view_cs.png" alt=" metadatos pdf nativos">

La vista Esquema proporciona las siguientes mejoras:

* El menú desplegable Opciones de vista se muestra en la parte superior del panel Vista de esquema. Si un elemento tiene un ID, un atributo y un texto, puede seleccionarlos en la lista desplegable para mostrarlos junto con el elemento. Los atributos que se pueden mostrar en el panel Vista de esquema están determinados por la configuración de Atributos de visualización que ha configurado el administrador en el **Configuración del editor**.

* Con la función de búsqueda, puede buscar un elemento por su nombre, ID, texto o valor de atributo.

Para obtener más información, consulte la descripción de la función Vista de esquema en la [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS) sección.

## Generar el informe Multimedia desde el editor web

AEM Guías de proporciona la función para generar los informes de los documentos técnicos.  Puede utilizar esta función para ver la lista de temas y administrar los metadatos de sus documentos. Ahora también puede ver el contenido multimedia utilizado en todas las referencias para el mapa actual desde el **Informes** en el Editor Web.

Puede generar el informe multimedia que contiene información detallada sobre el contenido multimedia utilizado en sus referencias dentro del mapa actual. Tiene la flexibilidad de filtrar y ordenar los archivos multimedia enumerados en el informe.
También puede generar el CSV para descargar la instantánea actual de los elementos multimedia utilizados en el mapa DITA.

<img src="assets/web-editor-reports-multimedia.png" alt="informe multimedia" width="600">

Para obtener más información, consulte la descripción de la función Generar un informe multimedia en la [Informe de mapa DITA del editor web](../user-guide/reports-web-editor.md) sección.

## PDF nativo | Barra de cambios para indicar los temas modificados en la Tabla de contenido

Ahora, las guías del PDF le permiten identificar rápidamente los temas modificados en la tabla de contenido de la salida del AEM.  Muestra una barra de cambios a la izquierda de los temas modificados en el índice. Puede hacer clic en el tema del índice y ver los cambios detallados.

<img src="assets/change-marker-toc.png" alt="Cambiar marcador en TDC " width="500">

Para obtener más información, consulte [Trabajar con estilos de barras de cambios personalizados](../native-pdf/change-bar-style.md).



## PDF nativo | Aplicar estilo al marcador de página en el componente de nota al pie

Ahora puede aplicar estilo al marcador de página en las notas al pie. Por ejemplo, puede agregar corchetes o cambiar su color. Estos estilos ayudan a los usuarios a identificar fácilmente los marcadores de página del documento.

Para obtener más información, consulte [Usar estilos personalizados en las notas al pie](../native-pdf/footnote-number-style.md).

## Abra y reproduzca archivos de vídeo o audio en el Editor web

AEM Guías de la aplicación ahora proporciona la función para abrir y reproducir los archivos de audio o vídeo en el Editor Web. Puede cambiar el volumen o la vista del vídeo. En el menú contextual, también tiene las opciones para **Descargar**, cambiar **Velocidad de reproducción**, o vista **Imagen en imagen**.

<img src="assets/video-web-editor.png" alt="reproducir vídeo" width="600">

Para obtener más información, consulte la descripción de la función Vista de repositorio en la [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS) sección.
