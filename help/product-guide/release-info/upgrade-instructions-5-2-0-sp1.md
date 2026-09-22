---
title: Notas de versión | Instrucciones de actualización para el paquete de servicio 1 de Adobe Experience Manager Guides 5.2.0
description: Obtenga información acerca de la matriz de compatibilidad y cómo actualizar a la versión 5.2.0 del Service Pack 1 de Adobe Experience Manager Guides.
source-git-commit: 6841c373b75770e8691a2cac4d56aeb368b09480
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 3%
---
# Instrucciones de actualización para la versión 5.2.0 del paquete de servicio 1 (septiembre de 2026)

Este artículo cubre las instrucciones de actualización y la matriz de compatibilidad para la versión 5.2.0 del paquete de servicio 1 de Adobe Experience Manager Guides.

Para obtener más información acerca de las nuevas características y mejoras, vea [Novedades de la versión 5.2.0 del Service Pack 1](../release-info/whats-new-5-2-1.md).

Para ver la lista de problemas que se han corregido en esta versión, consulte [Problemas corregidos en la versión 5.2.0 del paquete de servicio 1](../release-info/fixed-issues-5-2-0-sp1.md).

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con la versión Experience Manager Guides 5.2.0 Service Pack 1.

| Guías de AEM | Versión de AEM | Service Pack |
| --- | --- | --- |
| Paquete de servicio 1 (UUID) de 5.2.0 | 6.5 LTS | 2 |
| Paquete de servicio 1 (UUID) de 5.2.0 | 6.5 | 24, 23, 22 |

Para obtener más información, consulte la sección [Requisitos técnicos](../install-conf-guide/aemg-technical-requirements.md) en la Guía de instalación y configuración local.


### Recursos de Java SDK

Utilice los siguientes recursos al desarrollar complementos de Java personalizados o integraciones con Experience Manager Guides. Asegúrese de que la versión de SDK coincida con la versión de Experience Manager Guides instalada.

| Versión | Versión de Java SDK | Maven Central | Referencia de API de Java |
|---|---|---|----|
| Paquete de servicio 1 (UUID) de 5.2.0 | 5.2.2 | [API de AEM Guides SDK 5.2.2](https://central.sonatype.com/artifact/com.adobe.aem/aem-guides-sdk-api/5.2.2/) | [Javadoc 5.2.2](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api/latest/index.html) |

Para obtener más información, vea [Configurar y usar el JAR de API del repositorio de Maven Central](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/api-reference/introduction).


### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión | FMPS | FM |
| --- | --- | --- |
| Paquete de servicio 1 (UUID) de 5.2.0 | Compatible | 2026 o superior |

### Conector de oxígeno

| Versión | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- |--- |--- |
| Paquete de servicio 1 (UUID) de 5.2.0 | 3.8-uuid.1 | 3.8-uuid.1 | 2,3 | 2,3 |

### Versión de plantilla de base de conocimiento

| Nombre del paquete de componentes | Versión de componentes | Versión de plantilla |
|---|---|---|
| Paquete de contenido de componentes de Experience Manager Guides para Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |

### Nueva versión de plantilla del sitio AEM


| Guías de AEM | Versión de AEM | Versión de componentes | Versión del sitio |
|---|---|---| ---|
| UUID del paquete de servicio 1 de 5.2.0 | 6.5 LTS | guides-components.all-1.4.1 | ND |
| UUID del paquete de servicio 1 de 5.2.0 | 6.5 | guides-components.all-1.4.0 | aemg-sites-template-1.3.0 |

## Requisitos previos

Antes de iniciar el proceso de actualización del paquete de servicio 1 de Experience Manager Guides 5.2.0, asegúrese de que dispone de lo siguiente:

1. Se ha actualizado a Experience Manager Guides versión 5.2.0.
1. (Opcional) Cerró todas las tareas de traducción.
1. Se ha cambiado el nivel de registro a **INFO** para la clase `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` y se han anexado estos registros a un nuevo archivo de registro, por ejemplo, `logs/translation_upgrade.log`.

## Ruta de actualización del paquete de servicio 1 de Experience Manager Guides 5.2.0

Puede actualizar fácilmente su versión actual de Experience Manager Guides a la versión 5.2.0 Service Pack 1 en **AEM 6.5** o **AEM 6.5 LTS**.

>[!IMPORTANT]
>
> - **Para AEM 6.5 LTS**: Experience Manager Guides 5.2.0 Service Pack 1 solo es compatible con AEM 6.5 LTS Service Pack 2.
> - **Para AEM 6.5**: el paquete de servicio 1 de Experience Manager Guides 5.2.0 solo es compatible con el paquete de servicio 24, 23 y 22 de AEM 6.5.
> - Si actualmente está en AEM 6.5 y planea pasar a AEM 6.5 LTS, asegúrese de completar primero la actualización de AEM antes de continuar con la actualización de Experience Manager Guides 5.2.0. Para obtener más información, vea [Actualización a Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).
> - Si actualmente está en AEM 6.5 y planea pasar a AEM 6.5 Service Pack 24 o posterior, asegúrese de completar primero la actualización de AEM. Una vez finalizado, vuelva a instalar Experience Manager Guides 5.2.0. antes de instalar Experience Manager Guides 5.2.1.

Antes de continuar actualizando al paquete de servicio 1 de Experience Manager Guides versión 5.2.0, debe tener en cuenta los siguientes puntos:

- Si utiliza la versión 5.2.0, puede actualizar directamente a la versión 5.2.0 Service Pack 1.
- Si utiliza las versiones 5.0.0, 5.0.3, 5.1.0, 5.1.3 o 5.1.4, puede actualizar directamente a la versión 5.2.0.
- Si utiliza las versiones 4.6.3, 4.6.4 y 5.0.x, puede actualizar directamente a la versión 5.1.0.
- Si está utilizando la versión 4.6.0, 4.6.1, debe actualizar a la versión 4.6.3 o 4.6.4 o 5.0.0 antes de actualizar a la versión 5.1.0.
- Si está utilizando la versión 4.3.x, 4.2, 4.2.1 (revisión 4.2.1.3), 4.1 o 4.1.x, debe actualizar a la versión 4.4 antes de actualizar a la versión 5.1.0.
- Si utiliza la versión 4.0, debe actualizar a la versión 4.2 antes de actualizar a la versión 4.3.x.
- Si utiliza la versión 3.8.5, debe actualizar a la versión 4.0 antes de actualizar a la versión 4.2.
- Si tiene una versión anterior a la 3.8.5, consulte la sección Actualizar Experience Manager Guides en la guía de instalación específica del producto disponible en [Adobe Experience Manager Guides help PDF archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

## Proceso de actualización para el paquete de servicio 1 de Experience Manager Guides 5.2.0

>[!IMPORTANT]
>
> El posprocesamiento y la indexación pueden tardar unas horas. Se recomienda iniciar el proceso de actualización durante las horas de menor actividad.

1. Descargue el paquete de la versión 5.2.0 del Service Pack 1 desde el [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html).
1. Instale el paquete de versión en el que desea actualizar y espere hasta que se instale el paquete.
1. *(Opcional)* Actualizar el complemento Conector de oxígeno lanzado con la versión a la que está actualizando.
1. Borre la caché del explorador después de instalar el paquete.
1. Si ha habilitado la configuración `Enable markup find and replace` para tener acceso a la característica Buscar y reemplazar en la vista Código fuente para el contenido capturado anteriormente, debe reindexar el índice `guidesAssetLucene`. Para obtener más información, vea [Reindexación para buscar y reemplazar](../install-conf-guide/custom-indexing-on-prem.md).







