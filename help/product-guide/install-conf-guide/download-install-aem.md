---
title: Instalación de Adobe Experience Manager
description: Obtenga información sobre cómo instalar Adobe Experience Manager
feature: Introduction, Installation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---

# Instalación de Adobe Experience Manager {#id213BCI020E8}

AEM Guides es un complemento que se instala sobre Adobe Experience Manager. La instalación de AEM requiere conocer algunos conceptos básicos de AEM y escenarios de implementación recomendados. Los siguientes recursos de vínculos le ayudarán a iniciarse en la instalación de AEM:

- [Conceptos básicos de AEM](https://helpx.adobe.com/es/experience-manager/6-5/sites/deploying/using/deploy.html#BasicConcepts)

- [Implementaciones de AEM recomendadas](https://helpx.adobe.com/es/experience-manager/6-5/sites/deploying/using/recommended-deploys.html)

>[!IMPORTANT]
>
> Si usa Java 11 con AEM 6.5.x, es posible que tenga un problema: *JDK 11 causa`NoClassDefFoundError`*. Consulte el artículo [JDK 11 causes NoClassDefFoundError \| AEM 6.5](https://helpx.adobe.com/experience-manager/kb/jdk-11-causes-noclassdeffounderror---aem-6-5.html) para resolver este problema.

Una vez que haya identificado la estrategia de implementación que mejor funciona para su organización, realice el proceso de instalación como se describe en la sección *[Introducción](https://helpx.adobe.com/es/experience-manager/6-5/sites/deploying/using/deploy.html#GettingStarted)* de la documentación de AEM.

Si planea actualizar la instancia de AEM, debe seguir la secuencia indicada:

1. Desinstale AEM Guides.
1. Actualice la instancia de AEM.
1. Vuelva a instalar AEM Guides.

>[!IMPORTANT]
>
> Existen varias recomendaciones de optimización del rendimiento que puede considerar para mejorar el rendimiento del sistema. Consulte [Recomendaciones para la optimización del rendimiento](./perf-optimization-on-prem.md) para obtener más información.
