---
title: Notas de versión | Se han corregido problemas en la versión 2024.4.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2024.04.0 de Adobe Experience Manager Guides as a Cloud Service.
exl-id: 35351d71-7739-4ad3-a063-67adf64906bf
TQID: https://experienceleague.adobe.com/cHKuFCElWbjxik0EHgoTrtlq2t3I62LQ5zUArzBoMqk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 577
ht-degree: 8%

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

- La generación de resultados del sitio de AEM falla cuando la opción **Eliminar sitio huérfano** está habilitada. (15896)
- La funcionalidad de edición no funciona al agregar archivos a la colección de mapas. (15813)
- En la salida JSON, los metadatos del tema o del mapa DITA no se pueden propagar a los archivos de salida JSON. (15713)
- La publicación nativa de PDF falla al cambiar el nombre del ajuste preestablecido. (15662)
- La propiedad **sourcePath** no es correcta en el resultado publicado del sitio de AEM. (15502)
- La selección y personalización de las variables de idioma no funcionan correctamente en el ajuste preestablecido de salida nativo de PDF. (15399)
- La generación nativa de PDF falla al utilizar una plantilla con una hoja de estilos o un diseño grandes. (15344)
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
