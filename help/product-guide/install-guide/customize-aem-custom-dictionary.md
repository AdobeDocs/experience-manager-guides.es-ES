---
title: AEM Personalizar diccionario predeterminado
description: AEM Aprenda a personalizar el diccionario predeterminado de la aplicación
exl-id: 8bfd3ea7-0be8-4e7a-b389-5face043200b
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 2%

---

# AEM Personalizar diccionario predeterminado {#id209SD8000WU}

AEM El editor web se puede configurar para que utilice el corrector ortográfico o el corrector ortográfico del explorador, así como para que utilice el corrector ortográfico de la aplicación. AEM Si decide trabajar con el corrector ortográfico de la, tendrá la flexibilidad de definir la lista de palabras personalizadas. AEM A continuación, estas palabras personalizadas se añaden al diccionario de recursos y estas palabras no se marcan con \(como incorrectas\) en el Editor web.

AEM Realice los siguientes pasos para crear la lista de palabras personalizadas, que se agregan en el diccionario de:

1. AEM Inicie sesión en la aplicación y abra el modo CRXDE Lite.

1. Vaya al siguiente nodo:

   /apps/fmdita/config

1. Cree un nuevo archivo denominado user\_dictionary.txt.

1. Abra el archivo y agregue una lista de palabras que desee definir en el diccionario personalizado.

   La siguiente captura de pantalla muestra la lista de palabras personalizadas agregada al archivo user\_dictionary.txt:

   ![](assets/custom-words-list-dictionary.png){width="650" align="left"}

1. Guarde y cierre el archivo.


AEM Los autores necesitarían reiniciar su sesión del editor web para obtener la lista de palabras personalizadas actualizada en el diccionario de palabras de la aplicación.

**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
