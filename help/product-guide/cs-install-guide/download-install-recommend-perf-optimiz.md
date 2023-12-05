---
title: Recommendations para la optimización del rendimiento
description: Conozca Recommendations para optimizar el rendimiento
exl-id: 92ac1f81-2f51-44b0-82c3-56b39e8f3027
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---

# Recommendations para la optimización del rendimiento {#id213BD0JG0XA}

Para optimizar el rendimiento, tenga en cuenta los siguientes puntos:

- Para optimizar el contenido y la experiencia de indexación, consulte [Optimizar la búsqueda de contenido y la indexación](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=es) AEM en la documentación de.

- Parche Xerces Jar mientras utiliza DITA-OT personalizado para la publicación. Esta es una configuración obligatoria, según el caso de uso. Este cambio sólo es necesario si utiliza DITA-OT personalizado para publicar resultados.

  *Configuración requerida*: reemplace el archivo Jar de Xerces del paquete DITA-OT personalizado por el OOTB enviado. El archivo predeterminado OOTB xercesImpl-2.11.0.jar está disponible en el archivo /libs/fmdita/dita\_resources/DITA-OT.zip. Asegúrese de cambiar el nombre del archivo xercesImpl-2.11.0.jar para que coincida con el archivo Jar de Xerces antiguo que se está reemplazando. Esto se puede hacer en tiempo de ejecución.

  Este cambio reduce el tiempo de publicación y el uso de memoria al publicar asignaciones DITA con un gran número de temas.


**Tema principal:**[ Descargar e instalar](download-install.md)
