---
title: Notas de versión | Se han corregido problemas en la versión Adobe Experience Manager Guides 5.1.0 Service Pack 1
description: Obtenga información acerca de las correcciones de errores en la versión 5.1.0 del Service Pack 1 de Adobe Experience Manager Guides
role: Leader
exl-id: 4b51085b-1f71-41e2-b0a9-88a12990fc97
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 144
ht-degree: 1%

---

# Se han corregido problemas en la versión 5.1.0 del paquete de servicio 1 (octubre de 2025)


Este artículo cubre los errores corregidos en varias áreas de la versión 5.1.0 del paquete de servicio 1 de Adobe Experience Manager Guides.

Obtenga información acerca de [instrucciones de actualización para el Service Pack 1 versión 5.1.0](upgrade-instructions-5-1-0-sp1.md).


## Plataforma

- Al migrar de un UUID que no es UUID a UUID y actualizar a la versión más reciente (5.0+), si mueve imágenes referidas entre carpetas y, a continuación, revierte los archivos DITA (a los que se hace referencia en estas imágenes) a versiones anteriores, se rompen las referencias de imagen. (GUIDES-34315)

## Publicación

- Al publicar un mapa DITA con línea de base en AEM Sites (con asignación de componentes heredados), los elementos de mapa con el atributo `processing-role = resource-only` también se publican. (GUIDES-34298)
