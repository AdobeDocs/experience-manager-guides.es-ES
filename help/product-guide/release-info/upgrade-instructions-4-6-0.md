---
title: Notas de versión | Instrucciones de actualización para la versión 4.6.0 de Adobe Experience Manager Guides
description: Obtenga información sobre cómo actualizar a la versión 4.6.0 de Adobe Experience Manager Guides
role: Leader
source-git-commit: 1880d889dc9063ef05c4f856d6082d1ea03b7946
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 5%

---

# Instrucciones de actualización para la versión 4.6.0 (septiembre de 2024)

Este artículo describe las instrucciones de actualización y la matriz de compatibilidad para la versión 4.6.0 de Adobe Experience Manager Guides.

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 4.6.0](../release-info/whats-new-4-6.md).

Para ver la lista de problemas que se han corregido en esta versión, consulte [Problemas corregidos en la versión 4.6.0](../release-info/fixed-issues-4-6-0.md).

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con la versión 4.6.0 de Experience Manager Guides.

### Adobe Experience Manager

**4.6.0 sin UUID**
Paquete de servicio 21, 20 y 19 de la versión 6.5

**UUID 4.6.0**
Paquete de servicio 21, 20 y 19 de la versión 6.5

Para obtener más información, consulte la sección [Requisitos técnicos](../install-guide/download-install-technical-requirements.md) en la Guía de instalación y configuración local.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión | FMPS 2022 | FMPS 2020 | FM 2022 | FM 2020 |
| --- | --- | --- | --- | --- |
| 4.6.0 (no UUID) | 2022 o superior | 2020.2 o superior* | 2022 o superior | 2020.3 o superior |
| 4.6.0 (UUID) | 2022 o superior | 2020.2 o superior* | 2022 o superior | 2020.4 o superior |
| | | | |

AEM *La línea de base y las condiciones creadas en la versión de FMPS a partir de 2020.2 son compatibles con las versiones de FMPS.

### Conector de oxígeno

| Versión | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.6.0 (no UUID) | 2.8-regular-10 | 2.8-regular-10 | 1,6 | 1,6 |
| 4.6.0 (UUID) | 3.6-uuid.9 | 3.6-uuid.9 | 2,3 | 2,3 |
|  |  |   |

### Versión de plantilla de base de conocimiento

| Nombre del paquete de componentes | Versión de componentes | Versión de plantilla |
|---|---|---|
| Paquete de contenido de componentes de Experience Manager Guides para Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

### AEM Nueva versión de plantilla del sitio


| Versión de componentes | Versión del sitio |
|---|---|
| guides-components.all-1.0.0 | aemg-docs.all-1.0.0 |

## Actualización a la versión 4.6.0 de Experience Manager Guides

Puede actualizar fácilmente su versión actual de Guides a la versión 4.6.0. Antes de continuar actualizando a la versión 4.6.0 de Experience Manager Guides, debe tener en cuenta los siguientes puntos:

- Si utiliza las versiones 4.4, 4.3.1 o 4.3.0 , puede actualizar directamente a la versión 4.6.0.
- Si utiliza las versiones 4.2, 4.2.1 (revisión 4.2.1.3), 4.1 o 4.1.x, debe actualizar a la versión 4.4 antes de actualizar a la versión 4.6.0.
- Si utiliza la versión 4.0, debe actualizar a la versión 4.2 antes de actualizar a la versión 4.3.x.
- Si utiliza la versión 3.8.5, debe actualizar a la versión 4.0 antes de actualizar a la versión 4.2.
- Si tiene una versión anterior a la 3.8.5, consulte la sección Actualizar Experience Manager Guides en la guía de instalación específica del producto disponible en [Archivo del PDF de ayuda de Adobe Experience Manager Guides](https://helpx.adobe.com/es/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
>AEM Debe instalar el paquete de servicio de antes de actualizar la versión de Experience Manager Guides.

Para obtener más información, vea [Instrucciones de actualización para las versiones On-Premise](../install-guide/upgrade-xml-documentation.md) de Experience Manager Guides.
