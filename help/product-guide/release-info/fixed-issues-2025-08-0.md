---
title: Notas de versión | Se han corregido problemas en la versión 2025.08.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2025.08.0 de Adobe Experience Manager Guides as a Cloud Service.
exl-id: 05fe0e2c-ec65-4aec-a543-9b9a75c82f2c
TQID: https://experienceleague.adobe.com/7J25vfpTwwPyT3-qNF6-LLbPra8EePs5XaKqkAjEk5I
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 713
ht-degree: 6%

---

# Se han corregido problemas en la versión 2025.08.0

Este artículo cubre los errores corregidos en varias áreas de la versión 2025.08.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 2025.08.0](whats-new-2025-08-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2025.08.0](upgrade-instructions-2025-08-0.md).

## Creación

- Los archivos **CSS** y **Page layout** de las plantillas nativas de PDF muestran un comportamiento inconsistente de bloqueo de archivos, lo que permite realizar modificaciones incluso cuando los archivos están bloqueados. (GUIDES-26688)
- Al actualizar la página después de agregar botones personalizados al panel izquierdo, se crean pestañas duplicadas. (GUIDES-30899)
- Cuando el contenido XML que contiene corchetes angulares (como &lt;/ o />) se agrega dentro de un elemento `code block` en un tema, el elemento de bloque de código aparece en blanco en el resultado final. (GUIDES-31007)
- Los valores de las variables globales `canCheckIn` y `canCheckOut` no se configuran correctamente cuando se desprotege y protege un archivo desde la barra de herramientas del Editor. (GUIDES-29890)
- Al abrir un mapa DITA con el shell unificado habilitado, el editor se actualiza intermitentemente. (GUIDES-26919)
- Cuando se selecciona un mapa DITA en la vista Mapa, el recuento de selecciones no se muestra correctamente al principio porque los nodos secundarios del mapa no están seleccionados. El recuento de selección correcto y la inclusión de todos los nodos secundarios solo se reflejan en la selección posterior. (GUIDES-25663)
- Los archivos Markdown no se recuperan cuando se buscan en el panel Repositorio utilizando el filtro **DITA topic**. Además, **Buscar y reemplazar** no funciona con archivos Markdown ni con contenido relacionado. (GUIDES-27133)
- No se puede personalizar el menú desplegable **Menú** de la barra de herramientas del Editor usando el marco de trabajo de la extensión. Como resultado, no se puede ocultar ni mostrar ningún botón existente ni agregar botones nuevos en la lista desplegable Menú. (GUIDES-28748)

## Administración de recursos

- Copiar una carpeta con un gran número de recursos desde la interfaz de usuario de Assets lleva a un tiempo de espera de API. La operación sigue ejecutándose en el back-end y se completa después de un tiempo, pero no se muestra ningún mensaje de éxito o error ni notificación en la interfaz de usuario. (GUIDES-30900)
- La operación de copiar y pegar realizada en una carpeta de la interfaz de usuario de Assets falla debido a errores posteriores al procesamiento. (GUIDES-30840)
- La operación de copiar y pegar falla en las carpetas que contienen recursos compuestos (recursos con subrecursos) en la interfaz de usuario de Assets. (28107)
- Las carpetas con un gran número de recursos no se cargan correctamente en el repositorio. (GUIDES-32500)
- Los nombres de los nodos de carpeta se muestran incorrectamente en lugar de los títulos de las carpetas en el Editor. (GUIDES-32402)
- Se produce un error al cargar recursos con caracteres no admitidos o prohibidos en los nombres de archivo. (GUIDES-28845)

## Publicación

- En la salida nativa de PDF, la lista de índices (LOI) aparece en un orden no alfabético y los términos de índice anidados no se agrupan correctamente, lo que dificulta la navegación por el índice. (GUIDES-29090)
- La lista desplegable **Plantilla de página de mapa** y **Plantilla de página de tema** de la página de salida de la asignación de componentes de AEM Sites aparece en blanco cuando la ruta de destino contiene una variable con dos puntos. (GUIDES-28119)
- Cuando un mapa DITA contiene diferentes tipos de referencias temáticas, como Concepto, Referencia o Tarea, y se combina con el atributo `chunk=to-content` para generar una salida de página única en AEM Sites con asignación de componentes, el contenido no se publica correctamente debido a errores de publicación. (GUIDES-28118)

## Línea de base

- Al copiar un mapa DITA desde la interfaz de usuario de Assets, también se copia la línea de base adjunta al nuevo mapa. (GUIDES-11227)

## Página de inicio

- La página de inicio queda en blanco cuando uno de los archivos enumerados en el widget **Archivos recientes** se basa en una plantilla cuya plantilla de origen no incluye una miniatura. (GUIDES-31506)

## Problemas conocidos

Adobe ha identificado los siguientes problemas conocidos para la versión 2025.08.0:

- Cuando se cambia el nombre de un archivo abierto en el Editor o se mueve, al cambiar entre los modos (como **Autor**, **Vista previa** y más) se actualiza el contenido en el área de edición, pero no se resalta visualmente el modo activo en la esquina inferior derecha. (GUIDES-32719) <br> **Solución alternativa**: Actualice la página para resolver el problema.
- Las imágenes con espacios en los nombres de archivo no se muestran en la salida cuando se marcan con atributos condicionales. (GUIDES-33858)
- En el panel **Propiedades de contenido**, el campo Atributos se cierra automáticamente cuando intenta actualizar una referencia desde el cuadro de diálogo **Actualizar vínculo**, lo que impide que se actualice el vínculo. (GUIDES-17767)
