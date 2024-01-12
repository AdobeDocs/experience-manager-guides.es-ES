---
title: Notas de versión | Novedades de la versión 4.2 de las guías de Adobe Experience Manager
description: Conozca las funciones nuevas y mejoradas de las versiones 4.2 de las guías de Adobe Experience Manager
exl-id: 46367ccf-58ff-4889-8314-cdd5bf5d0f1d
feature: What's New
role: Leader
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '2423'
ht-degree: 0%

---

# Novedades de la versión 4.2 de las guías de Adobe Experience Manager (febrero de 2023)

Este artículo cubre las funciones nuevas y mejoradas de la versión 4.2 de las guías de Adobe Experience Manager (que posteriormente se denominarán *AEM Guías de*).

Para obtener más información sobre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en esta versión, consulte la [Notas de versión](release-notes-4.2.md) artículo.

## Generar informes desde el editor web

AEM Las guías de usuario incluyen una función en el editor web que permite comprobar la integridad general de los documentos técnicos y generar informes para ellos.
Puede ver la lista de temas y administrar los metadatos de todas las referencias para el mapa actual desde el
**Informes** en el Editor Web.

**Generar la vista Lista de temas**

Puede generar la Lista de temas que proporciona información detallada sobre los temas, como el tipo de referencia, el estado del documento y el autor. También puede generar el CSV para descargar la instantánea actual de los temas en el mapa DITA.

**Administrar metadatos y cambiar el estado del documento**

Puede aplicar etiquetas a un tema individual o utilizar la función de etiquetado masivo para aplicar varias etiquetas a varios temas, a un mapa DITA o a un submapa. También puede cambiar el estado del documento de todos los temas seleccionados al siguiente estado común posible del documento.

<img src="assets/web-editor-metadata-panel.png" alt="administrar metadatos" width="600">

## Experiencia de usuario modificada para la funcionalidad de revisión

AEM Ahora, las guías de usuario de proporcionan un UX mejorado que le ayuda a revisar los temas compartidos para su revisión. En la experiencia más reciente, la funcionalidad de revisión presenta las siguientes mejoras:

* Interfaz de usuario actualizada
* Panel Condiciones que le permite resaltar el contenido según las condiciones disponibles en el tema.
* Cada comentario del panel de comentarios está vinculado al texto correspondiente del tema actual. Ayuda a identificar el texto comentado.
* Los comentarios se muestran en el orden del texto comentado en el documento.
* El nombre de la tarea de revisión se muestra en el flujo de trabajo de revisión.
* Seleccione el mapa de raíz para la tarea de revisión que se utiliza para resolver todas las referencias clave y los términos del glosario utilizados en el contenido de la revisión.
* Barra de herramientas contextual que le ayuda a resaltar o tachar texto rápidamente.
* Menú Opciones para editar o eliminar sus propios comentarios.
* Para los comentarios obsoletos, tiene acceso a la vista en paralelo que le ayuda a comparar la versión anterior del tema con la versión de revisión actual
* Al utilizar los filtros, los comentarios del panel derecho se filtran según la selección y el número de comentarios del panel izquierdo se actualiza en consecuencia.


<img alt="revisar tarea" src="assets/comment-pop-up-panel.png" width="600">


Para obtener más información, consulte la *Revisar temas o mapas* de la guía Uso de guías de Adobe Experience Manager.

## Mejoras de traducción

Ahora tiene mejoras más fáciles de usar en el panel de traducción que le ayudan a traducir fácilmente sus documentos desde el Editor web.


**Columna Etiqueta de versión añadida al panel de traducción**

En el panel de traducción, también puede ver la columna Etiqueta de versión. Muestra la etiqueta de la versión seleccionada del archivo de origen. Esto puede ayudarle a seleccionar todos los archivos con una etiqueta específica y traducirlos de una sola vez.

**Ver la diferencia de versión de los archivos sin sincronizar en el panel de traducción**

Ahora puede comprobar las diferencias entre la versión seleccionada y la última versión de origen traducida de los temas. También puede optar por traducir el **Fuera de sincronización** archivos basados en los cambios realizados entre las dos versiones de un tema.

<img src="assets/translation-version-diff.png" alt="comité de traducción" width="600">



**Pasar la etiqueta de versión a la versión de destino**

