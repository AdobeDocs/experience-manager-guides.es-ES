---
title: Personalizar el diccionario predeterminado de AEM
description: Aprenda a personalizar el diccionario predeterminado de AEM
exl-id: ecffcd14-6728-4938-a209-5c4b12af6fbb
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/omWGECpXvtuNBUH8dcOnggOHmG8z1PevjBmZ-ZcYWjY'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 1%
---
# Personalizar el diccionario predeterminado de AEM {#id209SD8000WU}

El editor web se puede configurar para que utilice el corrector ortográfico de AEM o el del explorador. Si decide trabajar con el corrector ortográfico de AEM, tendrá la flexibilidad de definir la lista de palabras personalizadas. Estas palabras personalizadas se añaden al diccionario de AEM y no se marcan con \(como incorrectas\) en el Editor Web.

Realice los siguientes pasos para crear la lista de palabras personalizada, que se agregan en el diccionario de AEM:

1. Cree el archivo user\_dictionary.txt con una lista de palabras que desee definir en el diccionario personalizado.

   >[!NOTE]
   >
   > Cada palabra personalizada debe definirse en una nueva línea.

1. Guarde el archivo en la siguiente ubicación del repositorio Git de Cloud Manager:

   /apps/fmdita/config

1. Guarde el archivo.

   Confirme los cambios y ejecute la canalización \(CI/CD\) de Cloud Manager para implementar los cambios de configuración.


Los autores necesitarían reiniciar su sesión del editor web para obtener la lista de palabras personalizadas actualizada en el diccionario de AEM.

**Tema principal:**&#x200B;[&#x200B; Personalizar editor web](conf-web-editor.md)
