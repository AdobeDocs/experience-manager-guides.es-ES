---
title: Notas de versión | Se han corregido problemas en la versión 2026.03.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2026.03.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 764f6cc0b061020b78cd2808e08a5d05bd183c81
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 3%

---

# Se han corregido problemas en la versión 2026.03.0

Este artículo cubre los errores corregidos en varias áreas de la versión 2026.03.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 2026.03.0](whats-new-2026-03-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2026.03.0](upgrade-instructions-2026-03-0.md).

## Creación

- Al editar un archivo de Schematron (`*.sch`) y utilizar la característica Buscar y reemplazar, el panel Buscar y reemplazar aparece parcialmente fuera de la pantalla en la parte inferior, lo que impide el acceso a sus campos y controles de entrada. (GUIDES-38412)

## Publicación

- Cuando se reutiliza el mismo tema en varias asignaciones con diferentes ajustes preestablecidos condicionales, la publicación de la asignación más reciente en Salesforce sobrescribe el contenido del tema, lo que da como resultado que se muestren datos incorrectos a los usuarios de asignaciones publicadas anteriormente. (GUIDES-37806)
- Al publicar un PDF nativo para un mapa que incluye procesamiento condicional o ciertas asignaciones anidadas, el `dc:title` definido en el mapa no aparece en la portada de PDF, lo que da como resultado que falta un título de portada. (GUIDES-37733)
- La generación de la salida del sitio de AEM (mediante la asignación de componentes compuestos) para un mapa falla y provoca un error cuando la variable `map_title` está presente en la ruta de salida. (GUIDES-36968)
- Cuando se especifica una ruta de salida con una barra diagonal en el ajuste preestablecido de salida nativa de PDF, la interfaz de usuario añade automáticamente una barra diagonal adicional, lo que da como resultado una ruta de doble barra que provoca que la carga de PDF falle en determinados casos. (GUIDES-34932)
- La publicación involuntaria de páginas de AEM Sites generadas a partir de contenido DITA mediante Publicación rápida o Administrar publicación publica los recursos DITA asociados. (GUIDES-27967)
- Al publicar una asignación en AEM Sites (mediante asignación de componentes heredados), las referencias cruzadas (`xrefs`) con `scope = peer` que dirigen subelementos de un tema (como párrafos) en un mapa diferente no se resuelven en el ID de elemento específico y, en su lugar, solo en el tema principal, lo que hace que la página se cargue al principio del tema en lugar de desplazarse a la sección deseada. (GUIDES-21802)


## Traducción

- Cuando una imagen administrada inicialmente como un recurso específico del idioma con una versión específica (por ejemplo, en `/en/`) se mueve a una carpeta global con una versión actualizada y se realiza una exportación de línea de base, la nueva línea de base sigue haciendo referencia a versiones obsoletas específicas del idioma de esa imagen, lo que provoca un error en la exportación de línea de base. (GUIDES-39394)
- Al procesar proyectos de traducción creados fuera de Experience Manager Guides, se generan varios mensajes de registro de error que indican que no se encontró la propiedad *`fmTarget`*. (GUIDES-37804)

## Línea de base

- Al crear una línea de base dinámica, el editor a veces deja de responder debido a varias solicitudes de API simultáneas, lo que provoca que todas las demás operaciones se detengan. (GUIDES-39054)

## Revisión

- Al asignar un usuario a una tarea de revisión, la lista desplegable muestra todos los usuarios, en lugar de solo aquellos asociados con los proyectos seleccionados, lo que da como resultado opciones de usuario no válidas. (GUIDES-37781)

## Informes

- Al abrir un informe para un mapa, se produce un retraso en la carga del panel Filtros (GUIDES-39385)

## Problemas conocidos

Adobe ha identificado los siguientes problemas conocidos para la versión 2026.03.0:

- Se carga una pantalla en blanco al crear un ajuste preestablecido duplicado de la Base de conocimiento de ServiceNow. (GUIDES-42732)
- La API para recuperar el estado del documento devuelve una respuesta nula para algunos archivos, lo que provoca que aparezcan estados de documento incorrectos en la interfaz de usuario. (GUIDES-42561)
- Las personalizaciones de la interfaz de usuario basadas en los nombres de pestañas del panel de mapas no se aplican. (GUIDES-42285)
- Cuando un archivo está abierto tanto en el Editor como en el panel Buscar, al eliminarlo del panel Explorador, se elimina el archivo y se actualiza la lista Explorador, pero al actualizar la página se sigue mostrando el archivo en el panel Buscar. (GUIDES-41935)
- Al actualizar una tarea de revisión activa, si se quita un tema que ya forma parte de la revisión y, a continuación, se vuelve a agregar sin hacer clic en **Actualizar**, se pierde la información de los revisores en la ficha Revisores.   (GUIDES-38774)
- Si se selecciona un tema en el modo Vista previa, este no se resalta en la vista Mapa si el tema se encuentra dentro de etiquetas de mapa de libros (contenido frontal, capítulo, parte o contenido posterior) o parte de contenido cíclico. (GUIDES-42416)
- En la interfaz de usuario de Assets, el botón **Mover** no se habilita en el primer intento cuando se seleccionan más de 2 archivos o carpetas. (GUIDES-42721) <br> **Solución alternativa**: después de seleccionar más de dos archivos o carpetas, espere unos segundos antes de seleccionar la carpeta de destino.
- Cuando navega a **Preferencias de usuario** desde el Editor y actualiza el mapa raíz mientras el modo de vista previa está abierto en el Editor, la vista previa del mapa se carga como una pantalla en blanco cuando vuelve al Editor. (GUIDES-42412) <br> **Solución alternativa**: al actualizar la vista previa con el icono **Actualizar** disponible en el modo de vista previa, se resuelve el problema.
- Al cambiar el nombre de una plantilla existente, no se actualiza el nombre en el panel **Plantillas de salida** hasta que la página se actualiza manualmente. (GUIDES-42528)<br> **Solución alternativa**: actualice el explorador para ver el nombre actualizado de la plantilla en el panel Plantillas de salida.