AEM Guías de le permite pasar la etiqueta del archivo de origen al archivo de destino. Esto le ayuda a identificar fácilmente la versión de origen del archivo traducido.

<img alt="etiquetas de traducción" src="assets/translation-pass-source-label.png" width="600">

Por ejemplo, si tiene algunos archivos de origen con la etiqueta de versión Release 1.0 aplicada a ellos, también puede pasar la etiqueta de origen (Versión 1.0) al archivo traducido.

**Forzar sincronización de recursos sin sincronizar**

AEM Si realiza cambios en algunos de los recursos, Guías de recursos los marca como Desincronizados. Puede volver a traducir los recursos modificados o elegir descartar el estado Fuera de sincronización. Por ejemplo, si ha realizado algunos cambios menores que realmente no necesitan traducción, puede marcar su estado como Sincronizado.

**Ver proyectos de traducción en curso de un tema o mapa**

Algunas de las referencias del panel de traducción pueden estar en curso. AEM Ahora, Guías de proporciona una función que le ayuda a ver la lista de todos los proyectos de traducción en curso (junto con el idioma de destino) que contienen la referencia seleccionada.

Para obtener más información, consulte la *Traducir documentos desde el editor web* de la guía Uso de guías de Adobe Experience Manager.

## Generar resultados en varios formatos desde el editor web

Ahora puede generar fácilmente el resultado de sus temas o mapa DITA desde el Editor Web. AEM Puede configurar varios ajustes preestablecidos de salida, como Sitio de la aplicación, PDF, HTML 5, JSON (un formato de salida sin encabezado) y salida personalizada. Utilícelos para generar los resultados correspondientes. Puede definir atributos en los temas DITA y, a continuación, utilizar el ajuste preestablecido de condición para aplicar una condición al publicar la salida. También se puede utilizar la función de publicación Línea base para publicar selectivamente una versión específica del tema o mapa DITA.

**Administrar ajustes preestablecidos de salida del perfil global y de carpeta**

AEM Las guías de proporcionan la función para crear y administrar ajustes preestablecidos de salida para los Perfiles global y de carpeta. A continuación, puede utilizar fácilmente estos ajustes preestablecidos de salida para generar resultados para todas las asignaciones relacionadas con ese perfil global o de carpeta.

<img alt="añadir ajuste preestablecido" src="assets/add-global-output-preset.png" width="400">


Estos ajustes preestablecidos globales aparecen en **Output** de todas las asignaciones relacionadas. Puede utilizarlas para generar la salida de todas las asignaciones relacionadas. Puede seleccionar el ajuste preestablecido como ajuste preestablecido por defecto del PDF para generar la salida del PDF. También puede **Editar**, **Cambiar nombre**, **Duplicar**, o **Eliminar** un ajuste preestablecido de salida existente del **Opciones** menú.

>[!NOTE]
>
>Solo los usuarios administrativos de nivel de carpeta pueden crear ajustes preestablecidos de Perfil global y de carpeta.

## Buscar y reemplazar el texto en el nivel de mapa

Ahora puede buscar archivos dentro de un mapa que contengan texto específico. El texto buscado se resalta en los archivos. También puede reemplazar la palabra o frase buscada por otra palabra o frase dentro de los archivos. Seleccione el **Reemplazar una sola incidencia** para reemplazar la incidencia actual y el **Reemplazar todo en archivo** para reemplazar todas las ocurrencias en el archivo seleccionado. Puede seleccionar **Reemplazar todo** para reemplazar todas las ocurrencias del término buscado en todos los archivos.

<img src="assets/map-find-replace.png" alt="mapa buscar reemplazar" width="600">


De forma predeterminada, las opciones **Archivo de retirada antes de reemplazar** y **Crear nueva versión tras reemplazar** están seleccionados, por lo que se extrae un archivo antes de reemplazar el texto y se crea una nueva versión después de reemplazar el texto. También se puede buscar la cadena en las referencias indirectas dentro del mapa DITA. De forma predeterminada, esta opción está desactivada, por lo que la búsqueda solo se realiza en las referencias directas.

## Vista Presentación en el editor de mapas


