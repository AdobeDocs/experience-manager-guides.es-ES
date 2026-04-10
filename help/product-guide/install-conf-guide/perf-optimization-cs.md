---
title: Recomendaciones para la optimización del rendimiento para Cloud Service
description: Conozca Recommendations para la optimización del rendimiento
feature: Performance Optimization
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 0%

---

# Recomendaciones para la optimización del rendimiento para Cloud Service {#id213BD0JG0XA}

Para optimizar el rendimiento, tenga en cuenta los siguientes puntos:

- Para optimizar el contenido y la experiencia de indexación, consulte [Optimizar la búsqueda e indexación de contenido](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=es) en la documentación de AEM.

- Parche Xerces Jar mientras utiliza DITA-OT personalizado para la publicación. Esta es una configuración obligatoria, según el caso de uso. Este cambio sólo es necesario si utiliza DITA-OT personalizado para publicar resultados.

  *Configuración requerida*: reemplace el archivo Xerces Jar del paquete DITA-OT personalizado por el OOTB enviado. El archivo OOTB `xercesImpl-2.11.0.jar` predeterminado está disponible en el archivo `/libs/fmdita/dita\_resources/DITA-OT.zip`. Asegúrese de cambiar el nombre del archivo `xercesImpl-2.11.0.jar` para que coincida con el archivo Xerces Jar antiguo que se va a reemplazar. Esto se puede hacer en tiempo de ejecución.

  Este cambio reduce el tiempo de publicación y el uso de memoria al publicar asignaciones DITA con un gran número de temas.

