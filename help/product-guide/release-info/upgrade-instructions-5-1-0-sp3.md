---
title: Notas de versión | Instrucciones de actualización para el paquete de servicio 3 de Adobe Experience Manager Guides 5.1.0
description: Obtenga información acerca de la matriz de compatibilidad y cómo actualizar a la versión 5.1.0 Service Pack 3 de Adobe Experience Manager Guides.
exl-id: 2452da05-36f2-4df3-aee9-918072a67d9c
TQID: https://experienceleague.adobe.com/qFrmvlpp7uxkLs2KXq3ItTVD6LxteJkMUuKdtmN9JY4
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: afb45297-4313-4f67-818e-bc0b03abe086
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 595
ht-degree: 4%

---

# Instrucciones de actualización para la versión 5.1.0 del paquete de servicio 3 (diciembre de 2025)

Este artículo cubre las instrucciones de actualización y la matriz de compatibilidad para la versión 5.1.0 del paquete de servicio 3 de Adobe Experience Manager Guides.

Para ver la lista de problemas que se han corregido en esta versión, consulte [Problemas corregidos en la versión 5.1.0 del paquete de servicio 3](../release-info/fixed-issues-5-1-0-sp3.md).

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con el paquete de servicio 3 de Experience Manager Guides 5.1.0.

| Guías de AEM | Versión de AEM | Service Pack |
| --- | --- | --- |
| Paquete de servicio 3 (UUID) de 5.1.0 | 6.5 LTS | 1 |
| Paquete de servicio 3 (UUID) de 5.1.0 | 6.5 | 23, 22, 21 |

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

| Guías de AEM | Versión de AEM | Versión de componentes | Versión del sitio |
|---|---|---| ---|
| UUID del paquete de servicio 3 de 5.1.0 | 6.5 LTS | guides-components.all-1.4.1 | aemg-docs.all-1.2.0 |
| UUID del paquete de servicio 3 de 5.1.0 | 6.5 | guides-components.all-1.4.0 | aemg-docs.all-1.2.0 |


## Requisitos previos

De acuerdo con el comportamiento estándar de DITA, el atributo scope=`external` no debe aplicarse a los vínculos internos, ya que está pensado únicamente para referencias a recursos externos. La aplicación de este atributo a los vínculos internos puede interrumpir los flujos de trabajo. Para el contenido administrado en Experience Manager Guides, use el ámbito predeterminado=`local` o referencias basadas en claves en su lugar.

## Actualización a la versión 5.1.0 del paquete de servicio 3 de Experience Manager Guides

Puede actualizar fácilmente su versión actual de Experience Manager Guides a la versión 5.1.0 Service Pack 3 en **AEM 6.5** o **AEM 6.5 LTS**.

>[!NOTE]
>
> Si está actualmente en AEM 6.5 y planea pasar a AEM 6.5 LTS, vea [Actualización a Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

Antes de continuar actualizando al paquete de servicio 3 de Experience Manager Guides versión 5.1.0, debe tener en cuenta los siguientes puntos:

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
