---
title: Notas de versión | Novedades de la versión 2025.11.0 de Adobe Experience Manager Guides
description: Obtenga información sobre las funciones nuevas y mejoradas de la versión 2025.11.0 de Adobe Experience Manager Guides
role: Leader
exl-id: 270a5faa-a16f-4939-900e-3c6c54660d2c
TQID: https://experienceleague.adobe.com/IuRSYXzBeHanuEsfc3-dPZuIGW3r67zPMeBILR34FvA
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 512
ht-degree: 3%

---

# Novedades de la versión 2025.11.0 (noviembre de 2025)

Este artículo cubre las funciones nuevas y mejoradas introducidas con la versión 2025.11.0 de Adobe Experience Manager Guides as a Cloud Service.

Para ver la lista de problemas corregidos en esta versión, consulte [Problemas solucionados en la versión 2025.11.0](fixed-issues-2025-11-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2025.11.0](../release-info/upgrade-instructions-2025-11-0.md).


## Introducción de un nuevo repositorio en la página de inicio y una experiencia de búsqueda mejorada

El repositorio, ahora accesible directamente desde la página de inicio, sirve como espacio centralizado para mejorar la capacidad de detección de carpetas y archivos. Incluye **panel de navegación de carpetas** dedicado y una **vista tabular personalizable del repositorio**. La experiencia renovada de búsqueda y filtrado facilita considerablemente la búsqueda y localización de archivos. Para obtener más información, vea [Conocer la interfaz del repositorio](../user-guide/home-page-repository-view.md).

![](assets/repository-view-home.png)

En el Editor, la experiencia de búsqueda y filtrado de archivos es ahora coherente con la página de inicio. Se ha introducido un nuevo [panel de búsqueda](../user-guide/search-panel-explorer.md) ubicado en la parte inferior de la interfaz del editor para mostrar los resultados de búsqueda. Además, ahora se cambia el nombre del repositorio a **Explorador** en el Editor, lo que le permite examinar carpetas y archivos como antes.

![](assets/search-panel-explorer.png)


## Indexación mejorada para sugerencias inteligentes en el asistente de IA

Ahora puede rastrear fácilmente el estado de cada intento de indexación de sugerencias inteligentes en el Asistente de IA con nuevos indicadores de estado: Indexación completada, No sincronizado, En curso y Error de indexación. La última marca de tiempo de indexación ahora se registra en el nivel de perfil de carpeta para mejorar la trazabilidad. Además, se aplican restricciones de carpeta principal-secundaria al especificar una carpeta o ruta de archivo para la indexación.

Para obtener más información, vea [Configurar el Asistente de IA para obtener ayuda y crear experiencias inteligentes](../cs-install-guide/conf-folder-level.md#configure-ai-assistant-for-smart-help-and-authoring).

## Mejoras de rendimiento

### Limpieza automatizada del árbol B para un rendimiento óptimo

Para mantener la eficiencia del sistema y evitar la congestión de recursos, un nuevo proceso de fondo limpia regularmente los árboles B del nivel del sistema. Esto garantiza que los recursos que ya no existen o que se agregaron temporalmente no ocupen un espacio innecesario.

El sistema identifica de forma inteligente a los candidatos para la limpieza y realiza la eliminación automatizada. Además, esta función es configurable, lo que proporciona a los administradores control sobre su comportamiento en función de las necesidades operativas.

Para obtener más información, vea [Configurar la limpieza del árbol B](../cs-install-guide/configure-btree-cleanup-cs.md).

### Se ha mejorado el manejo de los mapas DITA con un gran número de claves

Ahora puede trabajar sin problemas con mapas DITA que contienen un gran número de claves. Esta mejora garantiza una carga más rápida y un rendimiento mejorado, lo que facilita la administración de mapas complejos sin interrupciones.

Después de la actualización de la compilación, el sistema puede experimentar un aumento temporal de la carga, lo que provoca un retraso en el posprocesamiento de los datos recién cargados. Esto se debe a un script de un solo uso automatizado (OTS) que se ejecuta en segundo plano. Una vez que el script se complete, el rendimiento del sistema volverá a la normalidad.

### Procesamiento de recursos mejorado

Se ha introducido un proceso automatizado para mantener los recursos de `/content/dam` actualizados. El sistema déclencheur el reprocesamiento de recursos cada 15 minutos. Durante cada ciclo, los recursos que se agregaron recientemente o que permanecieron sin procesar en el intervalo de 15 minutos más reciente se recogen y se vuelven a procesar, lo que mejora la eficacia y la coherencia en todo el repositorio de contenido.

Para obtener más información, vea [Procesar recursos](../user-guide/asset-processor.md).
