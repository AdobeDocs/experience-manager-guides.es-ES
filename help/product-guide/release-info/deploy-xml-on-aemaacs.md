---
title: Cómo agregar [!DNL AEM Guides] a su [!DNL AEM as a Cloud Service] entorno
description: Aprenda a añadir [!DNL AEM Guides] a su [!DNL AEM as a Cloud Service] entorno
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%

---

# [!DNL AEM Guides] implementación as a Cloud Service

Aprenda a añadir [!DNL Guides] a su [!DNL AEM as a Cloud Service] entorno.

## Implementación manual mediante la canalización de Git de Cloud Manager

Si ha comprado [!DNL AEM Guides] as a Cloud Service antes del 29 de marzo de 2022, siga estas instrucciones de implementación:

* Si comienza con nuevo, puede reemplazar el código generado automáticamente por [!UICONTROL Cloud Manager] con el código del siguiente repositorio que ya tiene integrado el complemento XML: https://github.com/Adobe-TCS/XML-documentation-for-AEMaaCS

* Si ya ha protegido las personalizaciones en [!UICONTROL Cloud Manager] Para obtener las instrucciones sobre cómo añadir el complemento XML en el código existente, consulte el siguiente repositorio de Git: https://github.com/Adobe-TCS/DoX-Installer-for-AEMaaCS

## Implementación mediante Cloud Manager

Si es un cliente de que ha comprado [!DNL AEM Guides] as a Cloud Service el 29/03/2022 o posteriormente, siga estas instrucciones para agregar [!DNL Guides] a su [!DNL AEM as a Cloud Service] entorno:

1. Inicie sesión en [!UICONTROL Cloud Manager].

1. Edite el programa para el que desea configurar [!DNL AEM Guides].

1. Cambiar a **[!UICONTROL Soluciones y complementos]** pestaña.

1. En el **[!UICONTROL Soluciones y complementos]** , haga clic en **[!UICONTROL Assets]**.

1. Seleccionar **[!UICONTROL Guías]** y seleccione **[!UICONTROL Guardar]**.

AEM Ha configurado correctamente su programa para el aprovisionamiento automático de la solución Guías de la aplicación de forma automática.

![AEM Configuración de la solución Guides](assets/addon-configuration.png)

>[!NOTE]
>
>Para instalar [!DNL AEM Guides] en cualquier entorno bajo el programa integrado, debe ejecutar la canalización asociada al entorno. No se requiere ninguna configuración adicional en la base de código Git de CM para la instalación [!DNL AEM Guides].
