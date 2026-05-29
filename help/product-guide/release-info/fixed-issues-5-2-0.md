---
title: Notas de versión | Se han corregido problemas en la versión 5.2.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 5.2.0 de Adobe Experience Manager Guides.
source-git-commit: 5eee826022f798b4eb0014ea4b97d2916eb92f33
workflow-type: tm+mt
source-wordcount: '3559'
ht-degree: 0%

---

# Se han corregido problemas en la versión 5.2.0 (mayo de 2026)

Este artículo trata sobre los errores corregidos en varias áreas de la versión 5.2.0 de Adobe Experience Manager Guides.

Para obtener más información acerca de las nuevas características y mejoras, vea [Novedades de la versión 5.2.0](whats-new-5-2-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 5.2.0](upgrade-instructions-5-2-0.md).


## Creación

- Si se agrega un elemento `prop` vacío sin atributos ni valores a un archivo DITAVAL, no se podrán agregar elementos `prop` adicionales. (GUIDES-33597)
- Después de actualizar Experience Manager Guides a la versión 2025.08.0, la opción de habilitar o deshabilitar la ficha **Acrolinx** personalizada ya no aparece en **Configuración de Workspace**. (GUIDES-35261)
- CSS personalizado aplicado en un perfil de nivel de carpeta para temas o asignaciones se revierte al estilo predeterminado en el modo de Vista previa al actualizar el explorador. (GUIDES-31098)
- Las operaciones **Deshacer** y **Rehacer** no funcionan según lo esperado en la vista Source del Editor para archivos DITA. (GUIDES-24914, GUIDES-25034)
- Al hacer referencia a un mapa DITA en un tema utilizando el elemento `Xref`, se muestra el nombre de archivo del mapa al que se hace referencia en lugar del título del mapa. (GUIDES-21759)
- Al agregar varios archivos de Schematron para su validación a través del panel derecho de la interfaz del Editor, se muestra un error **Los archivos de Schematron no existen o tienen errores** aunque los archivos agregados sean válidos y no tengan errores. (GUIDES-33731)
- Las ecuaciones de MathML grandes o complejas no se muestran en el Editor. (GUIDES-29095)
- Cuando hay varios temas o mapas DITA abiertos y uno de los temas está cerrado, el botón **>** que muestra todas las pestañas abiertas se superpone con las pestañas abiertas restantes de la barra de pestañas. (GUIDES-31421)
- Con el **flujo de trabajo de aprobación** habilitado, el botón **Iniciar una nueva versión** no está visible en la barra de herramientas del Editor si el panel izquierdo y el panel de propiedades de contenido están abiertos. (GUIDES-29093)
- Cuando los nombres de fragmento superan la anchura del panel de fragmento, se ajustan incorrectamente en la línea siguiente, lo que da como resultado una superposición con fragmentos adyacentes y afecta a la legibilidad. (GUIDES-22685)
- Cuando se agrega la misma referencia varias veces a un mapa DITA, la vista **Map** muestra el título únicamente de la última ocurrencia, mientras que las anteriores muestran el UUID de la referencia. (GUIDES-9699)
- Los archivos DITAVAL siguen siendo editables, incluso cuando están bloqueados por otro usuario o cuando el servidor tiene **Deshabilitar la edición sin bloquear el archivo** habilitado y el archivo se abre en modo de solo lectura. (GUIDES-27754)
- Los registros de los nodos que faltan se generan a partir de trabajos de limpieza interna que no son necesarios y se marcan incorrectamente como errores, lo que da como resultado archivos de registro agrupados. (GUIDES-31765)
- Al editar un archivo de Schematron (`*.sch`) y utilizar la característica Buscar y reemplazar, el panel Buscar y reemplazar aparece parcialmente fuera de la pantalla en la parte inferior, lo que impide el acceso a sus campos y controles de entrada. (GUIDES-38412)
- No se pueden agregar varias **etiquetas de versión** a un tema desde el cuadro de diálogo **Guardar como nueva versión**. (GUIDES-32716)
- Al seleccionar una imagen en el Editor mediante el cuadro de diálogo **Seleccionar archivo**, solo se muestran los formatos de trama (como JPG, PNG y GIF). Los archivos vectoriales (como .ai y .eps) no se muestran y no se pueden seleccionar. (GUIDES-45110)
- En el momento de la actualización, la configuración `tagsView` está desactivada de forma predeterminada, aunque su valor predeterminado en `ui_config.json` esté establecido en `true`. (GUIDES-44651)
- En el Editor, las referencias de archivo se muestran como GUID en lugar de como rutas de archivo a pesar de la configuración de `xmleditor.uuid`. (GUIDES-42438)
- Cuando se aplican esquemas de asunto con valores de clave similares en un tema DITA, se resaltan con colores casi idénticos, lo que dificulta su distinción e identificar qué esquema se aplica. (GUIDES-38472)
- Al editar una asignación de esquema de asunto en la vista de autor, al agregar el elemento `hasInstance` se déclencheur automáticamente el cuadro de diálogo de selección de archivos, lo que requiere que los autores inserten un elemento `href` no deseado que apunte a un recurso de AEM. Además, el panel **Propiedades de contenido** no se puede cargar para estos mapas, lo que impide que los autores actualicen los atributos de los elementos en la vista Autor y requiere que utilicen la vista Source para actualizar los atributos. (GUIDES-38164)
- Al editar un archivo `.ditaval`, los comentarios XML agregados en la vista de Source se quitan al cambiar a la vista Autor y, a continuación, volver a la vista de Source. (GUIDES-33228)
- Al actualizar una ecuación de MathML en línea mediante la opción Editar MathML del menú contextual, el valor actualizado no se refleja hasta que se actualiza la página. (GUIDES-38198)
- Cuando un tema contiene muchos elementos reutilizables (aquellos con ID) agregados en el panel Reutilizables, es posible que algunos elementos no sean accesibles debido a la altura fija del contenedor. (GUIDES-37220)
- Al insertar una referencia cruzada en un archivo, los iconos de los mapas y los temas son idénticos. (GUIDES-36662)
- Al editar un mapa, los símbolos especiales de `navtitle` no se muestran para `topichead` en la vista Autor. (GUIDES-35435)

