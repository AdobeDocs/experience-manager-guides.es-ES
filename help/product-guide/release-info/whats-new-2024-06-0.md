---
title: Notas de versión | Novedades de la versión 2024.06.0 de las guías de Adobe Experience Manager
description: Conozca las funciones nuevas y mejoradas de la versión 2024.06.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: cf60d11f483fdd663bd5decccb63f8ed7d6fff51
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 2%

---

# Novedades de la versión 2024.06.0

Este artículo cubre las nuevas y mejoradas funciones de la versión 2024.06.0 de las guías de Adobe Experience Manager.

Para ver la lista de problemas corregidos en esta versión, consulte [Problemas solucionados en la versión 2024.06.0](fixed-issues-2024-06-0.md).

Más información [instrucciones de actualización para la versión 2024.06.0](upgrade-instructions-2024-06-0.md).


## Publicación de un tema o sus elementos en un fragmento de experiencia

Un fragmento de experiencia es una unidad de contenido modular dentro de Adobe Experience Manager que integra contenido y diseño. Los fragmentos de experiencias son fundamentales para crear experiencias coherentes y atractivas que se pueden reutilizar en varios canales.


Las Guías del Experience Manager ahora permiten publicar un tema o sus elementos en un Fragmento de experiencia. Puede crear una asignación basada en JSON entre un tema y sus elementos en un Fragmento de experiencia. Por ejemplo, puede crear fragmentos de experiencias para encabezados o pies de página con elementos de marca, titulares promocionales, testimonios de clientes y promociones de eventos.




Para obtener más información, consulte [Publicar fragmentos de experiencias](../user-guide/publish-experience-fragment.md).


## Mejoras en la publicación de fragmentos de contenido

Guías del Experience Manager también proporciona algunas mejoras útiles en Fragmentos de contenido:

- Puede filtrar fácilmente el contenido con condiciones mientras publica en un fragmento de contenido, mediante un archivo DITAVAL o atributos condicionales.

- También puede publicar y ver los fragmentos de contenido de un tema desde el **Salidas** de la sección **Propiedades de archivo**.

![ficha opciones de propiedades de archivo](./assets/file-properties-outputs-tab.png){width="300" align="left"}

Para obtener más información, consulte [Publicar fragmentos de contenido](../user-guide/publish-content-fragment.md).


## Capacidad para pasar metadatos de propiedades de archivo de tema a la salida del PDF nativo

Ahora, Guías del Experience Manager le permite agregar los metadatos de las propiedades de archivo de un tema a los diseños de página mientras genera la salida del PDF nativo. Utilice esta función para agregar metadatos específicos del tema, como el título, las etiquetas y la descripción a los diseños de página. También puede personalizar el PDF publicado en función de los metadatos del tema, como agregar una marca de agua al fondo del tema en función del estado del documento del tema.

![añadir pdf nativo de metadatos](./assets/add-metadata-native-pdf.png) {width="300" align="left"}

*Añada metadatos a los campos en los diseños de página.*

Obtenga información sobre cómo [adición de campos y metadatos](../native-pdf/design-page-layout.md#add-fields-metadata) en un diseño de página.

## Selección de contenido parcial entre elementos para las operaciones

Las guías del Experience Manager mejoran la experiencia de selección del contenido en los elementos del editor web. Puede seleccionar fácilmente contenido en diferentes elementos y realizar operaciones como ponerlo en negrita, cursiva y subrayado. Esta función le permite aplicar o quitar sin problemas el formato del contenido seleccionado parcialmente. También puede eliminar rápidamente el contenido seleccionado en todos los elementos. Una vez eliminado el contenido, si es necesario, el contenido restante se combina automáticamente con un solo elemento válido.

También se puede seleccionar contenido parcial entre elementos y, a continuación, rodearlo con un elemento DITA válido.
![cuadro de diálogo rodear elemento](./assets/surround-element.png) {width="300" align="left"}

*Rodee el contenido seleccionado con un elemento válido.*

En general, estas mejoras proporcionan una mejor experiencia y le ayudan a mejorar su eficacia al editar sus documentos.

Para obtener más información, consulte [Selección parcial del contenido entre elementos](../user-guide/web-editor-edit-topics.md#partial-selection-of-content-across-elements).

## Compatibilidad con documentos Markdown en la publicación nativa de PDF

Las guías del Experience Manager también admiten documentos Markdown en la publicación nativa de PDF. Esta función es útil y le ayuda a generar PDF para los archivos Markdown en el mapa DITA. La compatibilidad con Markdown en la publicación nativa de PDF le ayuda a crear, administrar y compartir fácilmente sus documentos.

Para obtener más información, consulte [compatibilidad con documentos de Markdown](../web-editor/native-pdf-web-editor.md#support-for-markdown-documents).


## Rendimiento y escalabilidad mejorados para proyectos de traducción grandes

La función de traducción es más rápida y escalable que nunca. Viene con una nueva arquitectura que proporciona un rendimiento mejorado. El tiempo de creación del proyecto es ahora más rápido que antes, y los conflictos durante el proceso son casi inexistentes. Este rendimiento mejorado le ayuda a realizar traducciones más rápidas, lo que garantiza un funcionamiento sin problemas incluso en proyectos de traducción grandes.

Esta mejora es muy beneficiosa, ya que mejora la productividad y la experiencia general.

Obtenga más información sobre cómo [traducir documentos desde el editor web](../user-guide/translate-documents-web-editor.md).
