---
title: Administrar la duplicación de recursos de origen DITA
description: Obtenga información sobre cómo duplicar recursos de origen DITA
feature: Publishing
role: User
exl-id: 71aec782-2cc1-4fd5-b35b-97a603c3dd48
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
subfeature_v2:
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 0%
---
# Administrar la duplicación de recursos de origen DITA

Cuando los resultados generados a partir del contenido DITA se publican mediante **Publicación rápida** o **Administrar publicación** en algún entorno de publicación, AEM también intenta publicar los recursos de origen DITA asociados, como mapas DITA y, en algunos casos, temas DITA. Esto ocurre porque AEM trata los recursos DITA como dependencias de las páginas de Sites generadas.

![](images/quick-publish-site-instance.png){width="350"}

Para evitar la replicación no deseada del contenido DITA en el entorno de publicación y evitar problemas de rendimiento, los administradores deben administrar explícitamente la replicación de recursos DITA mediante el Administrador de configuración. Esta configuración permite a los administradores controlar la replicación de tipos de recursos DITA admitidos, incluidos los mapas DITA, los temas DITA, los archivos XML y los archivos Markdown (.md).

Para configurar la característica de replicación de recursos DITA, vea [Configurar la replicación de recursos DITA para Cloud Service](../cs-install-guide/configure-dita-assets-replication.md) o [Configurar la replicación de recursos DITA para local](../install-guide/configure-dita-asset-replication.md) según la configuración que utilice
