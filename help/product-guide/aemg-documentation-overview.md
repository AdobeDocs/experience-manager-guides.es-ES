---
title: Documentación de Experience Manager Guides
description: Encuentre documentación para Adobe Experience Manager Guides. Obtenga información acerca de la compatibilidad nativa con DITA, la creación estructurada y la publicación multicanal en Experience Manager.
feature: AEM Guides Tutorials
role: User
TQID: https://experienceleague.adobe.com/S4wTM-7gfU7D-JfKVbb9nK3qoQIG6PdiY7jtpsc6kDs
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
    internal-label: Reports
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
subfeature_v2:
  - id: aad65a09-20cc-4780-ad44-329d14dc8481
    internal-label: Workflows
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
    internal-label: Web Editor
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
    internal-label: Content reuse
source-git-commit: a45df7e9eef75b0c4684e944fd9611eb6e7b060e
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 5%
---
# Documentación de Experience Manager Guides

Experience Manager Guides es un CCMS de nivel empresarial compatible con DITA nativo para la creación estructurada, la publicación multicanal y la administración del ciclo de vida de contenido.

**Implementación:** [!BADGE Cloud Service]{type=Positive} [!BADGE Local]{type=Informative}

## Comience por su función

::::landing-cards-container
:::card
![Icono de administradores](../assets/admin.png)

Administradores

Configure perfiles de carpeta, permisos, configuración de flujo de trabajo y plantillas de salida.

[Guía de administración](./install-conf-guide/introduction.md)
:::

:::card
![Icono de autores](../assets/author.png)

Autores

Cree y administre temas, mapas, reutilización de contenido y flujos de trabajo de revisión de DITA.

[Información general sobre la creación](./user-guide/authoring-content.md)
:::

:::card
![Icono de editores](../assets/publisher.png)

Editores

Configure ajustes preestablecidos de salida, administre líneas de base y genere resultados en todos los canales.

[Administración y publicación de mapas](./user-guide/map-console-overview.md)
:::

::::

<!--
:::card
![Architects icon](./user-guide/images/architect.svg)

Architects

Design DITA specializations, schemas, and content architecture for your implementation.

[DITA specialization](./install-conf-guide/dita-ot-specialization.md)
:::

::::
-->

## Explorar por área de funcionalidad

<!-- Author note: Six cards wrap to two rows of three in production. The landing-cards-container component is in beta — verify rendering in production before publishing. -->

::::landing-cards-container

:::card
![Icono de creación](../assets/authoring.png)

Creación

Editor web, integración de FrameMaker, contenido reutilizable y ciclos de revisión.

[Creación del contenido](./user-guide/web-editor.md)
:::

:::card
![Icono de revisión](../assets/review.png)

Revisión

Revisar temas, administrar tareas de revisión y revisar notificaciones.

[Introducción a la revisión](./user-guide/review.md)
:::

:::card
![Icono de publicación](../assets/publishing.png)

Publicación

Tipos de salida PDF, AEM Sites, HTML5, EPUB y JSON.

[Publicación del contenido](./user-guide/generate-output.md)
:::

:::card
![Icono de traducción](../assets/translation.png)

Traducción

Flujos de trabajo de traducción humana y automática para contenido multilingüe.

[Traducir contenido](./user-guide/translation.md)
:::

:::card
![Icono de informes](../assets/reports.png)

Informes

Lista de temas, multimedia, vínculos rotos e informes de metadatos.

[Generación de informes](./user-guide/reports-intro.md)
:::

:::card
![Icono de configuración](../assets/configure.png)

Configuración

Perfiles de carpeta, personalización DITA-OT y plantillas de salida.

[Configuración de perfiles de carpeta](./install-conf-guide/conf-profiles.md)
:::

::::

## Novedades

<!-- Author note: Update images, badge labels, feature titles, descriptions, and links each release cycle. Images are stored in /assets/. The shade box with a borderless HTML table provides the three-column layout. Blank lines inside each <td> are required for ExL to process badge and bold-link markdown syntax. -->

>[!BEGINSHADEBOX]

<table>
<tr style="border: 0;">
<td>

![Conector Git](../assets/whats-new-git-connector.svg)

**[Importar contenido mediante el conector Git](./user-guide/web-editor-git-connector.md)**

Importe contenido en Guías directamente desde repositorios Git.

</td>
<td>

![Colección de mapas](../assets/whats-new-map-collection.svg)

**[Nueva colección de mapas](./user-guide/generate-output-use-new-map-collection-output-generation.md)**

Interfaz unificada para administrar mapas y salidas de publicación.

</td>
<td>

![Delegar revisión](../assets/whats-new-delegate-review.svg)

**[Delegar una tarea de revisión](./user-guide/review-complete-review-tasks.md#delegate-a-review-task-to-another-reviewer)**

Los revisores pueden delegar una tarea de revisión a otro revisor.

</td>
</tr>
</table>

>[!ENDSHADEBOX]

## Recursos adicionales

* [Notas de la versión de Cloud Service](./release-info/latest-release-info-cs.md)
* [Notas de la versión de On-Premise](./release-info/latest-release-info.md)
* [comunidad de AEM Guides](https://experienceleaguecommunities.adobe.com/adobe-experience-manager-guides-11?profile.language=es){target="_blank"}
* [Repositorio de GitHub](https://github.com/AdobeDocs/experience-manager-guides.es-ES){target="_blank"}
* [Soporte](https://experienceleague.adobe.com/support/v2/en/?lang=es){target="_blank"}
* [Tutoriales en vídeo](https://experienceleague.adobe.com/es/docs/experience-manager-guides-learn/videos/getting-started/overview){target="_blank"}
