---
title: Notas de versión | Se han corregido problemas en la versión del paquete de servicio 4 de Adobe Experience Manager Guides 4.6.0
description: Obtenga información acerca de las correcciones de errores en la versión 4.6.0 del Service Pack 4 de Adobe Experience Manager Guides
role: Leader
exl-id: ad69ea47-7880-43d1-8567-cd608fedb462
TQID: https://experienceleague.adobe.com/4ILARUO5umX41xE3Lcie-FsP396sgSqfbrWlMqdjsQ4
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 234
ht-degree: 4%

---

# Se han corregido problemas en la versión 4.6.0 del paquete de servicio 4 (abril de 2025)


Este artículo cubre los errores corregidos en varias áreas de la versión 4.6.0 del paquete de servicio 4 de Adobe Experience Manager Guides.

Obtenga información acerca de [instrucciones de actualización para el Service Pack 4 de la versión 4.6.0](upgrade-instructions-4-6-0-sp4.md).

## Creación

- Si arrastra y suelta una imagen dentro de un tema en la vista **Autor**, la referencia de imagen se romperá y se perderán datos. (25769)
- Al arrastrar y soltar un(a) `topicref` dentro de un mapa en la vista del **Autor**, se produce un error al realizar la operación deseada y se quita el(la) `topicref` junto al(la) `topicref` arrastrado(a). (19460)
- Si no se cierran las conexiones de sesión JCR al actualizar o crear temas, se producen pérdidas de memoria y tiempo de inactividad del servicio. (26282)

## Publicación

- La publicación nativa de PDF continúa indefinidamente si el contenido DITA tiene un vínculo web sin tener el ámbito `external`. (26434)
- Al crear una nueva línea base con un gran número de etiquetas, se produce un error en el cargador de etiquetas y se evita que se recuperen las etiquetas. (16232)
- La publicación de PDF nativos y sitios de AEM se detiene y se pone en cola cuando hay errores en el contenido. (26516)

## Problemas conocidos

Adobe ha identificado el siguiente problema conocido para esta versión:

- La publicación nativa de PDF en Windows encuentra errores cuando el contenido DITA contiene un vínculo externo que no incluye el atributo `scope`.
