---
title: Verificar la instalación de AEM Guides
description: Obtenga información sobre cómo verificar la instalación de AEM Guides
exl-id: 4e566c57-a522-4605-bc70-47155f20b429
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---

# Verificar la instalación de AEM Guides {#id213BD030FBE}

Una vez instalado AEM Guides, debe comprobar si la instalación se ha realizado correctamente o no. Siga estos pasos para comprobar la instalación:

1. Acceda a la Developer Console de su Cloud Service.

   Para obtener más información sobre cómo acceder a Developer Console, consulte [Acceso a Developer Console AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=es) en la documentación de.

1. AEM Acceda a la lista de paquetes OSGi en la lista de paquetes de.

   AEM Para obtener más información sobre cómo acceder a los paquetes, consulte [Paquetes](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=es#bundles) en la documentación de la.

1. Busque fmdita en la lista de paquetes y compruebe su estado.

   El estado debería mostrar *Activo* para los paquetes implementados correctamente. AEM Si alguno de los paquetes no tiene un estado Activo, compruebe los registros de la para solucionar el problema de instalación.


**Tema principal:**&#x200B;[&#x200B; Descargar e instalar](download-install.md)
