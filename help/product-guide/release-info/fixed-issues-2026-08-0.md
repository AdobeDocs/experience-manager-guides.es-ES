---
title: Notas de versión | Se han corregido problemas en la versión 2026.08.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2026.08.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 6872e4298df8e51a3c46845793d4dad23f92eddb
workflow-type: tm+mt
source-wordcount: '1200'
ht-degree: 1%

---

# Se han corregido problemas en la versión 2026.08.0

Este artículo cubre los errores corregidos en las distintas áreas de la versión 2026.08.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas características y mejoras, vea [Novedades de la versión 2026.08.0](whats-new-2026-08-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2026.08.0](upgrade-instructions-2026-08-0.md).

## Creación

- Los temas no se pueden abrir en el Editor cuando se accede a ellos desde Informes de temas en el Panel de mapas. (GUIDES-45277)


## Editor 2.0

- Cuando una ecuación de MathML se inserta como `conref`, no se representa correctamente. (GUIDES-46601)
- Si se copia y pega `<keywords>` dentro de `<topicmeta>` dentro de `<keydef>` o `<topicref>`, las palabras clave se insertan dentro de etiquetas externas no deseadas. (GUIDES-45800)
- El uso de `Ctrl+click` en un vínculo roto en un editor de mapas déclencheur un error de aplicación. (GUIDES-45544)
- Al copiar una tabla de una hoja de cálculo de Excel y pegarla en el nuevo editor, todo el contenido de las celdas copiadas se coloca en una sola celda de tabla en lugar de distribuirse entre las celdas correspondientes. (GUIDES-47435)
- Un botón **Exportar como PDF** personalizado configurado a través de `editor_toolbar.json` se procesa y se puede hacer clic en él en el modo de vista previa, pero no realiza ninguna acción cuando se hace clic en él. (GUIDES-47402)
- Los elementos de MathML y SVG no representan su conjunto completo de atributos, lo que provoca que las clases CSS personalizadas y los atributos condicionales aplicados a estos elementos se rompan. (GUIDES-46371)
- Al abrir ciertos temas que contienen tablas, se agrega una etiqueta `<foreign>` inesperada con dos columnas nuevas, incluso cuando no se realizaron cambios en el tema. (GUIDES-46748)
- El atributo **Scale** no se aplica a las imágenes en la vista Autor. (GUIDES-45996)
- Si arrastra y suelta un elemento que contiene `keyref`, el valor `keyref` se convierte en una ruta de acceso absoluta. (GUIDES-45701)
- Al insertar un elemento en la posición `tgroup`, se muestra una advertencia **#text no se permite aquí**, lo que impide que se inserte una tabla normal en esa posición. (GUIDES-47446)
- Los términos alfanuméricos agregados al diccionario siguen marcados por el corrector ortográfico de AEM en lugar de ignorarse. (GUIDES-48587)

## Administración de recursos

- El procesamiento masivo de recursos incluye incorrectamente los recursos de fragmentos de contenido, lo que provoca registros de errores y errores en los informes de procesamiento. (GUIDES-47085)
- En el panel Mapa, los temas secundarios no se cargan y el icono de expansión desaparece cuando la casilla de verificación de asignación está seleccionada y no seleccionada repetidamente. (GUIDES-43546)

## Publicación

**AEM Sites**

Al publicar la salida de AEM Sites mediante la asignación de componentes compuestos:

- Se muestra una **lista de temas** en blanco cuando se usa una nueva línea de base en el ajuste preestablecido de AEM Sites con asignación de componentes compuestos. (GUIDES-46480)
- Los vínculos de referencia cruzada (`xref`) a recursos que no son DITA, como PDF, ZIP, DOCX y archivos de imagen, no se resuelven correctamente, por lo que se rompen los vínculos en la página generada. (GUIDES-44108)

Al publicar la salida de AEM Sites mediante la asignación de componentes heredados:

- Los nombres de archivo que no estén en inglés en los nombres de página generados se reemplazan con guiones, lo que dificulta la identificación del tema o archivo con el que están asociados. (GUIDES-48387)

**PDF nativo**

- En la salida nativa de PDF, las referencias de temas marcadas con el atributo `toc="no"` se siguen incluyendo en la tabla de contenido, lo que da como resultado una tabla de contenido larga y desordenada. (GUIDES-37940, GUIDES-20156)

**Colecciones de mapas y activación masiva**

