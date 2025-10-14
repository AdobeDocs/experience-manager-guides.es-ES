---
title: AEM Personalizar el diccionario predeterminado de
description: AEM Obtenga información sobre cómo personalizar el diccionario predeterminado de la
exl-id: ecffcd14-6728-4938-a209-5c4b12af6fbb
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 1%

---

# AEM Personalizar el diccionario predeterminado de {#id209SD8000WU}

AEM El editor web se puede configurar para que utilice el corrector ortográfico o el corrector ortográfico del explorador, respectivamente, para utilizar el corrector ortográfico de la aplicación de la misma. AEM Si decide trabajar con el corrector ortográfico de la, tendrá la flexibilidad de definir la lista de palabras personalizadas. AEM A continuación, estas palabras personalizadas se añaden al diccionario de la y estas palabras no se marcan con \(como incorrectas\) en el Editor Web.

AEM Realice los siguientes pasos para crear la lista de palabras personalizadas, que se agregan en el diccionario de la aplicación de palabras de la aplicación de la aplicación de la regla de comandos de la aplicación de la regla de comandos de la aplicación de comandos de la aplicación de comandos de:

1. Cree el archivo user\_dictionary.txt con una lista de palabras que desee definir en el diccionario personalizado.

   >[!NOTE]
   >
   > Cada palabra personalizada debe definirse en una nueva línea.

1. Guarde el archivo en la siguiente ubicación del repositorio Git de Cloud Manager:

   /apps/fmdita/config

1. Guarde el archivo.

   Confirme los cambios y ejecute la canalización \(CI/CD\) de Cloud Manager para implementar los cambios de configuración.


AEM Los autores necesitarían reiniciar su sesión del editor web para obtener la lista de palabras personalizadas actualizada en el diccionario de palabras de la aplicación.

**Tema principal:**&#x200B;[&#x200B; Personalizar editor web](conf-web-editor.md)
