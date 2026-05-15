---
title: Utilice variables para establecer las opciones Ruta de destino, Ruta del sitio, Nombre del sitio o Nombre de archivo
description: Aprenda a utilizar variables para establecer las opciones Ruta de destino, Nombre del sitio o Nombre de archivo. Conozca las variables listas para usarse admitidas en AEM Guides.
exl-id: 3396c971-6332-45b5-b2ef-b07f0abf97f7
feature: Publishing
role: User
TQID: https://experienceleague.adobe.com/JiQKZ28KLI-TI5cqYdpKLyW79uOzlR2VV3zqZPFoVWc
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 399
ht-degree: 0%

---

# Utilice variables para establecer las opciones Ruta de destino, Ruta del sitio, Nombre del sitio o Nombre de archivo


Al generar resultados en AEM Sites o PDF, puede utilizar variables para definir las opciones Ruta de destino, Ruta del sitio, Nombre del sitio AEM o Nombre de archivo PDF. Puede utilizar una sola variable o una combinación de ellas para definir estas opciones.

La siguiente tabla enumera las variables que se admiten de forma predeterminada:

| Variable | Ruta de destino final | Ejemplo |
| --- | --- | --- |
| `${map_filename}` | Utiliza el nombre de fichero de mapa DITA para crear la ruta de destino. | **Nombre de archivo de mapa DITA**:<br>`AEMGuides.ditamap`<br><br>**Ruta de destino** configurada como:<br>`/content/output/sites/${map_filename}`<br><br>**Ubicación de salida final**:<br>`/content/output/sites/aemGuides/AEMGuides.html` |
| `${map_title}` | Utiliza el título del mapa DITA para crear la ruta de destino. | **Nombre de archivo de mapa DITA**:<br>`AEMGuides.ditamap`<br><br>**Título de mapa DITA**:<br>`AEMGuides`<br><br>**Ruta de destino** configurada como:<br>`/content/output/sites/${map_title}`<br><br>**Ubicación de salida final**:<br>`/content/output/sites/AEMGuides/AEMGuides.html` |
| `${preset_name}` | Utiliza el nombre del ajuste preestablecido de salida para crear la ruta de destino. | **Nombre de ajuste preestablecido de salida**:<br>`AEM Guides PDF Output`<br><br>**Nombre de archivo de mapa DITA**:<br>`SampleDita.ditamap`<br><br>**Ruta de destino** configurada como:<br>`/content/output/sites/${preset_name}`<br><br>**Ubicación de salida final**:<br>`/content/output/sites/AEM Guides PDF Output/SampleDita.html` |
| `${language_code}` | Utiliza el código de idioma donde se encuentra el archivo de asignación para crear la ruta de destino. | **Nombre de archivo de mapa DITA**:<br>`SampleDita.ditamap`<br><br>**Ruta de archivo de mapa DITA**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Ruta de destino** configurada como:<br>`/content/output/sites/${language_code}`<br><br>**Ubicación de salida final**:<br>`/content/output/sites/en/SampleDita.html` |
| `${map_parentpath}` | Utiliza la ruta completa del archivo de asignación para crear la ruta de destino.La variable <br><br>**Note**:This no se puede usar para especificar el nombre del sitio de AEM o el nombre de archivo de PDF. | **Nombre de archivo de mapa DITA**:<br>`SampleDita.ditamap`<br><br>**Ruta de archivo de mapa DITA**:<br>`/content/dam/projects/AEM-Guides/en/user-guide`/<br><br>**Ruta de destino** configurada como:<br>`/content/output/sites/${map_parentpath}`<br><br>**Ubicación de salida final**:<br>`/content/output/sites/content/dam/projects/AEM-Guides/en/user-guide/SampleDita.html` |
| `${path_after_langfolder}` | Utiliza la ruta de acceso del archivo de asignación después de la carpeta de idioma para crear la ruta de acceso de destino.<br><br>**Nota**: esta variable no se puede usar para especificar el nombre del sitio de AEM o el nombre de archivo de PDF. | **Nombre de archivo de mapa DITA**:<br>`SampleDita.ditamap`<br><br>**Ruta de archivo de mapa DITA**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Ruta de destino** configurada como:<br>`/content/output/sites/${path\_after\_langfolder}`<br><br>**Ubicación de salida final**:<br>`/content/output/sites/user-guide/SampleDita.html` |
| `${system_date}` | Utiliza la fecha actual del servidor para crear la ruta de destino. | **Nombre de archivo de mapa DITA**: <br> `SampleDita.ditamap` <br><br> **Ruta del archivo de mapa DITA:** <br> `/content/dam/projects/AEM-Guides/en/user-guide/` <br><br> **Ruta de destino** configurada como: <br> `/content/output/sites/${system_date}` <br> <br> **Ubicación de salida final:** <br> /`content/output/sites/08252023/SampleDita.html` |
| `${system_time}` | Utiliza el tiempo actual del servidor para crear la ruta de destino. | **Nombre de archivo de mapa DITA:** <br>`SampleDita.ditamap` <br> <br> **Ruta de archivo de mapa DITA:** <br>`/content/dam/projects/AEM-Guides/en/user-guide/` <br><Br>**Ruta de destino** configurada como: <br> `/content/output/sites/${system_time}`<br><br>**Ubicación de salida final:**<br>`/content/output/sites/055612/SampleDita.html` |

Además, también se pueden utilizar los metadatos definidos para el fichero de mapa DITA o de mapa de libros como variables. Los metadatos se encuentran en el nodo `/jcr:content/metadata` del mapa DITA o del archivo bookmap. Por ejemplo, una de las propiedades de metadatos definidas en el nodo `/jcr:content/metadata` es `dc:title`. Puede especificar `${dc:title}` y el valor del título se utilizará en el resultado final.
**Tema principal:**&#x200B;[&#x200B; Generación de resultados](generate-output.md)
