---
title: Notas de versión | Se han corregido problemas en la versión 2026.01.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2026.01.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 8a9a82e79c757e403141e853aafbc64e1618c30a
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 3%

---

# Se han corregido problemas en la versión 2026.01.0

Este artículo cubre los errores corregidos en varias áreas de la versión 2026.01.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 2026.01.0](whats-new-2026-01-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2026.01.0](upgrade-instructions-2026-01-0.md).

## Creación

- Al actualizar una ecuación de MathML en línea mediante la opción Editar MathML del menú contextual, el valor actualizado no se refleja hasta que se actualiza la página. (GUIDES-38198)
- Cuando un tema contiene muchos elementos reutilizables (aquellos con ID) agregados en el panel Reutilizables, es posible que algunos elementos no sean accesibles debido a la altura fija del contenedor. (GUIDES-37220)
- Al insertar una referencia cruzada en un archivo, los iconos de los mapas y los temas son idénticos.(GUIDES-36662)
- Al editar un mapa, los símbolos especiales de `navtitle` no se muestran para `topichead` en la vista Autor. (GUIDES-35435)
- No se pueden agregar varias etiquetas de versión a un tema desde el cuadro de diálogo **Guardar como nueva versión**. (GUIDES-32716)

## Administración de recursos

- No se pueden quitar las etiquetas Versión del panel Historial de versiones en la IU de Assets. (GUIDES-38276)
- Al cargar recursos con un nombre de archivo que contiene caracteres no válidos, el recurso no se puede cargar y muestra un mensaje incorrecto **El archivo está bloqueado por otro usuario** a pesar de que el recurso está desbloqueado. (GUIDES-32680)
- En la búsqueda de Assets, los subrecursos y nodos de metadatos (como imágenes y PDF) se incluyen incorrectamente en los resultados. Además, para un ajuste preestablecido de salida cuando se aplican filtros DITAVAL, la búsqueda devuelve archivos DITAVAL generados internamente creados a partir de ajustes preestablecidos de condición. (GUIDES-35418)

## Publicación

- Al generar la salida de AEM Sites, los títulos de mapas que contienen palabras clave y títulos de temas con el elemento `<ph>` no se incluyen en la salida publicada. (GUIDES-36641)
- Al publicar con un ajuste preestablecido personalizado con contenido que contiene vínculos a PDF sin el ámbito establecido como externo, el proceso no se completa. (GUIDES-21708)
- Al realizar la activación masiva, la creación del paquete agrega filtros para todas las rutas enumeradas en la propiedad `fileReference` de una página, incluidas las rutas externas y de igual a igual. (GUIDES-24887)
- En la salida nativa de PDF, el elemento `abbreviated-form` muestra `glossterm` en lugar de `glossSurfaceForm` o `glossAcronym` designados. (GUIDES-26393)
- Para la salida nativa de PDF, se omite el elemento `<alt>` de las imágenes, lo que impide que se aplique texto alternativo para la accesibilidad. (GUIDES-29087)
- Al descargar archivos temporales para un mapa con una línea de base durante la publicación de un ajuste preestablecido, el archivo `metadata.xml` hace referencia incorrectamente a `versionPath` en lugar de a `dampath`.(GUIDES-29815)
- Al crear o editar un tema que incluye una cita, si el campo Autor no se agrega en el cuadro de diálogo de cita, la PDF no se genera. (GUIDES-37934)
- El archivo CSS (`rhdefault.css`) se aplica incorrectamente a la plantilla de PDF a pesar de que no se hace referencia a CSS, lo que provoca la falta de registros de errores en el archivo CSS.(GUIDES-31752)

## Plataforma

- Al intentar guardar un tema o asignación, la operación puede fallar intermitentemente con un error de **No se pudo guardar el archivo**, especialmente durante las tareas intensivas de procesamiento de recursos o los flujos de trabajo de traducción que se ejecutan en segundo plano. (GUIDES-37837)
- Si se usa `scope="external"` para una referencia al contenido de DAM dentro de un tema o asignación, la ruta relativa del recurso se sustituirá con un GUID. (GUIDES-38783)

## Informes

- El informe Lista rota incluye incorrectamente vínculos externos, `keyrefs` válidos y palabras clave que se han resuelto correctamente en el ámbito del mapa actual. (GUIDES-27774)

## Problemas conocidos

Adobe ha identificado los siguientes problemas conocidos para la versión 2026.01.0:

- Cuando se quita un tema de revisión de una tarea de revisión en curso, su estado del documento sigue siendo **En revisión**, aunque el tema ya no forme parte de ninguna tarea de revisión. (GUIDES-38709)<br>**Solución alternativa**: cambie el estado del documento del tema de **En revisión** al estado apropiado desde la página Propiedades o el panel Propiedades del archivo.
- Al realizar una búsqueda con **Buscar y reemplazar**, si abre un archivo desde los resultados de la búsqueda, lo cierra y, a continuación, intenta volver a abrirlo seleccionando el resultado de la lista, el archivo no se vuelve a abrir. (GUIDES-39050)<br>**Solución alternativa**: abra primero cualquier otro archivo de los resultados de búsqueda y, a continuación, vuelva a abrir el archivo cerrado anteriormente de la lista para resolver el problema.
- Al utilizar Guías con el servidor de base de datos, para el contenido que incluye referencias automáticas, el informe Lista de temas muestra entradas no válidas para cada referencia automática, lo que da como resultado un recuento de archivos inexacto. (GUIDES-39420)












