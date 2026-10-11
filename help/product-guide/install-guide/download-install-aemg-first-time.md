---
title: Descargue e instale AEM Guides por primera vez
description: Obtenga información sobre cómo descargar e instalar AEM Guides por primera vez
exl-id: 830a4381-303c-419c-b87f-9563352a7eeb
feature: Introduction, Installation
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/9EMSF4ux-NFRH6AuxPWneqRyp7AEGwm8ZTjbCvAx-XQ'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
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
source-wordcount: '262'
ht-degree: 3%
---
# Descargue e instale AEM Guides por primera vez {#id213BCL00KEV}

Realice los siguientes pasos para descargar e instalar AEM Guides por primera vez en un equipo:

>[!IMPORTANT]
>
> Si desea utilizar Livefyre junto con AEM Guides, asegúrese de instalar las versiones de Livefyre anteriores a la 3.0 antes de instalar AEM Guides. Si utiliza la versión 3.0 o superior de Livefyre, no existe dicha restricción.

1. Descargar AEM Guides desde [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html).

   >[!NOTE]
   >
   >Antes de instalar Experience Manager Guides, asegúrese de que su sistema cumpla [los requisitos técnicos](../install-guide/download-install-technical-requirements.md).

1. Inicie sesión en la instancia de AEM y vaya al Administrador de paquetes de CRX. La URL predeterminada para acceder al administrador de paquetes es:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

   El Administrador de paquetes administra los paquetes en la instalación local de AEM. Para obtener más información sobre cómo trabajar con el Administrador de paquetes, consulte [Cómo trabajar con paquetes](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html) en la documentación de AEM.

   ![](assets/package-manager.png){width="650"}

1. Para cargar el paquete de AEM Guides, haga clic en **Cargar paquete**.

1. En el cuadro de diálogo Cargar paquete, vaya al archivo AEM Guides que descargó en el paso 1 y haga clic en **Aceptar**.

   El paquete se carga en la instancia de AEM.

1. Para instalar el paquete, haz clic en **Instalar**.

   ![](assets/install-package.png){width="650"}

1. En el diálogo Instalar paquete, haga clic en **Instalar**.

1. Para comenzar con AEM Guides, haga clic en el botón Inicio ![](assets/home-button.png) en la esquina superior izquierda del Administrador de paquetes de CRX.


>[!NOTE]
>
> Realice el procedimiento de instalación en todas las instancias de servidores de AEM de la instalación.

**Tema principal:**[ Descargar e instalar](download-install.md)
