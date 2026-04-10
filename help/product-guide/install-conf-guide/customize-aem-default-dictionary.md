---
title: Personalizar el diccionario predeterminado de AEM
description: Aprenda a personalizar el diccionario predeterminado de AEM
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 2%

---

# Personalizar el diccionario predeterminado de AEM {#id209SD8000WU}

El editor web se puede configurar para que utilice el corrector ortográfico de AEM o el del explorador. Si decide trabajar con el corrector ortográfico de AEM, tendrá la flexibilidad de definir la lista de palabras personalizadas. Estas palabras personalizadas se añaden al diccionario de AEM y no se marcan con \(como incorrectas\) en el Editor Web.

Las siguientes pestañas proporcionan instrucciones para crear su lista de palabras personalizadas, que se añaden en el diccionario de AEM en función de su configuración de Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Cree el archivo user\_dictionary.txt con una lista de palabras que desee definir en el diccionario personalizado.

   >[!NOTE]
   >
   > Cada palabra personalizada debe definirse en una nueva línea.

1. Guarde el archivo en la siguiente ubicación del repositorio Git de Cloud Manager:

   /apps/fmdita/config

1. Guarde el archivo.

   Confirme los cambios y ejecute la canalización \(CI/CD\) de Cloud Manager para implementar los cambios de configuración.


Los autores necesitarían reiniciar su sesión del editor web para obtener la lista de palabras personalizadas actualizada en el diccionario de AEM.

>[!TAB Local]

1. Inicie sesión en AEM y abra el modo CRXDE Lite.

1. Vaya al siguiente nodo:

   /apps/fmdita/config

1. Cree un nuevo archivo denominado user\_dictionary.txt.

1. Abra el archivo y agregue una lista de palabras que desee definir en el diccionario personalizado.

   La siguiente captura de pantalla muestra la lista de palabras personalizadas agregada al archivo user\_dictionary.txt:

   ![](assets/custom-words-list-dictionary.png){width="650" align="left"}

1. Guarde y cierre el archivo.


Los autores necesitarían reiniciar su sesión del editor web para obtener la lista de palabras personalizadas actualizada en el diccionario de AEM.

>[!ENDTABS]

**Tema principal:**&#x200B;[&#x200B; Personalizar editor web](customize-overview.md)
