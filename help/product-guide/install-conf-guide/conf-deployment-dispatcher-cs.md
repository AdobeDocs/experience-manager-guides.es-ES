---
title: Implementación y configuración de Dispatcher
description: Obtenga información sobre la configuración de la implementación y Dispatcher en Experience Manager Guides as a Cloud Service
feature: Introduction, Installation
role: Admin
level: Experienced
exl-id: 657a42be-36e7-4657-83d5-e866f8e55f09
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: c5fd2af0-6cbb-4746-ab0d-40ecb093af12
    internal-label: Introduction
  - id: e557051c-ff02-4ff8-9421-cf452af0edd5
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 6%
---
# Implementación y configuración de Dispatcher

Este artículo proporciona información sobre cómo implementar Experience Manager Guides as a Cloud Service y configurar Dispatcher.

## Implementación de Experience Manager Guides as a Cloud Service

Puede empezar implementando Experience Manager Guides a través de Cloud Manager. Para implementar el módulo, siga las instrucciones mencionadas en [Implementación de AEM Guides as a Cloud Service](../release-info/deploy-xml-on-aemaacs.md).

>[!NOTE]
>
> A partir de la versión 2024.2.0, Experience Manager Guides solo está disponible como complemento automatizado para Experience Manager as a Cloud Service. Si utiliza diciembre de 2023 o versiones anteriores, puede descargar Adobe Experience Manager Guides desde el repositorio de GitHub e instalarlo. Si usa implementaciones manuales para Experience Manager Guides, quite la línea `<module>dox.installer</module> from file dox/pom.xml` de la base de código de Git de administración en la nube antes de habilitar Experience Manager Guides para su programa.

Siga estos pasos para implementar el módulo de Experience Manager Guides:

1. Inicie sesión en [!UICONTROL Cloud Manager].

1. Edite el programa para el que desea configurar [!DNL Experience Manager Guides].

1. Cambiar a la ficha **[!UICONTROL Soluciones y complementos]**.

1. En la tabla **[!UICONTROL Soluciones y complementos]**, haga clic en **[!UICONTROL Assets]**.

1. Seleccione **[!UICONTROL Guías]** y seleccione **[!UICONTROL Guardar]**.

Ha configurado correctamente su programa para el aprovisionamiento automático de la solución Experience Manager Guides.

![Configurando la solución de Experience Manager Guides](assets/addon-configuration.png)

>[!NOTE]
>
>Para instalar [!DNL Experience Manager Guides] en cualquier entorno bajo el programa integrado, debe ejecutar la canalización asociada al entorno. No se requiere ninguna configuración adicional en el código base de Git de CM para instalar [!DNL Experience Manager Guides].


## Configurar Dispatcher

Dispatcher es la herramienta de almacenamiento en caché o de equilibrio de carga de Adobe Experience Manager. Para obtener más información, consulte [Dispatcher en la nube](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/content-delivery/disp-overview.html?lang=es).

1. Para migrar la configuración de Dispatcher de AMS a Cloud Service, consulte [Migración de la configuración de Dispatcher de AMS a AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/content-delivery/ams-aem.html?lang=es).
1. Para obtener más información sobre cómo configurar Dispatcher, consulte [Configuración de Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=es).

>[!NOTE]
>
> AEM as a Cloud Service no es compatible con Dispatcher para instancias de autor.
