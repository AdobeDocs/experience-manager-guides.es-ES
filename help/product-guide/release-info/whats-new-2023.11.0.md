---
title: Notas de versión | Novedades de la versión de Adobe Experience Manager Guides, noviembre de 2023
description: Conozca las funciones nuevas y mejoradas de la versión de noviembre de 2023 de las guías de Adobe Experience Manager as a Cloud Service.
exl-id: 83c04e01-92f1-41b0-8866-a202f4106b51
feature: What's New
role: Leader
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 0%

---

# Novedades de la versión de noviembre de 2023 de Adobe Experience Manager Guides as a Cloud Service

Este artículo cubre las funciones nuevas y mejoradas de la versión de noviembre de 2023 de las guías de Adobe Experience Manager (más adelante denominadas *Guías del Experience Manager as a Cloud Service*).

Para obtener más información sobre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en esta versión, consulte [Notas de versión](release-notes-2023.11.0.md).

## Mejoras del PDF nativo

En la versión de noviembre de 2023 se realizaron las siguientes mejoras en el PDF nativo:

### Uso y duplicación de plantillas de PDF listas para usar

Las guías del Experience Manager proporcionan plantillas de PDF listas para usar o de fábrica. Duplique las plantillas de PDF de fábrica para crear las plantillas de PDF personalizadas.

Ahora, también puede previsualizar la imagen en miniatura de una plantilla al crear y duplicar una plantilla. También puede editar o eliminar esta imagen. Esta función es útil para marcar o distinguir plantillas con nombres similares.
Obtenga más información acerca de [plantilla de PDF](../native-pdf/pdf-template.md).

![Cuadro de diálogo Duplicar plantilla de PDF](assets/duplicate-template.png){width="550" align="left"}

*Duplique una plantilla de PDF existente.*


### Cambiar el orden de las páginas y publicar varias páginas por hoja

Además de publicar las páginas según el documento de origen, también puede cambiar el orden de las páginas en PDF al publicar un documento de varias páginas.  Esto le proporciona la flexibilidad para publicar las páginas en varios pedidos, como todas las páginas pares o impares primero. También puede publicar como un folleto y leer las páginas como un libro. También puede decidir el número de páginas que desea publicar en una sola hoja de papel. Para obtener más información, consulte [Organización de página](../native-pdf/components-pdf-template.md#page-organization) sección.

### Ordenar términos del glosario según los criterios de ordenación

Ahora, también puede ordenar los términos del glosario en función de los criterios de ordenación. Puede utilizar la etiqueta &quot;sort-as&quot; para definir un criterio de ordenación para los términos del glosario. A continuación, puede ordenarlos en función de los criterios de ordenación en lugar de los términos. Esto le permite ordenar los términos del glosario según los términos utilizados en distintos idiomas. También puede definir un único criterio de ordenación para un término del glosario con una frase o un grupo de palabras.
Para obtener más información, consulte [Configuración avanzada del PDF](../native-pdf/components-pdf-template.md#advanced-pdf-settings).


### Administración de recursos mejorada para plantillas de PDF nativas

Las guías del Experience Manager ahora han mejorado la administración de recursos para plantillas de PDF nativas. Ahora puede compartir y reutilizar recursos, como imágenes, archivos CSS y archivos de fuentes, en varias plantillas de PDF nativas. Con esta mejora, la administración de los recursos de un gran conjunto de plantillas es mucho más sencilla. No es necesario crear recursos duplicados para cada plantilla y puede mantenerlos en una carpeta compartida y utilizarlos en todas las plantillas de PDF nativas.
Para obtener más información, consulte [Plantilla de PDF](../native-pdf/pdf-template.md).

## Mejoras del editor web

En la versión de noviembre de 2023 se realizaron las siguientes mejoras en el editor web:


### Ver archivos por título o nombres de archivo

Ahora puede elegir la forma predeterminada de ver los archivos en el Editor Web. Puede ver la lista de archivos por títulos o nombres de archivo desde los distintos paneles de la vista Autor.

![Cuadro de diálogo Preferencias de usuario](assets/user-preferences-2311.png){width="550" align="left"}

*Cambie la forma predeterminada de ver los archivos desde el **Preferencias de usuario**diálogo.*


### Administrar ajustes preestablecidos de condición

Puede definir atributos de condición en los temas DITA. A continuación, utilice los atributos de condición en el ajuste preestablecido de condición para publicar el contenido en un mapa DITA. Guías del Experience Manager ahora también le permite crear y administrar ajustes preestablecidos de condición desde el Editor web. También puede editarlos, duplicarlos o eliminarlos fácilmente.

![Ajustes preestablecidos de condición desde la pestaña Administrar del editor web ](assets/web-editor-manage-condition-presets.png){width="550" align="left"}

Para obtener más información, consulte [Usar ajustes preestablecidos de condición](../user-guide/generate-output-use-condition-presets.md).

### Restaurar fichas de archivo al actualizar el explorador

Guías del Experience Manager restaura el estado de las fichas de archivo abiertas en el Editor Web al actualizar el explorador. Para obtener más información, consulte **Actualizar el explorador mientras edita los archivos** sección debajo de [Editar temas en el editor web](../user-guide/web-editor-edit-topics.md).

### Desenvolver un elemento fácilmente

Ahora puede desenvolver fácilmente un elemento utilizando la opción del menú contextual de un elemento en el Editor Web. Esto ayuda a combinar fácilmente el texto del elemento con su elemento principal.
Para obtener más información, consulte **Desenvolver un elemento** de la sección [otras funciones del editor web](../user-guide/web-editor-other-features.md).

### Métodos abreviados de teclado para mover el cursor

Las Guías del Experience Manager ahora también permiten utilizar métodos abreviados de teclado para mover el cursor en el Editor Web. Puede utilizar los métodos abreviados del teclado para mover rápidamente una palabra a la izquierda o a la derecha. También puede desplazarse al principio o al final de la línea con la ayuda de los métodos abreviados de teclado.
Ahora, también puede utilizar métodos abreviados de teclado para mover el cursor al principio del siguiente elemento o al final del elemento anterior.
Obtenga más información acerca de [métodos abreviados de teclado en el Editor Web](../user-guide/web-editor-keyboard-shortcuts.md).
