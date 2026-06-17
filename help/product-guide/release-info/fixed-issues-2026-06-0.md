---
title: Notas de versión | Se han corregido problemas en la versión 2026.06.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2026.06.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 010a11e20d518064549ce7d66648586f49f572ec
workflow-type: tm+mt
source-wordcount: '2174'
ht-degree: 0%

---

# Se han corregido problemas en la versión 2026.06.0

Este artículo cubre los errores corregidos en varias áreas de la versión 2026.06.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas características y mejoras, vea [Novedades de la versión 2026.06.0](whats-new-2026-06-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2026.06.0](upgrade-instructions-2026-06-0.md).

## Creación

- Al alternar el enfoque entre los campos **Width** y **Height** del cuadro de diálogo de propiedades de la imagen con tamaños basados en unidades como `in`, `mm` o `px`, los valores siguen aumentando gradualmente en lugar de permanecer estables. (GUIDES-45929)

## Editor 2.0

- Si se copia y pega `<keywords>` dentro de `<topicmeta>` dentro de `<keydef>` o `<topicref>`, las palabras clave se insertan dentro de etiquetas externas no deseadas. (GUIDES-45800)
- Las dimensiones de imagen especificadas con unidades como `mm` no se representan correctamente, lo que hace que las imágenes se muestren en su tamaño original en lugar de las dimensiones especificadas. (GUIDES-46275)
- Al arrastrar y soltar con la Vista de etiquetas habilitada, la selección de contenido junto con etiquetas XML o DITA parciales deja etiquetas huérfanas no deseadas, lo que da como resultado contenido o vista incorrectos. (GUIDES-28191)
- En la Vista de etiquetas de una tabla, al pulsar la tecla de flecha hacia arriba cuando el cursor se coloca en la celda directamente debajo de una etiqueta de entrada contraída, se omite la etiqueta contraída y se mueve el cursor al principio del documento. (GUIDES-45408)
- Al realizar cualquier operación desde la barra de herramientas contextual de la tabla, se cierra la barra de herramientas inesperadamente, interrumpiendo las siguientes operaciones de la tabla. (GUIDES-45405)
- Después de usar **Insertar después** o **Insertar antes** desde la vista Esquema o ruta de exploración, el cursor se mueve a una posición arbitraria en lugar de dentro de la etiqueta recién agregada. (GUIDES-45147)
- Cuando la opción **Editar MathML** se muestra incorrectamente en modo de solo lectura o cuando otro usuario desprotege un archivo, permite a los usuarios actualizar el contenido de MathML aunque el archivo no deba poder editarse. (GUIDES-45172)
- Al eliminar un comentario XML mediante la tecla de retroceso, la etiqueta de comentario no se elimina después de eliminar su contenido, y la operación de eliminación continúa en el elemento anterior. (GUIDES-45240)
- Al usar la opción **Copiar ruta** o **Copiar UUID** para las imágenes, se devuelve la ruta de representación completa en lugar de la ruta de recursos original. (GUIDES-45278)
- Copiar y pegar contenido en el mismo tema en una ubicación no válida del editor inserta una etiqueta `<foreign>` no deseada. (GUIDES-45378)
- En Windows, al copiar y pegar una fila de tabla se agregan atributos inesperados como `data-pm-slice` al elemento de tabla, lo que provoca errores de marcado que impiden guardar el documento. (GUIDES-45784)
- Si se usa la opción **Copiar** del menú contextual en un mapa o tema y, a continuación, se pega el contenido, se insertan etiquetas `<data>` adicionales en el resultado pegado. (GUIDES-45703)
- Al arrastrar una selección parcial desde un elemento `cmd`, el contenido no se puede soltar entre el texto existente o al final de otro elemento `cmd`. (GUIDES-44883)
- Al aplicar un atributo `scale` a una tabla, la tabla no se representa con el tamaño configurado en los modos Autor y Vista previa. (GUIDES-45984)
- Al pegar imágenes copiadas de fuentes externas como Paint o la Herramienta de recorte, no se inserta la imagen en el tema. (GUIDES-45983)
- El elemento `keyref` utilizado en un título de tema derivado de un mapa de palabras clave no aparece en la tabla de contenido o en la ficha de tema después de guardar, ni siquiera después de actualizar el explorador. (GUIDES-45799)
- Al abrir una tarea de revisión en el Editor mediante la vista en paralelo para la versión comentada, se muestra la versión como Ninguno en lugar de la versión asociada para el tema. (GUIDES-45127)
- Al acceder a la página de tareas Revisar, no se muestran los saltos de página entre los temas, lo que da como resultado una representación continua de las secciones de contenido. (GUIDES-46777)
- El estilo de la página de revisión no es coherente con la experiencia del nuevo editor, lo que da como resultado una experiencia visual incoherente (GUIDES-46061)

