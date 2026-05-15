---
title: Recomendaciones para la optimización del rendimiento
description: Conozca Recommendations para la optimización del rendimiento
exl-id: 92ac1f81-2f51-44b0-82c3-56b39e8f3027
feature: Performance Optimization
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/vh0hogZNMjKrCL12WdKVuwF2qXdzy64KxIhhB-K4esA
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: b1210526-416b-4ef6-bcc0-1692e99f30e9id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0eid: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
subfeature_v2: id: baa3aa24-d162-4a57-b73a-d27341145083id: c8841798-1a28-4264-a46a-984860f8e6f6
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 162
ht-degree: 5%

---

# Recomendaciones para la optimización del rendimiento {#id213BD0JG0XA}

Para optimizar el rendimiento, tenga en cuenta los siguientes puntos:

- Para optimizar el contenido y la experiencia de indexación, consulte [Optimizar la búsqueda e indexación de contenido](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=es) en la documentación de AEM.

- Parche Xerces Jar mientras utiliza DITA-OT personalizado para la publicación. Esta es una configuración obligatoria, según el caso de uso. Este cambio sólo es necesario si utiliza DITA-OT personalizado para publicar resultados.

  *Configuración requerida*: reemplace el archivo Xerces Jar del paquete DITA-OT personalizado por el OOTB enviado. El archivo predeterminado OOTB xercesImpl-2.11.0.jar está disponible en el archivo /libs/fmdita/dita\_resources/DITA-OT.zip. Asegúrese de cambiar el nombre del archivo xercesImpl-2.11.0.jar para que coincida con el archivo Jar de Xerces antiguo que se está reemplazando. Esto se puede hacer en tiempo de ejecución.

  Este cambio reduce el tiempo de publicación y el uso de memoria al publicar asignaciones DITA con un gran número de temas.


**Tema principal:**[ Descargar e instalar](download-install.md)
