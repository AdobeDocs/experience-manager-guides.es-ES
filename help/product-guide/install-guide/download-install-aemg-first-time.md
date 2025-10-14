---
title: Descargue e instale AEM Guides por primera vez
description: Obtenga información sobre cómo descargar e instalar AEM Guides por primera vez
exl-id: 830a4381-303c-419c-b87f-9563352a7eeb
feature: Introduction, Installation
role: Admin
level: Experienced
source-git-commit: dbcc625220c9ad1fa60942b2f43c38d3d6778541
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

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

1. AEM Inicie sesión en la instancia de y vaya al Administrador de paquetes de CRX. La URL predeterminada para acceder al administrador de paquetes es:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

   AEM El Administrador de paquetes administra los paquetes en la instalación local de la. AEM Para obtener más información acerca de cómo trabajar con el Administrador de paquetes, vea [Cómo trabajar con paquetes](https://helpx.adobe.com/es/experience-manager/6-5/sites/administering/using/package-manager.html) en la documentación de la documentación de la aplicación de paquetes de.

   ![](assets/package-manager.png){width="650" align="left"}

1. Para cargar el paquete de AEM Guides, haga clic en **Cargar paquete**.

1. En el cuadro de diálogo Cargar paquete, vaya al archivo AEM Guides que descargó en el paso 1 y haga clic en **Aceptar**.

   AEM El paquete se cargará en la instancia de la.

1. Para instalar el paquete, haz clic en **Instalar**.

   ![](assets/install-package.png){width="650" align="left"}

1. En el diálogo Instalar paquete, haga clic en **Instalar**.

1. Para comenzar con AEM Guides, haga clic en el botón Inicio ![](assets/home-button.png) en la esquina superior izquierda del Administrador de paquetes de CRX.


>[!NOTE]
>
> AEM Realice el procedimiento de instalación en todas las instancias de los servidores de la instalación de la aplicación de.

**Tema principal:**&#x200B;[&#x200B; Descargar e instalar](download-install.md)