## Administración de recursos

- Cuando un mapa contiene un(a) `topicref` externo que señala a un recurso no DITA (como `.html`), su vista previa no se muestra en la interfaz de usuario de Assets. (GUIDES-45409)
- El cuadro de diálogo Herramienta de movimiento masivo se desborda y carece de una barra de desplazamiento cuando se selecciona un gran número de carpetas de origen, lo que hace que el campo de ruta de destino y los botones de acción no sean accesibles para los usuarios que solo utilizan el ratón. (GUIDES-45805)
- Cuando el recurso se copia desde la interfaz de usuario de Assets, se recibe una notificación para `DXML reprocessing failure`. Esta notificación es engañosa y contribuye al desorden de la bandeja de entrada, ya que la copia se ha realizado correctamente. (GUIDES-45012)
- Al abrir el panel Filtro en el carril izquierdo de Assets dentro de una carpeta, el campo de búsqueda y las facetas permanecen desactivados hasta que se cierra y se vuelve a abrir el panel. (GUIDES-42652)
- Los fragmentos de contenido y los recursos de traducción intermedios creados durante los flujos de trabajo de traducción se procesan de forma involuntaria mediante el trabajo de procesamiento de recursos programado, lo que provoca excepciones en los registros y un procesamiento incorrecto de recursos que aún no están listos. (GUIDES-42582)

## Publicación

- Al trabajar con `.plt` y `.css` archivos en plantillas de PDF, la opción **Generar ID** está disponible en el menú contextual que se muestra al hacer clic con el botón secundario a pesar de que no es aplicable a estos tipos de archivo. (GUIDES-45254)
- El botón **Guardar** está habilitado incorrectamente de forma predeterminada al volver a abrir un ajuste preestablecido de AEM Sites nativo recién creado después de una actualización del explorador, incluso cuando no se han realizado cambios. (GUIDES-45171)
- Al duplicar un ajuste preestablecido de PDF nativo marcado como predeterminado, el duplicado también se establece como ajuste preestablecido predeterminado. Solo se debe designar un ajuste preestablecido como predeterminado a la vez. (GUIDES-44786)
- El atributo `outputclass` no se propaga a la salida generada de HTML o Native PDF, lo que impide que las clases personalizadas aplicadas a las ecuaciones de MathML afecten a la salida procesada. (GUIDES-44393)
- La activación masiva de la salida de AEM Sites generada con la nueva plantilla de AEM Sites producía un error que impedía la replicación correcta en la instancia de publicación. (GUIDES-44049)
- Se han identificado los JAR `jackson-databind` vulnerables (versión 2.9.8) agrupados con AEM Guides en el paquete DITA-OT. (GUIDES-43081)
- Al abrir cualquier salida nativa de AEM Sites desde una colección de mapas, se produce un error que indica que no se encuentra el recurso y evita el acceso a la salida generada. (GUIDES-42065)
- El elemento `<reltable>` de un mapa DITA se omite durante la generación nativa de PDF, lo que provoca que falten en la salida &quot;Conceptos relacionados&quot;, &quot;Tareas relacionadas&quot; y secciones de referencias cruzadas generadas automáticamente similares. (GUIDES-38333)
- Al publicar un mapa DITA con `processing-role=resource-only` elementos en AEM Sites (con asignación de componentes heredados), se generan páginas de sitio huérfanas para esos elementos en escenarios adicionales como `topicgroup` elementos y configuraciones de contenido específicas. (GUIDES-37650)
- Cuando se agrega un mapa con un nombre largo a una colección de mapas, la interfaz de usuario de la colección de mapas se representa con un diseño distorsionado. Este problema se ha resuelto con la colección New maps. (GUIDES-42062)
- Publicación con el motor nativo de PDF v1:
   - Al generar una salida nativa de PDF para determinado contenido, solo se procesa la primera página en PDF, a pesar de que la HTML intermedia contenga el contenido completo en varias páginas. (GUIDES-28270)
   - El orden de lectura del contenido en la salida nativa de PDF con la configuración de accesibilidad habilitada es incorrecto. Los números de página de los pies de página se leen antes del contenido principal en lugar de al final. (GUIDES-27790)
   - La barra de color de la salida nativa de PDF no se extiende por el ancho de página completo y se superpone cuando se personaliza el tamaño de página, lo que provoca que algunos cuadros de color se oculten. (GUIDES-15505)
   - El selector de pseudoclase `:is()` de CSS no se cumple en la salida nativa de PDF, lo que da como resultado diferencias de estilo en comparación con la representación del explorador. (GUIDES-11328)

  >[!NOTE]
  >
  > Los problemas mencionados se han resuelto con el motor nativo de PDF v2. Para obtener más información, vea [Trabajar con el motor de PDF nativo v2](../native-pdf/new-pdf-engine.md).

