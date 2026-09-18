---
title: Actualizar AEM Guides para Cloud Service
description: Obtenga información sobre cómo actualizar AEM Guides
feature: Installation
role: Admin
level: Experienced
exl-id: 9d48a7c4-384d-4ad4-a1d3-4c50d97e5d5b
source-git-commit: 82c93529b8535532cf50f6428c41a1881b24859e
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 2%
---
# Actualizar AEM Guides para Cloud Service {#id213BD050YPH}

Siga estos pasos para actualizar AEM Guides:

1. Acceda al repositorio de Git de Cloud Manager.

1. Actualizar el archivo `dox/dox.installer/pom.xml`.

1. Actualice el valor de la variable `dox.version` a los detalles de versión proporcionados por Adobe.

1. Confirme los cambios y ejecute la canalización de Cloud Manager para implementar el paquete actualizado.


>[!NOTE]
>
> Para obtener más información sobre el uso de la canalización de CI/CD, consulte [Uso de la canalización de CI/CD en Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html).

## Borre la caché del explorador

Después de completar el proceso de actualización, todos los usuarios deben borrar la caché del explorador antes de utilizar la versión actualizada de AEM Guides.