## Administración de recursos

- Cuando se vuelve a cargar una imagen editada a través de la interfaz de usuario de Experience Manager Guides, la representación original de la imagen se actualiza, pero el contenido DITA asociado sigue mostrando la versión anterior de la imagen. (GUIDES-33693)
- Al intentar mover dos o más carpetas desde su ubicación de origen a una ubicación diferente (mediante la herramienta de movimiento masivo), la operación falla si los nombres de las carpetas comienzan con la misma cadena (por ejemplo, Product y ProductImages). (GUIDES-29096)
- Al eliminar un recurso buscado de la interfaz de usuario de Omnisearch Assets, se omite el cuadro de diálogo de advertencia **Forzar eliminación** y se elimina directamente el recurso, incluso cuando se hace referencia a él en el contenido DITA existente. (GUIDES-17232)
- No se pudieron quitar las etiquetas Versión del panel **Historial de versiones** en la interfaz de usuario de Assets. (GUIDES-38276)
- Al crear un tema en una carpeta con espacios en su nombre, se crea incorrectamente una carpeta duplicada en la que los espacios se sustituyen por guiones y el tema se guarda allí en lugar de en la carpeta original. (GUIDES-41938)
- Durante la primera traducción de mapas grandes, se crean archivos XML vacíos para el idioma de destino, lo que aumenta la carga del servidor y ralentiza el rendimiento. (GUIDES-41613)
- En la búsqueda de Assets, los subrecursos y nodos de metadatos (como imágenes y PDF) se incluyen incorrectamente en los resultados. Además, para un ajuste preestablecido de salida cuando se aplican filtros DITAVAL, la búsqueda devuelve archivos DITAVAL generados internamente creados a partir de ajustes preestablecidos de condición. (GUIDES-35418)
- Al cargar recursos con un nombre de archivo que contiene caracteres no válidos, el recurso no se puede cargar y muestra un mensaje incorrecto **El archivo está bloqueado por otro usuario** a pesar de que el recurso está desbloqueado. (GUIDES-32680)

