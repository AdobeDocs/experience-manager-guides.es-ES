---
title: Notas de versión | Guías de Adobe Experience Manager as a Cloud Service, versión de febrero de 2023
description: Lanzamiento de febrero de las guías de Adobe Experience Manager as a Cloud Service
exl-id: 090eaf94-fe3a-47e9-9937-f84f8434550d
source-git-commit: eb3fe92d36bc58a11e47f786a10d5938e2ed0184
workflow-type: tm+mt
source-wordcount: '1426'
ht-degree: 0%

---

# Novedades de la versión de febrero de 2023 de Adobe Experience Manager Guides as a Cloud Service

Este artículo cubre las funciones nuevas y mejoradas de la versión de febrero de 2023 de las guías de Adobe Experience Manager (más adelante denominadas *AEM Guías de as a Cloud Service*).

Para obtener más información sobre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en esta versión, consulte la [Notas de versión](release-notes-2023.2.0.md) artículo.


## Generar informes desde el editor web

AEM Las guías de usuario incluyen una función en el editor web que permite comprobar la integridad general de los documentos técnicos y generar informes para ellos.
Puede ver la lista de temas, administrar los metadatos y ver el contenido multimedia utilizado en todas las referencias del mapa actual desde el
**Informes** en el Editor Web.

**Generar la vista Lista de temas**

Puede generar la Lista de temas que proporciona información detallada sobre los temas, como el tipo de referencia, el estado del documento y el autor. También puede generar el CSV para descargar la instantánea actual de los temas en el mapa DITA.

**Administrar metadatos y cambiar el estado del documento**

Puede aplicar etiquetas a un tema individual o utilizar la función de etiquetado masivo para aplicar varias etiquetas a varios temas, a un mapa DITA o a un submapa. También puede cambiar el estado del documento de todos los temas seleccionados al siguiente estado común posible del documento.

<img src="assets/web-editor-metadata-panel.png" alt="administrar metadatos" width="600">

**Generación del informe Multimedia**

Puede generar el informe multimedia que contiene información detallada sobre el contenido multimedia utilizado en sus referencias dentro del mapa actual. Tiene la flexibilidad de filtrar y ordenar los archivos multimedia enumerados en el informe.
También puede generar el CSV para descargar la instantánea actual de los elementos multimedia utilizados en el mapa DITA.

<img src="assets/web-editor-reports-multimedia.png" alt="informe multimedia" width="600">

## Experiencia de usuario modificada para la funcionalidad de revisión

AEM Ahora, las guías de usuario de proporcionan un UX mejorado que le ayuda a revisar los temas compartidos para su revisión. En la experiencia más reciente, la funcionalidad de revisión presenta las siguientes mejoras:

* Interfaz de usuario actualizada
* Panel Condiciones que le permite resaltar el contenido según las condiciones disponibles en el tema
* Cada comentario del panel de comentarios está vinculado al texto correspondiente del tema actual. Ayuda a identificar el texto comentado.
* Los comentarios se muestran en el orden del texto comentado en el documento.
* El nombre de la tarea de revisión se muestra en el flujo de trabajo de revisión.
* Seleccione el mapa de raíz para la tarea de revisión que se utiliza para resolver todas las referencias clave y los términos del glosario utilizados en el contenido de la revisión.
* Barra de herramientas contextual que le ayuda a resaltar o tachar texto rápidamente
* Menú Opciones para editar o eliminar sus propios comentarios
* Para los comentarios obsoletos, tiene acceso a la vista en paralelo que le ayuda a comparar la versión anterior del tema con la versión de revisión actual.
* Al utilizar los filtros, los comentarios del panel derecho se filtran según la selección y el número de comentarios del panel izquierdo se actualiza en consecuencia.


  <img alt="revisar tarea" src="assets/comment-pop-up-panel.png" width="600">



## Mejoras de traducción

Ahora tiene mejoras más fáciles de usar en el panel de traducción que le ayudan a traducir fácilmente sus documentos desde el Editor web.

**Pasar la etiqueta de versión a la versión de destino**

AEM Guías de le permite pasar la etiqueta del archivo de origen al archivo de destino. Esto le ayuda a identificar fácilmente la versión de origen del archivo traducido.

<img alt="etiquetas de traducción" src="assets/translation-pass-source-label.png" width="600">

Por ejemplo, si tiene algunos archivos de origen con la etiqueta de versión Release 1.0 aplicada a ellos, también puede pasar la etiqueta de origen (Versión 1.0) al archivo traducido.

**Forzar sincronización de recursos sin sincronizar**

AEM Si realiza cambios en algunos de los recursos, Guías de recursos los marca como Desincronizados. Puede volver a traducir los recursos modificados o elegir descartar el estado Fuera de sincronización. Por ejemplo, si ha realizado algunos cambios menores que realmente no necesitan traducción, puede marcar su estado como Sincronizado.

<img src="assets/translation-version-diff.png" alt="comité de traducción" width="600">

**Ver proyectos de traducción en curso de un tema o mapa**

