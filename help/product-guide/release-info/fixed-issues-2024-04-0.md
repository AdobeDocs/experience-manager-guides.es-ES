---
title: Notas de versión | Se han corregido problemas en la versión 2024.4.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2024.04.0 de Adobe Experience Manager Guides as a Cloud Service.
exl-id: 35351d71-7739-4ad3-a063-67adf64906bf
source-git-commit: 5d99274da8fdacbd255d426fa4913b5773ca45f8
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 3%

---

# Se han corregido problemas en la versión 2024.04.0

Este artículo cubre los errores corregidos en varias áreas de la versión 2024.04.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 2024.04.0](whats-new-2024-04-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2024.04.0](upgrade-instructions-2024-04-0.md).

## Creación

- La función **Copy** no puede duplicar las carpetas vacías en Adobe Experience Manager as a Cloud Service. (15353)
- Web Editor no puede cargar archivos .pptx. (14837)
- Al buscar un texto en el Editor Web, el cursor vuelve a la primera aparición del texto buscado, al pulsar la tecla Intro. (14820)
- El guardado automático causa varios problemas, reposiciona el cursor y requiere clics manuales en el documento. (14253)
- Los resultados de la búsqueda se deshabilitaron después de abrir un archivo encontrado a través de **Buscar y reemplazar** global. (12142)
- En la vista de origen, `</conbody>` se inserta ocasionalmente en ubicaciones incorrectas. (11305)
- En el Editor XML, la función de información del objeto no puede actualizar el campo Source. (15847)
- La característica **Compartir vínculo UUID** no funciona para las imágenes de Adobe Experience Manager. (15598)
- Se producen problemas de superposición de texto en las etiquetas `<reltable>` y `<fig>`. (15238)
- Los problemas de parpadeo se producen en el panel **Atributos**. (15237)
- Al eliminar un carácter o una palabra dentro del contenido, el cursor salta entre los elementos del bloque. (15224)
- El panel **Atributos** no se muestra en la vista Source del editor web. (14387)
- Los espacios no deseados y de no separación se añaden al editar al final de una etiqueta en el editor web. (11786)
- El contenido se elimina al corregir los errores ortográficos en los archivos DITA. (11610)


## Publicación

- AEM La generación de salida del sitio falla cuando la opción **Eliminar sitio huérfano** está habilitada. (15896)
- La funcionalidad de edición no funciona al agregar archivos a la colección de mapas. (15813)
- En la salida JSON, los metadatos del tema o del mapa DITA no se pueden propagar a los archivos de salida JSON. (15713)
- La publicación del PDF nativo falla al cambiar el nombre del ajuste preestablecido. (15662)
- AEM La propiedad **sourcePath** no es correcta en la salida publicada del sitio de la. (15502)
- La selección y personalización de las variables de idioma no funcionan correctamente en el ajuste preestablecido de salida del PDF nativo. (15399)
- La generación de PDF nativos falla al utilizar una plantilla con una hoja de estilo o un diseño grandes. (15344)
- El contenido no se representa correctamente en la salida publicada si `<conref>` se utiliza con una ruta de acceso absoluta.
- El acortamiento de URL de AEM Sites no funciona debido a conflictos entre `fmdita rewriter` y `ResourceResolver`. (14793)
- Los atributos **processing-role=&quot;resource-only&quot;**, **search=&quot;no&quot;** y **chunk=&quot;to-content&quot;** aparecen indistintamente en la salida de AEM Sites. (14442)
- Si una carpeta que contiene asignaciones 2k se establece en la ruta de carpeta dentro de cualquier perfil de carpeta, los cambios aplicados al ajuste preestablecido de salida fallan.(14852)

## Administración

- Los **Resoluciones de recursos** sin cerrar causan un aumento en el recuento de sesiones y errores PathNotFoundException posteriores a la versión de octubre de 2023 de Experience Manager Guides as a Cloud Service. (15604)
- El marcador de característica **fmdita.useapproval** no funciona como se esperaba. (15310)
- La creación de una línea de base mediante la API de Java no funciona con la versión de junio de 2023 de Experience Manager Guides as a Cloud Service. (14787)
- La API `/bin/fmdita/import` permanece atascada en una solicitud pendiente indefinidamente cuando los recursos que se cargan superan los 500 MB. (14743)

## Revisión

- Al eliminar los nodos de revisión, se interrumpe la capacidad de abrir y ver comentarios en Adobe Experience Manager Guides. (15366)
- En el Editor web, el panel Revisar se carga lentamente. (14680)

## Traducción

- **Aceptar traducción** no puede completar la traducción de los archivos temporales. (14665)
