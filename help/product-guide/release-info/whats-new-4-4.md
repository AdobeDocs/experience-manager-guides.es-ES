---
title: Notas de versión | Novedades de la versión 4.4.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las funciones nuevas y mejoradas de la versión 4.4.0 de Adobe Experience Manager Guides
role: Leader
exl-id: 63a2e93b-b4cf-4423-88e4-b01c6a52a532
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '2308'
ht-degree: 0%

---

# Novedades de la versión 4.4.0 (enero de 2024)

Este artículo cubre las funciones nuevas y mejoradas de la versión 4.4.0 de Adobe Experience Manager Guides.

Para ver la lista de problemas que se han corregido en esta versión, consulte [Problemas corregidos en la versión 4.4.0](../release-info/fixed-issues-4-4.md).

Obtenga información acerca de [instrucciones de actualización para la versión 4.4.0](../release-info/upgrade-instructions-4-4.md).



## Función del historial de versiones modificado en el editor web

Ahora Experience Manager Guides proporciona una función de historial de versiones mejorada que le permite comparar los cambios realizados en un documento a lo largo del tiempo. En la nueva vista en paralelo, puede comparar fácilmente el contenido y los metadatos de la versión actual con cualquier versión anterior del mismo documento. También puede ver las etiquetas y los comentarios de las versiones comparadas. Como administrador, puede controlar los metadatos de versión del tema y sus valores que se mostrarán en el cuadro de diálogo **Historial de versiones**.

![Cuadro de diálogo Historial de versiones](assets/version-history-dialog-web-editor.png){width="800" align="left"}
*Obtener una vista previa de los cambios en las distintas versiones de un tema.*

