---
title: Desinstalación de AEM Guides
description: Obtenga información sobre cómo desinstalar AEM Guides
feature: Installation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Desinstalar AEM Guides para instalación local{#id21BHG0C0SXA}

Puede desinstalar AEM Guides para instalación local mediante el Administrador de paquetes de CRX. Durante la desinstalación, el contenido del repositorio se revierte a la instantánea realizada inmediatamente antes de la instalación del paquete.

Siga estos pasos para desinstalar AEM Guides para instalación local:

1. Inicie sesión en la instancia de AEM y vaya al Administrador de paquetes de CRX. La URL predeterminada para acceder al administrador de paquetes es:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

1. Busque el paquete `com.adobe.fmdita`.
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
