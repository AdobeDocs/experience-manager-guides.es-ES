---
title: PDF
description: Genere y configure la salida de PDF para documentos de FrameMaker en AEM Guides.
exl-id: df3d3cd8-2aa1-4d82-8756-c3f5555cb904
feature: Publishing FrameMaker Documents
role: User
source-git-commit: b78a34430476c15cadacb23d65bd978b3c25bd23
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 3%

---

# PDF {#id205BB0T20RH}

Las siguientes opciones están disponibles para la salida de PDF:

>[!NOTE]
>
> Para abrir los ajustes preestablecidos de salida de PDF, seleccione un archivo FrameMaker \(`.fm` o `.book`\), luego seleccione los Ajustes preestablecidos de salida y elija la opción Salida de PDF.

| Opciones de PDF | Descripción |
|-----------|-----------|
| Tipo de salida | El tipo de salida que desea generar. Para generar la salida de PDF, elija la opción PDF. |
| Nombre de configuración | Asigne un nombre descriptivo a la configuración de salida de PDF que está creando. Por ejemplo, puede especificar *salida de clientes internos* o *salida de usuarios finales*. |
| **Configuración del trabajo** |
| Opciones | Elija el ajuste preestablecido de PDF que desea utilizar para generar la salida de PDF. |
| Generar PDF etiquetado | Seleccione esta opción para generar PDF etiquetados que contengan información sobre el contenido y la estructura del documento. Esta información la utilizan los lectores en pantalla. |
| Generar PDF para cada archivo del libro | Si está generando resultados para un archivo de libro, seleccione esta opción para generar un PDF independiente para cada archivo del libro. |
| Generar PDF solo para revisión | Seleccione esta opción para generar PDF con la función de comentarios habilitada. |
| Crear un destino con nombre para todos los elementos y párrafos | Seleccione esta opción para crear destinos con nombre basados en elementos y párrafos. |
| **Configuración de pantalla** |
| Abrir documento en la página | Especifique el número de página que debe mostrarse al abrir PDF. |
| Nivel de zoom inicial | Elija el nivel de zoom del documento. |
| Marca de registro | Para imprimir un documento con marcas de recorte y de registro, elija una opción en la lista desplegable Marcas de registro. |
| Anchura y altura de página | Especifique la anchura y la altura de la página. |
| Rango de páginas | Elija si desea publicar todas las páginas del libro o un rango de páginas. Si selecciona Rango, debe especificar el rango de páginas Desde y Hasta. |
| Convertir CYMK a RGB | Seleccione esta opción para convertir los colores CYMK a RGB en el PDF generado. |
| Generar marcadores de PDF | Cree una PDF accesible que contenga marcadores. |
| Ruta de destino | Ruta de acceso dentro del repositorio de AEM en la que se almacena la salida de PDF. |
| Ejecutar flujo de trabajo posterior a generación | Al elegir esta opción, se muestra una nueva lista desplegable Flujo de trabajo de generación posterior que contiene todos los flujos de trabajo configurados en AEM. Debe seleccionar un flujo de trabajo que desee ejecutar después de completar el flujo de trabajo de generación de resultados. |

**Tema principal:**&#x200B;[ Generar salida de documentos de FrameMaker](fm-output-generatation.md)
