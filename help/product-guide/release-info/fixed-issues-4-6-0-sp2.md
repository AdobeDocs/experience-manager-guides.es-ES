---
title: Notas de versión | Se han corregido problemas en la versión del paquete de servicio 3 de Adobe Experience Manager Guides 4.6.0
description: Obtenga información acerca de las correcciones de errores en la versión 4.6.0 del Service Pack 3 de Adobe Experience Manager Guides
role: Leader
source-git-commit: d60fea16831af458c479df24c877ef7095b2fd15
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# Se han corregido problemas en la versión 4.6.0 del paquete de servicio 3 (enero de 2025)


Este artículo cubre los errores corregidos en varias áreas de la versión 4.6.0 del paquete de servicio 3 de Adobe Experience Manager Guides.

Obtenga información acerca de [instrucciones de actualización para el Service Pack 3 versión 4.6.0](upgrade-instructions-4-6-0-sp2.md).

## Creación

- Todos los grupos de condiciones se pierden y las condiciones se acoplan al actualizar las condiciones desde el perfil de carpeta. (23526)
- Al cambiar el valor de las filas de encabezado de una tabla en el panel **Propiedades de contenido**, no se aplica el valor actualizado. (23213)
- Al añadir nuevas referencias de tema en el mapa DITA mediante el cuadro de diálogo de elemento **Referencia de tema** en la vista de diseño, las referencias añadidas se muestran como un vínculo roto. (22859)
- Al añadir temas en el mapa DITA mediante el cuadro de diálogo de elementos **Referencia de tema** en la vista de autor, los temas seleccionados se insertan en orden inverso al de su selección. (22858)
- Al copiar una imagen de cualquier producto externo (por ejemplo, MS PowerPoint) y pegarla en Guides, la funcionalidad para cargar el recurso sobre la marcha para utilizarlo en los saltos de archivo. (24983)
- Al buscar archivos en el repositorio mediante la funcionalidad **Buscar y filtrar**, no se pueden seleccionar varios archivos. (25104)

## Publicación

- La publicación en Salesforce falla cuando el contenido contiene espacios de no separación. (23664)
- En los temas con errores como los vínculos rotos, la publicación de Salesforce falla y la barra de progreso se muestra indefinidamente. (22985)
- En el caso de los mapas con vínculos rotos, la publicación de Salesforce falla y la barra de progreso se muestra indefinidamente. (24963)
- Si un vínculo externo contiene un UUID, se incluye en el procesamiento posterior y convierte el vínculo externo en un vínculo UUID, rompiendo así el vínculo en el editor web y también en los sitios de publicación. (22574)
- `xref` se convierte en vínculo relativo incluso cuando el **ámbito** del vínculo está establecido en **externo**. (23059)
- Error al generar el PDF nativo para el contenido con el atributo **chunk** establecido en **to-content**. (21772)
- El cuadro de diálogo **Editar propiedades** de una línea base no muestra los criterios guardados anteriormente para la línea base dinámica. (23964)


## Traducción

- Para las traducciones no heredadas (para las que no son UUID), mover un tema en la ruta de origen a una carpeta diferente provoca que se rompan las referencias en la configuración regional de destino. (24152)