Algunas de las referencias del panel de traducción pueden estar en curso. AEM Ahora, Guías de proporciona una función que le ayuda a ver la lista de todos los proyectos de traducción en curso (junto con el idioma de destino) que contienen la referencia seleccionada.


## Generar resultados en varios formatos desde el editor web

Ahora puede generar fácilmente el resultado de sus temas o mapa DITA desde el Editor Web. AEM Puede configurar varios ajustes preestablecidos de salida, como Sitio de la aplicación, PDF, HTML 5, JSON (un formato de salida sin encabezado) y salida personalizada. A continuación, puede utilizarlas para generar los resultados respectivos.

Puede definir atributos en los temas DITA y, a continuación, utilizar el ajuste preestablecido de condición para aplicar una condición al publicar la salida. También se puede utilizar la función de publicación Línea base para publicar selectivamente una versión específica del tema o mapa DITA.


## Buscar y reemplazar el texto en el nivel de mapa

AEM Guías de le permite buscar archivos dentro de un mapa que contengan texto específico. El texto buscado se resalta en los archivos. Ahora también puede reemplazar la palabra o frase buscada por otra palabra o frase dentro de todos los archivos. Puede seleccionar **Reemplazar todo** en la parte superior derecha de la lista para reemplazar todas las ocurrencias del término buscado en todos los archivos.

<img src="assets/map-find-replace.png" alt="mapa buscar reemplazar" width="600">

## Eliminar y duplicar archivos del panel del repositorio

Ahora puede crear fácilmente un duplicado o una copia de un archivo desde el **Opciones** menú del archivo seleccionado en el panel repositorio. De forma predeterminada, el archivo se crea con un sufijo (como `filename_1.extension`).

<img src="assets/options-menu-repo-view-file-level.png" alt="menú opciones de archivo " width="500">


## Otras mejoras del editor web

* AEM En Guías de la, puede realizar algunas operaciones comunes para imágenes y archivos multimedia mediante el menú contextual. Ahora también puede localizar la imagen o el medio seleccionado en el repositorio o ver la vista previa del archivo en la interfaz de usuario de Assets.

* El nombre del perfil de carpeta actual se muestra como una etiqueta para el icono Preferencias de usuario en la barra de herramientas principal. Esto le ayuda a identificar el perfil de carpeta en el que está trabajando.

* Cuando se abre un mapa en la vista de mapa, el título del mapa actual se muestra en el centro de la barra de herramientas principal. Esto resulta útil para que los usuarios sepan qué mapa está abierto actualmente.


## Ver el título en lugar del UUID en el editor de oxígeno

AEM Ahora, Guías de le permite elegir **Uso del título en el editor y el administrador de mapas** en Configuración. Si selecciona esta opción, el título del fichero se mostrará en la ficha del fichero cuando se abra en el Editor o en el Administrador de mapas DITA. Si no selecciona esta opción, el UUID del archivo se muestra en la pestaña del archivo.

## AEM Publicación basada en microservicios para Guías de as a Cloud Service

AEM El nuevo microservicio de publicación le permite ejecutar grandes cargas de trabajo de publicación simultáneamente en guías de publicación as a Cloud Service y aprovechar la plataforma Adobe I/O Runtime sin servidor líder del sector.

AEM Para cada solicitud de publicación, Guías de publicación ejecuta un contenedor as a Cloud Service que se adapta horizontalmente según las solicitudes de los usuarios. Esto le permite ejecutar varias solicitudes de publicación y obtener un rendimiento mejorado.

Para obtener más información, consulte [AEM Configuración de una nueva publicación basada en microservicios para guías de la aplicación de la as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/publishing/configure-microservices.md).

## PDF nativo | Añadir un marcador personalizado en la salida del PDF

Ahora puede agregar un marcador personalizado a un contenido en particular en la salida final del PDF para facilitar la navegación. Se añadirá al índice creado a partir de los títulos de temas o secciones del mapa DITA.

## PDF nativo | Aplicar un estilo personalizado a las entradas del índice y al contenido del tema

AEM Guías de proporciona la función para aplicar un estilo personalizado en las entradas de la tabla de contenido o en un tema concreto de la salida del PDF. Por ejemplo, puede cambiar el color del texto de la tabla de contenido y el título del tema. También puede aplicar estilos a todo el contenido dentro del tema.


## PDF nativo | Aplicar estilo al marcador de página en el componente de nota al pie

Ahora puede aplicar estilo al marcador de página en las notas al pie. Por ejemplo, puede agregar corchetes o cambiar su color. Estos estilos ayudan a los usuarios a identificar fácilmente los marcadores de página del documento.

## PDF nativo | Cambiar barra para indicar los temas cambiados en la tabla de contenido

Ahora, las guías del PDF le permiten identificar rápidamente los temas modificados en la tabla de contenido de la salida del AEM.  Muestra una barra de cambios a la izquierda de los temas modificados en el índice. Puede hacer clic en el tema del índice y ver los cambios detallados.

<img src="assets/change-marker-toc.png" alt="Cambiar marcador en TDC " width="500">