Ahora puede ver el diseño completo de un mapa DITA en el Editor de mapas. Cuando se abre un mapa para editarlo, se abre la vista Presentación del Editor de mapas. En esta vista, puede ver la jerarquía de mapas en una vista de árbol. También puede editar y organizar o estructurar los temas en un mapa.

<img src="assets/layout-view-map.png" alt=" vista de diseño del mapa" width="600">

La vista Presentación contiene una barra de herramientas independiente que le ayuda a realizar muchas tareas sobre los temas presentes en un mapa.
Puede insertar referencias de temas, grupos de temas y definiciones de claves en un mapa. Puede reorganizar los temas presentes en un mapa moviéndolos hacia arriba, hacia abajo, a la izquierda o a la derecha. También puede arrastrar y soltar los temas para moverlos en un mapa. El editor de mapas también proporciona los iconos para bloquear o desbloquear archivos, comprobar el historial de versiones y realizar una administración de etiquetas de versión.


La vista Presentación también proporciona el **Opciones de vista** para mostrar u ocultar el número de línea, mostrar u ocultar la casilla de verificación, o mostrar el nombre de archivo o el título de los temas de un mapa.
También puede ver los temas en función de los filtros condicionales aplicados.

Además de organizar los temas en el archivo de asignación, también puede agregar, mover, copiar, pegar o eliminar referencias utilizando **Opciones** menú disponible para un elemento en la vista Presentación.

<img src="assets/layout-inline-attributes.png" alt=" atributos de diseño de mapa" width="600">


El panel derecho muestra las Propiedades de contenido y las Propiedades de mapa en la vista Diseño del Editor de mapas. Ahora también puede establecer la información de metadatos para los temas o el mapa. Puede definir el título de navegación, el texto de vínculo, la descripción breve y las palabras clave para el tema o el mapa seleccionado.

Para obtener más información, consulte *Vista Presentación* de la guía Uso de guías de Adobe Experience Manager.

## Panel Generación rápida

AEM Ahora, Guías de proporciona el panel Generación rápida, que le ayuda a generar y ver rápidamente la salida de los ajustes preestablecidos creados para su mapa DITA.

<img src="assets/quick-generate-map-view.png" alt=" generar panel rápidamente" width="600">

En el **Generación rápida** , puede ver la lista de todos los ajustes preestablecidos de salida creados para el mapa DITA. También puede ver rápidamente el resultado generado para los ajustes preestablecidos. Al finalizar la generación de resultados, aparece un mensaje de éxito o error. También puede ver el registro de errores que contiene detalles del error que se produjo en el proceso de generación.

## Crear una línea base dinámica basada en etiquetas

AEM Ahora, Guías de le proporciona la función para crear líneas de base dinámicas basadas en etiquetas. Si genera una línea de base, descarga una línea de base o crea un proyecto de traducción utilizando una línea de base, los archivos se seleccionan dinámicamente en función de las etiquetas actualizadas. Esta función resulta útil, ya que no es necesario modificar la línea de base al actualizar las etiquetas.

<img src="assets/dynamic-baseline.png" alt=" línea base dinámica" width="400">

## Eliminar y duplicar archivos del panel del repositorio

Ahora puede eliminar fácilmente archivos (de uno en uno) de la **Opciones** menú del archivo seleccionado del panel repositorio. Se muestra un mensaje de confirmación antes de eliminar el archivo. Si no se hace referencia al archivo desde ningún otro archivo, se elimina y se muestra un mensaje de éxito.

<img src="assets/options-menu-repo-view-file-level.png" alt="menú opciones de archivo " width="500">

También puede crear un duplicado o una copia del archivo seleccionado. De forma predeterminada, el archivo se crea con un sufijo (como filename_1.extension).


## Otras mejoras del editor web

* AEM En Guías de la, puede realizar algunas operaciones comunes para imágenes y archivos multimedia mediante el menú contextual. Ahora también puede localizar la imagen o el medio seleccionado en el repositorio o ver la vista previa del archivo en la interfaz de usuario de Assets.

* El nombre del perfil de carpeta actual se muestra como una etiqueta para el icono Preferencias de usuario en la barra de herramientas principal. Esto le ayuda a identificar el perfil de carpeta en el que está trabajando.

* Cuando se abre un mapa en la vista de mapa, el título del mapa actual se muestra en el centro de la barra de herramientas principal. Esto resulta útil para que los usuarios sepan qué mapa está abierto actualmente.