Obtenga más información acerca de la descripción de la característica **Historial de versiones** en la sección [Panel izquierdo (heredado)](/help/legacy-product-guide/user-guide/web-editor-features.md#id2051EA0M0HS).

## Administrar ajustes preestablecidos de condición

Puede definir atributos de condición en los temas DITA. A continuación, utilice los atributos de condición en el ajuste preestablecido de condición para publicar el contenido en un mapa DITA. Experience Manager Guides ahora también proporciona una experiencia enriquecida en el editor web, que le ayuda a crear y administrar ajustes preestablecidos de condición de forma más eficaz. También puede editarlos, duplicarlos o eliminarlos fácilmente.

![Ajustes preestablecidos de condición de la ficha Administrar del editor web ](assets/web-editor-manage-condition-presets.png){width="550" align="left"}

Para obtener más información, vea [Usar ajustes preestablecidos de condición](../user-guide/generate-output-use-condition-presets.md).

## Experiencia modificada para editar los atributos

Ahora, obtendrá una experiencia renovada para agregar o editar los atributos de un elemento desde el panel **Propiedades de contenido** del Editor Web.

![Panel de atributos](assets/attributes-multiple-properties.png){width="300" align="left"}

*Agregar atributos desde el panel Propiedades de contenido.*

También puede editar y eliminar fácilmente los atributos.
Para obtener más información, consulte la descripción de la característica **Propiedades de contenido** en la sección [Panel derecho](../user-guide/web-editor-features.md#id2051EB003YK).

## Edición de metadatos durante la creación

Ahora, durante la creación, puede actualizar las etiquetas de metadatos del archivo mediante el menú desplegable de **Propiedades del archivo** en el panel derecho. También puede seleccionar **Editar más propiedades** para actualizar más metadatos.

![propiedades de archivo](assets/file-properties-general.png){width="300" align="left"}

*Actualice los metadatos y edite las propiedades del archivo desde el panel derecho.*

Para obtener más información, consulte la descripción de la característica **Propiedades del archivo** en la sección [Panel derecho](../user-guide/web-editor-features.md#id2051EB003YK).

## Ver los atributos clave en la vista Mapa

Al definir atributos clave para el tema o las referencias de mapa, también puede ver el título, el icono correspondiente y la clave en el panel izquierdo. La clave se muestra como `key=<key-name>`.

![claves en la vista de mapa](assets/view-key-title-map-view.png) {width="300" align="left"}

*Ver el atributo clave en la vista de mapa.*


Para obtener más información, consulte la descripción de la característica **Vista de mapa** en la sección [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Capacidad para duplicar una línea de base según una etiqueta

Experience Manager Guides ahora proporciona una experiencia de usuario mejorada para crear las líneas de base desde el Editor web.
Las opciones **Actualización manual** y **Actualización automática** son más intuitivas y le ayudan a elegir fácilmente entre crear una línea de base estática o actualizarla automáticamente según las etiquetas.

![crear nueva línea base](assets/dynamic-baseline-4-4.png) {width="300" align="left"}
*Crear línea de base desde el editor web.*

También le permite duplicar una línea de base basada en la etiqueta. La versión de referencia se selecciona en función de la etiqueta dada (si existe) mientras se duplica o, de lo contrario, elige la versión de la línea de base duplicada.


![duplicar una línea de base ](assets/duplicate-baseline.png) {width="300" align="left"}

*Duplicar una línea de base basándose en una etiqueta o crear una copia exacta.*

Obtenga más información sobre cómo [crear y administrar líneas de base desde el Editor web](../user-guide/web-editor-baseline.md).

## Panel de recopilación de mapas mejorado

Experience Manager Guides proporciona un panel de recopilación de mapas mejorado. En una colección de mapas, puede configurar rápidamente las propiedades de metadatos de forma masiva para los mapas DITA. Esta función es útil, ya que no es necesario actualizar las propiedades de metadatos para cada mapa DITA de forma individual.

Ahora puede ver el nombre de archivo del mapa DITA. También puede ver las líneas base. Esto le ayudará a encontrar rápidamente la línea de base utilizada para un ajuste preestablecido.

![Panel de recopilación de mapas](assets/map-collection-dashboard.png){width="800" align="left"}

*Ver, editar y generar resultados desde el panel de recopilación de mapas.*

Aprenda a [usar la colección de mapas para generar resultados](../user-guide/generate-output-use-map-collection-output-generation.md).

## Panel de traducción mejorada

Se ha mejorado el panel **Traducción**.  Puede ver la lista **Idiomas disponibles** y seleccionar rápidamente la configuración regional en la que desea traducir el proyecto. Con una sola selección, también puedes elegir **Seleccionar todo** para traducir el proyecto a todos los idiomas disponibles.

![panel de traducción](assets/translation-languages-4.4.png){width="300" align="left"}



*Seleccione las configuraciones regionales en las que desea traducir el proyecto. Elija la versión predeterminada, de línea de base o la más reciente de los archivos para la traducción.*

Más información sobre cómo [traducir contenido](../user-guide/translation.md).

## Se ha mejorado la lógica de búsqueda en el cuadro de diálogo Insertar elemento

Ahora puede encontrar fácilmente los elementos en el cuadro de diálogo Insertar elemento.  Puede escribir una cadena en el cuadro de búsqueda y obtener una lista de todos los elementos válidos que comienzan con la cadena introducida.

Por ejemplo, al editar un párrafo que desea insertar un elemento, puede buscar un carácter &#39;t&#39; para obtener
todos los elementos válidos que comienzan con &#39;t&#39;.


![Cuadro de diálogo Insertar](assets/insert-element.png){width="300" align="left"}

*Escriba un carácter para buscar todos los elementos válidos que comiencen por el carácter.*


Para obtener más información, vea la descripción de la característica **Insertar elemento** en la sección [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS).


## Capacidad para dividir una lista en el mismo nivel

Ahora puede dividir fácilmente la lista en el Editor Web. Seleccione la opción **Split List** en el menú contextual de un elemento de lista para dividir la lista actual. Se crea una lista nueva en el mismo nivel, empezando por el elemento de lista seleccionado para la división.

![panel de traducción](assets/context-menu-split-list.png){width="300" align="left"}

*Seleccione la opción para dividir la lista actual.*

Para obtener más información, vea la descripción de la característica **Insertar lista** en la sección [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Desenvolver fácilmente elementos DITA

Ahora puede desenvolver fácilmente un elemento utilizando la opción del menú contextual de un elemento en el Editor Web. Esto ayuda a combinar fácilmente el texto del elemento con su elemento principal.
Para obtener más información, vea la sección **Desenvolver un elemento** de las [otras características del editor web](../user-guide/web-editor-other-features.md).

## Acceso a las propiedades del archivo en el modo de origen de la creación

Ahora puede acceder a la función **Propiedades del archivo** del panel derecho en los cuatro modos o vistas siguientes: Diseño, Autor, Source y Vista previa.  Esto le ayuda a ver las propiedades del archivo incluso cuando cambia entre los distintos modos.

Para obtener más información, vea la descripción de la característica **Propiedades del archivo** en la sección [Panel derecho](../user-guide/web-editor-features.md#id2051EB003YK).


## Ver archivos por título o nombres de archivo

Ahora puede elegir la forma predeterminada de ver los archivos en el Editor Web. Puede ver la lista de archivos por títulos o nombres de archivo desde los distintos paneles de la vista Autor.

![Cuadro de diálogo Preferencias de usuario](assets/user-preferences-2311.png){width="550" align="left"}

*Cambie la forma predeterminada de ver los archivos desde el cuadro de diálogo **Preferencias de usuario**.*


## Restaurar fichas de archivo al actualizar el explorador

Experience Manager Guides restaura el estado de las fichas de archivo abiertas en el Editor Web al actualizar el explorador. Para obtener más información, vea la sección **Actualizar el explorador mientras edita los archivos** en [Editar temas en el editor web](../user-guide/web-editor-edit-topics.md).


## Capacidad de navegación mediante los métodos abreviados del teclado

Experience Manager Guides ahora también permite utilizar métodos abreviados de teclado para mover el cursor en el Editor Web. Puede utilizar los métodos abreviados del teclado para mover rápidamente una palabra a la izquierda o a la derecha. También puede desplazarse al principio o al final de la línea con la ayuda de los métodos abreviados de teclado.
Ahora, también puede utilizar métodos abreviados de teclado para mover el cursor al principio del siguiente elemento o al final del elemento anterior.
Obtenga más información acerca de los [métodos abreviados de teclado en el Editor Web](../user-guide/web-editor-keyboard-shortcuts.md).


## AEM Resolución de vínculos de mapas cruzados en la salida del sitio de la

AEM Los vínculos de mapas cruzados (XREF con ámbito del mismo nivel) que se representan en la salida del sitio de la publicación de la lista de distribución ahora se resuelven según el título de archivo del contexto de publicación establecido para la asignación generada.


## AEM Configure la dirección URL de la salida del sitio de para utilizar el título del documento

Experience Manager Guides AEM le permite, como administrador, configurar la dirección URL de la salida del sitio de la. AEM Si el nombre de archivo no existe o contiene todos los caracteres especiales, puede configurarlos para reemplazarlos con un separador en la dirección URL de la salida del sitio de la página de la página de la página de la página de salida de la página de la página. También puede reemplazarlos con el nombre del primer tema secundario. AEM Aprenda a [configurar la dirección URL de la salida del sitio de para que use el título del documento](../cs-install-guide/conf-output-generation.md#configure-the-url-of-the-aem-site-output-to-use-the-document-title).


## Varios ajustes preestablecidos de salida de Publish en paralelo

Experience Manager proporciona la función para crear líneas base seleccionando automáticamente los temas según la etiqueta aplicada a ellos. Ahora, también puede publicar sin problemas varios ajustes preestablecidos de salida con líneas de base automáticas del mismo mapa DITA. No es necesario publicar solo un ajuste preestablecido a la vez, pero es fácil publicar varios ajustes preestablecidos de salida en paralelo.

Obtenga más información sobre cómo [crear y administrar líneas de base desde el Editor web](../user-guide/web-editor-baseline.md).

## Mejoras del PDF nativo

En la versión 4.4.0 se han realizado las siguientes mejoras en el PDF nativo:

### Usar variables en la salida del PDF

Puede utilizar variables para insertar y administrar de forma dinámica información reutilizable. Experience Manager Guides le ayuda a crear, editar y previsualizar variables mientras genera la salida del PDF. Puede modificar rápidamente los valores de las variables y hacer que sus documentos sean portátiles y fáciles de actualizar.

![variables de pdf nativas](assets/add-variable-default.png){width="800" align="left"}

*Crear y administrar variables en el editor web.*

También puede crear conjuntos de variables que anulen los valores predeterminados y asignen valores alternativos a las variables. Inserte estas variables dentro del diseño de página y utilice el mismo diseño de PDF. No es necesario crear diseños independientes para cada conjunto de valores. Por ejemplo, puede crear un conjunto de variables para cada versión del producto. Este conjunto de variables puede constar de variables para distintos detalles del producto, como el nombre del producto, el número de versión y la fecha de lanzamiento. A continuación, puede agregar valores diferentes para estas variables.

**Conjunto de variables 1: Adobe-set1**

* Nombre del producto: Experience Manager Guides
* Número de versión: 2311
* Fecha de versión: 2/11/2023

**Conjunto de variables 2: Adobe-set2**

* Nombre del producto: Experience Manager Guides
* Número de versión: 2310
* Fecha de versión: 27/09/2023



<img src="./assets/native-pdf-variable-output.png" alt="Pie de página en salida de PDF" width="500" border="2px">

*Generar la salida del PDF mediante variables en el diseño del PDF.*

Puede aplicar estilos y utilizar marcado de HTML para dar formato a las variables.  También puede actualizar rápidamente los valores de cualquier variable siempre que sea necesario y volver a generar la salida. Por ejemplo, si necesita actualizar los detalles de una versión, puede editar el valor de la versión en la variable VersionNumber y volver a generar el resultado.


Obtenga más información acerca de cómo usar [variables en la salida del PDF](../native-pdf/native-pdf-variables.md).


### Propagar metadatos de recursos a la salida del PDF

Experience Manager ahora permite transferir las propiedades de metadatos de los recursos desde el mapa DITA a la salida del PDF.
Desde el ajuste preestablecido de salida PDF nativo, puede elegir los metadatos que desea propagar al proceso de publicación PDF. Puede seleccionar las propiedades personalizadas y las predeterminadas.  Las propiedades de metadatos seleccionadas se transfieren al archivo de PDF generado mediante el PDF nativo.

Esta función es útil, ya que le ayuda a mantener la coherencia de las propiedades del recurso, como el autor, la fecha de creación o el título del documento. Esto facilita la organización, la búsqueda y la clasificación de los documentos.

Para obtener más información, vea la configuración de **Advanced** en la [salida del PDF de Publish](../web-editor/native-pdf-web-editor.md).

### Usar metadatos agregados en el elemento `topicmeta` para la salida del PDF

La función de metadatos de la publicación de PDF nativos ayuda en la administración de contenido y en la búsqueda de archivos en Internet.
<img src="assets/pdf-metadata-4-4.png" alt="ficha de metadatos" width="800">

*Seleccione una opción para agregar y personalizar opciones de metadatos.*

Ahora Experience Manager Guides proporciona la opción de usar los metadatos agregados en el elemento `topicmeta` del mapa DITA para rellenar los campos de metadatos de la salida del PDF. Esta opción está seleccionada de forma predeterminada.

Esta función ayuda a mejorar la administración de documentos, garantiza la coherencia y permite realizar búsquedas en sus documentos.

Para obtener más información, vea la ficha **Metadatos** en la [salida del PDF de Publish](../web-editor/native-pdf-web-editor.md).

### Uso y duplicación de plantillas de PDF listas para usar

Experience Manager Guides proporciona plantillas de PDF listas para usar o de fábrica. Duplique las plantillas de PDF de fábrica para crear las plantillas de PDF personalizadas.

Ahora, también puede previsualizar la imagen en miniatura de una plantilla al crear y duplicar una plantilla. También puede editar o eliminar esta imagen. Esta función es útil para marcar o distinguir plantillas con nombres similares.
Más información sobre la [plantilla de PDF](../native-pdf/pdf-template.md).

![Cuadro de diálogo Duplicar plantilla de PDF](assets/duplicate-template.png){width="550" align="left"}

*Duplicar una plantilla de PDF existente.*


### Cambiar el orden de las páginas y publicar varias páginas por hoja

Además de publicar las páginas según el documento de origen, también puede cambiar el orden de las páginas en PDF al publicar un documento de varias páginas.  Esto le proporciona la flexibilidad para publicar las páginas en varios pedidos, como todas las páginas pares o impares primero. También puede publicar como un folleto y leer las páginas como un libro. También puede decidir el número de páginas que desea publicar en una sola hoja de papel. Para obtener más información, consulte la sección [Organización de la página](../native-pdf/components-pdf-template.md#page-organization).

### Ordenar términos del glosario según los criterios de ordenación

Ahora, también puede ordenar los términos del glosario en función de los criterios de ordenación. Puede utilizar la etiqueta &quot;ordenar como&quot; para definir un criterio de ordenación para los términos del glosario. A continuación, puede ordenarlos en función de los criterios de ordenación en lugar de los términos. Esto le permite ordenar los términos del glosario según los términos utilizados en distintos idiomas. También puede definir un único criterio de ordenación para un término del glosario con una frase o un grupo de palabras.
Para obtener más información, vea [Configuración avanzada de PDF](../native-pdf/components-pdf-template.md#advanced-pdf-settings).


### Administración de recursos mejorada para plantillas de PDF nativas

Experience Manager Guides ahora ha mejorado la administración de recursos para plantillas de PDF nativas. Ahora puede compartir y reutilizar recursos, como imágenes, archivos CSS y archivos de fuentes, en varias plantillas de PDF nativas. Con esta mejora, la administración de los recursos de un gran conjunto de plantillas es mucho más sencilla. No es necesario crear recursos duplicados para cada plantilla y puede mantenerlos en una carpeta compartida y utilizarlos en todas las plantillas de PDF nativas.
Para obtener más información, vea [Plantilla de PDF](../native-pdf/pdf-template.md).
