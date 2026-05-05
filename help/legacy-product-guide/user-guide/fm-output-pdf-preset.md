---
title: PDF
description: Genere y configure la salida de PDF para documentos de FrameMaker en AEM Guides.
feature: Publishing FrameMaker Documents
role: User
hide: true
exl-id: 3a8cb163-94ac-48b1-ae6b-1309179f462a
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 3%

---

# PDF {#id205BB0T20RH}

Las siguientes opciones están disponibles para la salida de PDF:

>[!NOTE]
>
> Para abrir los ajustes preestablecidos de salida de PDF, haga clic en un archivo FrameMaker \(`.fm` o `.book`\), luego haga clic en Ajustes preestablecidos de salida y, por último, haga clic en la opción Salida de PDF.

| Opciones de PDF | Descripción |
|-----------|-----------|
| Tipo de salida | El tipo de salida que desea generar. Para generar la salida de PDF, elija la opción PDF. |
| Nombre de configuración | Asigne un nombre descriptivo a la configuración de salida de PDF que está creando. Por ejemplo, puede especificar *salida de clientes internos* o *salida de usuarios finales*. |
| **Configuración del trabajo** |  |
| Opciones | Elija el ajuste preestablecido de PDF que desea utilizar para generar la salida de PDF. |
| Generar PDF etiquetado | Seleccione esta opción para generar PDF etiquetados que contengan información sobre el contenido y la estructura del documento. Esta información la utilizan los lectores en pantalla. |
| Generar PDF para cada archivo del libro | Si está generando resultados para un archivo de libro, seleccione esta opción para generar un PDF independiente para cada archivo del libro. |
| Generar PDF solo para revisión | Seleccione esta opción para generar PDF con la función de comentarios habilitada. |
| Crear un destino con nombre para todos los elementos y párrafos | Seleccione esta opción para crear destinos con nombre basados en elementos y párrafos. |
| **Configuración de pantalla** |  |
| Abrir documento en la página | Especifique el número de página que debe mostrarse al abrir PDF. |
| Nivel de zoom inicial | Elija el nivel de zoom del documento. |
| Marca de registro | To print a document with crop marks and registration marks, choose an option from the Registration Marks drop-down list. |
| Page Width and Page Height | Specify the width and height of the page. |
| Rango de páginas | Choose whether you want to publish all pages in the book or a range of pages. If you choose Range, then you must specify the From and To page range. |
| Convert CYMK to RGB | Select this option to convert CYMK colors to RGB in the generated PDF. |
| Generate PDF Bookmarks | Create accessible PDF that contains bookmarks. |
| Ruta de destino | The path within your AEM repository where the PDF output is stored. |
| Run Post Generation Workflow | When you choose this option, a new Post Generation Workflow drop-down list is displayed containing all workflows configured in AEM. You must select a workflow that you want to execute after completion of the output generation workflow. |

**Parent topic:**&#x200B;[&#x200B; Generate output of FrameMaker documents](fm-output-generatation.md)
