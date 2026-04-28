---
title: Verificar la instalación de AEM Guides
description: Obtenga información sobre cómo verificar la instalación de AEM Guides
exl-id: 8e0afe18-5675-4c7e-b216-6de1a752bd01
feature: Installation
role: Admin
level: Experienced
source-git-commit: ccaf2ead1a9a24ab822298c6b9ef6866a1c32e8c
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 0%

---

# Verificar la instalación de AEM Guides {#id213BD030FBE}

Una vez instalado AEM Guides, debe comprobar si la instalación se ha realizado correctamente o no. Siga estos pasos para comprobar el proceso de instalación:

1. Inicie sesión en la instancia de AEM y vaya a la página Paquetes de la consola web de AEM. La URL predeterminada para acceder a la página de paquetes es:

   ```http
   http://<server name>:<port>/system/console/bundles
   ```

   Se muestra una lista de paquetes.

1. Filtre la lista de paquetes introduciendo fmdita en el cuadro de texto de filtrado y pulse **Intro**.

   La lista de paquetes se filtra para mostrar los paquetes instalados por AEM Guides. Si la instalación se realizó correctamente, todos los paquetes instalados tendrán un **estado** de **Activo**.

   Si alguno de los paquetes no tiene el estado **Activo**, compruebe los registros de AEM para solucionar el problema de instalación.


>[!IMPORTANT]
>
> Existen varias recomendaciones de optimización del rendimiento que puede considerar para mejorar el rendimiento del sistema. Consulte [Recomendaciones para la optimización del rendimiento](download-install-recommend-perf-optimiz.md#) para obtener más información.

**Tema principal:**&#x200B;[&#x200B; Descargar e instalar](download-install.md)
