---
title: Cómo agregar [!DNL Experience Manager Guides] a su entorno [!DNL Experience Manager as a Cloud Service]
description: Aprenda a agregar [!DNL AEM Guides] a su entorno [!DNL AEM as a Cloud Service]
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
feature: Installation
role: Leader
TQID: 'https://experienceleague.adobe.com/lb5mjLR6M3pdFlsdQpwGXotEhbPeyetJ4zVwKV-J-Yg'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: e557051c-ff02-4ff8-9421-cf452af0edd5
    internal-label: Installation
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 0%
---
# [!DNL Adobe Experience Manager Guides] implementación de as a Cloud Service

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