## Traducción

- La aplicación de una línea de base a una asignación con muchos recursos retrasa la carga del informe de traducción para el idioma seleccionado, a veces conduce al tiempo de espera de solicitud antes de que se procese el informe. (GUIDES-45508)
- Los grupos de idiomas de la ficha Traducción en Configuración de Workspace no se conservan cuando la carpeta de idioma seleccionada utiliza un código de configuración regional con guiones (por ejemplo, `da-DK`) en lugar de un formato de guion bajo (`da_dk`). (GUIDES-37843)

## Revisión

- Falta la información sobre herramientas del icono **Historial de versiones** en el panel izquierdo de la interfaz de usuario de revisión junto al nombre del tema. (GUIDES-45511)
- Al editar una tarea de revisión activa, si se quita un tema que ya forma parte de la revisión y, a continuación, se vuelve a agregar sin seleccionar **Actualizar**, se pierde la información del revisor para ese tema. (GUIDES-38774)
- El panel de contenido de la IU de revisión muestra una barra de desplazamiento horizontal en determinadas resoluciones de pantalla, incluida la resolución recomendada de 1600 píxeles, lo que provoca que los comentarios de revisión se oculten cuando el contenido se extiende más allá de la anchura del panel. (GUIDES-44082)

## Contenido de aprendizaje

- Al añadir preguntas a una prueba utilizando la opción Insertar del banco de preguntas, las preguntas de respuesta corta no aparecen a pesar de tener un ID de pregunta válido. (GUIDES-44942)
- Al insertar preguntas utilizando la opción Insertar desde el banco de preguntas, el diálogo Insertar desde el banco de preguntas parpadea o cambia de tamaño inesperadamente al abrir. (GUIDES-45524)
- Al insertar preguntas utilizando la opción Insert from question bank, se produce un error si el título de la pregunta contiene una imagen. (GUIDES-45383)
- Si se selecciona una plantilla de salida SCORM, se produce un error de aplicación cuando se modifica el título de la plantilla. (GUIDES-45521)
- Los archivos de subtítulo (`.vtt`) no son visibles en la vista Repositorio o Explorador después de cargarse en una carpeta. (GUIDES-46014)
- Al cargar contenido de vídeo en la vista previa de HTML, la ruta de origen (`src`) incluye una ruta de representación anexada en lugar de conservar la ruta de acceso del archivo original, lo que impide que el vídeo se represente correctamente. (GUIDES-41776)
- La publicación de la salida SCORM desde el explorador Safari hace que el paquete se descargue como una carpeta en lugar de un archivo zip, junto con problemas de procesamiento y funcionalidad en el contenido generado (por ejemplo, contenido estirado, acordeón no funcionando y más). (GUIDES-45119)
- Se observa un retraso antes de activar el botón Siguiente en los cursos, lo que afecta a la experiencia de navegación del alumno. (GUIDES-45113)
- El estilo de pregunta de respuesta corta se representa incorrectamente en la salida de publicación a pesar de mostrarse correctamente en la previsualización. (GUIDES-46478)
- Al generar la salida de PDF para cursos que contienen vídeos, el contenido del vídeo no se procesa y solo se muestra la ruta del archivo en lugar de una imagen de marcador de posición como una miniatura de vídeo o una imagen de póster. Este problema se ha resuelto habilitando la opción **Incrustar archivos multimedia** en el ajuste preestablecido de salida nativo de PDF.(GUIDES-45117)
- Las pseudoclases y los elementos CSS se representan en blanco en el Editor de la guía, lo que las hace invisibles o difíciles de leer contra el fondo del editor. (GUIDES-45116)

