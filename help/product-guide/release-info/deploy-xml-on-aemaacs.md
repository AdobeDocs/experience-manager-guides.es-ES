---
title: Cómo agregar [!DNL Experience Manager Guides] a su [!DNL Experience Manager as a Cloud Service] entorno
description: Aprenda a añadir [!DNL AEM Guides] a su [!DNL AEM as a Cloud Service] entorno
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
feature: Installation
role: Leader
source-git-commit: 1b25f1df67fa2442ab79830dc2ac5a6eabd0394c
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# [!DNL Adobe Experience Manager Guides] implementación as a Cloud Service

Aprenda a añadir [!DNL Experience Manager Guides] a su [!DNL Experience Manager as a Cloud Service] entorno.


>[!NOTE]
>
> A partir de la versión 2024.2.0, las guías del Experience Manager solo están disponibles como complemento automatizado para Experience Manager as a Cloud Service. Si utiliza implementaciones manuales para las guías del Experience Manager, elimine la línea `<module>dox.installer</module> from file dox/pom.xml` en la nube, administre el código base de Git antes de habilitar las guías del Experience Manager para su programa.

1. Inicie sesión en [!UICONTROL Cloud Manager].

1. Edite el programa para el que desea configurar [!DNL Experience Manager Guides].

1. Cambiar a **[!UICONTROL Soluciones y complementos]** pestaña.

1. En el **[!UICONTROL Soluciones y complementos]** , haga clic en **[!UICONTROL Assets]**.

1. Seleccionar **[!UICONTROL Guías]** y seleccione **[!UICONTROL Guardar]**.

Ha configurado correctamente su programa para el aprovisionamiento automático de la solución Guías de Experience Manager.

![Configuración de la solución Guías del Experience Manager](assets/addon-configuration.png)

>[!NOTE]
>
>Para instalar [!DNL Experience Manager Guides] en cualquier entorno bajo el programa integrado, debe ejecutar la canalización asociada al entorno. No se requiere ninguna configuración adicional en la base de código Git de CM para la instalación [!DNL Experience Manager Guides].
