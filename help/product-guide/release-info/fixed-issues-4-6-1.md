---
title: Notas de versión | Se han corregido problemas en la versión 4.6.1 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 4.6.1 de Adobe Experience Manager Guides
role: Leader
source-git-commit: 3547eb43977f31dae297ca5cb1f1ab53f7f2b067
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 0%

---


# Se han corregido problemas en la versión 4.6.1 (octubre de 2024)


Este artículo trata sobre los errores corregidos en varias áreas de la versión 4.6.1 de Adobe Experience Manager Guides.

Obtenga información acerca de [instrucciones de actualización para la versión 4.6.1](upgrade-instructions-4-6-1.md).

## Creación

- La creación de mapas DITA en una instancia UUID falla cuando `xmleditor.uniquefilenames` está habilitado en `XMLEditorConfig`. (21201)
- Al cerrar un archivo, los comentarios y las etiquetas agregados en el cuadro de diálogo **Guardar cambios y Desbloquear archivo** no se guardan en el Historial de versiones con la nueva versión. Esto es específico de un caso de uso en el que **Pedir protección al cerrar** o **Pedir nueva versión al cerrar** está habilitado en `XMLEditorConfig`. (20065)
- El estado del documento marcado como **Listo** vuelve a **Borrador** antes de guardar una nueva versión, lo que hace que el estado **Listo** no persista en ninguna versión del documento. (20006)
- No se puede agregar un archivo de PDF como referencia de imagen en un tema del Editor Web. (21206)
- Al seleccionar un archivo DITA en la interfaz de usuario de Assets, se muestra la opción **Abrir en el FrameMaker**, incluso cuando está desactivada en la configuración. (20082)


## Publicación

- La carga de archivos adjuntos en Salesforce falla si la ruta de archivos adjuntos supera la longitud permitida. (19420)
- Al publicar un tema en Salesforce, los vínculos del archivo PDF no se resuelven. (19304)
- El error `DUPLICATE_VALUE` se produce de forma intermitente al intentar volver a publicar un artículo existente en Salesforce. (17932)
- En la salida del PDF nativo, faltan títulos de capítulo en la TDC, lo que conduce a una jerarquía incorrecta. (21840)
- Al publicar AEM Sites, solo está disponible un número limitado de atributos para su inclusión en el índice. (7483)

## Administración

- Se producen fugas de recursos debido a errores **ResourceResolver** sin cerrar en los registros. (18488)
- Al crear una línea base nueva o duplicada, las etiquetas se muestran en orden aleatorio. (19307)









