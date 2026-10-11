---
title: Verificar la instalación de AEM Guides
description: Obtenga información sobre cómo verificar la instalación de AEM Guides
feature: Installation
role: Admin
level: Experienced
exl-id: 19cded6f-6545-42af-8511-7c32cf4ddf2d
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
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
source-wordcount: '311'
ht-degree: 5%
---
# Verificar la instalación de AEM Guides {#id213BD030FBE}

Una vez instalado AEM Guides, debe comprobar si la instalación se ha realizado correctamente o no.

Las siguientes pestañas proporcionan instrucciones para comprobar la instalación de AEM Guides en función de la configuración de Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Siga estos pasos para comprobar la instalación:

1. Acceda a la Developer Console de su Cloud Service.

   Para obtener más información sobre cómo acceder a Developer Console, consulte [Acceso a Developer Console](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=es) en la documentación de AEM.

1. Acceda a la lista de paquetes OSGi en AEM.

   Para obtener más información sobre cómo acceder a los paquetes, consulte [Paquetes](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=en#bundles) en la documentación de AEM.

1. Busque fmdita en la lista de paquetes y compruebe su estado.

   El estado debería mostrar *Activo* para los paquetes implementados correctamente. Si alguno de los paquetes no tiene un estado Activo, compruebe los registros de AEM para solucionar el problema de instalación.

>[!TAB Local]

Siga estos pasos para comprobar la instalación:

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
> Existen varias recomendaciones de optimización del rendimiento que puede considerar para mejorar el rendimiento del sistema. Consulte [Recomendaciones para la optimización del rendimiento](perf-optimization-on-prem.md#) para obtener más información.

>[!ENDTABS]
