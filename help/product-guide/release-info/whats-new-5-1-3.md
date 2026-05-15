---
title: Notas de versión | Novedades de la versión del paquete de servicio 3 de Adobe Experience Manager Guides 5.1.0
description: Obtenga información acerca de las funciones nuevas y mejoradas de la versión 5.1.0 del paquete de servicio 3 de Adobe Experience Manager Guides
role: Leader
exl-id: 1b2e45a8-bea6-4b78-bd2e-cc02df86f40a
TQID: https://experienceleague.adobe.com/dXXQ1YvVduT11vvF5qyXHLqnuo1xMKkAb5I-EoD2JAA
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2: id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 176
ht-degree: 0%

---

# Novedades de la versión 5.1.0 del paquete de servicio 3 (diciembre de 2025)

Este artículo cubre las funciones nuevas y mejoradas introducidas con la versión 5.1.0 del paquete de servicio 3 de Adobe Experience Manager Guides.

Para ver la lista de problemas que se han corregido en esta versión, consulte [Problemas corregidos en la versión 5.1.0 del paquete de servicio 3](fixed-issues-5-1-0-sp3.md).

Obtenga información acerca de [instrucciones de actualización para el Service Pack 3 de la versión 5.1.0](../release-info/upgrade-instructions-5-1-0-sp3.md).


## Configurar representaciones de imágenes personalizadas para ajustes preestablecidos de salida específicos

Ahora puede configurar diferentes representaciones de imagen para ajustes preestablecidos de salida individuales bajo el mismo tipo de salida utilizando el atributo `outputName` en `renditionmapping.xml`. Esta mejora le proporciona una mayor flexibilidad a la hora de publicar contenido que requiera distintas resoluciones de imagen para diferentes escenarios. Por ejemplo, es posible que desee una imagen de alta resolución para la salida principal de HTML5 mientras utiliza una miniatura más pequeña para un ajuste preestablecido ligero.

Para obtener más información, vea [Controlar la representación de imágenes en la generación de salida](../install-guide/conf-output-generation.md#handle-image-rendition-during-output-generation).
