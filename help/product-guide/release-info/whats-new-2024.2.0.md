---
title: Notas de versión | Novedades de la versión de febrero de 2024 de las guías de Adobe Experience Manager
description: Conozca las funciones nuevas y mejoradas de la versión de febrero de 2024 de las guías de Adobe Experience Manager as a Cloud Service.
source-git-commit: 324e332d66996ab2c113092aae1fa3a4b55032c0
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 0%

---

# Novedades de la versión de febrero de 2024 de Adobe Experience Manager Guides as a Cloud Service

Este artículo cubre las funciones nuevas y mejoradas de la versión de febrero de 2024 de las guías de Adobe Experience Manager (más adelante denominadas *Guías del Experience Manager as a Cloud Service*).

Para obtener más información sobre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en esta versión, consulte [Notas de versión](release-notes-2023.12.0.md).

## Sugerencias inteligentes basadas en IA para crear contenido

Ahora puede mejorar el recorrido de la creación con Sugerencias inteligentes, una nueva función basada en IA en el Editor web. Mientras crea el contenido, esta función inteligente proporciona sugerencias en tiempo real para referencias de contenido, mejorando el flujo de trabajo, añadiendo precisión y garantizando una eficacia sin igual.


Para mantener el contenido correcto y coherente, la búsqueda y las sugerencias se limitan al contenido propiedad de su organización y coinciden estrechamente con las palabras clave que busca.

![Panel de sugerencias inteligentes en el editor web ](web-editor-smart-suggestion.png) {width="800" align="left"}


*Vea Sugerencias inteligentes para buscar y agregar referencias de contenido coincidentes desde el repositorio de contenido.*

También puede comparar el contenido actual con contenido similar en los demás temas. A continuación, puede elegir fácilmente los fragmentos de contenido de varios temas y agregarlos como referencias de contenido al tema actual. Añadir las referencias de contenido hace que las actualizaciones sean más manejables, especialmente en proyectos de documentación más grandes. Por ejemplo, supongamos que está creando un folleto sobre las últimas funciones del producto. En ese caso, puede añadir rápidamente las especificaciones actualizadas como referencias de contenido desde los documentos de funciones relacionados.

El uso de esta función inteligente reduce el esfuerzo manual de búsqueda de contenido relacionado y le ayuda a centrarse en la creación de nuevo contenido.  También ayuda a mantener la coherencia y facilita una mejor colaboración en equipo.

## Función del historial de versiones modificado en el editor web

Ahora, Guías del Experience Manager proporciona una característica de historial de versiones mejorada que le permite comparar los cambios realizados en un documento a lo largo del tiempo. En la nueva vista en paralelo, puede comparar fácilmente el contenido y los metadatos de la versión actual con cualquier versión anterior del mismo documento. También puede ver las etiquetas y los comentarios de las versiones comparadas. Como administrador, puede controlar los metadatos de versión del tema y sus valores que se mostrarán en la **Historial de versiones** Cuadro de diálogo.

![Cuadro de diálogo Historial de versiones](assets/version-history-dialog-web-editor.png){width="800" align="left"}
*Previsualizar los cambios en las distintas versiones de un tema.*


Obtenga más información acerca de **Historial de versiones** descripción de la función en [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS) sección.

## Panel de traducción mejorada

El **Traducción** se ha mejorado el panel.  Puede ver el **Idiomas disponibles** y seleccione rápidamente la configuración regional en la que desea traducir el proyecto. Con una sola selección, también puede elegir **Seleccionar todo** para traducir el proyecto a todos los idiomas disponibles.

![panel de traducción](assets/translation-languages-4.4.png){width="300" align="left"}

*Seleccione las configuraciones regionales en las que desea traducir el proyecto. Elija la versión predeterminada, la de línea de base o la más reciente de los archivos que desea traducir.*

Obtenga más información sobre cómo [traducir contenido](../user-guide/translation.md).


## Se ha mejorado la lógica de búsqueda en el cuadro de diálogo Insertar elemento

