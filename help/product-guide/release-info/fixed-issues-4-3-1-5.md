---
title: Notas de versión | Se han corregido problemas en la versión 4.3.1.5 de las Guías de Adobe Experience Manager
description: Obtenga información acerca de las correcciones de errores en la versión 4.3.1.5 de las guías de Adobe Experience Manager
role: Leader
source-git-commit: 485f88e2e8724d1dc28deac13d677734fcc15c25
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 2%

---


# Se han corregido problemas en la versión 4.3.1.5


Este artículo cubre los errores corregidos en varias áreas de la versión 4.3.1.5 de Adobe Experience Manager Guides.



Más información [instrucciones de actualización para la versión 4.3.1.5](../release-info/upgrade-instructions-4-3-1-5.md).


## Creación

- Añadir espacios entre elementos en línea dentro de `<codeblock>` provoca un salto de línea en la salida generada. (15247)
- Se producen problemas de experiencia al añadir elementos desde el cuadro de diálogo &quot;Insertar elemento&quot;. (15108)

## Publicación

- Los registros de errores muestran información incorrecta sobre la publicación de contenido con ámbitos externos. (15242)
- Vínculos internos a archivos DITA que empiezan por `HTTP` se tratan como vínculos externos y causan errores de ámbito. (15155)
- AEM La regeneración del sitio de la página falla en los mapas DITA. (14369)

## Administración

- **fmditaTopicrefs** muestra rutas relativas en lugar de rutas absolutas. (15341)

