---
title: Cómo agregar [!DNL Experience Manager Guides] a tu [!DNL Experience Manager as a Cloud Service] entorno
description: Aprenda a agregar  [!DNL AEM Guides] a su entorno [!DNL AEM as a Cloud Service] de
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
feature: Installation
role: Leader
source-git-commit: 1b25f1df67fa2442ab79830dc2ac5a6eabd0394c
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# [!DNL Adobe Experience Manager Guides] implementación as a Cloud Service

Aprenda a agregar [!DNL Experience Manager Guides] a su entorno [!DNL Experience Manager as a Cloud Service].


>[!NOTE]
>
> A partir de la versión 2024.2.0, Experience Manager Guides solo está disponible como complemento automatizado para Experience Manager as a Cloud Service. Si usa implementaciones manuales para Experience Manager Guides, elimine la línea `<module>dox.installer</module> from file dox/pom.xml` de la base de código de Git de Cloud Manager antes de habilitar Experience Manager Guides para su programa.

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
