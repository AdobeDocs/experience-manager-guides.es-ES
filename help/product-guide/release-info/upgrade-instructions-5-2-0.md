---
title: Notas de versión | Instrucciones de actualización para la versión 5.2.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de la matriz de compatibilidad y cómo actualizar a la versión 5.2.0 de Adobe Experience Manager Guides.
source-git-commit: a2d4731af4f4996c87dd177a6e45f1d8ebabd6cf
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 4%

---

# Instrucciones de actualización para la versión 5.2.0 (mayo de 2026)

Este artículo describe las instrucciones de actualización y la matriz de compatibilidad para la versión 5.2.0 de Adobe Experience Manager Guides.

Para obtener más información acerca de las nuevas características y mejoras, vea [Novedades de la versión 5.2.0](../release-info/whats-new-5-2-0.md).

Para ver la lista de problemas que se han corregido en esta versión, consulte [Problemas corregidos en la versión 5.2.0](../release-info/fixed-issues-5-2-0.md).

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con la versión 5.2.0 de Experience Manager Guides.

| Guías de AEM | Versión de AEM | Service Pack |
| --- | --- | --- |
| 5.2.0 (UUID) | 6.5 LTS | 2 |
| 5.2.0 (UUID) | 6.5 | 24, 23, 22 |

Para obtener más información, consulte la sección [Requisitos técnicos](../install-guide/download-install-technical-requirements.md) en la Guía de instalación y configuración local.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión | FMPS | FM |
| --- | --- | --- |
| 5.2.0 (UUID) | Compatible | 2026 o superior |

### Conector de oxígeno

| Versión | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- |--- |--- |
| 5.2.0 (UUID) | 3.8-uuid.1 | 3.8-uuid.1 | 2,3 | 2,3 |

### Versión de plantilla de base de conocimiento

| Nombre del paquete de componentes | Versión de componentes | Versión de plantilla |
|---|---|---|
| Paquete de contenido de componentes de Experience Manager Guides para Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |

### Nueva versión de plantilla del sitio AEM


| Guías de AEM | Versión de AEM | Versión de componentes | Versión del sitio |
|---|---|---| ---|
| UUID 5.2.0 | 6.5 LTS | guides-components.all-1.4.1 | ND |
| UUID 5.2.0 | 6.5 | guides-components.all-1.4.0 | aemg-sites-template-1.3.0 |

## Requisitos previos

Antes de iniciar el proceso de actualización de Experience Manager Guides 5.2.0, asegúrese de lo siguiente:

1. Se ha actualizado a Experience Manager Guides versión 5.0.0, 5.0.3, 5.1.0, 5.1.3 o 5.1.4.
1. (Opcional) Cerró todas las tareas de traducción.
1. Se ha cambiado el nivel de registro a **INFO** para la clase `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` y se han anexado estos registros a un nuevo archivo de registro, por ejemplo, `logs/translation_upgrade.log`.

## Ruta de actualización para Experience Manager Guides 5.2.0

Puede actualizar fácilmente su versión actual de Experience Manager Guides a la versión 5.2.0 en **AEM 6.5** o **AEM 6.5 LTS**.

