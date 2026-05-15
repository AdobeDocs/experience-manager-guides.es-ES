---
title: Administración de etiquetas para archivos DITA en AEM Guides
description: Breve artículo sobre la administración de cq:tags en AEM Guides
exl-id: 2d805c26-df9b-405a-81ca-7aa84c6f86c8
feature: Metadata Management
author: Pulkit Nagpal(punagpal)
role: User, Admin
TQID: https://experienceleague.adobe.com/u3MZ3fUZIp-FYQE895I7kDRkF3l96KhwYMRMJ-rG2RE
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0eid: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: c1579802-ddd4-4214-8a91-97b2066abe11id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 362
ht-degree: 0%

---

# Adición, eliminación y administración de etiquetas en el contenido DITA

Las etiquetas resultan útiles para categorizar el contenido. Si el contenido está correctamente etiquetado, puede ayudarle a localizar los temas exactos en el mapa de datos y el usuario final encuentra el contenido adecuado más rápidamente en la salida publicada

> **_NOTE:_** El artículo siguiente es para AEM Guides Build 4.2 (local) /Feb 2023 (versión en la nube ) o versiones posteriores


## Creación de etiquetas

El etiquetado es una función nativa de AEM y el administrador de AEM puede ayudarle a crear y configurar inicialmente estas etiquetas.


## Adición, eliminación y administración de etiquetas en el contenido DITA

**Todas las etiquetas creadas en AEM cq: tags se pueden añadir, eliminar y administrar para el contenido DITA**

Existen varias formas de añadir etiquetas al contenido DITA, pero este artículo se concentrará en la interfaz de usuario del editor web de AEM Guides.

### Pasos:

1. Ir a la vista del repositorio en la IU de Guides
2. Haga doble clic en ditamap y abra en la vista de mapa
3. Ir a la pestaña Administrar
4. En la pestaña Administrar, vaya a la opción Metadatos
5. Todos sus archivos de mapa directo e indirecto se cargan aquí.
6. Seleccione uno o varios archivos y haga clic en el icono &quot;administrar&quot;. Aquí puede añadir etiquetas a los archivos seleccionados.
También puede quitar las etiquetas existentes que son comunes en los archivos seleccionados.

<img title="Administración de etiquetas en AEM Guides " alt="Administración de etiquetas en DITA " src="ManageTags.jpg">

## Solución de problemas y preguntas más frecuentes

### La lista en administrar->metadatos está vacía o incompleta

`If list is empty or  incomplete then you may need to run the indexing on your ditamap, You can refer` [Instrucciones de actualización(Indexe su contenido)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/install-guide/on-prem-ig/download-install-upgrade-aemg/upgrade-xml-documentation.html?lang=en#steps-to-index-the-existing-content-to-use-the-new-find-and-replace%3A)

### Los metadatos personalizados no aparecen en la lista

`Only Tags present in cq:tags can be managed from here and custom metadata is not supported`




## Otros recursos útiles

- [Etiquetado masivo mediante el tablero de mapas (IU de Assets)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/manaege-metadata/map-editor-bulk-tagging.html?lang=en)
- [Informes Ditamap en el editor web](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/reports-aem-guide/reports-web-editor.html?lang=en)
- [Etiquetado en AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/configuring/tagging.html?lang=en)


**Póngase en contacto con su CSM respectivo para cualquier otra consulta**
