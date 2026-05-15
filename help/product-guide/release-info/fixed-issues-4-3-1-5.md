---
title: Notas de versión | Se corrigieron problemas en la versión 4.3.1.5 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 4.3.1.5 de Adobe Experience Manager Guides
role: Leader
exl-id: 082dca28-15da-417c-b511-74eb5ac68078
TQID: https://experienceleague.adobe.com/ujQFyhAp5bIB1OJnmqvbHCaiDip7T2qsjlVAWevykK8
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 130
ht-degree: 6%

---

# Se corrigieron problemas en la versión 4.3.1.5


Este artículo cubre los errores corregidos en varias áreas de la versión 4.3.1.5 de Adobe Experience Manager Guides.



Obtenga información acerca de [instrucciones de actualización para la versión 4.3.1.5](../release-info/upgrade-instructions-4-3-1-5.md).


## Creación

- Si se agregan espacios entre elementos en línea dentro de `<codeblock>`, se producirá un salto de línea en la salida generada. (15247)
- Se producen problemas de experiencia al añadir elementos desde el cuadro de diálogo &quot;Insertar elemento&quot;. (15108)

## Publicación

- Los registros de errores muestran información incorrecta sobre la publicación de contenido con ámbitos externos. (15242)
- Los vínculos internos a archivos DITA que comienzan con `HTTP` se tratan como vínculos externos y causan errores de ámbito. (15155)
- La regeneración del sitio de AEM falla en los mapas DITA. (14369)

## Administración

- La propiedad **fmditaTopicrefs** muestra rutas relativas en lugar de rutas absolutas. (15341)
