---
title: AEM Verificar la instalación de guías de
description: AEM Obtenga información sobre cómo verificar la instalación de las guías de
exl-id: 4e566c57-a522-4605-bc70-47155f20b429
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---

# AEM Verificar la instalación de guías de {#id213BD030FBE}

AEM Una vez que haya instalado las guías de la aplicación, debe comprobar si la instalación se ha realizado correctamente o no. Siga estos pasos para comprobar la instalación:

1. Acceda a la consola de desarrollador del Cloud Service.

   Para obtener más información sobre el acceso a Developer Console, consulte [Acceso a Developer Console](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=es) AEM en la documentación de.

1. AEM Acceda a la lista de paquetes OSGi en la lista de paquetes de.

   Para obtener más información sobre el acceso a paquetes, consulte [Paquetes](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=en#bundles) AEM en la documentación de.

1. Busque fmdita en la lista de paquetes y compruebe su estado.

   El estado debe mostrar *Activo* para paquetes implementados correctamente. AEM Si alguno de los paquetes no tiene un estado Activo, compruebe los registros de la para solucionar el problema de instalación.


**Tema principal:**[ Descargar e instalar](download-install.md)
