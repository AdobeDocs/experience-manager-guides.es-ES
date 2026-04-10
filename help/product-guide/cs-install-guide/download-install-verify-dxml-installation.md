---
title: Verificar la instalación de AEM Guides
description: Obtenga información sobre cómo verificar la instalación de AEM Guides
exl-id: 4e566c57-a522-4605-bc70-47155f20b429
feature: Installation
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---

# Verificar la instalación de AEM Guides {#id213BD030FBE}

Una vez instalado AEM Guides, debe comprobar si la instalación se ha realizado correctamente o no. Siga estos pasos para comprobar la instalación:

1. Acceda a la Developer Console de su Cloud Service.

   Para obtener más información sobre cómo acceder a Developer Console, consulte [Acceso a Developer Console](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=es) en la documentación de AEM.

1. Acceda a la lista de paquetes OSGi en AEM.

   Para obtener más información sobre cómo acceder a los paquetes, consulte [Paquetes](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=es#bundles) en la documentación de AEM.

1. Busque fmdita en la lista de paquetes y compruebe su estado.

   El estado debería mostrar *Activo* para los paquetes implementados correctamente. Si alguno de los paquetes no tiene un estado Activo, compruebe los registros de AEM para solucionar el problema de instalación.


**Tema principal:**&#x200B;[&#x200B; Descargar e instalar](download-install.md)
