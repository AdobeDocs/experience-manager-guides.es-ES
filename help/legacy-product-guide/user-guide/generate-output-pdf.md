---
title: Generar PDF
description: Obtenga información sobre cómo crear un ajuste preestablecido de PDF desde el editor web y el panel de mapas. Configure el ajuste preestablecido de salida de PDF en AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: fae55104-fef6-4994-911a-139598332b96
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '1060'
ht-degree: 1%

---

# PDF {#id205BE600HAH}

Puede crear el ajuste preestablecido de PDF de dos formas:

**En el editor web:** En el panel Repositorio, abra el archivo de mapa DITA en la vista Mapa y, a continuación, en la pestaña Salida, seleccione el icono + para crear un ajuste preestablecido de salida y, a continuación, seleccione PDF en la lista desplegable Tipo del cuadro de diálogo Agregar ajuste preestablecido.

>[!NOTE]
>
> Puede elegir el método para generar PDF mediante DITA-OT, Native PDF o FMPS \(si el administrador del sistema lo ha configurado).

En el editor web, las configuraciones se han organizado en las pestañas General y Avanzadas:

**General**

La ficha **General** contiene las siguientes configuraciones:

- Ruta de salida
- Argumentos de línea de comandos DITA-OT
- Nombre de transformación
- Nombre de archivo PDF
- Aplicar condiciones con \(Si las condiciones están definidas para un mapa\)
- Utilizar Línea base \(Si se crea una línea base para un mapa\)
- Flujo de trabajo de generación posterior

**Avanzado**

La pestaña Advanced contiene las siguientes configuraciones:

- Activar control de versiones
- Conservar archivos temporales

Para obtener más información, consulte [Configuración de PDF](#id231KIM004X1).

**Del tablero de mapas**

Para abrir los ajustes preestablecidos de salida para PDF, haga clic en un archivo de mapa DITA en la interfaz de usuario de Assets, a continuación, haga clic en Ajustes preestablecidos de salida y, por último, haga clic en la opción PDF. En el panel Mapa, haz clic en **Editar** en la parte superior para actualizar las distintas configuraciones y, a continuación, haz clic en **Guardar**.

**Configuración de PDF**

Las siguientes opciones están disponibles para la salida de PDF:

| Opciones de PDF | Descripción |
| --- | --- |
| Tipo de salida | El tipo de salida que desea generar. Para generar la salida de PDF, elija la opción PDF. |
| Nombre de configuración | Asigne un nombre descriptivo a la configuración de salida de PDF que está creando. Por ejemplo, puede especificar _salida de clientes internos_ o _salida de usuarios finales_. |
| Argumentos de línea de comandos DITA-OT | Especifique los argumentos adicionales que desea que DITA-OT procese durante la generación de resultados. Para obtener más información acerca de los argumentos de línea de comandos admitidos en DITA-OT, consulte [documentación de DITA-OT](https://www.dita-ot.org/). |
| Aplicación de condiciones mediante | Seleccione una de las siguientes opciones:<br><br>* **Ninguna aplicada**: Seleccione esta opción si no desea aplicar ninguna condición en la salida publicada.<br>* **Archivo DITAVal**: Seleccione los archivos DITAVal para generar contenido personalizado. Puede seleccionar varios archivos DITAVal mediante el cuadro de diálogo de exploración o escribiendo la ruta del archivo. Utilice el icono en forma de cruz situado cerca del nombre del archivo para eliminarlo. Los archivos DITAVal se evalúan en el orden especificado, por lo que las condiciones especificadas en el primer archivo tienen prioridad sobre las condiciones coincidentes especificadas en archivos posteriores. Puede mantener el orden de los archivos añadiendo o eliminando archivos. Si el archivo DITAVal se mueve a otra ubicación o se elimina, no se elimina automáticamente del panel de asignaciones. Debe actualizar la ubicación en caso de que los archivos se muevan o eliminen. Puede pasar el ratón sobre el nombre del archivo para ver la ruta en el repositorio de AEM donde está almacenado el archivo. Solo puede seleccionar archivos DITAVal y se muestra un error si ha seleccionado cualquier otro tipo de archivo. FrameMaker Publishing Server no admite varios archivos DITAVAL.<br>* **Ajuste preestablecido de condición**: seleccione un ajuste preestablecido de condición en la lista desplegable para aplicar una condición al publicar la salida. La opción está visible si se ha añadido una condición presente en la ficha Ajustes preestablecidos de condición de la consola de mapa DITA. Para obtener más información sobre los ajustes preestablecidos de condición, consulte [Usar ajustes preestablecidos de condición](generate-output-use-condition-presets.md#id1825FL004PN). |
| Generación de PDF con | Seleccione DITA-OT para generar PDF. |
| Ejecutar flujo de trabajo posterior a generación | Al elegir esta opción, se muestra una nueva lista desplegable Flujo de trabajo de generación posterior que contiene todos los flujos de trabajo configurados en AEM. Debe seleccionar un flujo de trabajo que desee ejecutar después de finalizar el flujo de trabajo de generación de resultados.<br><br>**Nota**: para obtener más información acerca de la creación de un flujo de trabajo de generación posterior a la salida personalizado, vea Personalizar el flujo de trabajo de generación posterior a la salida en Instalar y configurar Adobe Experience Manager Guides as a Cloud Service. |
| Transformation Name | Specify the type of output you want to generate. This is required if you want to generate output using your own custom plug-in, which is integrated in the DITA-OT plug-in. For example, if you want to generate XHTML output, specify `xhtml`. For a list of transformations available in DITA-OT, see [DITA-OT transformations (output formats)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) in OASIS DITA-OT User Guide. |
| Nombre de archivo | Specify the file name with which you want to save the PDF.<br><br>You can also use variables while setting the PDF File Name. For more details about using variables, see [Use variables for setting the Destination Path, Site Name, or File Name options](generate-output-use-variables.md#id18BUG70K05Z).<br><br>**Note**: If you do not provide a file name, then the DITA map&#39;s title is used to generate the final PDF&#39;s file name. If the map does not have a title, then the DITA map&#39;s file name is used to name is the final PDF. The file name is sanitized using the rules configured in the system to handle any invalid character. |
| Ruta de destino | The path within your AEM repository where the PDF is stored.<br><br>You can also use variables while setting the Destination Path. For more details about using variables, see [Use variables for setting the Destination Path, Site Name, or File Name options](generate-output-use-variables.md#id18BUG70K05Z). |
| Retain temporary files | Select this option to retain the temporary files generated by DITA-OT. If you are experiencing errors while generating output through DITA-OT, select this option to retain the temporary files. You can then use those files to troubleshoot output generation errors.<br> <br>  After generating the output, select the **Download temporary files** ![download temporary files icon](images/download-temp-files-icon.png) icon to download the ZIP folder containing the temporary files. <br><br> **Note**:  If file properties are added during generation, the output temporary files also include a *metadata.xml* file containing those properties. |
| Use Baseline | If you have created a Baseline for the selected DITA map, select this option to specify the version that you want to publish.<br><br>See [Work with Baseline](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) for more detail. |
| File Properties | Select the properties that you want to process as metadata. These properties are set from the Properties page of the DITA map or bookmap file. The properties you select from the dropdown list appear under the **File Properties** field. Seleccione el icono en forma de cruz situado junto a la propiedad para eliminarla. <br><br>Nota: también puede pasar los metadatos a la salida mediante la publicación DITA-OT. Para obtener más información, consulte [Pasar los metadatos a la salida mediante DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Tema principal:**&#x200B;[&#x200B; Explicación de los ajustes preestablecidos de salida](generate-output-understand-presets.md)
