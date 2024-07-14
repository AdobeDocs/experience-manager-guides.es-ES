---
title: Notas de versión | Se han corregido problemas en la versión 4.3.1.5 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 4.3.1.5 de Adobe Experience Manager Guides
role: Leader
exl-id: 082dca28-15da-417c-b511-74eb5ac68078
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 2%

---

# Se han corregido problemas en la versión 4.3.1.5


Este artículo cubre los errores corregidos en varias áreas de la versión 4.3.1.5 de Adobe Experience Manager Guides.



Obtenga información acerca de [instrucciones de actualización para la versión 4.3.1.5](../release-info/upgrade-instructions-4-3-1-5.md).


## Creación

- Si se agregan espacios entre elementos en línea dentro de `<codeblock>`, se producirá un salto de línea en la salida generada. (15247)
- Se producen problemas de experiencia al añadir elementos desde el cuadro de diálogo &quot;Insertar elemento&quot;. (15108)

## Publicación

- Los registros de errores muestran información incorrecta sobre la publicación de contenido con ámbitos externos. (15242)
- Los vínculos internos a archivos DITA que comienzan con `HTTP` se tratan como vínculos externos y causan errores de ámbito. (15155)
- AEM La regeneración del sitio de la página falla en los mapas DITA. (14369)

## Administración

- La propiedad **fmditaTopicrefs** muestra rutas relativas en lugar de rutas absolutas. (15341)
