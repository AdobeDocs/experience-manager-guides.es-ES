---
title: Notas de versión | Novedades de la versión 2024.2.0 de Adobe Experience Manager Guides
description: Conozca las funciones nuevas y mejoradas de la versión 2024.2.0 de Adobe Experience Manager Guides as a Cloud Service.
exl-id: 234d430a-d775-484a-aea8-6e422b0a01eb
source-git-commit: b1bb2b9da71bf0551fe40c84ac382df0e78e007b
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 1%

---

# Novedades de la versión 2024.2.0

Este artículo cubre las nuevas y mejoradas funciones de la versión 2024.2.0 de Adobe Experience Manager Guides.

Para ver la lista de problemas corregidos en esta versión, consulte [Problemas solucionados en la versión 2024.2.0](fixed-issues-2024-2-0.md).


Obtenga información acerca de [instrucciones de actualización para la versión 2024.2.0](upgrade-instructions-2024-2-0.md).



## Sugerencias inteligentes con tecnología de IA para agregar referencias de contenido al crear contenido

Ahora puede mejorar el recorrido de la creación con Sugerencias inteligentes, una nueva función basada en IA en el Editor web. Mientras crea el contenido, esta función inteligente proporciona sugerencias en tiempo real para referencias de contenido, mejorando el flujo de trabajo, añadiendo precisión y garantizando una eficacia sin igual.


Para mantener el contenido correcto y coherente, la búsqueda y las sugerencias se limitan al contenido propiedad de su organización y coinciden estrechamente con las palabras clave que busca.

![Panel de sugerencias inteligentes en el editor web ](assets/web-editor-smart-suggestion.png) {width="800" align="left"}


*Ver sugerencias inteligentes para buscar y agregar referencias de contenido coincidentes desde el repositorio de contenido.*

También puede comparar el contenido actual con contenido similar en los demás temas. A continuación, puede elegir fácilmente los fragmentos de contenido de varios temas y agregarlos como referencias de contenido al tema actual. Añadir las referencias de contenido hace que las actualizaciones sean más manejables, especialmente en proyectos de documentación más grandes. Por ejemplo, está creando un folleto sobre las últimas funciones de su producto. En ese caso, puede añadir rápidamente las especificaciones actualizadas como referencias de contenido desde los documentos de funciones relacionados.

El uso de esta función inteligente reduce el esfuerzo manual de búsqueda de contenido relacionado y le ayuda a centrarse en la creación de nuevo contenido.  También ayuda a mantener la coherencia y facilita una mejor colaboración en equipo.

Más información sobre [sugerencias inteligentes con tecnología de IA para crear contenido](../user-guide/authoring-ai-based-smart-suggestions.md).

## Función del historial de versiones modificado en el editor web

Ahora Experience Manager Guides proporciona una función de historial de versiones mejorada que le permite comparar los cambios realizados en un documento a lo largo del tiempo. En la nueva vista en paralelo, puede comparar fácilmente el contenido y los metadatos de la versión actual con cualquier versión anterior del mismo documento. También puede ver las etiquetas y los comentarios de las versiones comparadas. Como administrador, puede controlar los metadatos de versión del tema y sus valores que se mostrarán en el cuadro de diálogo **Historial de versiones**.

![Cuadro de diálogo Historial de versiones](assets/version-history-dialog-web-editor.png){width="800" align="left"}
*Obtener una vista previa de los cambios en las distintas versiones de un tema.*


