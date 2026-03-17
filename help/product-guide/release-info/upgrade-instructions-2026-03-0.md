---
title: Notas de versión | Instrucciones de actualización y problemas corregidos en la versión 2026.03.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de la matriz de compatibilidad y cómo actualizar a la versión 2026.03.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 91befea8c232cd487762ea71f522004e5ca63ee0
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 11%

---

# Instrucciones de actualización para la versión 2026.03.0

Este artículo describe las instrucciones de actualización y la matriz de compatibilidad para la versión 2026.03.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 2026.03.0](whats-new-2026-03-0.md).

Para ver la lista de problemas corregidos en esta versión, consulte [Problemas solucionados en la versión 2026.03.0](fixed-issues-2026-03-0.md).

## Matriz de compatibilidad

Esta sección indica la matriz de compatibilidad para las aplicaciones de software compatibles con la versión 2026.03.0 de Experience Manager Guides as a Cloud Service.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión de Experience Manager Guides as a Cloud | FMPS | FrameMaker | Oxygen Author |
| --- | --- | --- | --- |
| 2026.03.0 | No compatible | 2022 o superior | 26,1 |


### Conector de oxígeno

| Versión de Experience Manager Guides as a Cloud | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2026.03.0 | 3.8 -uuid 1 | 3.8 -uuid 1 | 2,3 | 2,3 |


### Versión de plantilla del sitio AEM

| Versión de componentes | Versión del sitio |
|---|---|
| guides-components.all-1.4.0 | aemg-sites-template-1.3.0 |

### Versión de plantilla de base de conocimiento

| Nombre del paquete de componentes | Versión de componentes | Versión de plantilla |
|---|---|---|
| Paquete de contenido de componentes de Experience Manager Guides para Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |

## Actualizar a la versión 2026.03.0

Experience Manager Guides se actualiza automáticamente al actualizar a la última versión de Experience Manager as a Cloud Service.

>[!IMPORTANT]
>
> Esta versión incluye actualizaciones de la configuración del perfil de carpeta (ui_config.json). Si utiliza una configuración personalizada, asegúrese de realizar una copia de seguridad de ellas antes de actualizar. Después de la actualización, revise y ajuste la configuración para que se ajuste a los cambios introducidos en la versión más reciente.

Revise y valide las configuraciones de configuración para confirmar que se han implementado correctamente. Si ha introducido algún cambio en la configuración personalizada, vea [Configuración adicional para actualizar Cloud Service](../cs-install-guide/additional-config-for-cloud-service.md) para cualquier procedimiento adicional aplicable a la versión desde la que está actualizando.

