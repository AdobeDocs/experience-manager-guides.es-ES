---
title: AEM Personalizar el diccionario predeterminado de
description: AEM Obtenga información sobre cómo personalizar el diccionario predeterminado de la
exl-id: 8bfd3ea7-0be8-4e7a-b389-5face043200b
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 2%

---

# AEM Personalizar el diccionario predeterminado de {#id209SD8000WU}

AEM El editor web se puede configurar para que utilice el corrector ortográfico o el corrector ortográfico del explorador, respectivamente, para utilizar el corrector ortográfico de la aplicación de la misma. AEM Si decide trabajar con el corrector ortográfico de la, tendrá la flexibilidad de definir la lista de palabras personalizadas. AEM A continuación, estas palabras personalizadas se añaden al diccionario de la y estas palabras no se marcan con \(como incorrectas\) en el Editor Web.

AEM Realice los siguientes pasos para crear la lista de palabras personalizadas, que se agregan en el diccionario de la aplicación de palabras de la aplicación de la aplicación de la regla de comandos de la aplicación de la regla de comandos de la aplicación de comandos de la aplicación de comandos de:

1. AEM Inicie sesión en la aplicación y abra el modo CRXDE Lite.

1. Vaya al siguiente nodo:

   /apps/fmdita/config

1. Cree un nuevo archivo denominado user\_dictionary.txt.

1. Abra el archivo y agregue una lista de palabras que desee definir en el diccionario personalizado.

   La siguiente captura de pantalla muestra la lista de palabras personalizadas agregada al archivo user\_dictionary.txt:

   ![](assets/custom-words-list-dictionary.png){width="650" align="left"}

1. Guarde y cierre el archivo.


AEM Los autores necesitarían reiniciar su sesión del editor web para obtener la lista de palabras personalizadas actualizada en el diccionario de palabras de la aplicación.

**Tema principal:**&#x200B;[ Personalizar editor web](conf-web-editor.md)
