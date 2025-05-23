---
title: Desinstalación de AEM Guides
description: Obtenga información sobre cómo desinstalar AEM Guides
exl-id: 6c6b9692-cdec-426f-bc3b-f09d0091da39
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Desinstalación de AEM Guides {#id21BHG0C0SXA}

Puede desinstalar AEM Guides mediante el Administrador de paquetes de CRX. Durante la desinstalación, el contenido del repositorio se revierte a la instantánea realizada inmediatamente antes de la instalación del paquete.

Siga estos pasos para desinstalar AEM Guides:

1. AEM Inicie sesión en la instancia de y vaya al Administrador de paquetes de CRX. La URL predeterminada para acceder al administrador de paquetes es:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

1. Busque el paquete com.adobe.fmdita.
1. Haga clic en el paquete para expandirlo.
1. Haga clic en **Más** para abrir el menú desplegable.
1. Haz clic en **Desinstalar** y espera a que se complete la desinstalación.
1. Si ya no necesita este paquete, haga clic en **Eliminar** después de desinstalar el paquete.

## Después de la desinstalación

Para limpiar los archivos residuales después de la desinstalación, realice los siguientes pasos:

1. Limpie la caché de la secuencia de comandos mediante:

   ```http
   http://<host>:<port>/system/console/scriptcache
   ```

1. Puede invalidar la caché mediante lo siguiente:

   ```http
   http://<host>:<port>/libs/granite/ui/content/dumplibs.rebuild.html?back=true
   ```

1. Haga clic en **Invalidar caché**.
1. Limpie la caché del explorador.

**Tema principal:**&#x200B;[ Descargar e instalar](download-install.md)
