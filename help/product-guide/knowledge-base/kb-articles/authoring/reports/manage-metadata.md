---
title: AEM Administración de etiquetas para archivos DITA en las guías de la
description: AEM Breve artículo sobre la administración de cq:tags en Guías de
exl-id: 2d805c26-df9b-405a-81ca-7aa84c6f86c8
source-git-commit: eb3fe92d36bc58a11e47f786a10d5938e2ed0184
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 1%

---

# Adición, eliminación y administración de etiquetas en el contenido DITA

Las etiquetas resultan útiles para categorizar el contenido. Si el contenido está correctamente etiquetado, puede ayudarle a localizar los temas exactos en el mapa de datos y el usuario final encuentra el contenido adecuado más rápidamente en la salida publicada

> **_NOTA:_**  AEM El siguiente artículo es para la versión 4.2 (local)/febrero de 2023 (versión en la nube ) de las Guías de o versiones posteriores


## Creación de etiquetas

AEM AEM El etiquetado es una función nativa de la, y el administrador de la aplicación puede ayudarle en la creación y configuración iniciales de estas etiquetas.


## Adición, eliminación y administración de etiquetas en el contenido DITA

**AEM Todas las etiquetas creadas en la cq: tags pueden añadirse, eliminarse y gestionarse para el contenido DITA**

AEM Existen varias formas de añadir etiquetas al contenido DITA, pero este artículo se concentrará en la interfaz de usuario del editor web de Guías.

### Pasos:

1. Ir a la vista del repositorio en la IU de Guides
2. Haga doble clic en ditamap y abra en la vista de mapa
3. Ir a la pestaña Administrar
4. En la pestaña Administrar, vaya a la opción Metadatos
5. Todos sus archivos de mapa directo e indirecto se cargan aquí.
6. Seleccione uno o varios archivos y haga clic en el icono &quot;administrar&quot;. Aquí puede añadir etiquetas a los archivos seleccionados.
También puede quitar las etiquetas existentes que son comunes en los archivos seleccionados.

<img title="AEM Administración de etiquetas en Guías de " alt="Administración de etiquetas en DITA " src="ManageTags.jpg">

## Solución de problemas y preguntas más frecuentes

### La lista en administrar->metadatos está vacía o incompleta

`If list is empty or  incomplete then you may need to run the indexing on your ditamap, You can refer` [Instrucciones de actualización (indexe el contenido)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/install-guide/on-prem-ig/download-install-upgrade-aemg/upgrade-xml-documentation.html?lang=en#steps-to-index-the-existing-content-to-use-the-new-find-and-replace%3A)

### Los metadatos personalizados no aparecen en la lista

`Only Tags present in cq:tags can be managed from here and custom metadata is not supported`




## Otros recursos útiles

- [Etiquetado masivo mediante el tablero de mapas (IU de Assets)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/manaege-metadata/map-editor-bulk-tagging.html?lang=en)
- [Informes Ditamap en el editor web](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/reports-aem-guide/reports-web-editor.html?lang=en)
- [AEM Etiquetado en la](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/configuring/tagging.html?lang=en)


**Póngase en contacto con su CSM correspondiente para cualquier otra consulta**
