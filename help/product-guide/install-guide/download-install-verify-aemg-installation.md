---
title: AEM Verificar la instalación de guías de
description: AEM Obtenga información sobre cómo verificar la instalación de las guías de
exl-id: 8e0afe18-5675-4c7e-b216-6de1a752bd01
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---

# AEM Verificar la instalación de guías de {#id213BD030FBE}

AEM Una vez que haya instalado las guías de la aplicación, debe comprobar si la instalación se ha realizado correctamente o no. Siga estos pasos para comprobar el proceso de instalación:

1. AEM AEM Inicie sesión en la instancia de y navegue hasta la página de paquetes de la consola web de. La URL predeterminada para acceder a la página de paquetes es:

   ```http
   http://<server name>:<port>/system/console/bundles
   ```

   Se muestra una lista de paquetes.

1. Filtre la lista de paquetes introduciendo fmdita en el cuadro de texto de filtrado y pulse **Entrar**.

   AEM La lista de paquetes se filtra para mostrar los paquetes instalados por las guías de. Si la instalación se ha realizado correctamente, todos los paquetes instalados tendrán un **Estado** de **Activo**.

   Si alguno de los paquetes no tiene un **Activo** AEM estado y, a continuación, compruebe los registros de para solucionar el problema de instalación.


>[!IMPORTANT]
>
> Existen varias recomendaciones de optimización del rendimiento que puede considerar para mejorar el rendimiento del sistema. Consulte [Recommendations para la optimización del rendimiento](download-install-recommend-perf-optimiz.md#) para obtener más información.

**Tema principal:**[ Descargar e instalar](download-install.md)
