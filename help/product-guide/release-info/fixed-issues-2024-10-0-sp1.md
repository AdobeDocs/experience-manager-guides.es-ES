---
title: Notas de versión | Se han corregido problemas en la versión 2024.10.0 Service Pack 1 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2024.10.0 Service Pack 1 de Adobe Experience Manager Guides as a Cloud Service.
exl-id: d5fa200b-1f15-4ec2-adf9-a29382afc3de
TQID: https://experienceleague.adobe.com/ziRAAFKf5Dl-6Hd7ziXwSJepbiVzkXLGz5jDWIILPkU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 299
ht-degree: 5%

---

# Se han corregido problemas en la versión 2024.10.0 Service Pack 1

Este artículo cubre los errores corregidos en varias áreas de la versión 2024.10.0 del Service Pack 1 de Adobe Experience Manager Guides as a Cloud Service.

## Creación

- La creación de mapas DITA en una instancia UUID produce un error cuando `xmleditor.uniquefilenames` está habilitado en `XMLEditorConfig`. (21201)
- Al cerrar un archivo, los comentarios y las etiquetas agregados en el cuadro de diálogo **Guardar cambios y Desbloquear archivo** no se guardan en el Historial de versiones con la nueva versión. Esto es específico de un caso de uso en el que **Pedir protección al cerrar** o **Pedir nueva versión al cerrar** está habilitado en `XMLEditorConfig`. (20065)
- El estado del documento marcado como **Listo** vuelve a **Borrador** antes de guardar una nueva versión, lo que hace que el estado **Listo** no persista en ninguna versión del documento. (20006)
- No se puede agregar un archivo PDF como referencia de imagen en un tema del Editor Web. (21206)
- Al seleccionar un archivo DITA en la interfaz de usuario de Assets, se muestra la opción **Abrir en FrameMaker**, incluso cuando está desactivada en la configuración. (20082)

## Publicación

- En la salida nativa de PDF, faltan títulos de capítulo en la TDC, lo que conduce a una jerarquía incorrecta. (21840)


## Administración

- Se producen fugas de recursos debido a **errores ResourceResolver no cerrado** en los registros. (18488)
- Al crear una línea base nueva o duplicada, las etiquetas se muestran en orden aleatorio. (19307)


## Línea de base

- Si la línea de base tiene un gran número de temas o asignaciones, se agota el tiempo de espera de edición y, a continuación, Guardar una línea de base en una nube, después de 1 minuto. (19558)

## Traducción

- La traducción de mapas mediante Línea de base se hace lenta y, finalmente, no puede cargar la lista de todos los temas asociados y los archivos de asignaciones. (19733)
