---
title: Implementación y configuración de Dispatcher
description: Obtenga información sobre la configuración de la implementación y Dispatcher en Experience Manager Guides as a Cloud Service
feature: Introduction, Installation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 3%

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
