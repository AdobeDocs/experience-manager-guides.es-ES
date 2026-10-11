---
title: Configurar nombres de archivo válidos para la salida del sitio de AEM
description: Obtenga información sobre cómo configurar nombres de archivo válidos para la salida del sitio de AEM
exl-id: 05215bec-653b-4563-83c6-a1bb16200469
feature: Filename Configuration
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/hhc9Q8A-Eq3e8PAHHDXf1jXf8qVb-p4sU3Cum53ra9M'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
    internal-label: Filename configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 1%
---
# Configurar nombres de archivo válidos para la salida del sitio de AEM {#id214GK0X0KXA}

De forma similar a la lista de caracteres de nombre de archivo válidos permitidos para los temas DITA, también se puede configurar una lista de caracteres de nombre de archivo válidos para la salida del sitio de AEM. Algunos de los caracteres conocidos que no están permitidos en una dirección URL son: ``'<>`@$``. Estos caracteres se configuran para que se conviertan automáticamente en un guion bajo &quot;`_`&quot; cuando se encuentren al generar los nombres de archivo de salida del sitio de AEM.

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para establecer caracteres válidos en la salida del sitio de AEM:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Agregue los caracteres que desee reemplazar con un guion bajo en los nombres de los archivos de salida del sitio de AEM. <br> **Valor predeterminado**: ``'<\>\`@$`` |

**Tema principal:**&#x200B;[&#x200B; Configurar nombres de archivo](conf-file-names.md)
