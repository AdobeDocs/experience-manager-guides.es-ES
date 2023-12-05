---
title: AEM Guías de actualización
description: AEM Obtenga información sobre cómo actualizar las guías de la
exl-id: 57ae906f-69e3-4319-89f6-0fa9ddb7a3ff
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 0%

---

# AEM Guías de actualización {#id213BD050YPH}

1. Acceda al repositorio de Git de Cloud Manager.

1. Actualice el archivo dox/dox.installer/pom.xml.

1. Actualice el valor de la variable dox.version a los detalles de la versión proporcionados por el Adobe.

1. Confirme los cambios y ejecute la canalización de Cloud Manager para implementar el paquete actualizado.


>[!NOTE]
>
> Para obtener más información sobre el uso de la canalización de CI/CD, consulte [Uso de la canalización de CI/CD en Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html).

## Borrar caché del explorador

AEM Después de completar el proceso de actualización, todos los usuarios deben borrar la memoria caché del explorador antes de utilizar la versión actualizada de las guías de la aplicación de la versión de la aplicación de la versión de la versión de la.

**Tema principal:**[ Descargar e instalar](download-install.md)