## Problemas conocidos

Adobe ha identificado los siguientes problemas conocidos para la versión 2026.06.0:

## Editor 2.0

- El cambio entre los modos Source y Autor causa incoherencias en el contenido, con partes del tema que desaparecen o no se reflejan en los distintos modos. (GUIDES-47432)

- Al trabajar en la vista Esquema con **Control de cambios** habilitado, al rechazar un cambio se quita todo el contenido de la etiqueta en lugar de rechazar únicamente el contenido modificado específico. (GUIDES-48319)

- El botón **Exportar como PDF** en el modo de vista previa no realiza ninguna acción cuando la barra de herramientas del editor se personaliza con `editor_toolbar.json` en un perfil de carpeta. (GUIDES-47525)

- Al realizar operaciones de eliminación, pueden producirse algunas incoherencias menores en el movimiento y la navegación del cursor en los mapas de imagen, los elementos estructurados, las etiquetas de formato en línea y los bloques no combinables, lo que a veces provoca un comportamiento inesperado del cursor o la eliminación. (GUIDES-46756)

- El uso de `Ctrl+click` en un vínculo roto en un editor de mapas déclencheur un error de aplicación. (GUIDES-45544)

- Si presiona la barra espaciadora al principio de un párrafo inmediatamente después del contenido de solo lectura (como un párrafo de `conref`), puede eliminar o combinar inesperadamente el párrafo editable, lo que provocará la eliminación inesperada del párrafo editable. (GUIDES-45049)

- Cuando se aplican indicadores de condición a elementos como `bodydiv`, los indicadores se desbordan hasta las etiquetas adyacentes en la Vista de etiquetas completas, lo que da como resultado una representación visual incorrecta. (GUIDES-44971)

- Al trabajar en el Editor, no puede seleccionar `keyrefs` o claves derivadas de mapas (incluidas las entradas del glosario dentro de los mapas a los que se hace referencia en `term` o `abbreviated-form` elementos), lo que provoca una experiencia de creación degradada. (GUIDES-45790) <br> **Solución alternativa**: puede cambiar el valor de `keyref` desde el panel derecho usando los valores de atributos.

- En la vista Esquema, volver a habilitar **Mostrar texto** después de cerrar y volver a abrir un tema no muestra texto junto a las etiquetas de elementos. (GUIDES-48320) <br> **Solución alternativa**: habilite la opción **Mostrar texto** y vuelva a abrir el tema. Después de volver a abrir, el texto se muestra correctamente junto a las etiquetas de elemento.

- Cuando se cambia el nombre de una etiqueta en línea mediante la opción **Rename element**, la ruta de exploración no se actualiza inmediatamente y refleja el cambio solo después de que el cursor se mueva a la etiqueta o de que se cambie el modo de vista. (GUIDES-44993) <br> **Solución alternativa**: actualice el explorador después de cambiar el nombre de la etiqueta en línea para actualizar la ruta de exploración.

- Cuando una ecuación de MathML se inserta como `conref`, no se representa correctamente. (GUIDES-46601) <br> **Solución alternativa**: ajuste la ecuación de MathML dentro de un elemento `<p>` y use ese elemento `<p>` como origen de referencia.

## Revisión

- Cuando se reasigna una tarea de revisión a un usuario fuera del equipo del proyecto, el usuario puede realizar acciones de revisión a pesar de que no sea miembro del proyecto, mientras que la visibilidad del revisor, el seguimiento del estado de la revisión y las notificaciones de delegación no funcionan correctamente. (GUIDES-46602)

## Publicación

- Al publicar contenido con un filtro DITAVAL que excluye todos los elementos de lista con viñetas mediante perfiles condicionales, la salida retiene incorrectamente un marcador de viñeta vacío en lugar de eliminar toda la estructura de la lista. (GUIDES-47238)

- Al publicar un resultado de sitio AEM nativo con una nueva línea de base, la lista de temas aparece en blanco y no muestra los temas incluidos en la línea de base seleccionada. (GUIDES-46480) <br> **Solución alternativa**: publique el resultado nativo del sitio de AEM usando la línea de base antigua, que se puede configurar mediante el administrador de configuración.





