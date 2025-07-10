---
title: Notas de versión | Se han corregido problemas en la versión 2025.07.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2025.07.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: bf8b295444a1e21fc19bfbc04efaa20fe78f71bb
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 4%

---

# Se han corregido problemas en la versión 2025.07.0

Este artículo cubre los errores corregidos en varias áreas de la versión 2025.07.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 2025.07.0](whats-new-2025-07-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2025.07.0](upgrade-instructions-2025-07-0.md).

## Creación

- Cuando se agrega un comentario XML dentro de un elemento en la vista de Source, los espacios iniciales y finales alrededor del comentario se pierden al cambiar de vista. (GUIDES-29781)
- Las opciones multimedia no funcionan cuando están presentes dentro del icono de puntos suspensivos (el menú **Más**) en la barra de herramientas. (GUIDES-29583)
- Al crear un nuevo tema a través de la interfaz de usuario o del editor de Assets, el tema no se abre automáticamente en el editor si la configuración de `xmleditor.uniquefilenames` está establecida en true en `XMLEditorConfig`. (GUIDES-28171)
- Los espacios añadidos dentro de una ecuación de MathML en la vista de Source no se conservan al cambiar a las vistas del editor. (GUIDES-26111)

## Administración de recursos

- Al abrir un tema en la vista Autor después de actualizar el explorador, las etiquetas aplicadas anteriormente en el panel Propiedades del archivo no se conservan y la adición de nuevas etiquetas sobrescribe las existentes, especialmente cuando hay un gran número de etiquetas disponibles para su selección. (GUIDES-29078)
- Al generar un informe de metadatos para un mapa DITA que contiene un gran número de recursos, el botón **Administrar** deja de responder o muestra una respuesta retrasada. (GUIDES-28443)

## Revisión

- Los intentos de crear tareas de revisión a través del flujo de trabajo de AEM fallan de forma consistente porque no se crea el nodo de revisión. (GUIDES-28214)

## Publicación

- El error de calidad del código se produce al implementar el paquete de componentes de publicación de AEM Sites `guides-components.all-1.3.0.zip` mediante Cloud Manager. (GUIDES-28873)
- Al publicar un mapa DITA con el atributo `chunk=to-content`, se crean nodos JCR duplicados en la nueva salida de AEM Sites, lo que da como resultado una estructura de contenido redundante en AEM Sites. (GUIDES-28104)
- Al publicar un mapa DITA con la nueva salida de AEM Sites, si un tema tiene el atributo `chunk =to-content` y la salida está configurada para utilizar títulos de temas como nombres de página, el nombre de página generado muestra incorrectamente la palabra **fragmento** en lugar de conservar el nombre de tema original. (GUIDES-28102)
- La propiedad `cq:template` establecida en la plantilla de tema de AEM Guides para la nueva publicación de AEM Sites muestra un valor incorrecto, que afecta a la estructura de la plantilla y a la representación de contenido. (GUIDES-27789)


## Plataforma

- Los problemas de rendimiento como tiempos de carga más largos y tiempos de espera intermitentes se observan al trabajar con colecciones grandes. (GUIDES-29065, GUIDES-28793)
- Vulnerabilidades asociadas con la biblioteca de Guava en desuso que se utiliza en los componentes de AEM Guides cargados en Experience Manager Guides.(GUIDES-27402)

## Problemas conocidos

Adobe ha identificado los siguientes problemas conocidos para la versión 2025.07.0:

- Al trabajar con temas de Markdown, aparece un botón **Referencia de tema** en la barra de herramientas del Editor, pero no funciona. (GUIDES-31038)
- Cuando se cargan carpetas con nombres en mayúsculas mediante la aplicación de escritorio de Adobe Experience Manager, la carcasa no se conserva y los nombres aparecen en minúsculas en el Editor. (GUIDES-30909)
- En el cuadro de diálogo **Combinar**, la lista desplegable muestra incorrectamente **Contenido principal** en lugar de mostrar las versiones disponibles del tema seleccionado. (GUIDES-30820)
- Al abrir un mapa DITA con el shell unificado habilitado, el editor se actualiza de forma intermitente.(GUIDES-26919)