## Publicación

- Al publicar un mapa DITA con línea de base en AEM Sites (con asignación de componentes heredados), los elementos de mapa con el atributo `processing-role = resource-only` también se publican. (GUIDES-37649)
- En algunos casos, la propiedad `jcr:content/fmUuidOfSource` se encuentra sin aparecer en las páginas de salida de AEM Sites (con asignación de componentes heredados), lo que hace que las páginas de contenido recién creadas no se puedan detectar. (GUIDES-34242)
- El filtrado de contenido mediante filtros DITAVal y ajustes preestablecidos condicionales no funciona para la publicación en Salesforce. (GUIDES-33515)
- No se puede crear un ajuste preestablecido de PDF nativo para un mapa si existe una carpeta con el mismo nombre en su jerarquía de contenido. (GUIDES-33012)
- Cuando la salida de PDF nativa se genera usando una línea de base dinámica, el término **PDFProject** se muestra como el título de PDF en lugar del título real del mapa. (GUIDES-31102)
- La generación de resultados nativos de PDF con ciertos valores de atributo `print` en las referencias de temas no funciona como se esperaba. (GUIDES-31101)
- Cuando se mueve una carpeta que contiene asignaciones DITA mediante la interfaz de usuario de Assets o la opción **Mover masivamente**, las colecciones de asignaciones existentes y las colecciones de activación masiva que hacen referencia a esas asignaciones no se cargan. (GUIDES-28355)
- Cuando se mueve una carpeta que contiene un mapa con ajustes preestablecidos de condición, las condiciones no se aplican en la salida generada después del movimiento. (GUIDES-28352)
- Cuando se genera la salida de AEM Sites mediante la asignación de componentes heredados, los temas que utilizan el atributo `copy-to` se publican con el nombre del tema `copy-from` en lugar del nombre establecido en el atributo `copy-to`. (GUIDES-22155)
- La activación de una o más asignaciones DITA desde **tablero de publicación en lotes** genera registros excesivamente grandes. (GUIDES-20746)
- Al generar PDF, las reglas de filtrado en un archivo DITAVAL se ignoran si algún nombre de propiedad contiene un punto. (GUIDES-33229)
- La publicación en Salesforce muestra un estado correcto en la interfaz de usuario incluso cuando un mapa DITA que contiene un elemento `topichead` no puede publicar los temas incluidos en él. (GUIDES-32143)
- Para el ajuste preestablecido de salida HTML5, la funcionalidad de filtro de búsqueda no funciona en los AEM Assets para el filtrado DITAVAL, ya que los archivos correspondientes no se muestran cuando se selecciona el filtro DITAVAL. (GUIDES-28231)
- Al generar un PDF nativo para un mapa DITA con varios temas, si algún tema contiene un elemento `fig` en un elemento `figgroup` junto con un elemento `title`, el título `figgroup` se representa incorrectamente como un título de capítulo en la tabla de contenido. (GUIDES-23223)
- Al duplicar plantillas de PDF desde la interfaz de usuario de, el UUID también se duplica, lo que provoca que los archivos de plantilla se eliminen y den como resultado salidas de PDF incorrectas. (GUIDES-30456)
- Al generar PDF nativo para un mapa DITA, el título del elemento `example` se representa como `h1` nivel de encabezado, lo que produce incoherencia visual y una estructura de TDC incorrecta. (GUIDES-19958)
- Cuando se reutiliza el mismo tema en varias asignaciones con diferentes ajustes preestablecidos condicionales, la publicación de la asignación más reciente en Salesforce sobrescribe el contenido del tema, lo que da como resultado que se muestren datos incorrectos a los usuarios de asignaciones publicadas anteriormente. (GUIDES-37806)
- Al publicar un PDF nativo para un mapa que incluye procesamiento condicional o ciertas asignaciones anidadas, el `dc:title` definido en el mapa no aparece en la portada de PDF, lo que da como resultado que falta un título de portada. (GUIDES-37733)
- La generación de la salida del sitio de AEM (mediante la asignación de componentes compuestos) para un mapa falla y provoca un error cuando la variable `map_title` está presente en la ruta de salida. (GUIDES-36968)
- Cuando se especifica una ruta de salida con una barra diagonal en el ajuste preestablecido de salida nativa de PDF, la interfaz de usuario añade automáticamente una barra diagonal adicional, lo que da como resultado una ruta de doble barra que provoca que la carga de PDF falle en determinados casos. (GUIDES-34932)
- La publicación involuntaria de páginas de AEM Sites generadas a partir de contenido DITA mediante Publicación rápida o Administrar publicación publica los recursos DITA asociados. (GUIDES-27967)
- Al publicar una asignación en AEM Sites (mediante asignación de componentes heredados), las referencias cruzadas (`xrefs`) con `scope = peer` que dirigen subelementos de un tema (como párrafos) en un mapa diferente no se resuelven en el ID de elemento específico y, en su lugar, solo en el tema principal, lo que hace que la página se cargue al principio del tema en lugar de desplazarse a la sección deseada. (GUIDES-21802)
- Al publicar un mapa DITA con línea de base en AEM Sites (con asignación de componentes heredados), los elementos de mapa con el atributo `processing-role = resource-only` también se publican. (GUIDES-34298)
- Cuando los cambios en un ajuste preestablecido de salida en un perfil de carpeta se aplican a asignaciones existentes, se restablece el **contexto de publicación** guardado para el ajuste preestablecido de AEM Sites. (GUIDES-38377)
- El símbolo de marca comercial (®) no aparece en la portada de la salida de PDF nativo cuando se utiliza el elemento `tm` dentro del título de un mapa o un mapa de libros. (GUIDES-28832)
- Al publicar un mapa mediante una plantilla de PDF nativa, el **título del mapa** no incluye contenido de los elementos secundarios utilizados en el mapa `title`, y el filtrado de contenido correspondiente no se aplica al título. (GUIDES-33730)
- Los vínculos del mismo nivel de asignación cruzada en la salida de AEM Sites no se pueden resolver cuando apuntan a un(a) `topicref` que usa `chunk="to-content"`. (GUIDES-37873)
- Durante la publicación, los archivos asociados con el indicador basado en DITAVAL se mueven a una nueva carpeta generada por el sistema en lugar de permanecer en la ubicación relativa esperada en la salida. (GUIDES-37564)
- Cuando se utilizan varios archivos DITAVAL con condiciones en conflicto, la salida nativa de PDF falla. (GUIDES-37484)
- Al crear o editar un tema que incluye una cita, si el campo Autor no se agrega en el cuadro de diálogo de cita, la PDF no se genera. (GUIDES-37934)
- Al generar la salida de AEM Sites, los títulos de mapas que contienen palabras clave y títulos de temas con el elemento `<ph>` no se incluyen en la salida publicada. (GUIDES-36641)
- El archivo CSS (`rhdefault.css`) se aplica incorrectamente a la plantilla de PDF a pesar de que no se hace referencia a CSS, lo que provoca la falta de registros de errores en el archivo CSS. (GUIDES-31752)
- Al descargar archivos temporales para un mapa con una línea de base durante la publicación de un ajuste preestablecido, el archivo `metadata.xml` hace referencia incorrectamente a `versionPath` en lugar de a `dampath`.(GUIDES-29815)
- Para la salida nativa de PDF, se omite el elemento `<alt>` de las imágenes, lo que impide que se aplique texto alternativo para la accesibilidad. (GUIDES-29087)
- En la salida nativa de PDF, el elemento `abbreviated-form` muestra `glossterm` en lugar de `glossSurfaceForm` o `glossAcronym` designados. (GUIDES-26393)
- Al realizar la activación masiva, la creación del paquete agrega filtros para todas las rutas enumeradas en la propiedad `fileReference` de una página, incluidas las rutas externas y de igual a igual. (GUIDES-24887)
- Al publicar con un ajuste preestablecido personalizado con contenido que contiene vínculos a PDF sin el ámbito establecido como externo, el proceso no se completa. (GUIDES-21708)
- La publicación de Salesforce falla con un error de aplicación, cuando ya existe un tema con el mismo nombre y dirección URL. (GUIDES-32390)
- La división automática de palabras no se aplica en la salida nativa de PDF, incluso cuando el ajuste **Usar división automática de palabras** está habilitado para el ajuste preestablecido de salida. (GUIDES-19703)

