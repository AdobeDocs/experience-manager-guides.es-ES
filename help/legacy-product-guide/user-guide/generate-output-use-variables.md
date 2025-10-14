---
title: Utilice variables para establecer las opciones Ruta de destino, Nombre del sitio o Nombre de archivo
description: Aprenda a utilizar variables para establecer las opciones Ruta de destino, Nombre del sitio o Nombre de archivo. Conozca las variables listas para usarse admitidas en AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: 19d9121f-6b72-445c-a7d9-07f00026b654
source-git-commit: 1426cdaecdd358f06e76908b09330e65997e8452
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---

# Utilice variables para establecer las opciones Ruta de destino, Nombre del sitio o Nombre de archivo


Al generar resultados en AEM Site o PDF, puede utilizar variables para definir las opciones Ruta de destino, Nombre de sitio AEM o Nombre de archivo PDF. Puede utilizar una sola variable o una combinación de ellas para definir estas opciones.

La siguiente tabla enumera las variables que se admiten de forma predeterminada:

| Variable | Ruta de destino final | Ejemplos |
| --- | --- | --- |
| `${map_filename}` | Utiliza el nombre de fichero de mapa DITA para crear la ruta de destino. | **Nombre de archivo de mapa DITA**:<br>`AEMGuides.ditamap`<br><br>**Ruta de destino** configurada como:<br>`/content/output/sites/${map_filename}`<br><br>**Ubicación de salida final**:<br>`/content/output/sites/aemGuides/AEMGuides.html` |
| `${map_title}` | Utiliza el título del mapa DITA para crear la ruta de destino. | **Nombre de archivo de mapa DITA**:<br>`AEMGuides.ditamap`<br><br>**Título de mapa DITA**:<br>`AEMGuides`<br><br>**Ruta de destino** configurada como:<br>`/content/output/sites/${map_title}`<br><br>**Ubicación de salida final**:<br>`/content/output/sites/AEMGuides/AEMGuides.html` |
| `${preset_name}` | Utiliza el nombre del ajuste preestablecido de salida para crear la ruta de destino. | **Nombre de ajuste preestablecido de salida**:<br>`AEM Guides PDF Output`<br><br>**Nombre de archivo de mapa DITA**:<br>`SampleDita.ditamap`<br><br>**Ruta de destino** configurada como:<br>`/content/output/sites/${preset_name}`<br><br>**Ubicación de salida final**:<br>`/content/output/sites/AEM Guides PDF Output/SampleDita.html` |
| `${language_code}` | Utiliza el código de idioma donde se encuentra el archivo de asignación para crear la ruta de destino. | **Nombre de archivo de mapa DITA**:<br>`SampleDita.ditamap`<br><br>**Ruta de archivo de mapa DITA**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Ruta de destino** configurada como:<br>`/content/output/sites/${language_code}`<br><br>**Ubicación de salida final**:<br>`/content/output/sites/en/SampleDita.html` |
| `${map_parentpath}` | Utiliza la ruta completa del archivo de asignación para crear la ruta de destino.<br><br>**Nota**: esta variable no se puede usar para especificar el nombre del sitio de AEM o el nombre de archivo de PDF. | **Nombre de archivo de mapa DITA**:<br>`SampleDita.ditamap`<br><br>**Ruta de archivo de mapa DITA**:<br>`/content/dam/projects/AEM-Guides/en/user-guide`/<br><br>**Ruta de destino** configurada como:<br>`/content/output/sites/${map_parentpath}`<br><br>**Ubicación de salida final**:<br>`/content/output/sites/content/dam/projects/AEM-Guides/en/user-guide/SampleDita.html` |
| `${path_after_langfolder}` | Utiliza la ruta del archivo de asignación después de la carpeta de idioma para crear la ruta de destino.<br><br>**Nota**: esta variable no se puede usar para especificar el nombre del sitio de AEM o el nombre del archivo de PDF. | **Nombre de archivo de mapa DITA**:<br>`SampleDita.ditamap`<br><br>**Ruta de archivo de mapa DITA**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Ruta de destino** configurada como:<br>`/content/output/sites/${path\_after\_langfolder}`<br><br>**Ubicación de salida final**:<br>`/content/output/sites/user-guide/SampleDita.html` |
| `${system_date}` | Utiliza la fecha actual del servidor para crear la ruta de destino. | **Nombre de archivo de mapa DITA**: <br> `SampleDita.ditamap` <br><br> **Ruta del archivo de mapa DITA:** <br> `/content/dam/projects/AEM-Guides/en/user-guide/` <br><br> **Ruta de destino** configurada como: <br> `/content/output/sites/${system_date}` <br> <br> **Ubicación de salida final:** <br> /`content/output/sites/08252023/SampleDita.html` |
| `${system_time}` | Utiliza el tiempo actual del servidor para crear la ruta de destino. | **Nombre de archivo de mapa DITA:** <br>`SampleDita.ditamap` <br> <br> **Ruta de archivo de mapa DITA:** <br>`/content/dam/projects/AEM-Guides/en/user-guide/` <br><Br>**Ruta de destino** configurada como: <br> `/content/output/sites/${system_time}`<br><br>**Ubicación de salida final:**<br>`/content/output/sites/055612/SampleDita.html` |

Además, también se pueden utilizar los metadatos definidos para el fichero de mapa DITA o de mapa de libros como variables. Los metadatos se encuentran en el nodo `/jcr:content/metadata` del mapa DITA o del archivo bookmap. Por ejemplo, una de las propiedades de metadatos definidas en el nodo `/jcr:content/metadata` es `dc:title`. Puede especificar `${dc:title}` y el valor del título se utilizará en el resultado final.
**Tema principal:**&#x200B;[&#x200B; Generación de resultados](generate-output.md)
