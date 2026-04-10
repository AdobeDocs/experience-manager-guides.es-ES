---
title: Configurar nombres de archivo válidos para la salida del sitio de AEM
description: Obtenga información sobre cómo configurar nombres de archivo válidos para la salida del sitio de AEM
exl-id: 1e69d6f8-7baf-4189-bbbd-34cd0fec6634
feature: Filename Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 0%

---

# Configurar nombres de archivo válidos para la salida del sitio de AEM {#id214GK0X0KXA}

De forma similar a la lista de caracteres de nombre de archivo válidos permitidos para los temas DITA, también se puede configurar una lista de caracteres de nombre de archivo válidos para la salida del sitio de AEM. Algunos de los caracteres conocidos que no están permitidos en una dirección URL son: ```'<>`@$```. Estos caracteres están configurados para convertirse automáticamente en un guion bajo &quot;_&quot; cuando se encuentran al generar nombres de archivo de salida del sitio de AEM. La configuración que le permite establecer caracteres válidos en la salida del sitio de AEM está presente en el paquete `com.adobe.fmdita.common.SanitizeNodeNameImpl`. **Establezca el valor de Conjunto de caracteres no permitidos para la publicación en AEM Sites** para incluir caracteres que desee reemplazar con un guion bajo en los nombres de los archivos de salida del sitio de AEM.

**Tema principal:**[ Configurar nombres de archivo](conf-file-names.md)
