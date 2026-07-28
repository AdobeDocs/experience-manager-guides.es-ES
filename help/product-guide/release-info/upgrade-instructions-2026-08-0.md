---
title: Notas de versión | Instrucciones de actualización y problemas corregidos en la versión 2026.08.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de la matriz de compatibilidad y cómo actualizar a la versión 2026.08.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 0de22d4883096f6a9f3b2ca8acfad4a10992f5e7
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 1%

---

# Instrucciones de actualización para la versión 2026.08.0

Este artículo describe las instrucciones de actualización y la matriz de compatibilidad para la versión 2026.08.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas características y mejoras, vea [Novedades de la versión 2026.08.0](whats-new-2026-08-0.md).

Para obtener la lista de problemas corregidos en esta versión, vea [Problemas corregidos en la versión 2026.08.0](fixed-issues-2026-08-0.md).

## Matriz de compatibilidad

Esta sección indica la matriz de compatibilidad para las aplicaciones de software compatibles con la versión 2026.08.0 de Experience Manager Guides as a Cloud Service.

### Recursos de Java SDK

Utilice los siguientes recursos al desarrollar complementos de Java personalizados o integraciones con Experience Manager Guides. Asegúrese de que la versión de SDK coincida con la versión de Experience Manager Guides instalada.

| Versión | Versión de Java SDK | Maven Central | Referencia de API de Java |
|---|---|---|----|
| 2026.08.0 | 2026.8.0 | [API de AEM Guides SDK 2026.8.0](https://central.sonatype.com/artifact/com.adobe.aem/aem-dox-sdk-api/2026.8.0) | [Javadoc 2026.8.0](https://javadoc.io/doc/com.adobe.aem/aem-dox-sdk-api/latest/index.html) |

Para obtener más información, vea [Configurar y usar el JAR de API del repositorio de Maven Central](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/api-reference/introduction).

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión de Experience Manager Guides as a Cloud | FMPS | FrameMaker | Oxygen Author |
| --- | --- | --- | --- |
| 2026.08.0 | No compatible | 2022 o superior | 26.1 |


### Conector de oxígeno

| Versión de Experience Manager Guides as a Cloud | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2026.08.0 | 3.8 -uuid 1 | 3.8 -uuid 1 | 2,3 | 2,3 |


### Versión de plantilla del sitio AEM

| Versión de componentes | Versión del sitio |
|---|---|
| guides-components.all-1.5.1 | aemg-sites-template-1.3.0 |

### Versión de plantilla de base de conocimiento

| Nombre del paquete de componentes | Versión de componentes | Versión de plantilla |
|---|---|---|
| Paquete de contenido de componentes de Experience Manager Guides para Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |

## Actualizar a la versión 2026.08.0

Experience Manager Guides se actualiza automáticamente al actualizar a la última versión de Experience Manager as a Cloud Service.

>[!IMPORTANT]
>
> La versión incluye actualizaciones en la configuración del perfil de carpeta (ui_config.json). Si utiliza una configuración personalizada, asegúrese de realizar una copia de seguridad de ellas antes de actualizar. Después de la actualización, revise y ajuste la configuración para que se ajuste a los cambios introducidos en la versión más reciente.

Revise y valide las configuraciones de configuración para confirmar que se han implementado correctamente. Si ha introducido algún cambio en la configuración personalizada, vea [Configuración adicional para actualizar Cloud Service](../install-conf-guide/additional-config-for-upgrade.md) para cualquier procedimiento adicional aplicable a la versión desde la que está actualizando.
