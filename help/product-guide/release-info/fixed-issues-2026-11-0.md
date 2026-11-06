---
title: Notas de versión | Se han corregido problemas en la versión 2026.11.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2026.11.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 0ebd3941a6ea5160c86e68a9ca6bdda50900a78d
workflow-type: tm+mt
source-wordcount: '1456'
ht-degree: 0%

---

# Se han corregido problemas en la versión 2026.11.0

Este artículo cubre los errores corregidos en varias áreas de la versión 2026.11.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas características y mejoras, vea [Novedades de la versión 2026.11.0](./whats-new-2026-11-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2026.11.0](./upgrade-instructions-2026-11-0.md).

## Editor 2.0

- Cuando se selecciona una fila de la tabla utilizando las rutas de exploración en el Editor y la opción **Delete** se selecciona en el menú contextual, sólo se quita el contenido de la celda en lugar de eliminar toda la fila. (GUIDES-56759)
- Cuando se pega una tabla desde Microsoft Word, se crean las celdas de fila de encabezado pero se pierde su contenido. (GUIDES-49847)
- Las marcas de revisión de los archivos creados antes de pasar a Editor 2.0 no aparecen en el panel **Control de cambios**. (GUIDES-44777)
- Cuando el código se pega en un elemento `codeblock`, desde Microsoft Word o editores de texto similares, mediante Ctrl+V, se pierden los saltos de línea y los espacios iniciales y el código se acopla en una sola línea. (GUIDES-33247)

## Creación

- Cuando se habilita el shell unificado, el encabezado de Adobe Experience Manager Guides también aparece en el Editor y en la consola de Mapa. (GUIDES-56812)
- En la interfaz de usuario de Assets, las acciones específicas de DITA como **Ver origen**, **Editar temas** y **Compartir vínculo UUID** aparecen para los recursos que no son DITA. Además, **Compartir vínculo UUID** genera un vínculo no válido para los recursos que no tienen un UUID. (GUIDES-47043)
- En el panel Esquema de asunto, el título para mostrar solo se selecciona del atributo `navtitle`. El elemento `navtitle` se omite incluso cuando ambos están presentes. (GUIDES-37722)
- En la **vista Título** del panel Repositorio, los puntos suspensivos no son visibles inicialmente para archivos con nombres largos. Al hacer clic con el botón derecho en un archivo de este tipo, los puntos suspensivos y el menú contextual aparecen muy a la derecha del archivo, a veces parcialmente fuera de la pantalla. (GUIDES-37118)
- En el panel Condiciones, las condiciones se ordenan alfabéticamente según sus valores en lugar de según sus etiquetas. (GUIDES-14593)
- En Plantillas de salida, el botón **Nuevo estilo** (+) no se muestra en el panel Estilos cuando se abre una hoja de estilo, como layout.css. (GUIDES-49448)

## Administración de recursos

- Cuando carga un archivo modificado con la opción **Sobrescribir archivo existente**, la carga parece completarse si el archivo existente no tiene UUID de guías y está almacenado en una carpeta enumerada en **Rutas ignoradas para el procesamiento posterior**. Sin embargo, el archivo existente no se sobrescribe y no se crea ninguna nueva versión. (GUIDES-55866)
- En un mapa de libros, cuando un elemento `booktitle` contiene varios subelementos, como `booklibrary` y `mainbooktitle`, se agrega espacio en blanco adicional entre sus valores en los metadatos `dc:title`. (GUIDES-28877)

## Publicación

- En la consola Mapa, una vez que se genera la salida de un mapa, el botón **Generar** se desactiva cuando se abre otro mapa. Al actualizar el explorador, se vuelve a activar el botón. (GUIDES-54591)
- La publicación de determinadas asignaciones en un sitio de AEM con asignación de componentes produce un error mientras se crea la tabla de contenido. (GUIDES-53807)
- La publicación de un mapa en un sitio de AEM con asignación de componentes falla cuando el mapa contiene un elemento `topicref` con un atributo `navtitle` y ningún atributo `href`. Los intentos posteriores también dan error, incluso después de quitar el elemento, hasta que se eliminan los nodos de sitio generados. (GUIDES-53707)
- En la salida del sitio de AEM con asignación de componentes, los encabezados de Markdown de los niveles 2 a 6 se representan como encabezados de nivel 1. (GUIDES-51134)
- Para la salida del sitio de AEM con asignación de componentes, los metadatos del prólogo, como autor, palabras clave e ID de recurso, aparecen en el cuerpo de página de la salida publicada. (GUIDES-44087)
- Cuando se publica un tema en ServiceNow, el cuerpo del artículo incluye la descripción breve y el prólogo del tema. (GUIDES-47868)
- Cuando se vuelve a publicar un tema que ya se ha publicado en ServiceNow, se crea un nuevo artículo en el estado Borrador en lugar de sobrescribir el artículo existente. (GUIDES-37872)
- Cuando los ajustes preestablecidos de condición excluyen las referencias temáticas durante la publicación en Salesforce, la generación de resultados se comunica como fallida, aunque los temas restantes se hayan publicado correctamente. (GUIDES-37807)
- La publicación de un mapa grande en Salesforce falla con un error de tiempo de espera de puerta de enlace. (GUIDES-33722)
- La publicación de una asignación en Salesforce falla con un error de límite excedido cuando una solicitud contiene más de 25 operaciones. (GUIDES-33721)
- En el tablero de mapas (antiguo), **Añadir todo** en un ajuste preestablecido de condición existente no recoge los valores de condición que se añadieron o cambiaron después de crearse el ajuste preestablecido. (GUIDES-45940)
- Los registros de la página **Historial de salida** que contienen advertencias se muestran con un icono verde, que no indica que haya advertencias. (GUIDES-27000)
- El glosario no se incluye en la salida cuando ningún término del contenido del mapa hace referencia a una entrada del glosario. (GUIDES-52964)
- Los temas de un submapa al que se hace referencia en un apéndice se representan como capítulos en lugar de contenido del apéndice. (GUIDES-52775)
- Algunos caracteres chinos simplificados se representan con una fuente japonesa cuando el idioma de salida se establece en chino (simplificado). (GUIDES-48094)
- Las entradas de índice pierden el texto de elementos secundarios, como `keyword`, `ph` y `sup`. Como resultado, algunas etiquetas de índice están incompletas o vacías. (GUIDES-40902)
- No se conservan los espacios alrededor de los elementos `option` en línea, lo que hace que el texto adyacente aparezca unido. (GUIDES-40900)

