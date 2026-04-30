---
title: Personalizar el diccionario predeterminado de AEM
description: Aprenda a personalizar el diccionario predeterminado de AEM
exl-id: 8bfd3ea7-0be8-4e7a-b389-5face043200b
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 12ba7129255257970ddd7a0989149be664ce9803
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 2%

---

# Personalizar el diccionario predeterminado de AEM {#id209SD8000WU}

El editor web se puede configurar para que utilice el corrector ortográfico de AEM o el del explorador. Si decide trabajar con el corrector ortográfico de AEM, tendrá la flexibilidad de definir la lista de palabras personalizadas. Estas palabras personalizadas se añaden al diccionario de AEM y no se marcan con \(como incorrectas\) en el Editor Web.

Realice los siguientes pasos para crear la lista de palabras personalizada, que se agregan en el diccionario de AEM:

1. Inicie sesión en AEM y abra el modo CRXDE Lite.

1. Vaya al siguiente nodo:

   /apps/fmdita/config

1. Cree un nuevo archivo denominado user\_dictionary.txt.

1. Abra el archivo y agregue una lista de palabras que desee definir en el diccionario personalizado.

   La siguiente captura de pantalla muestra la lista de palabras personalizadas agregada al archivo user\_dictionary.txt:

   ![](assets/custom-words-list-dictionary.png){width="650"}

1. Guarde y cierre el archivo.


Los autores necesitarían reiniciar su sesión del editor web para obtener la lista de palabras personalizadas actualizada en el diccionario de AEM.

**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