Ahora puede encontrar fácilmente los elementos en el cuadro de diálogo Insertar elemento.  Puede escribir una cadena en el cuadro de búsqueda y obtener una lista de todos los elementos válidos que comienzan con la cadena introducida.

Por ejemplo, al editar un párrafo que desea insertar un elemento, puede buscar un carácter &quot;t&quot; para obtener todos los elementos válidos que comiencen por &quot;t&quot;.


![Cuadro de diálogo Insertar](assets/insert-element.png){width="300" align="left"}

*Escriba un carácter para buscar todos los elementos válidos que comiencen por el carácter.*


Para obtener más información, consulte **Insertar elemento** descripción de la función en [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS) sección.


## Capacidad para dividir una lista en el mismo nivel

Ahora puede dividir fácilmente la lista en el Editor Web. Seleccione el **Dividir lista** del menú contextual de un elemento de lista para dividir la lista actual. Se crea una lista nueva en el mismo nivel, empezando por el elemento de lista seleccionado para la división.

![panel de traducción](assets/context-menu-split-list.png){width="300" align="left"}

*Seleccione la opción para dividir la lista actual.*

Para obtener más información, consulte **Insertar lista** descripción de la función en [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS) sección.

## Acceso a las propiedades del archivo en el modo de origen de la creación

Ahora, puede acceder al panel derecho de **Propiedades de archivo** en los cuatro modos o vistas: Diseño, Autor, Origen y Vista previa.  Esto le ayuda a ver las propiedades del archivo incluso cuando cambia entre los distintos modos.

Para obtener más información, consulte **Propiedades de archivo** descripción de la función en [Panel derecho](../user-guide/web-editor-features.md#id2051EB003YK) sección.

## Publicar varios ajustes preestablecidos de salida en paralelo

Experience Manager proporciona la función para crear líneas base seleccionando automáticamente los temas según la etiqueta aplicada a ellos. Ahora, también puede publicar sin problemas varios ajustes preestablecidos de salida con líneas de base automáticas del mismo mapa DITA. No es necesario publicar solo un ajuste preestablecido a la vez, pero es fácil publicar varios ajustes preestablecidos de salida en paralelo.


## Mejoras del PDF nativo

En la versión de febrero de 2024 se realizaron las siguientes mejoras en el PDF nativo:

### Pasar metadatos de recursos a la salida del PDF

Experience Manager ahora permite pasar las propiedades de metadatos de los recursos desde el mapa DITA a la salida del PDF.
En el ajuste preestablecido de salida de PDF nativo, puede elegir los metadatos que desea pasar al proceso de publicación de PDF. Puede seleccionar las propiedades personalizadas y las predeterminadas.  Las propiedades de metadatos seleccionadas se pasan al archivo de PDF generado mediante el PDF nativo.

Esta función es útil, ya que le ayuda a mantener la coherencia de las propiedades del recurso, como el autor, la fecha de creación o el título del documento. Esto facilita la organización, la búsqueda y la clasificación de los documentos.

Para obtener más información, consulte **Avanzadas** configuración en la [Salida del PDF de publicación](../web-editor/native-pdf-web-editor.md).


### Usar metadatos agregados en `topicmeta` para la salida del PDF

La función de metadatos de la publicación de PDF nativos ayuda en la administración de contenido y en la búsqueda de archivos en Internet.
<img src="assets/pdf-metadata-4-4.png" alt="ficha de metadatos" width="800">

*Seleccione una opción para agregar y personalizar opciones de metadatos.*

Ahora, Guías del Experience Manager proporciona la opción de usar los metadatos que ha agregado en `topicmeta` del mapa DITA para rellenar los campos de metadatos de la salida del PDF. Esta opción está seleccionada de forma predeterminada.

Esta función ayuda a mejorar la administración de documentos, garantiza la coherencia y permite realizar búsquedas en sus documentos.

Para obtener más información, consulte **Metadatos** en la pestaña [Salida del PDF de publicación](../web-editor/native-pdf-web-editor.md).