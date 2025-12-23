---
title: Notas de versión | Instrucciones de actualización para el paquete de servicio 3 de Adobe Experience Manager Guides 5.1.0
description: Obtenga información acerca de la matriz de compatibilidad y cómo actualizar a la versión 5.1.0 Service Pack 3 de Adobe Experience Manager Guides.
source-git-commit: 172599c2bd99f1779b04255aac5e7d505614b463
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 1%

---

# Instrucciones de actualización para la versión 5.1.0 del paquete de servicio 3 (diciembre de 2025)

Este artículo cubre las instrucciones de actualización y la matriz de compatibilidad para la versión 5.1.0 del paquete de servicio 3 de Adobe Experience Manager Guides.

Para ver la lista de problemas que se han corregido en esta versión, consulte [Problemas corregidos en la versión 5.1.0 del paquete de servicio 3](../release-info/fixed-issues-5-1-0-sp3.md).

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con la versión 5.1.0 de Experience Manager Guides.

### Adobe Experience Manager

**UUID del paquete de servicio 3 5.1.0**

Paquete de servicio 23, Paquete de servicio 22 y Paquete de servicio 21 de la versión 6.5

Para obtener más información, consulte la sección [Requisitos técnicos](../install-guide/download-install-technical-requirements.md) en la Guía de instalación y configuración local.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión | FMPS | FM |
| --- | --- | --- |
| Paquete de servicio 3 (UUID) de 5.1.0 | Compatible | 2022 o superior |

### Conector de oxígeno

| Versión | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- |--- |--- |
| Paquete de servicio 3 (UUID) de 5.1.0 | 3.8-uuid.1 | 3.8-uuid.1 | 2,3 | 2,3 |

### Versión de plantilla de base de conocimiento

| Nombre del paquete de componentes | Versión de componentes | Versión de plantilla |
|---|---|---|
| Paquete de contenido de componentes de Experience Manager Guides para Cloud Service | dxml-components.all-1.3.0 | aem-site-template-dxml.all-1.0.4 |

### Nueva versión de plantilla del sitio AEM


| Versión de componentes | Versión del sitio |
|---|---|
| guides-components.all-1.4.0 | aemg-docs.all-1.2.0 |

## Requisitos previos

De acuerdo con el comportamiento estándar de DITA, el atributo scope=`external` no debe aplicarse a los vínculos internos, ya que está pensado únicamente para referencias a recursos externos. La aplicación de este atributo a los vínculos internos puede interrumpir los flujos de trabajo. Para el contenido administrado en Experience Manager Guides, use el ámbito predeterminado=`local` o referencias basadas en claves en su lugar.

## Actualización a la versión 5.1.0 del paquete de servicio 3 de Experience Manager Guides

Puede actualizar fácilmente su versión actual de Guides a la versión 5.1.0 Service Pack 3. Antes de continuar actualizando al paquete de servicio 3 de Experience Manager Guides versión 5.1.0, debe tener en cuenta los siguientes puntos:

- Si utiliza la versión 5.1.0 o 5.1.x , puede actualizar directamente a la versión 5.1.0 Service Pack 3.
- Si utiliza las versiones 4.6.0, 4.6.x, 5.0.0 o 5.0.x, debe actualizar a la versión 5.1.0.
- Si utiliza las versiones 4.6.3, 4.6.1, 4.6 o 4.4, debe actualizar a la versión 5.0.0.
- Si está utilizando la versión 4.3.x, 4.2, 4.2.1 (revisión 4.2.1.3), 4.1 o 4.1.x, debe actualizar a la versión 4.4 antes de actualizar a la versión 5.0.0.
- Si utiliza la versión 4.0, debe actualizar a la versión 4.2 antes de actualizar a la versión 4.3.x.
- Si utiliza la versión 3.8.5, debe actualizar a la versión 4.0 antes de actualizar a la versión 4.2.
- Si tiene una versión anterior a la 3.8.5, consulte la sección Actualizar Experience Manager Guides en la guía de instalación específica del producto disponible en [Adobe Experience Manager Guides help PDF archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
> Debe instalar AEM Service Pack antes de actualizar la versión de Experience Manager Guides.

Para obtener más información, vea [Instrucciones de actualización para las versiones On-Premise](../install-guide/upgrade-xml-documentation.md) de Experience Manager Guides.
