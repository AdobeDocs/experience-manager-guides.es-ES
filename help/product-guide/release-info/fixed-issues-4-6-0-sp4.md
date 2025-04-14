---
title: Notas de la versión | Problemas corregidos en Adobe Experience Manager versión Service Pack 4 de las Guías 4.6.0
description: Obtenga información sobre las correcciones de errores de la versión 4.6.0 Service Pack 4 de Adobe Experience Manager Guides
role: Leader
source-git-commit: f9a03ae620a362989a36ebaefb264ea28220a4b3
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 1%

---

# Se han corregido problemas en la versión 4.6.0 Service Pack 4 (abril de 2025)


Este artículo cubre los errores corregidos en varias áreas de la versión 4.6.0 Service Pack 4 de Adobe Experience Manager Guides.

Obtenga información sobre las instrucciones de [actualización para la versión](upgrade-instructions-4-6-0-sp4.md) 4.6.0 Service Pack 4.

## Creación

- Arrastrar y soltar una imagen dentro de un tema en **Autor** vista hace que la referencia de imagen se rompa, lo que provoca la pérdida de datos. (25769)
- Al arrastrar y soltar un `topicref` mapa en **Autor** vista no logra realizar la operación prevista y quita el `topicref` siguiente al archivo `topicref`. (19460)
- Si no se cierran las conexiones de la sesión de JCR durante la actualización o la creación de temas, se producen fugas de memoria y tiempo de inactividad del servicio. (26282)

## Publicación

- La publicación nativa en PDF continúa indefinidamente, si el contenido DITA tiene un enlace web sin tener ámbito como `external`. (26434)
- Al crear una nueva línea base con un gran número de etiquetas, hace que el cargador de etiquetas falle e impide que se recuperen las etiquetas. (16232)
- Publicación de PDF nativos y AEM sitios se detiene y se pone en cola, cuando hay errores en el contenido. (26516)

## Problemas conocidos

Adobe Systems ha identificado el siguiente problema conocido para esta versión:

- La publicación nativa de PDF en Windows encuentra errores cuando el contenido DITA contiene un vincular externo que no incluye el `scope` atributo.