## Traducción

- Al ampliar la pantalla de la interfaz de usuario de traducción, el botón **Enviar para traducción** se mueve bajo los puntos suspensivos y se activa incluso sin que se haya seleccionado ningún recurso. (GUIDES-33720)
- Al seleccionar archivos con estado **Fuera de sincronización** en la interfaz de usuario de traducción, y el ancho de la pantalla está restringido debido a que se abren los paneles Izquierdo y Derecho, la etiqueta **Enviar para traducción** se trunca. (GUIDES-33692)
- Cuando una imagen administrada inicialmente como un recurso específico del idioma con una versión específica (por ejemplo, en `/en/`) se mueve a una carpeta global con una versión actualizada y se realiza una exportación de línea de base, la nueva línea de base sigue haciendo referencia a versiones obsoletas específicas del idioma de esa imagen, lo que provoca un error en la exportación de línea de base. (GUIDES-39394)
- Al procesar proyectos de traducción creados fuera de Experience Manager Guides, se generan varios mensajes de registro de error que indican que no se encontró la propiedad *`fmTarget`*. (GUIDES-37804)

## Línea de base

- Al crear una línea de base dinámica, el editor a veces deja de responder debido a varias solicitudes de API simultáneas, lo que provoca que todas las demás operaciones se detengan. (GUIDES-39054)
- Las referencias a temas dentro de un mapa se muestran incorrectamente como indirectas cuando se utiliza una DITA-OT personalizada, aunque se haga referencia a ellas directamente. Este problema se ha resuelto con la nueva experiencia de línea de base. (GUIDES-19286)
- Las referencias con `scope="peer"` se incluyen incorrectamente en el contexto de línea de base, lo que hace que la publicación tarde más de lo esperado. Este problema se ha resuelto con la nueva experiencia de línea de base. (GUIDES-41823)


