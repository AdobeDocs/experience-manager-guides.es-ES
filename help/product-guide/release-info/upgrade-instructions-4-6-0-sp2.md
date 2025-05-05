---
title: Notas de versión | Instrucciones de actualización para el paquete de servicio 3 de Adobe Experience Manager Guides 4.6.0
description: Obtenga información sobre cómo actualizar al paquete de servicio 3 4.6.0 de Adobe Experience Manager Guides
role: Leader
source-git-commit: 8a24d2fd50b6b6ac93b5513e7a99953fdc1735b8
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 1%

---

# Instrucciones de actualización para la versión 4.6.0 del paquete de servicio 3 (enero de 2025)

Este artículo cubre las instrucciones de actualización y la matriz de compatibilidad para la versión 4.6.0 del paquete de servicio 3 de Adobe Experience Manager Guides.

Para ver la lista de problemas que se han corregido en esta versión, consulte [Problemas corregidos en la versión 4.6.0 del paquete de servicio 3](fixed-issues-4-6-0-sp2.md).

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con el paquete de servicio 3 de Experience Manager Guides 4.6.0.

### Adobe Experience Manager

**4.6.0 Service Pack 3 sin UUID**
Paquete de servicio 21, 20 y 19 de la versión 6.5

**4.6.0 Service Pack 3 UUID**
Paquete de servicio 21, 20 y 19 de la versión 6.5

Para obtener más información, consulte la sección [Requisitos técnicos](../install-guide/download-install-technical-requirements.md) en la Guía de instalación y configuración local.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión | FMPS 2022 | FMPS 2020 | FM 2022 | FM 2020 |
| --- | --- | --- | --- | --- |
| Paquete de servicio 3 de 4.6.0 (no UUID) | 2022 o superior | 2020.2 o superior* | 2022 o superior | 2020.3 o superior |
| Paquete de servicio 3 (UUID) de 4.6.0 | 2022 o superior | 2020.2 o superior* | 2022 o superior | 2020.4 o superior |
| | | | |

AEM *La línea de base y las condiciones creadas en la versión de FMPS a partir de 2020.2 son compatibles con las versiones de FMPS.

### Conector de oxígeno

| Versión | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- |--- |--- |
| Paquete de servicio 3 de 4.6.0 (no UUID) | 2.8-regular-10 | 2.8-regular-10 | 1,6 | 1,6 |
| Paquete de servicio 3 (UUID) de 4.6.0 | 3.6-uuid.9 | 3.6-uuid.9 | 2,3 | 2,3 |
|  |  |   |

### Versión de plantilla de base de conocimiento

| Nombre del paquete de componentes | Versión de componentes | Versión de plantilla |
|---|---|---|
| Paquete de contenido de componentes de Experience Manager Guides para Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

### AEM Nueva versión de plantilla del sitio

| Versión de componentes | Versión del sitio |
|---|---|
| guides-components.all-1.0.0 | aemg-docs.all-1.0.0 |

## Actualice a la versión 4.6.0 Service Pack 3 de Experience Manager Guides

Puede actualizar fácilmente su versión actual de Guides a 4.6.0 Service Pack 3. Antes de continuar con la actualización, debe tener en cuenta los siguientes puntos:

- Si utiliza la versión 4.6.0 o 4.6.0 Service Pack 1, puede actualizar directamente al paquete de servicio 3 4.6.0.
- Si utiliza las versiones 4.4, 4.3.1 o 4.3.0 , debe actualizar a la versión 4.6.0.
- Si utiliza las versiones 4.2, 4.2.1 (revisión 4.2.1.3), 4.1 o 4.1.x, debe actualizar a la versión 4.4 antes de actualizar a la versión 4.6.0.
- Si utiliza la versión 4.0, debe actualizar a la versión 4.2 antes de actualizar a la versión 4.3.x.
- Si utiliza la versión 3.8.5, debe actualizar a la versión 4.0 antes de actualizar a la versión 4.2.
- Si tiene una versión anterior a la 3.8.5, consulte la sección Actualizar Experience Manager Guides en la guía de instalación específica del producto disponible en [Archivo del PDF de ayuda de Adobe Experience Manager Guides](https://helpx.adobe.com/es/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
>AEM Debe instalar el paquete de servicio de antes de actualizar la versión de Experience Manager Guides.

El proceso de actualización para el paquete de servicio 3 de la versión 4.6.0 sigue los mismos pasos que en la versión 4.6.0. Para obtener instrucciones detalladas, vea [Instrucciones de actualización para las versiones On-Premise](../install-guide/upgrade-xml-documentation.md) de Experience Manager Guides.