>[!IMPORTANT]
>
> - **Para AEM 6.5 LTS**: Experience Manager Guides 5.2.0 solo es compatible con AEM 6.5 LTS Service Pack 2.
> - **Para AEM 6.5**: Experience Manager Guides 5.2.0 solo es compatible con AEM 6.5 Service Pack 24, 23 y 22.
> - Si actualmente está en AEM 6.5 y planea pasar a AEM 6.5 LTS, asegúrese de completar primero la actualización de AEM antes de continuar con la actualización de Experience Manager Guides 5.2.0. Para obtener más información, vea [Actualización a Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

Antes de continuar actualizando a la versión 5.2.0 de Experience Manager Guides, debe tener en cuenta los siguientes puntos:

- Si utiliza las versiones 5.0.0, 5.0.3, 5.1.0, 5.1.3 o 5.1.4, puede actualizar directamente a la versión 5.2.0.
- Si utiliza las versiones 4.6.3, 4.6.4 y 5.0.x, puede actualizar directamente a la versión 5.1.0.
- Si está utilizando la versión 4.6.0, 4.6.1, debe actualizar a la versión 4.6.3 o 4.6.4 o 5.0.0 antes de actualizar a la versión 5.1.0.
- Si está utilizando la versión 4.3.x, 4.2, 4.2.1 (revisión 4.2.1.3), 4.1 o 4.1.x, debe actualizar a la versión 4.4 antes de actualizar a la versión 5.1.0.
- Si utiliza la versión 4.0, debe actualizar a la versión 4.2 antes de actualizar a la versión 4.3.x.
- Si utiliza la versión 3.8.5, debe actualizar a la versión 4.0 antes de actualizar a la versión 4.2.
- Si tiene una versión anterior a la 3.8.5, consulte la sección Actualizar Experience Manager Guides en la guía de instalación específica del producto disponible en [Adobe Experience Manager Guides help PDF archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

## Proceso de actualización para Experience Manager Guides 5.2.0

>[!IMPORTANT]
>
> El posprocesamiento y la indexación pueden tardar unas horas. Le recomendamos que inicie el proceso de actualización durante las horas de menor actividad.

1. Descargue el paquete de la versión 5.2.0 desde el [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html).
1. Instale el paquete de versión en el que desea actualizar y espere hasta que se instale el paquete.
1. *(Opcional)* Actualizar el complemento Conector de oxígeno lanzado con la versión a la que está actualizando.
1. Borre la caché del explorador después de instalar el paquete.
1. Si ha habilitado la configuración `Enable markup find and replace` para tener acceso a la característica Buscar y reemplazar en la vista Código fuente para el contenido capturado anteriormente, debe reindexar el índice `guidesAssetLucene`. Para obtener más información, vea [Reindexación para buscar y reemplazar](../install-conf-guide/custom-indexing-on-prem.md).
1. Actualice la configuración del sistema para incorporar las nuevas configuraciones introducidas en la versión 5.2.0, lo que garantiza la compatibilidad con las siguientes mejoras:


| Configuraciones agregadas | Archivo de configuración | Etiqueta de visualización de la configuración | Nombre de la configuración |
|-----|-----|------|-----|
| Habilitar o deshabilitar el nuevo editor | `com.adobe.fmdita.config.ConfigManager` | Habilitar Editor 2.0 | `enable.markup.editor` |
| Habilitar o deshabilitar la nueva línea base | `com.adobe.fmdita.config.ConfigManager` | Habilitar línea de base más rápida (v2) | `enable.baseline.v2` |
| Omitir propiedades de metadatos para marcar una versión como sucia | `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | Omitir propiedad de metadatos para versión sucia | `xmleditor.dirtychecker.ignoremetadata` |
| Buscar y reemplazar características en la vista de Source | `com.adobe.fmdita.config.ConfigManager` | Habilitar el marcado para buscar y reemplazar | `enable.markup.findreplace` |
| Habilitar o deshabilitar el omitido de vínculos de igual a igual para la línea de base antigua | `com.adobe.fmdita.config.ConfigManager` | Omitir vínculos de igual a igual para Línea base V1 | `guides.baseline.v1.skip.peer.links` |
| Habilite o deshabilite la inicialización de copias de destino con contenido de origen en el flujo de trabajo de traducción. Esto solo es aplicable cuando el flujo de trabajo de traducción heredada está desactivado.  | `com.adobe.fmdita.config.ConfigManager` | Inicializar copia de idioma de destino con contenido de origen | `translation.workflow.propagate.source.content` |
| Limpieza del almacén de referencia | `com.adobe.fmdita.config.ConfigManager` | Eliminación del árbol b de guías habilitada | `btree.deletion.enabled` |
| Replicación de recursos DITA | `com.adobe.fmdita.config.ConfigManager` | Replicar recursos DITA | `publish.replicate` |
| Procesamiento de recursos | `com.adobe.fmdita.config.ConfigManager` | Trabajo programado para el procesamiento de recursos de las guías | `enable.asset.processing.scheduler` |

Para obtener información detallada sobre esta configuración, vea [Actualizaciones de configuración](../install-conf-guide/configuration-on-prem.md).







