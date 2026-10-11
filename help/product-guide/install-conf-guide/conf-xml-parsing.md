---
title: Configurar la entidad de análisis de XML para Cloud Service y local
description: Obtenga información sobre cómo configurar la entidad de análisis XML para Cloud Service y On-Premise
feature: Output Generation
role: Admin
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 1%
---
# Configurar el límite de tamaño de entidad del analizador XML

Experience Manager Guides permite establecer un límite en el tamaño total de la entidad que acepta el analizador XML durante la publicación. Esto ayuda a evitar problemas como ataques de expansión de entidades XML y procesamiento de cargas útiles sobredimensionadas.

>[!NOTE]
>
>Puede configurar un límite en el tamaño total de la entidad que acepta el analizador XML durante la publicación para mitigar riesgos como ataques de expansión de entidades XML y procesamiento de cargas útiles sobredimensionadas. La administración de los límites de tamaño de la entidad difiere entre Java 21 y Java 25; por lo tanto, se recomienda a los entornos que actualizan a Java 25 que revisen y validen su configuración para garantizar que los flujos de trabajo de publicación sigan funcionando sin errores.

Esta configuración implica dos propiedades relacionadas:

* **Aplicar límite total de tamaño de entidad del analizador XML** (`dxml.publish.xml.apply.total.entity.size.limit`): habilita o deshabilita la comprobación total de límite de tamaño de entidad.
* **Límite total de tamaño de entidad del analizador XML** (`dxml.publish.xml.total.entity.size.limit`): especifica el valor (caracteres) de JAXP `totalEntitySizeLimit` que se aplica a los analizadores XML seguros cuando el indicador de aplicación está habilitado.

Las siguientes pestañas proporcionan instrucciones para configurar estas propiedades en función de la configuración de Experience Manager Guides: Cloud Service o Local.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md) para crear el archivo de configuración.

1. En el archivo de configuración, proporcione los siguientes detalles (propiedad):

   | PID | Clave de propiedad | Valor de propiedad |
   |---|---|---|
   | `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService` | `dxml.publish.xml.apply.total.entity.size.limit` | **Valor predeterminado:** &quot;true&quot; |
   | `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService` | `dxml.publish.xml.total.entity.size.limit` | **Valor predeterminado:** &quot;50000000&quot; |

>[!TAB Local]

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete *com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService*.

1. Configure las siguientes opciones según sus necesidades:

   * **Aplicar límite total de tamaño de entidad del analizador XML** (`dxml.publish.xml.apply.total.entity.size.limit`): de forma predeterminada, esta configuración está deshabilitada.
   * **Límite total de tamaño de entidad del analizador XML** (`dxml.publish.xml.total.entity.size.limit`): De forma predeterminada, este valor está establecido en `50000000` caracteres. Esta configuración entra en vigor únicamente cuando la opción **Aplicar límite de tamaño total de entidad del analizador XML** está habilitada.

1. Seleccione **Guardar**.

>[!ENDTABS]



