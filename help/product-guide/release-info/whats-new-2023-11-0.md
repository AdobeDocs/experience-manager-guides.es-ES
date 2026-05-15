---
title: Notas de versión | Novedades de la versión de Adobe Experience Manager Guides de noviembre de 2023
description: Conozca las funciones nuevas y mejoradas de la versión de noviembre de 2023 de Adobe Experience Manager Guides as a Cloud Service.
exl-id: 83c04e01-92f1-41b0-8866-a202f4106b51
feature: What's New
role: Leader
TQID: https://experienceleague.adobe.com/XAwjfiapDvgvcwAuWm943W36PsAEiBfJUkN37DJeSZ0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 811
ht-degree: 0%

---

# Novedades de la versión de noviembre de 2023 de Adobe Experience Manager Guides as a Cloud Service

Este artículo cubre las funciones nuevas y mejoradas de la versión de noviembre de 2023 de Adobe Experience Manager Guides (más adelante denominada *Experience Manager Guides as a Cloud Service*).

Para obtener más información sobre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en esta versión, vea [Notas de la versión](release-notes-2023-11-0.md).

## Mejoras nativas de PDF

En la versión de noviembre de 2023 se realizaron las siguientes mejoras en el PDF nativo:

### Uso y duplicación de plantillas de PDF listas para usar

Experience Manager Guides proporciona plantillas de PDF listas para usar o de fábrica. Duplique las plantillas PDF de fábrica para crear las plantillas PDF personalizadas.

Ahora, también puede previsualizar la imagen en miniatura de una plantilla al crear y duplicar una plantilla. También puede editar o eliminar esta imagen. Esta función es útil para marcar o distinguir plantillas con nombres similares.
Más información sobre la [plantilla de PDF](../native-pdf/pdf-template.md).

![Cuadro de diálogo Duplicar plantilla de PDF](assets/duplicate-template.png){width="550"}

*Duplicar una plantilla de PDF existente.*


### Cambiar el orden de las páginas y publicar varias páginas por hoja

Además de publicar las páginas según el documento de origen, también puede cambiar el orden de las páginas en PDF al publicar un documento de varias páginas.  Esto le proporciona la flexibilidad para publicar las páginas en varios pedidos, como todas las páginas pares o impares primero. También puede publicar como un folleto y leer las páginas como un libro. También puede decidir el número de páginas que desea publicar en una sola hoja de papel. Para obtener más información, consulte la sección [Organización de la página](../native-pdf/components-pdf-template.md#page-organization).

### Ordenar términos del glosario según los criterios de ordenación

Ahora, también puede ordenar los términos del glosario en función de los criterios de ordenación. Puede utilizar la etiqueta &quot;sort-as&quot; para definir un criterio de ordenación para los términos del glosario. A continuación, puede ordenarlos en función de los criterios de ordenación en lugar de los términos. Esto le permite ordenar los términos del glosario según los términos utilizados en distintos idiomas. También puede definir un único criterio de ordenación para un término del glosario con una frase o un grupo de palabras.
Para obtener más información, vea [Configuración avanzada de PDF](../native-pdf/components-pdf-template.md#advanced-pdf-settings).


### Administración de recursos mejorada para plantillas nativas de PDF

Experience Manager Guides ahora ha mejorado la administración de recursos para plantillas nativas de PDF. Ahora puede compartir y reutilizar recursos como imágenes, archivos CSS y archivos de fuentes en varias plantillas nativas de PDF. Con esta mejora, la administración de los recursos de un gran conjunto de plantillas es mucho más sencilla. No es necesario crear recursos duplicados para cada plantilla, y puede mantenerlos en una carpeta compartida y utilizarlos en todas las plantillas nativas de PDF.
Para obtener más información, vea [Plantilla de PDF](../native-pdf/pdf-template.md).

## Mejoras del editor web

En la versión de noviembre de 2023 se realizaron las siguientes mejoras en el editor web:


### Ver archivos por título o nombres de archivo

Ahora puede elegir la forma predeterminada de ver los archivos en el Editor Web. Puede ver la lista de archivos por títulos o nombres de archivo desde los distintos paneles de la vista Autor.

![Cuadro de diálogo Preferencias de usuario](assets/user-preferences-2311.png){width="550"}

*Cambie la forma predeterminada de ver los archivos desde el cuadro de diálogo **Preferencias de usuario**.*


### Administrar ajustes preestablecidos de condición

Puede definir atributos de condición en los temas DITA. A continuación, utilice los atributos de condición en el ajuste preestablecido de condición para publicar el contenido en un mapa DITA. Experience Manager Guides ahora también le permite crear y administrar ajustes preestablecidos de condición desde el Editor web. También puede editarlos, duplicarlos o eliminarlos fácilmente.

![Ajustes preestablecidos de condición de la ficha Administrar del editor web &#x200B;](assets/web-editor-manage-condition-presets.png){width="550"}

Para obtener más información, vea [Usar ajustes preestablecidos de condición](../user-guide/generate-output-use-condition-presets.md).

### Restaurar fichas de archivo al actualizar el explorador

Experience Manager Guides restaura el estado de las fichas de archivo abiertas en el Editor Web al actualizar el explorador. Para obtener más información, vea la sección **Actualizar el explorador mientras edita los archivos** en [Editar temas en el editor web](../user-guide/web-editor-edit-topics.md).

### Desenvolver un elemento fácilmente

Ahora puede desenvolver fácilmente un elemento utilizando la opción del menú contextual de un elemento en el Editor Web. Esto ayuda a combinar fácilmente el texto del elemento con su elemento principal.
Para obtener más información, vea la sección **Desenvolver un elemento** de las [otras características del editor web](../user-guide/web-editor-other-features.md).

### Métodos abreviados de teclado para mover el cursor

Experience Manager Guides ahora también permite utilizar métodos abreviados de teclado para mover el cursor en el Editor Web. Puede utilizar los métodos abreviados del teclado para mover rápidamente una palabra a la izquierda o a la derecha. También puede desplazarse al principio o al final de la línea con la ayuda de los métodos abreviados de teclado.
Ahora, también puede utilizar métodos abreviados de teclado para mover el cursor al principio del siguiente elemento o al final del elemento anterior.
Obtenga más información acerca de los [métodos abreviados de teclado en el Editor Web](../user-guide/web-editor-keyboard-shortcuts.md).
