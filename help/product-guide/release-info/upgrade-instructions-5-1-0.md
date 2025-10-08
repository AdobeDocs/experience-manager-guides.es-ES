---
title: Notas de versión | Instrucciones de actualización para la versión 5.1.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de la matriz de compatibilidad y cómo actualizar a la versión 5.1.0 de Adobe Experience Manager Guides.
exl-id: 4b7b6756-d260-4baf-a9cb-d99fc02f020f
source-git-commit: 6bcfed792036a51aa0c11498e4cb489199280a56
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 7%

---

# Instrucciones de actualización para la versión 5.1.0 (septiembre de 2025)

Este artículo describe las instrucciones de actualización y la matriz de compatibilidad para la versión 5.1.0 de Adobe Experience Manager Guides.

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 5.1.0](../release-info/whats-new-5-1-0.md).

Para ver la lista de problemas que se han corregido en esta versión, consulte [Problemas corregidos en la versión 5.1.0](../release-info/fixed-issues-5-1-0.md).

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con la versión 5.1.0 de Experience Manager Guides.

| Guías de AEM | Versión de AEM | Service Pack |
| --- | --- | --- |
| 5.1.0 (UUID) | 6.5 LTS | 1 |
| 5.1.0 (UUID) | 6.5 | 23, 22, 21 |

Para obtener más información, consulte la sección [Requisitos técnicos](../install-guide/download-install-technical-requirements.md) en la Guía de instalación y configuración local.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión | FMPS | FM |
| --- | --- | --- |
| 5.1.0 (UUID) | Compatible | 2022 o superior |

### Conector de oxígeno

| Versión | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- |--- |--- |
| 5.1.0 (UUID) | 3.8-uuid.1 | 3.8-uuid.1 | 2,3 | 2,3 |

### Versión de plantilla de base de conocimiento

| Nombre del paquete de componentes | Versión de componentes | Versión de plantilla |
|---|---|---|
| Paquete de contenido de componentes de Experience Manager Guides para Cloud Service | dxml-components.all-1.3.0 | aem-site-template-dxml.all-1.0.4 |

### Nueva versión de plantilla del sitio AEM


| Guías de AEM | Versión de AEM | Versión de componentes | Versión del sitio |
|---|---|---| ---|
| UUID 5.1.0 | 6.5 LTS | guides-components.all-1.4.1 | aemg-docs.all-1.2.0 |
| UUID 5.1.0 | 6.5 | guides-components.all-1.4.0 | aemg-docs.all-1.2.0 |

## Actualización a Experience Manager Guides 5.1.0

Puede actualizar fácilmente su versión actual de Experience Manager Guides a la versión 5.1.0 en **AEM 6.5** o **AEM 6.5 LTS**.

>[!NOTE]
>
> Si actualmente está en AEM 6.5 y planea pasar a AEM 6.5 LTS, asegúrese de completar primero la actualización de AEM antes de continuar con la actualización de Experience Manager Guides 5.1.0. Para obtener más información, vea [Actualización a Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

Antes de continuar actualizando a la versión 5.1.0 de Experience Manager Guides, debe tener en cuenta los siguientes puntos:

- Si utiliza las versiones 4.6.3, 4.6.4, 5.0.0 o 5.0.0 Service Pack 1, puede actualizar directamente a la versión 5.1.0.
- Si está utilizando la versión 4.6.0, 4.6.1, debe actualizar a la versión 4.6.3 o 4.6.4 o 5.0.0 antes de actualizar a la versión 5.1.0.
- Si está utilizando la versión 4.3.x, 4.2, 4.2.1 (revisión 4.2.1.3), 4.1 o 4.1.x, debe actualizar a la versión 4.4 antes de actualizar a la versión 5.1.0.
- Si utiliza la versión 4.0, debe actualizar a la versión 4.2 antes de actualizar a la versión 4.3.x.
- Si utiliza la versión 3.8.5, debe actualizar a la versión 4.0 antes de actualizar a la versión 4.2.
- Si tiene una versión anterior a la 3.8.5, consulte la sección Actualizar Experience Manager Guides en la guía de instalación específica del producto disponible en [Adobe Experience Manager Guides help PDF archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
>Debe instalar AEM Service Pack antes de actualizar la versión de Experience Manager Guides.

Para obtener más información, vea [Instrucciones de actualización para las versiones On-Premise](../install-guide/upgrade-xml-documentation.md) de Experience Manager Guides.