## Depuración de versiones seleccionadas de archivos

A medida que crea y mantiene el contenido, es posible que se creen muchas versiones para los archivos DITA en el repositorio. AEM Guías de permite depurar versiones anteriores de los archivos DITA del repositorio y liberar espacio en disco.

<img src="assets/preview-purge-report.png" alt="Previsualizar informe de depuración" width="500">

AEM Guías no elimina la primera versión del archivo o una versión que se incluye en una línea de base, ni tiene una etiqueta aplicada. La operación de purga ni siquiera elimina los archivos que se incluyen en una traducción o en un flujo de trabajo de revisión. Puede elegir el número de versiones que desea conservar y también decidir eliminar los archivos que sean anteriores al número de días definido.

Antes de iniciar la operación de depuración, puede obtener una vista previa del informe para ver las versiones que se van a purgar. A continuación, puede decidir iniciar o cancelar la operación de depuración.

<img src="assets/download-purge-report.png" alt="Informe de purga de PDownload" width="500">

Una vez finalizada la operación de depuración, puede comprobar el informe de depuración para ver los archivos depurados.

## Ver el título en lugar del UUID en el editor de oxígeno

AEM Ahora, Guías de le permite elegir **Uso del título en el editor y el administrador de mapas** en Configuración. Si selecciona esta opción, el título del fichero se mostrará en la ficha del fichero cuando se abra en el Editor o en el Administrador de mapas DITA. Si no selecciona esta opción, el UUID del archivo se muestra en la pestaña del archivo.

## IU de metadatos disponible para ajustes preestablecidos de PDF

Puede definir los metadatos a partir del ajuste preestablecido de salida de un mapa DITA. Puede establecer los metadatos de Título, Autor, Asunto y Palabras clave. Estos metadatos se asignan a los metadatos de las propiedades de archivo del PDF de salida. Estos metadatos anulan los metadatos definidos en el nivel de libro. Puede definir los metadatos específicamente en cada ajuste preestablecido de salida y pasarlos al PDF de salida.

## PDF nativo | PDF con barra de cambios que muestra la diferencia entre las versiones del documento

Ahora puede crear un PDF que muestre las diferencias de contenido entre dos versiones con la barra de cambios. Puede elegir comparar la versión actual con una línea base de la versión anterior o comparar entre las dos versiones de línea base seleccionadas.

<img src="assets/pdf-change-version.png" alt="pdf-change-version" width="600">

Aparecerá una barra de cambios en el PDF para indicar el contenido modificado, insertado o eliminado. También tiene las opciones para hacer lo siguiente:
* Mostrar el contenido insertado en color verde y subrayado
* Mostrar el contenido eliminado en color rojo y marcado con un tachado

## PDF nativo | Compatibilidad de variables con ruta de salida y nombre de archivo del PDF

Ahora también puede utilizar las siguientes variables integradas para definir la ruta de salida y el archivo del PDF. Puede utilizar una sola variable o una combinación de ellas para definir estas opciones:
* `${map_filename}`
* `${map_title}`
* `${preset_name}`
* `${language_code}`
* `${map_parentpath}` (Solo para la ruta de salida)
* `${path_after_langfolder}` (Solo para la ruta de salida)

## PDF nativo | Generación de una tabla de contenido para mapas DITA y reordenación de diseños de página

Ahora también se puede generar la tabla de contenido en mapas DITA utilizando un ajuste de PDF avanzado de la plantilla. Puede elegir habilitar o deshabilitar la visualización de los distintos diseños de página y también reordenar su posición.

## PDF nativo | Añadir un marcador personalizado en la salida del PDF

Ahora puede agregar un marcador personalizado a un contenido en particular en la salida final del PDF para facilitar la navegación. Se añadirá al índice creado a partir de los títulos de temas o secciones del mapa DITA.

## PDF nativo | Aplicar un estilo personalizado a las entradas del índice y al contenido del tema

AEM Guías de proporciona la función para aplicar un estilo personalizado en las entradas de la tabla de contenido o en un tema concreto de la salida del PDF. Por ejemplo, puede cambiar el color del texto de la tabla de contenido y el título del tema. También puede aplicar estilos a todo el contenido dentro del tema.
