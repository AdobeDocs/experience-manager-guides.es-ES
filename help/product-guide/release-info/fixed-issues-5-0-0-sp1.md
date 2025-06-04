---
title: Notas de versión | Se han corregido problemas en la versión Adobe Experience Manager Guides 5.0.0 Service Pack 1
description: Obtenga información acerca de las correcciones de errores en la versión 5.0.0 del Service Pack 1 de Adobe Experience Manager Guides
role: Leader
source-git-commit: 083a8e16b9d3cd6c3894d7eaa2fee489b1dc0bb8
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 1%

---


# Se han corregido problemas en la versión 5.0.0 del paquete de servicio 1 (junio de 2025)


Este artículo cubre los errores corregidos en varias áreas de la versión 5.0.0 del paquete de servicio 1 de Adobe Experience Manager Guides.

Obtenga información acerca de [instrucciones de actualización para la versión 5.0.0 del Service Pack 1](upgrade-instructions-5-0-0-sp1.md).

## Creación

- Cuando el contenido se pega en `codeblock` o cuando se agregan espacios en `codeblock` y se cambia la vista, se pierde el espaciado. (GUIDES-29347)
- Cuando se agrega un comentario XML dentro de un elemento en la vista **Source**, los espacios iniciales y finales alrededor del comentario se pierden al cambiar de vista. (GUÍAS- 28188)

## Administración de recursos

- Al abrir un tema en la vista **Autor** después de actualizar el explorador, las etiquetas aplicadas anteriormente en el panel **Propiedades del archivo** no se conservan y al agregar nuevas etiquetas se sobrescriben las existentes, especialmente cuando hay un gran número de etiquetas disponibles para la selección. (GUIDES-29078)
- Al generar un informe de metadatos para un mapa DITA que contiene un gran número de recursos, el botón **Administrar** deja de responder o muestra una respuesta retrasada. (GUIDES-29778)

## Traducción

- Al enviar recursos para su traducción desde Experience Manager Guides, no se agregan en el trabajo de traducción, lo que impide que aparezca el botón **Start** y que inicie el trabajo de traducción. (GUIDES-28237)

## Publicación

- Al modificar la configuración de un ajuste preestablecido de salida dentro del perfil de carpeta y seleccionar **Aplicar cambios preestablecidos**, los cambios no se propagan a los ajustes preestablecidos de salida presentes en el mapa DITA. (GUIDES-26694)

## Revisión

- Los intentos de crear tareas de revisión a través del flujo de trabajo de AEM fallan de forma consistente porque no se crea el nodo de revisión. (GUIDES-28214)
