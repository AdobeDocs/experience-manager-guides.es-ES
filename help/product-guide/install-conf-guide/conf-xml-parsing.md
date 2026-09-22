---
title: Configurar la entidad de análisis de XML para Cloud Service y local
description: Obtenga información sobre cómo configurar la entidad de análisis XML para Cloud Service y On-Premise
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: e4019ae1e605bd26f7df676a4fab8c632fd8fa8e
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