## Revisión

- Al asignar un usuario a una tarea de revisión, la lista desplegable muestra todos los usuarios, en lugar de solo aquellos asociados con los proyectos seleccionados, lo que da como resultado opciones de usuario no válidas. (GUIDES-37781)
- Cuando un revisor completa una tarea de revisión o el iniciador actualiza la tarea de revisión sin introducir comentarios, el correo electrónico de notificación enviado muestra el comentario anterior más reciente. (GUIDES-33590)

## Informes

- Al abrir un informe para un mapa, se produce un retraso en la carga del panel Filtros (GUIDES-39385)
- El informe Lista rota incluye incorrectamente vínculos externos, `keyrefs` válidos y palabras clave que se han resuelto correctamente en el ámbito del mapa actual. (GUIDES-27774)

## Plataforma

- Registros de errores que se generan al cargar un recurso a través de la interfaz de usuario de Assets o al crear un nuevo archivo desde la interfaz del editor; utilice incorrectamente el término `predecessor` en lugar de `successor` en el mensaje de registro. (GUIDES-35607)
- Si se usa `scope="external"` para una referencia al contenido de DAM dentro de un tema o asignación, la ruta relativa del recurso se sustituirá con un GUID. (GUIDES-38783)
- Cuando un tema contiene un gran número de referencias vinculadas desde carpetas con muchos archivos, la instancia de autor puede ralentizarse o dejar de responder, lo que en algunos casos requiere el reinicio de la instancia. (GUIDES-43547)
- Al intentar guardar un tema o asignación, la operación puede fallar intermitentemente con un error de **No se pudo guardar el archivo**, especialmente durante las tareas intensivas de procesamiento de recursos o los flujos de trabajo de traducción que se ejecutan en segundo plano. (GUIDES-37837)


