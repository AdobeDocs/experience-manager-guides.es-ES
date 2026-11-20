---
title: Notas de versión | Se han corregido problemas en la versión de Adobe Experience Manager Guides 2026.11.0 Service Pack 1
description: Obtenga información acerca de las correcciones de errores en la versión 2026.11.0 Service Pack 1 de Adobe Experience Manager Guides as a Cloud Service.
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 8821e671951d83439688aa33f88ac1f91f0919eb
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%
---
# Se han corregido problemas en la versión 2026.11.0 del paquete de servicio 1

Este artículo cubre los errores corregidos en la versión 2026.11.0 del paquete de servicio 1 de Adobe Experience Manager Guides as a Cloud Service.

## Publicación

Los siguientes problemas se producen al publicar en AEM Sites (con asignación de componentes compuestos):

- La regeneración de los temas seleccionados o de un submapa con publicación de `microservice-based` tarda aproximadamente el mismo tiempo que la generación del mapa completo. (GUIDES-59322)
- La regeneración de un submapa que contiene temas fragmentados hace que la TDC muestre títulos y vínculos incorrectos. Cada entrada de tema fragmentada muestra el título del último tema dividido. (GUIDES-58650)

Los siguientes problemas se producen al publicar en AEM Sites mediante una línea de base dinámica, ya sea Línea de base (heredada) o Nueva línea de base:

- La línea de base se reconstruye más de una vez durante la misma operación de publicación, lo que alarga el tiempo de publicación y, en algunos casos, hace que la reconstrucción se detenga. Con Nueva línea de base, la publicación incremental también utiliza una línea de base obsoleta en lugar de la actual, por lo que es posible que el resultado no refleje el contenido más reciente. (GUIDES-60189)
- Se observan algunos problemas de rendimiento al utilizar el panel Mapa. (GUIDES-60189, GUIDES-55646)

## Problemas conocidos

Adobe ha identificado los siguientes problemas conocidos para la versión 2026.11.0 del paquete de servicio 1:

- Al utilizar Experience Manager Guides as a Cloud Service 2026.11.0 o posterior, la publicación falla con un error de aplicación si AEM reinicia ciertos servicios internos durante el proceso de publicación, como cuando se inicia una instancia de servidor. (GUIDES-60804)<br>**Solución alternativa:** Para resolver el problema, vuelva a intentar la publicación.
- Al generar resultados para varios ajustes preestablecidos de AEM Sites (mediante la asignación de componentes compuestos) o de PDF nativos a través de **colección de mapas** o API, la generación de resultados falla con una excepción `Rebuild the Baseline`. <br>**Solución alternativa:** Publique los ajustes preestablecidos secuencialmente en lugar de simultáneamente para evitar el problema.