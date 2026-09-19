---
title: Configurar nombres de archivo válidos para la salida del sitio de AEM
description: Obtenga información sobre cómo configurar nombres de archivo válidos para la salida del sitio de AEM
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: b2bc5159-2144-4683-970d-738949ac9662
source-git-commit: 82c93529b8535532cf50f6428c41a1881b24859e
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%
---
# Configurar nombres de archivo válidos para la salida del sitio de AEM {#id214GK0X0KXA}

De forma similar a la lista de caracteres de nombre de archivo válidos permitidos para los temas DITA, también se puede configurar una lista de caracteres de nombre de archivo válidos para la salida del sitio de AEM. Algunos de los caracteres conocidos que no están permitidos en una dirección URL son: ``'<>`@$``. Estos caracteres se configuran para que se conviertan automáticamente en un guion bajo &quot;`_`&quot; cuando se encuentren al generar los nombres de archivo de salida del sitio de AEM.

Las siguientes pestañas proporcionan instrucciones para configurar nombres de archivo válidos para la salida del sitio de AEM en función de la configuración de Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para establecer caracteres válidos en la salida del sitio de AEM:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Agregue los caracteres que desee reemplazar con un guion bajo en los nombres de los archivos de salida del sitio de AEM. <br> **Valor predeterminado**: ``'<\>\`@$`` |

>[!TAB Local]

La configuración que le permite establecer caracteres válidos en la salida del sitio de AEM está presente en el paquete `com.adobe.fmdita.common.SanitizeNodeNameImpl`. **Establezca el valor de Conjunto de caracteres no permitidos para la publicación en AEM Sites** para incluir caracteres que desee reemplazar con un guion bajo en los nombres de los archivos de salida del sitio de AEM.

>[!ENDTABS]
