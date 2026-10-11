---
title: Implementación de indexación personalizada para la configuración On-Premise
description: Aprenda a personalizar el contenido de los índices para la configuración On-Premise
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 87c0519d-120a-4bb7-b70f-7d217bcd7580
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 0%
---
# Función de reindexación para buscar y reemplazar (vista de Source) para in situ

Se requiere la reindexación para habilitar la función **Buscar y reemplazar (vista de Source)**, que le permite analizar todo el contenido visible en la vista Autor y también el contenido de Source subyacente (estructura XML, incluidos elementos, etiquetas y valores de atributo) para la cadena buscada.

## Reindexación

Para las configuraciones on-premise, la definición del índice se incluye con el paquete. Para habilitar la función, debe reindexar el contenido.

Comience la reindexación estableciendo la propiedad `reindex=true (Boolean)` en el nodo: ` /oak:index/guidesAssetLucene` para reindexar el contenido capturado anteriormente.

El proceso de reindexación continuará hasta que el sistema vuelva a cambiar automáticamente esta propiedad a false. Puede supervisar el progreso de la operación de reindexación en los registros del sistema.