## Traducción

- En la página Traducción, al buscar y ordenar por **Título**, se usa el valor de metadatos localizado en lugar del título que se muestra en la columna. (GUIDES-45396)

## Revisión

- En la página **Revisores**, durante la creación o edición de una tarea de revisión, los botones **Borrar selección**, **Agregar revisores**, **Quitar revisores** y **Volver a asignar revisores** están habilitados de forma predeterminada, incluso cuando no hay filas seleccionadas. (GUIDES-35125)
- En la bandeja de entrada AEM, las notificaciones relacionadas con las tareas de revisión, como la asignación de tareas, los comentarios recibidos, las menciones y los recordatorios de vencimientos o vencidos, se muestran sin nombre de proyecto. (GUIDES-10912)
- En la vista simultánea de un tema en una tarea de revisión, el contenido marcado con tachado aparece con un formato diferente en las dos vistas. (GUIDES-56079)

## Contenido de aprendizaje

- La generación de una salida SCORM para un curso grande, normalmente de 300 MB a 600 MB, tarda más de 30 minutos y falla sin detalles de error en los registros. (GUIDES-56101)
- Los criterios de finalización para una salida SCORM no se pueden definir en Experience Manager Guides. (GUIDES-55520)
- Las imágenes en formato AVIF se muestran en el editor, pero no aparecen en la salida publicada. (GUIDES-55515)
- El atributo `href` se quita de las etiquetas de anclaje en la salida publicada, por lo que no se puede hacer clic en los vínculos. (GUIDES-55514)

## Plataforma

- Cuando se asigna a un usuario como usuario administrador en un perfil de carpeta pero no es miembro del grupo de administradores, no puede agregar correctamente otros usuarios administradores. Aunque aparece un mensaje de éxito, los usuarios recién añadidos desaparecen después de actualizar la página. (GUIDES-50144)

## Problemas conocidos

Adobe ha identificado los siguientes problemas conocidos para la versión 2026.11.0:

## Creación

- Cuando se crea un mapa a partir de una plantilla que contiene temas o submapas dependientes, la creación del mapa puede fallar de forma intermitente con un error, especialmente cuando el servidor está bajo una carga pesada. (GUIDES-58715)

### Editor 2.0

- La opción **Actualizar atributo de título de navegación** no agrega el atributo `@navtitle` a los elementos `topicref` existentes en un mapa DITA. (GUIDES-54348)

**Rastrear cambios**

Cuando **Rastrear cambios** está activado:

- Las eliminaciones anidadas por el mismo usuario no siempre se combinan en una sola entrada cuando se cambia el nombre o el formato del elemento que contiene el contenido eliminado. (GUIDES-58429)
- El panel **Control de cambios** a veces muestra contenido incompleto para el elemento principal cuando un usuario diferente realiza una eliminación anidada. (GUIDES-58428)
- El marcador rojo de margen interno no aparece a la izquierda cuando se elimina contenido dentro de una inserción realizada por otro usuario. (GUIDES-58418)

### Publicación

- En la salida nativa de PDF, el formato de superíndice y subíndice no se conserva en las entradas de índice. (GUIDES-58349)
- Cuando se utiliza el mismo ajuste preestablecido global para generar resultados para diferentes mapas, la selección del tema del mapa anterior puede afectar a la salida del nuevo mapa. (GUIDES-58346)
- La publicación de un mapa de libros a veces da como resultado una página en blanco cuando, en un escenario específico, un `<chapter>` define simultáneamente un destino `href` directo y ese capítulo contiene `<topicref>` elementos secundarios anidados. (GUIDES-58266)
- Cuando navega a la pestaña **Historial de salida** desde un ajuste preestablecido con cambios no guardados, los botones **Guardar** y **Generar salida** permanecen visibles. (GUIDES-57989)
- Cuando se configura un flujo de trabajo posterior a la publicación para un ajuste preestablecido, la duración de la publicación que se muestra en **Historial de salida** no incluye el tiempo que tarda el flujo de trabajo. (GUIDES-57856)
- No puede cancelar la generación de resultados nativos de PDF desde la página **Historial de resultados**. (GUIDES-57821)

### Revisión

- Abrir una tarea de revisión creada en las versiones 2026.08.0 o 2026.09.0 produce a veces un error de aplicación cuando el contenido revisado contiene *cualquier anotación de revisión* junto con espacios de no separación (`&nbsp;`). (GUIDES-56583) <br>**Solución alternativa:** Complete o cierre todas las tareas de revisión creadas en estas versiones.

