---
title: Notas de versión | Se han corregido problemas en la versión Adobe Experience Manager Guides 4.6.0 Service Pack 3
description: Obtenga información acerca de las correcciones de errores en la versión 4.6.0 del Service Pack 3 de Adobe Experience Manager Guides
role: Leader
exl-id: 8ff26c28-4a88-4eb2-b359-5b1b0138dd4b
TQID: https://experienceleague.adobe.com/bsiTHK--FPkvfF4bdYUnL-HbAMuhtBKj7wT2eCmd7hM
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 370
ht-degree: 4%

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
- Si un vínculo externo contiene un UUID, se incluye en el procesamiento posterior y convierte el vínculo externo en un vínculo UUID, rompiendo así el vínculo en el editor y también en los sitios de publicación. (22574)
- `xref` se convierte en vínculo relativo incluso cuando el **ámbito** del vínculo está establecido en **externo**. (23059)
- La generación nativa de PDF falla en el contenido con **chunk** atributo establecido en **to-content**. (21772)
- El cuadro de diálogo **Editar propiedades** de una línea base no muestra los criterios guardados anteriormente para la línea base dinámica. (23964)


## Traducción

- Para las traducciones no heredadas (para las que no son UUID), mover un tema en la ruta de origen a una carpeta diferente provoca que se rompan las referencias en la configuración regional de destino. (24152)
