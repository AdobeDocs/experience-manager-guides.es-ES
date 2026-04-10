---
title: Personalizar el diccionario predeterminado de AEM
description: Aprenda a personalizar el diccionario predeterminado de AEM
exl-id: ecffcd14-6728-4938-a209-5c4b12af6fbb
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '175'
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