Los siguientes problemas se han corregido con la característica [Nueva colección de mapas](../user-guide/generate-output-use-new-map-collection-output-generation.md#use-new-map-collection-for-output-generation-beta) disponible en la versión 2020.08.0 de Experience Manager Guides:

- No se puede cargar una colección de mapas con más de 100 entradas de mapa debido a un error de red. (GUIDES-34007)
- No se pueden seleccionar varias asignaciones a la vez de una carpeta en la IU de recopilación de mapas. (GUIDES-29581)
- No se pueden buscar o filtrar colecciones de mapas en la interfaz de usuario de Colecciones de mapas. (GUIDES-27723)
- No se puede cerrar el panel de activación/publicación en lotes ni volver a **Herramientas** o la página principal sin usar el botón Atrás del explorador. (GUIDES-26797)
- Incapacidad para administrar fácilmente colecciones de mapas con un gran número de mapas o idiomas. (GUIDES-21735)
- No se puede ver ni publicar el resultado generado directamente desde las interfaces de la colección de mapas o el tablero de activación masiva. (GUIDES-18712)
- No se puede usar una sola colección para generar y activar asignaciones, ya que las colecciones de mapas y el tablero de activación masiva administran conjuntos de colecciones independientes. (GUIDES-12730)

## Revisión

- En la IU de revisión, la lista de etiquetado muestra todos los usuarios de la tarea de revisión, lo que dificulta la selección del usuario correcto en un comentario o respuesta. (GUIDES-33420)
- Al abrir la vista **en paralelo** en el panel Comentarios, se muestra la copia de trabajo junto a la versión comentada, pero los paneles no se desplazan en sincronización horizontal y al hacer clic en un comentario no se mueve el cursor al texto correspondiente. (GUIDES-44083)

## Base de datos

- `DatabaseConfiguratorService` genera un error en los registros aunque no esté configurado o habilitado. (GUIDES-43481)

## Problemas conocidos

Adobe ha identificado los siguientes problemas conocidos para la versión 2026.08.0:

## Creación

- Si se cierra un archivo DITAVAL que se haya movido a una ubicación diferente, aparecerá un mensaje de error `ERROR IN FETCHING VERSION DETAILS`. (GUIDES-51420)
- La API de conflicto falla y provoca un error de aplicación cuando la ruta de la carpeta del repositorio termina con una barra diagonal. (GUIDES-51006)

## Editor 2.0


- Al seleccionar un elemento de instrucción de procesamiento en la vista Esquema, se resalta toda la etiqueta principal en lugar del elemento seleccionado. (GUIDES-48318)
- Si edita una palabra clave dentro de un(a) `keyref` en la vista de origen, se interrumpe la palabra clave cuando la vista cambia a cualquier otra vista. (GUIDES-49998)
- Una ecuación de MathML incluida en un bloque `foreign` y `equation` genera un espaciado no deseado, y escribir dentro de la ecuación causa problemas incluso después de ajustar la sangría. (GUIDES-46606)
- No se puede colocar un cursor dentro de un(a) `topicref` dentro de un(a) `reltable` cuando la opción **Mostrar etiquetas** está habilitada y la opción **Mostrar atributos** está deshabilitada en la configuración del Editor. (GUIDES-46565)

- Espacio en blanco introducido inmediatamente antes de que se elimine una etiqueta en línea dentro de una celda de tabla `<entry>`. (GUIDES-49144)

## Publicación

- Si se selecciona **Ver salida** después de generar la salida de Edge Delivery Services, se abre una dirección URL `hlx.live` que devuelve un error 403 prohibido en lugar de la dirección URL `aem.live`. (GUIDES-51572)
- Los componentes no válidos se muestran en la página `common.plt` al agregar una imagen, un hipervínculo o un iframe desde la barra de herramientas de una plantilla. (GUIDES-51165)
- Al publicar un mapa que hace referencia a un tema mediante el atributo `copy-to`, se quita el vínculo de ámbito de igual a igual del tema correspondiente en el mapa de origen. (GUIDES-50701)
- Cuando se hace referencia a un PDF como `xref` con el ámbito establecido en `Peer`, se publica en el sitio de AEM (mediante asignación de componentes heredados) en lugar de proceder del mapa cruzado. (GUIDES-50213)

**Colecciones de mapas**

- La eliminación de una colección de mapas a veces falla si cambia de pestaña (como Repositorio o Información general) y vuelve a la página Colección de mapas antes de eliminarla. (GUIDES-50997)
- Al generar el mismo ajuste preestablecido mientras una generación anterior está en curso, ya no se muestra un mensaje que indique que la generación anterior está en curso. (GUIDES-50523)
- La marca de tiempo de la última generación no se muestra ni se actualiza en la IU de recopilación de mapas después de generar un mapa y, si se vuelve a añadir un ajuste preestablecido que se eliminó anteriormente, se vuelve a perder su historial de generación. (GUIDES-50511)
- La publicación desde el **Historial de generación** siempre publica el último resultado de un ajuste preestablecido en lugar de la generación seleccionada. (GUIDES-50508)
- El estado de publicación no se actualiza automáticamente para las colecciones de mapas recién creadas. (GUIDES-50367)

## Traducción

- Al iniciar una traducción con la opción **Crear solo estructura** se devuelve un error. (GUIDES-51261)

## Revisión

- Al tachar mediante un método abreviado de teclado el texto que incluye contenido condicional oculto, también se tachará el contenido oculto. (GUIDES-49837)