## Problemas resueltos disponibles con Editor 2.0

Los siguientes problemas se han corregido y ya no se producen al utilizar Editor 2.0 (también conocido como Nuevo editor):

- Cuando se eliminan dos o más columnas de una tabla, la estructura de la tabla se vuelve incoherente o dañada. (GUIDES-35438)
- Cuando se elimina una columna de una tabla que contiene celdas combinadas, se agrega una nueva columna en blanco. (GUIDES-30147)
- Cuando se inserta una fila nueva en una tabla existente desde el menú de rutas de exploración, la estructura de la tabla cambia inesperadamente, lo que da como resultado la falta de bordes y una columna adicional. (GUIDES-29194)
- En la vista Autor, copiar y pegar una fila de la tabla coloca el contenido fuera de la tabla en lugar de insertarlo como una fila nueva dentro de la tabla. (GUIDES-24372)
- Cuando se copia y pega un elemento de sección seleccionado mediante el arrastre del mouse en el modo Autor, se convierte en elementos de párrafo `(<p>)` en lugar de conservar la estructura de sección. (GUIDES-30023)
- Cuando se edita el texto resaltado dentro de elementos como step o uicontrol, el texto seleccionado no se reemplaza correctamente y se anexa o se antepone, lo que provoca errores de validación. (GUIDES-24371)
- Cuando se establece el ancho de una columna de tabla utilizando valores relativos, las columnas restantes no se ajustan proporcionalmente, lo que provoca que el diseño de la tabla no esté alineado correctamente. (GUIDES-26109)
- Cuando se pega un título de tema copiado con las etiquetas desactivadas, la primera pegado aplica un estilo incorrecto y asigna el tipo en las propiedades de Contenido como tema en lugar de título. (GUIDES-28838)
- Cuando se editan secciones grandes de contenido, el movimiento de desplazamiento no intencionado hace que la vista del editor salte del contenido activo. (GUIDES-35436)
- Cuando se utiliza Retroceso en elementos, el editor se desplaza hasta la parte superior del tema independientemente de la posición del cursor. (GUIDES-32520)
- Cuando se utiliza la tecla de flecha izquierda o derecha para desplazarse fuera de las etiquetas en línea, el cursor salta inesperadamente en el primer intento. (GUIDES-26363)
- La revisión ortográfica de AEM solo funciona para el idioma en-US predeterminado y no respeta otras configuraciones regionales. (GUIDES-14731)
- Cuando se desbloquean temas DITA grandes en el Editor, se vuelve a abrir el mismo tema en una ficha duplicada. Además, se activa una advertencia de límite de etiquetas donde se muestra `NaN` en lugar del recuento real de etiquetas. (GUIDES-34008)
- Las sugerencias de Acrolinx no se resaltan correctamente en el Editor de temas de solo lectura o bloqueados. (GUIDES-29614)
- Al crear un(a) nuevo(a) `reltable` sin una fila de encabezado en la vista Autor, el diseño de la tabla cambia después de agregar un tema a la primera celda, lo que provoca que la siguiente columna se contraiga y dificulta la colocación de temas relacionados. (GUIDES-19555)
- Cuando se agrega un vínculo `xref` a una celda de tabla pequeña en el modo Autor, el vínculo no permanece dentro de la celda y aparece en las celdas adyacentes de la misma fila. (GUIDES-5489)
- Al cambiar de la vista Autor a la vista Source, la posición del cursor no se conserva y el Editor se desplaza de nuevo a la parte superior. Además, en los temas largos, la posición del cursor se pierde y salta aleatoriamente al centro o a la parte superior al alternar entre las vistas Autor y Source. (GUIDES-18114, GUIDES-21164)
- Al presionar *Entrar* dentro de un elemento `<li>`, se crea un nuevo elemento `<li>`, pero al volver a un elemento `<li>` anterior y presionar *Entrar*, el contenido del elemento actual se convierte incorrectamente en un elemento `<p>`, lo que rompe la estructura de la lista. (GUIDES-27505)

