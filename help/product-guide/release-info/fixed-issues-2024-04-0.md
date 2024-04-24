---
title: Notas de versión | Se han corregido problemas en las guías de Adobe Experience Manager, versión 2024.4.0
description: Obtenga información acerca de las correcciones de errores en la versión 2024.04.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 9d1b0bea20b2fe3ae8fb2ee7cf4387cf7271562d
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 0%

---


# Se han corregido problemas en la versión 2024.04.0

Este artículo cubre los errores corregidos en varias áreas de la versión 2024.04.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 2024.04.0](whats-new-2024-04-0.md).

Más información [instrucciones de actualización para la versión 2024.04.0](upgrade-instructions-2024-04-0.md).

## Creación

- El **Copiar** La función no puede duplicar las carpetas vacías en Adobe Experience Manager as a Cloud Service. (15353)
- Web Editor no puede cargar archivos .pptx. (14837)
- Al buscar un texto en el Editor Web, el cursor vuelve a la primera aparición del texto buscado, al pulsar la tecla Intro. (14820)
- El guardado automático causa varios problemas, reposiciona el cursor y requiere clics manuales en el documento. (14253)
- Los resultados de la búsqueda se desactivan después de abrir un archivo encontrado a través de global **Buscar y reemplazar**. (12142)
- En la vista de código fuente, `</conbody>` se inserta ocasionalmente en ubicaciones incorrectas. (11305)
- En el Editor XML, la función de información de objeto no puede actualizar el campo Origen. (15847)
- El **Compartir vínculo UUID** Esta función no funciona para las imágenes de Adobe Experience Manager. (15598)
- Los problemas de texto superpuestos se producen en `<reltable>` y `<fig>` etiquetas. (15238)
- Los problemas de parpadeo se producen en **Atributos** panel. (15237)
- Al eliminar un carácter o una palabra dentro del contenido, el cursor salta entre los elementos del bloque. (15224)
- El **Atributos** El panel no se muestra en la vista Código fuente del editor web. (14387)
- Los espacios no deseados y de no separación se añaden al editar al final de una etiqueta en el editor web. (11786)
- El contenido se elimina al corregir los errores ortográficos en los archivos DITA. (11610)


## Publicación

- AEM La generación de salida del sitio falla cuando **Eliminar sitio huérfano** La opción está activada. (15896)
- La funcionalidad de edición no funciona al agregar archivos a la colección de mapas. (15813)
- En la salida JSON, los metadatos del tema o del mapa DITA no se pueden propagar a los archivos de salida JSON. (15713)
- La publicación del PDF nativo falla al cambiar el nombre del ajuste preestablecido. (15662)
- El **sourcePath** AEM La propiedad de es incorrecta en la salida publicada del sitio de la. (15502)
- La selección y personalización de las variables de idioma no funcionan correctamente en el ajuste preestablecido de salida del PDF nativo. (15399)
- La generación de PDF nativos falla al utilizar una plantilla con una hoja de estilo o un diseño grandes. (15344)
- El contenido no se representa correctamente en la salida publicada si `<conref>` se utiliza con una ruta absoluta.
- El acortamiento de la URL de AEM Sites no funciona debido a conflictos entre las variables `fmdita rewriter` y `ResourceResolver`. (14793)
- El **processing-role=&quot;resource-only&quot;**, **search=&quot;no&quot;**, y **chunk=&quot;to-content&quot;** los atributos aparecen de forma independiente en la salida de AEM Sites. (14442)
- Si una carpeta que contiene asignaciones 2k se establece en la ruta de carpeta dentro de cualquier perfil de carpeta, los cambios aplicados al ajuste preestablecido de salida fallan.(14852)

## Administración

- Sin cerrar **Resoluciones de recursos** causar un aumento del recuento de sesiones y errores PathNotFoundException después de la versión de octubre de 2023 de las guías del Experience Manager as a Cloud Service. (15604)
- El indicador de funcionalidad **fmdita.useapproval** no funciona como se esperaba. (15310)
- La creación de una línea de base mediante la API de Java no funciona con la versión de junio de 2023 de las guías del Experience Manager as a Cloud Service. (14787)
- El `/bin/fmdita/import` La API permanece atascada en una solicitud pendiente indefinidamente cuando los recursos que se cargan superan los 500 MB. (14743)

## Revisión

- La eliminación de nodos de revisión interrumpe la capacidad de abrir y ver comentarios en las guías de Adobe Experience Manager. (15366)
- En el Editor web, el panel Revisar se carga lentamente. (14680)

## Traducción

- **Aceptar traducción** no se puede completar la traducción de los archivos temporales. (14665)