Obtenga más información acerca de la descripción de la característica **Historial de versiones** en la sección [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Experiencia del usuario mejorada en el panel Traducción

Se ha mejorado el panel **Traducción**.  Puede ver la lista **Idiomas disponibles** y seleccionar rápidamente la configuración regional en la que desea traducir el proyecto. Con una sola selección, también puedes elegir **Seleccionar todo** para traducir el proyecto a todos los idiomas disponibles.

![panel de traducción](assets/translation-languages-4.4.png){width="300" align="left"}

*Seleccione las configuraciones regionales en las que desea traducir el proyecto. Elija la versión predeterminada, de línea de base o la más reciente de los archivos para la traducción.*

Más información sobre cómo [traducir contenido](../user-guide/translation.md).


## Se ha mejorado la lógica de búsqueda en el cuadro de diálogo Insertar elemento

Ahora puede encontrar fácilmente los elementos en el cuadro de diálogo Insertar elemento.  Puede escribir una cadena en el cuadro de búsqueda y obtener una lista de todos los elementos válidos que comienzan con la cadena introducida.

Por ejemplo, al editar un párrafo que desea insertar un elemento, puede buscar un carácter &#39;t&#39; para obtener
todos los elementos válidos que comiencen por &quot;t&quot;.


![Cuadro de diálogo Insertar](assets/insert-element.png){width="300" align="left"}

*Escriba un carácter para buscar todos los elementos válidos que comiencen por el carácter.*


Para obtener más información, vea la descripción de la característica **Insertar elemento** en la sección [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS).


## Capacidad para dividir la lista actual y comenzar con un nuevo elemento de lista en el mismo nivel

Ahora puede dividir fácilmente la lista en el Editor Web. Seleccione la opción **Split List** en el menú contextual de un elemento de lista para dividir la lista actual. Se crea una lista nueva en el mismo nivel, empezando por el elemento de lista seleccionado para la división.

![panel de traducción](assets/context-menu-split-list.png){width="300" align="left"}

*Seleccione la opción para dividir la lista actual.*

Para obtener más información, vea la descripción de la característica **Insertar lista** en la sección [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Acceso a las propiedades del archivo en el modo de origen de la creación

Ahora puede acceder a la función **Propiedades del archivo** del panel derecho en los cuatro modos o vistas siguientes: Diseño, Autor, Source y Vista previa.  Esto le ayuda a ver las propiedades del archivo incluso cuando cambia entre los distintos modos.

Para obtener más información, vea la descripción de la característica **Propiedades del archivo** en la sección [Panel derecho](../user-guide/web-editor-features.md#id2051EB003YK).

## Capacidad para publicar varios ajustes preestablecidos de salida con líneas de base dinámicas en paralelo

Experience Manager proporciona la función para crear líneas base seleccionando automáticamente los temas según la etiqueta aplicada a ellos. Ahora, también puede publicar sin problemas varios ajustes preestablecidos de salida con líneas de base automáticas del mismo mapa DITA. No es necesario publicar solo un ajuste preestablecido a la vez, pero es fácil publicar varios ajustes preestablecidos de salida en paralelo.


## Mejoras del PDF nativo

En la versión 2024.2.0 de se han realizado las siguientes mejoras en el PDF nativo:

### Pasar metadatos de recursos a la salida del PDF

Experience Manager ahora permite pasar las propiedades de metadatos de los recursos desde el mapa DITA a la salida del PDF.
En el ajuste preestablecido de salida de PDF nativo, puede elegir los metadatos que desea pasar al proceso de publicación de PDF. Puede seleccionar las propiedades personalizadas y las predeterminadas.  Las propiedades de metadatos seleccionadas se pasan al archivo de PDF generado mediante el PDF nativo.

Esta función es útil, ya que le ayuda a mantener la coherencia de las propiedades del recurso, como el autor, la fecha de creación o el título del documento. Esto facilita la organización, la búsqueda y la clasificación de los documentos.

Para obtener más información, vea la configuración de **Advanced** en la [salida del PDF de Publish](../web-editor/native-pdf-web-editor.md).


### Usar metadatos agregados en el elemento `topicmeta` para la salida del PDF

La función de metadatos de la publicación de PDF nativos ayuda en la administración de contenido y en la búsqueda de archivos en Internet.
<img src="assets/pdf-metadata-4-4.png" alt="ficha de metadatos" width="800">

*Seleccione una opción para agregar y personalizar opciones de metadatos.*

Ahora Experience Manager Guides proporciona la opción de usar los metadatos agregados en el elemento `topicmeta` del mapa DITA para rellenar los campos de metadatos de la salida del PDF. Esta opción está seleccionada de forma predeterminada.

Esta función ayuda a mejorar la administración de documentos, garantiza la coherencia y permite realizar búsquedas en sus documentos.

Para obtener más información, vea la ficha **Metadatos** en la [salida del PDF de Publish](../web-editor/native-pdf-web-editor.md).
