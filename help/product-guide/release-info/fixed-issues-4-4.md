---
title: Notas de versión | Se han corregido problemas en la versión 4.4.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 4.4.0 de Adobe Experience Manager Guides
role: Leader
exl-id: ff3083d3-062b-4a79-875f-86991978a18e
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '1434'
ht-degree: 0%

---

# Se han corregido problemas en la versión 4.4.0 (enero de 2024)


Este artículo cubre los errores corregidos en varias áreas de la versión 4.4.0 de Adobe Experience Manager Guides.

Para obtener más información acerca de las nuevas características y mejoras, vea [Novedades de la versión 4.4.0](./whats-new-4-4.md).

Obtenga información acerca de [instrucciones de actualización para la versión 4.4.0](../release-info/upgrade-instructions-4-4.md).


## Creación

- La revisión ortográfica en el editor no permite la selección de sugerencias. (15045)
- El botón de navegación global no funciona y el panel no se puede cargar. (14968)
- En el editor web, la función de mapa de descarga no almacena en déclencheur una notificación emergente cuando está lista para descargarse. (14626)
- En el editor web, la función de mapa de descarga no puede descargar un mapa con una línea de base. (14622)
- Error de DTD no válido en Experience Manager Guides. (14482)
- El título de la ficha Editor Web se trunca después de un punto (.) extra. (14372)
- No se ha actualizado la mensajería de error para nombres de mapa duplicados en la IU de Assets. (14320)
- Se produce un error en la lógica de creación de versiones al arrastrar y soltar recursos. (14291)
- El contenido reutilizable omite los ID de elemento. (14213)
- Falta el control de configuración para ocultar el panel **Variables de idioma** en la ficha **Salida**. (14194)
- El editor web genera errores de aplicación al agregar una nueva referencia o tema mediante un esquema especializado en la vista **Layout**. (14094)
- El espacio posterior al elemento `<ph>` de la referencia desaparece al guardar el tema. (13642)
- Se produce un error de aplicación al intentar guardar archivos DITA antes de que finalice el posprocesamiento. (13571)
- Un vínculo de anclaje al elemento `<dlentry>` o `<dt>` no puede mostrar el texto del vínculo. (13543)
- La colección **Favoritos** del Editor web no se puede cargar. (13495)
- Si el título de un tema contiene una barra diagonal `/`, la ficha del Editor Web sólo mostrará las cartas que le siguen. (13455)
- La previsualización de la imagen no desaparece después de mostrar la previsualización en el editor web. (13454)
- Las citas muestran vínculos en los que no se puede hacer clic cuando se crean con un ID único con espacios. (13447)
- AEM Al cerrar un tema después de editarlo, se le redirige a la página de inicio de la página de inicio de la página de en lugar de volver a la vista de carpeta. (13306)
- La ventana emergente Insertar palabra clave no aparece al utilizar claves definidas por mapa raíz en otros temas. (12950)
- Los iconos de cierre no son visibles cuando se muestran gráficos muy altos en el panel **Historial de versiones**. (12867)
- No se puede modificar la zona horaria de la columna **Versión creada el** para las líneas de base. (12711)
- Los archivos Zip no se reconocen en el Editor Web y no se pueden arrastrar y soltar. (12709)
- El panel **Historial de versiones** de la IU de Assets muestra una marca de tiempo incorrecta para el campo **Actual**. (12624)
- En la vista **Diseño** para un Bookmap, al usar **Mover a la derecha** para hacer que un capítulo seleccionado sea un subelemento no funcione. (12567)
- La creación de un fichero DITA a partir de una plantilla con un nombre de fichero que empieza por caracteres numéricos da lugar a un error de espacio de nombres. (12188)
- La configuración de mapa de raíz persiste en el editor web aunque el usuario no la haya establecido explícitamente desde **Preferencias de usuario**. (11551)
- El contenido con algunos atributos aplicados no se resalta en el modo **Autor** o **Vista previa**. (11063)
- En el editor web, se abre la ventana **Referencias clave** al insertar la etiqueta `varname`. (10940)
- Si arrastra un tema del glosario desde el repositorio a un mapa del glosario, se creará `topicref`. (10767)
- La ventana de vista previa del Editor XML se trunca en los navegadores Google Chrome y Microsoft Edge. (10755)
- El editor web carece de la capacidad de envolver un elemento dentro de los posibles elementos principales. (8791)
- El editor web se desinstala después de volver a instalar la versión 4.3.1 de Adobe Experience Manager Guides. (14519)
- El instalador de la versión 4.3.1 encuentra un conflicto de filtros, que provoca la anulación de `apps/cq/core/content/projects/properties`. (14517)
- Aparecerá un vínculo de referencia en la lista de **Vínculos rotos** en los informes. (13539)
- La pantalla de vista previa de los fragmentos de código está inmovilizada. (14840)
- Aparecen caracteres rotos al crear los fragmentos en coreano. (13489)

## Publicación

