---
title: PDF
description: Generar y configurar la salida del PDF para documentos de FrameMaker en AEM Guides.
feature: Publishing FrameMaker Documents
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 3%

---

# PDF {#id205BB0T20RH}

Las siguientes opciones están disponibles para la salida del PDF:

>[!NOTE]
>
> Para abrir los ajustes preestablecidos de salida del PDF, haga clic en un archivo de FrameMaker \(`.fm` o `.book`\), a continuación, haga clic en Ajustes preestablecidos de salida y, por último, haga clic en la opción Salida del PDF.

| Opciones del PDF | Descripción |
|-----------|-----------|
| Tipo de salida | El tipo de salida que desea generar. Para generar la salida del PDF, seleccione la opción PDF. |
| Nombre de configuración | Asigne un nombre descriptivo a la configuración de salida del PDF que está creando. Por ejemplo, puede especificar *salida de clientes internos* o *salida de usuarios finales*. |
| **Configuración del trabajo** |
| Opciones | Seleccione el ajuste preestablecido de PDF que desee utilizar para generar la salida del PDF. |
| Generar PDF etiquetado | Seleccione esta opción para generar PDF etiquetados que contengan información sobre el contenido y la estructura del documento. Esta información la utilizan los lectores en pantalla. |
| Generar PDF para cada archivo del libro | Si está generando resultados para un archivo de libro, seleccione esta opción para generar un PDF independiente para cada archivo del libro. |
| Generar PDF solo para revisión | Seleccione esta opción para generar un PDF con la función de comentarios habilitada. |
| Crear un destino con nombre para todos los elementos y párrafos | Seleccione esta opción para crear destinos con nombre basados en elementos y párrafos. |
| **Configuración de pantalla** |
| Abrir documento en la página | Especifique el número de página que debe mostrarse al abrir el PDF. |
| Nivel de zoom inicial | Elija el nivel de zoom del documento. |
| Marca de registro | Para imprimir un documento con marcas de recorte y de registro, elija una opción en la lista desplegable Marcas de registro. |
| Anchura y altura de página | Especifique la anchura y la altura de la página. |
| Rango de páginas | Elija si desea publicar todas las páginas del libro o un rango de páginas. Si selecciona Rango, debe especificar el rango de páginas Desde y Hasta. |
| Convertir CYMK a RGB | Seleccione esta opción para convertir los colores CYMK en RGB en el PDF generado. |
| Generar marcadores de PDF | Cree un PDF accesible que contenga marcadores. |
| Ruta de destino | AEM Ruta de acceso del repositorio de en la que se almacena la salida del PDF. |
| Ejecutar flujo de trabajo posterior a generación | AEM Al elegir esta opción, se muestra una nueva lista desplegable Flujo de trabajo de generación de publicaciones que contiene todos los flujos de trabajo configurados en el flujo de trabajo de creación de flujos de trabajo de creación de flujos de trabajo de la. Debe seleccionar un flujo de trabajo que desee ejecutar después de completar el flujo de trabajo de generación de resultados. |

**Tema principal:**[ Generar salida de documentos de FrameMaker](fm-output-generatation.md)
