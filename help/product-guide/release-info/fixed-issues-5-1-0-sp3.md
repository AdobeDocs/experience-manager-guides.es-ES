---
title: Notas de versión | Se han corregido problemas en la versión del paquete de servicio 3 de Adobe Experience Manager Guides 5.1.0
description: Obtenga información acerca de las correcciones de errores en la versión 5.1.0 del Service Pack 3 de Adobe Experience Manager Guides
role: Leader
exl-id: faa9a5d7-616f-4692-98d1-23abc78556b6
TQID: https://experienceleague.adobe.com/qiVY-B-D3FcHq2PH7Go2AAFpnstCrPJ2MVLEalQCVn0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 297
ht-degree: 1%

---

# Se han corregido problemas en la versión 5.1.0 del paquete de servicio 3 (diciembre de 2025)


Este artículo cubre los errores corregidos en varias áreas de la versión 5.1.0 del paquete de servicio 3 de Adobe Experience Manager Guides.

Obtenga información acerca de [instrucciones de actualización para el Service Pack 3 de la versión 5.1.0](upgrade-instructions-5-1-0-sp3.md).


## Creación

- CSS personalizado aplicado en un perfil de nivel de carpeta para temas o asignaciones se revierte al estilo predeterminado en el modo de Vista previa al actualizar el explorador. (GUIDES-31098)
- No se pueden agregar varias **etiquetas de versión** a un tema desde el cuadro de diálogo **Guardar como nueva versión**. (GUIDES-32716)


## Administración de recursos

- No se pudieron quitar las etiquetas Versión del panel **Historial de versiones** en la interfaz de usuario de Assets. (GUIDES-38276)


## Revisión

- Cuando un revisor completa una tarea de revisión o el iniciador actualiza la tarea de revisión sin introducir comentarios, el correo electrónico de notificación enviado muestra el comentario anterior más reciente. (GUIDES-33590)

## Publicación

- Cuando se genera la salida de AEM Sites mediante la asignación de componentes heredados, los temas que utilizan el atributo `copy-to` se publican con el nombre del tema `copy-from` en lugar del nombre establecido en el atributo `copy-to`. (GUIDES-22155)
- Cuando la salida de PDF nativa se genera usando una línea de base dinámica, el término **PDFProject** se muestra como el título de PDF en lugar del título real del mapa. (GUIDES-31102)

## Plataforma

- Si se usa `scope="external"` para una referencia al contenido de DAM dentro de un tema o asignación, la ruta relativa del recurso se sustituirá con un GUID. (GUIDES-35605)

## Problema conocido

Adobe ha identificado el siguiente problema conocido para el paquete de servicio 3 de la versión 5.1.0:

- Cuando marca una tarea de revisión como completada desde la página de detalles de la tarea, esta se completa y se cierra; sin embargo, su estado sigue mostrándose como **En curso** en el panel Revisar. (GUIDES-39375)