- La publicación de AEM Sites falla y causa errores de ámbito para los archivos que tienen `xref` en el archivo DITA que comienza con &quot;HTTP&quot;. (15154)
- En la publicación de PDF nativo, las propiedades de metadatos de mapa DITA no se pueden utilizar para rellenar los metadatos de salida de archivo de PDF. (15159)
- En la publicación de PDF nativos, los atributos personalizados dentro de ajustes preestablecidos de condición no funcionan para la publicación de PDF nativos. (14943)
- No se puede agregar una plantilla personalizada desde la ficha **Salidas** del Editor. (14846)
- AEM El ajuste preestablecido **Site** no funciona debido a una ruta de acceso de plantilla vacía. (14804)
- AEM La regeneración de sitios falla en los mapas DITA con temas que contienen ecuaciones MathML. (14790)
- En la publicación de PDF nativo, la generación de PDF genera errores al obtener dependencias para la publicación `Node.js`. (14445)
- AEM El ajuste preestablecido **Site** no permite la selección de una plantilla fuera de la jerarquía `/content` en el editor web. (14260)
- La funcionalidad para publicar como fragmento de contenido no funciona para los archivos enumerados en los resultados de búsqueda. (14090)
- Los componentes de Fodita tienen una ruta de acceso codificada de `delegator.jsp`, lo que evita la superposición de los componentes de AEM Sites. (13993)
- La vista etiquetada del reactor de PDF en la salida de publicación del PDF nativo no funciona como se esperaba. (13622)
- En la publicación nativa de PDF, la selección de color de fondo en el diseño **Template** requiere una recarga de página al revertir a `None`. (13621)
- AEM La publicación de sitios encuentra un problema al comprometerse con el almacén de datos para mapas grandes con vínculos de igual a igual de ámbito. (13531)
- AEM Se produce un problema al comprometerse con el almacén de datos para un mapa DITA grande con vínculos de igual a igual de ámbito en la publicación de sitios de. (13530)
- El icono y la información de objeto incorrectos se muestran para la opción **Editar contenido** en la barra de herramientas de **Diseños de página** de las plantillas utilizadas en la publicación de PDF nativos. (13492)
- No se puede activar un sitio mediante Experience Manager Guides **Tablero de Publish en lotes**. (13439)
- En la publicación nativa en PDF, la accesibilidad se ve comprometida, ya que las imágenes del encabezado y del pie de página no muestran texto alternativo. (12829)
- En la salida de AEM Sites, el estilo o los saltos de línea se perdieron para el elemento `<lines>` que tiene subelementos.(12542)
- La duplicación del diseño de página en el PDF nativo no funciona sin que se agregue ninguna extensión automáticamente. (12534)
- La localización de las etiquetas de elementos no funciona correctamente en la salida de AEM Sites. (12144)
- Los metadatos personalizados no están disponibles en la salida final. (12116)
- `fmdita rewriter` entra en conflicto con la configuración de reescritura del usuario y conduce a la visualización de direcciones URL largas en lugar de los vínculos. (12076)
- Falta la opción **ditaval** en los ajustes preestablecidos de salida de nivel de perfil de carpeta creados mediante la interfaz de usuario del editor web. (11903)
- AEM En el ajuste preestablecido de **Sitio de**, la opción de **Generar PDF independiente para cada tema** no funciona. (11555)
- La publicación en PDF nativo no es compatible con la conversión del espacio de color CMYK. (10754)
- Al actualizar a la versión 4.3.1, se producen algunas excepciones en el nodo PDF nativo. (14492)
- Al generar la salida del PDF con la publicación del PDF nativo, el nombre del archivo se trunca después de un punto. (13620)


## Administración

- La referencia de contenido se interrumpe al copiar y pegar los archivos DITA con vínculos de referencia automática sin GUID. (13540)
- Los archivos de **Filtro de línea de base** no funcionan con Nombre de archivo en el Editor web. (13486)
- En el Editor Web, la instantánea muestra el título de la versión anterior en lugar de la versión seleccionada del fichero DITA. (13444)
- Desactivar la indexación del mapa DITA principal para obtener un mejor rendimiento puede afectar a la funcionalidad de determinadas funciones.(12213)
- No se crean ajustes preestablecidos de condición para mapas DITA grandes. (10936)
- No se pueden editar los ajustes preestablecidos de las primeras asignaciones de la colección mientras se edita una colección de asignaciones. (10649)
- Las etiquetas del archivo `labels.json` aparecen en orden aleatorio en el Editor Web. (10508)
- Las llamadas de línea de base dinámicas utilizan el nombre en lugar del título, lo que provoca el fallo de la API Exportar mapa DITA. (14268)

## Revisión

- El menú contextual del botón secundario no funciona para que **Accept** o **Reject** realice un seguimiento de los cambios. (14607)
- Cambiar para cerrar los temas de DITA en la pantalla de revisión no funciona en la versión 4.3.1 de Adobe Experience Manager Guides. (14537)
- Los problemas de simetría se producen en los paneles de revisión en paralelo de las versiones anterior y actual en el Editor Web. (14156)
- La personalización de las plantillas de correo electrónico para el flujo de trabajo de revisión no funciona con la superposición. (13954)
- Los archivos adjuntos coreanos en la pantalla de revisión de Experience Manager Guides no se pueden seleccionar. (13436)
- El título del mapa se corta en la pantalla de revisión y colaboración, sin opción de ver el título completo. (13012)

## Traducción

- Los botones **Aceptar/Rechazar** aparecen erróneamente para la traducción humana aprobada automáticamente. (14318)
- AEM Los problemas de internacionalización (i18n) se producen durante la transformación de archivos DITA que no están en inglés a páginas de. (14286)
- La aprobación automática no funciona algunas veces y se producen excepciones si se establece un valor incorrecto en **Estado de traducción**. (13607)
- La línea de base exportada desde el panel de traducción produce un error y no se abre en el idioma de destino. (12993)
- El contenido traducido no se puede sincronizar desde proyectos de traducción temporales y el asistente de traducción del editor XML DITA muestra incorrectamente el estado **En curso** para los trabajos aprobados. (9938)

## Problema conocido

El Adobe ha identificado el siguiente problema conocido para la versión 4.4.0:

- La versión 1.0 no se muestra en la interfaz de usuario del archivo DITA duplicado.