## Problemas conocidos

### Creación

- Al cargar imágenes marcadas en archivos DITAVAL, las imágenes se rompen después de que se actualice el explorador cuando la configuración `Enable UUIDs` está deshabilitada. (GUIDES-45853)
- En el Editor, los archivos de `.ditval` y `.md` pasan a ser no editables cuando se habilita *Flujo de trabajo de aprobación*. (GUIDES-42037)
- Si se selecciona un tema en el modo Vista previa, este no se resalta en la vista Mapa si el tema se encuentra dentro de etiquetas de mapa de libros (frontal, capítulo, parte o capa) o parte del contenido cíclico. (GUIDES-42416)
- Cuando un archivo está abierto tanto en el Editor como en el panel Buscar, al eliminarlo del panel Explorador, se elimina el archivo y se actualiza la lista Explorador, pero al actualizar la página se sigue mostrando el archivo en el panel Buscar. (GUIDES-41935)

### Administración de recursos

- En la interfaz de usuario de Assets, el botón **Mover** no se habilita en el primer intento cuando se seleccionan más de 2 archivos o carpetas. (GUIDES-42721) <br> **Solución alternativa**: después de seleccionar más de dos archivos o carpetas, espere unos segundos antes de seleccionar la carpeta de destino.

### Revisión

- Al actualizar una tarea de revisión activa, si se quita un tema que ya forma parte de la revisión y, a continuación, se vuelve a agregar sin hacer clic en Actualizar, se pierde la información de los revisores en la ficha Revisores. (GUIDES-38774)
- Cuando se quita un tema de revisión de una tarea de revisión en curso, su estado del documento sigue siendo **En revisión**, aunque el tema ya no forme parte de ninguna tarea de revisión. (GUIDES-38709)<br>**Solución alternativa**: cambie el estado del documento del tema de **En revisión** al estado apropiado desde la página Propiedades o el panel Propiedades del archivo.

### Editor 2.0

- Copiar y pegar contenido en el mismo tema en una ubicación no válida del editor inserta una etiqueta externa no deseada. (GUIDES-45378)
- Copiar y pegar `<keywords>` dentro de `<topicmeta>` en `<keydef>` o `<topicref>` inserta etiquetas externas no deseadas. (GUIDES-45800)
- Cuando el contenido se copia de un mapa o tema utilizando la opción Copiar en el menú contextual y, a continuación, se pegan, se insertan etiquetas `<data>` adicionales inesperadas en el contenido pegado. (GUIDES-45703)
- En Windows, copiar y pegar una fila de tabla agrega atributos no deseados a la tabla, lo que provoca errores de marcado y evita que se guarde el documento. (GUIDES-45784)
- Arrastrar la selección alrededor de una tabla o tabla simple no funciona como se esperaba. (GUIDES-45406)
- Al pegar imágenes de fuentes externas, no se insertan en el tema. (GUIDES-45983)
- El contenido de MathML al que se hace referencia mediante `conref` no se representa correctamente. (GUIDES-46601)
- El procesamiento incompleto de atributos para elementos de MathML y SVG interrumpe las clases CSS personalizadas y la administración de atributos de condición. (GUIDES-46371)
- Las ecuaciones de MathML incluidas en las etiquetas `foreign` y `equation-block` introducen espacios no deseados e interrumpen la edición. (GUIDES-46606)
- Si arrastra y suelta un elemento que contiene una referencia clave, se convierte `keyref` en una ruta de acceso absoluta. (GUIDES-45701)
- En el editor de mapas, `Ctrl+click` en un vínculo roto déclencheur un error de aplicación. (GUIDES-45544)
