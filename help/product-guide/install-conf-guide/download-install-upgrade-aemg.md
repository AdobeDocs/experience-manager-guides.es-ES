---
title: Actualizar AEM Guides para Cloud Service
description: Obtenga información sobre cómo actualizar AEM Guides
feature: Installation
role: Admin
level: Experienced
exl-id: 9d48a7c4-384d-4ad4-a1d3-4c50d97e5d5b
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
> Para obtener más información sobre el uso de la canalización de CI/CD, consulte [Uso de la canalización de CI/CD en Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html?lang=es).

## Borre la caché del explorador

Después de completar el proceso de actualización, todos los usuarios deben borrar la caché del explorador antes de utilizar la versión actualizada de AEM Guides.
