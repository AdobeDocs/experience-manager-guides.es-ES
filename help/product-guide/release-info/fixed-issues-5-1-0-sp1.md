---
title: Notas de versión | Se han corregido problemas en la versión Adobe Experience Manager Guides 5.1.0 Service Pack 1
description: Obtenga información acerca de las correcciones de errores en la versión 5.1.0 del Service Pack 1 de Adobe Experience Manager Guides
role: Leader
source-git-commit: 575488e1b378c17419add75876a8e7f7423d5116
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 1%

---

# Se han corregido problemas en la versión 5.1.0 del paquete de servicio 1 (octubre de 2025)


Este artículo cubre los errores corregidos en varias áreas de la versión 5.1.0 del paquete de servicio 1 de Adobe Experience Manager Guides.

Obtenga información acerca de [instrucciones de actualización para el Service Pack 1 versión 5.1.0](upgrade-instructions-5-1-0-sp1.md).


## Plataforma

- Al migrar de un UUID que no es UUID a UUID y actualizar a la versión más reciente (5.0+), si mueve imágenes referidas entre carpetas y, a continuación, revierte los archivos DITA (a los que se hace referencia en estas imágenes) a versiones anteriores, se rompen las referencias de imagen. (GUIDES-34315)

## Publicación

- Al publicar un mapa DITA con línea de base en AEM Sites (con asignación de componentes heredados), los elementos de mapa con el atributo `processing-role = resource-only` también se publican. (GUIDES-34298)
