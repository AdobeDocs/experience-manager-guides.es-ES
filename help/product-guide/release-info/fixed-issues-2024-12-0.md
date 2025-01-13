---
title: Notas de versión | Se han corregido problemas en la versión 2024.12.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2024.12.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: f643a4a22151af2ff14288ab3885c1a6657a80ca
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 1%

---

# Se han corregido problemas en la versión 2024.12.0

Este artículo cubre los errores corregidos en varias áreas de la versión 2024.12.0 de Adobe Experience Manager Guides as a Cloud Service.

Obtenga información acerca de [instrucciones de actualización para la versión 2024.12.0](./upgrade-instructions-2024-12-0.md).

## Creación

- La creación de mapas DITA en una instancia UUID produce un error cuando `xmleditor.uniquefilenames` está habilitado en `XMLEditorConfig`. (21201)
- Al cerrar un archivo, los comentarios y las etiquetas agregados en el cuadro de diálogo **Guardar cambios y Desbloquear archivo** no se guardan en el Historial de versiones con la nueva versión. Esto es específico de un caso de uso en el que **Pedir protección al cerrar** o **Pedir nueva versión al cerrar** está habilitado en `XMLEditorConfig`. (20065)
- El estado del documento marcado como **Listo** vuelve a **Borrador** antes de guardar una nueva versión, lo que hace que el estado **Listo** no persista en ninguna versión del documento. (20006)
- No se puede agregar un archivo de PDF como referencia de imagen en un tema del Editor Web. (21206)
- Al seleccionar un archivo DITA en la interfaz de usuario de Assets, se muestra la opción **Abrir en el FrameMaker**, incluso cuando está desactivada en la configuración. (20082)

## Publicación

- En la salida del PDF nativo, faltan títulos de capítulo en la TDC, lo que conduce a una jerarquía incorrecta. (21840)


## Administración

- Se producen fugas de recursos debido a **errores ResourceResolver no cerrado** en los registros. (18488)
- Al crear una línea base nueva o duplicada, las etiquetas se muestran en orden aleatorio. (19307)


## Línea de base

- Editar y luego guardar una línea de base en una configuración de nube agota el tiempo de espera después de 1 minuto si la línea de base tiene un gran número de temas o mapas. (19558)

## Traducción

- La traducción de mapas mediante línea de base se hace lenta y, finalmente, no puede cargar la lista de todos los temas asociados y los archivos de asignaciones. (19733)
