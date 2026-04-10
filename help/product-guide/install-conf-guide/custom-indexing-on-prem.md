---
title: Implementación de indexación personalizada para la configuración On-Premise
description: Aprenda a personalizar el contenido de los índices para la configuración On-Premise
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 0%

---

# Función de reindexación para buscar y reemplazar (vista de Source) para in situ

Se requiere la reindexación para habilitar la función **Buscar y reemplazar (vista de Source)**, que le permite analizar todo el contenido visible en la vista Autor y también el contenido de Source subyacente (estructura XML, incluidos elementos, etiquetas y valores de atributo) para la cadena buscada.

## Reindexación

Para las configuraciones on-premise, la definición del índice se incluye con el paquete. Para habilitar la función, debe reindexar el contenido.

Comience la reindexación estableciendo la propiedad `reindex=true (Boolean)` en el nodo: ` /oak:index/guidesAssetLucene` para reindexar el contenido capturado anteriormente.

El proceso de reindexación continuará hasta que el sistema vuelva a cambiar automáticamente esta propiedad a false. Puede supervisar el progreso de la operación de reindexación en los registros del sistema.
