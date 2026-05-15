---
title: Desinstalación de AEM Guides
description: Obtenga información sobre cómo desinstalar AEM Guides
exl-id: 6c6b9692-cdec-426f-bc3b-f09d0091da39
feature: Installation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/W6cpFBqAnriNXNYqP6r-GZm7tJhPWnlSI53q33iduvE
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 147
ht-degree: 0%

---

# Desinstalación de AEM Guides {#id21BHG0C0SXA}

Puede desinstalar AEM Guides mediante el Administrador de paquetes de CRX. Durante la desinstalación, el contenido del repositorio se revierte a la instantánea realizada inmediatamente antes de la instalación del paquete.

Siga estos pasos para desinstalar AEM Guides:

1. Inicie sesión en la instancia de AEM y vaya al Administrador de paquetes de CRX. La URL predeterminada para acceder al administrador de paquetes es:

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

**Tema principal:**[ Descargar e instalar](download-install.md)
