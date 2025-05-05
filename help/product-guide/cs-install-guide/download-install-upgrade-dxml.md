---
title: Actualizar AEM Guides
description: Obtenga información sobre cómo actualizar AEM Guides
exl-id: 57ae906f-69e3-4319-89f6-0fa9ddb7a3ff
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 0%

---

# Actualizar AEM Guides {#id213BD050YPH}

1. Acceda al repositorio de Git de Cloud Manager.

1. Actualice el archivo dox/dox.installer/pom.xml.

1. Actualice el valor de la variable dox.version a los detalles de la versión proporcionados por el Adobe.

1. Confirme los cambios y ejecute la canalización de Cloud Manager para implementar el paquete actualizado.


>[!NOTE]
>
> Para obtener más información acerca del uso de la canalización de CI/CD, vea [Usar la canalización de CI/CD en Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html).

## Borrar caché del explorador

Después de completar el proceso de actualización, todos los usuarios deben borrar la caché del explorador antes de utilizar la versión actualizada de AEM Guides.

**Tema principal:**&#x200B;[ Descargar e instalar](download-install.md)
