---
title: Configurar nombres de archivo válidos para la salida del sitio de AEM
description: Obtenga información sobre cómo configurar nombres de archivo válidos para la salida del sitio de AEM
exl-id: 05215bec-653b-4563-83c6-a1bb16200469
feature: Filename Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 1%

---

# Configurar nombres de archivo válidos para la salida del sitio de AEM {#id214GK0X0KXA}

De forma similar a la lista de caracteres de nombre de archivo válidos permitidos para los temas DITA, también se puede configurar una lista de caracteres de nombre de archivo válidos para la salida del sitio de AEM. Algunos de los caracteres conocidos que no están permitidos en una dirección URL son: ``'<>`@$``. Estos caracteres se configuran para que se conviertan automáticamente en un guion bajo &quot;`_`&quot; cuando se encuentren al generar los nombres de archivo de salida del sitio de AEM.

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para establecer caracteres válidos en la salida del sitio de AEM:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Agregue los caracteres que desee reemplazar con un guion bajo en los nombres de los archivos de salida del sitio de AEM. <br> **Valor predeterminado**: ``'<\>\`@$`` |

**Tema principal:**[ Configurar nombres de archivo](conf-file-names.md)
