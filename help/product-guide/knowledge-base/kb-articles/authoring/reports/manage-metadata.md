---
title: Administración de etiquetas para archivos DITA en AEM Guides
description: Breve artículo sobre la administración de cq:tags en AEM Guides
exl-id: 2d805c26-df9b-405a-81ca-7aa84c6f86c8
feature: Metadata Management
author: Pulkit Nagpal(punagpal)
role: User, Admin
source-git-commit: f971be4be9e2d32618616727cd9c682941dd3fb2
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 1%

---

# Adición, eliminación y administración de etiquetas en el contenido DITA

Las etiquetas resultan útiles para categorizar el contenido. Si el contenido está correctamente etiquetado, puede ayudarle a localizar los temas exactos en el mapa de datos y el usuario final encuentra el contenido adecuado más rápidamente en la salida publicada

> **_NOTA:_** El artículo siguiente es para AEM Guides Build 4.2 (local) /Feb 2023 (versión en la nube ) o versiones posteriores


## Creación de etiquetas

AEM AEM El etiquetado es una función nativa de la, y el administrador de la aplicación puede ayudarle en la creación y configuración iniciales de estas etiquetas.


## Adición, eliminación y administración de etiquetas en el contenido DITA

AEM **Todas las etiquetas creadas en el cq: se pueden agregar, quitar y administrar para el contenido de DITA**

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

`If list is empty or  incomplete then you may need to run the indexing on your ditamap, You can refer` [Instrucciones de actualización(Indexe su contenido)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/install-guide/on-prem-ig/download-install-upgrade-aemg/upgrade-xml-documentation.html?lang=es#steps-to-index-the-existing-content-to-use-the-new-find-and-replace%3A)

### Los metadatos personalizados no aparecen en la lista

`Only Tags present in cq:tags can be managed from here and custom metadata is not supported`




## Otros recursos útiles

- [Etiquetado masivo mediante el panel de mapas (IU de Assets)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/manaege-metadata/map-editor-bulk-tagging.html?lang=en)
- [Informes Ditamap en el editor web](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/reports-aem-guide/reports-web-editor.html?lang=en)
- AEM [Etiquetado en el código de tiempo de trabajo](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/configuring/tagging.html?lang=es)


**Póngase en contacto con su CSM respectivo para cualquier otra consulta**
