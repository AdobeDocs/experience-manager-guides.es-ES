---
title: Generación de PDF con DITA-OT
description: Aprenda a crear un ajuste preestablecido de PDF con DITA-OT desde la consola de mapas y el tablero de mapas. Configure el ajuste preestablecido de salida de PDF en AEM Guides.
feature: Publishing
role: User
source-git-commit: b970df013a24ca256d7cbd07308367b1207e9163
workflow-type: tm+mt
source-wordcount: '1330'
ht-degree: 0%

---

# Crear ajuste preestablecido de salida DITA-OT PDF {#id205BE600HAH}

El ajuste preestablecido de salida DITA-OT PDF se puede crear de dos formas:

- [Cree el ajuste preestablecido de DITA-OT PDF desde la consola Mapa](#create-the-dita-ot-pdf-preset-from-the-map-console)
- [Cree el ajuste preestablecido de DITA-OT PDF desde el tablero de mandos Mapa](#create-the-dita-ot-pdf-preset-from-the-map-dashboard)

## Cree el ajuste preestablecido de DITA-OT PDF desde la consola Mapa

Siga estos pasos para crear el ajuste preestablecido de PDF desde la consola Mapa:

1. [Abra un archivo de mapa DITA en la consola de mapas](./open-files-map-console.md).

   También puede obtener acceso al archivo de asignación desde el widget **Archivos recientes** en la [sección Información general](./intro-home-page.md#overview). El archivo de mapa seleccionado se abriría en la consola de mapas.
1. En la pestaña **Ajustes preestablecidos de salida**, seleccione el icono + para crear un ajuste preestablecido de salida.
1. Seleccione **PDF** del menú desplegable Tipo en el cuadro de diálogo **Nuevo ajuste preestablecido de salida**.
1. En el campo **Nombre**, proporcione un nombre para este ajuste preestablecido.
1. En el campo **Generar PDF con**, seleccione **DITA-OT**.
1. Seleccione la opción **Agregar al perfil de carpeta actual** para crear un ajuste preestablecido de salida dentro del perfil de carpeta actual. El ![icono de perfil de carpeta](images/global-preset-icon.svg) indica un ajuste preestablecido de nivel de perfil de carpeta.

   Obtenga más información sobre [Administrar ajustes preestablecidos de salida de perfil global y de carpeta](./web-editor-manage-output-presets.md).

1. Seleccione **Añadir**.

   Se crea el ajuste preestablecido de PDF.

   ![](./images/pdf-preset-map-console.png){width="350" align="left"}

En la consola Mapa, las opciones de configuración preestablecidas para DITA-OT se organizan en las fichas **General** y **Avanzado** de la consola Mapa.

![](./images/dita-ot-preset-config.png){width="350" align="left"}

**General**

La ficha **General** contiene las siguientes opciones de configuración:

- Ruta de salida
- Argumentos de línea de comandos DITA-OT
- Nombre de archivo de PDF
- Filtro condicional \(Si las condiciones están definidas para un mapa\)
- Usar línea de base \(Si se crea una línea de base para un mapa\)
- Flujo de trabajo de generación posterior

**Avanzado**

La ficha **Avanzado** contiene las siguientes opciones de configuración:

- Activar control de versiones
- Conservar archivos temporales
- Propiedades del archivo

Para obtener más información sobre las opciones de configuración preestablecidas, consulte la sección [configuración preestablecida de PDF](#pdf-preset-configuration).


## Cree el ajuste preestablecido de DITA-OT PDF desde el tablero de mandos Mapa

Siga estos pasos para crear el ajuste preestablecido de PDF desde el panel de asignaciones:

1. En la interfaz de usuario de Assets, desplácese hasta el mapa DITA y selecciónelo para abrirlo en el panel de mapas.
1. Asegúrese de que la ficha **Ajustes preestablecidos de salida** esté seleccionada.
1. Seleccione **Crear** en la barra de herramientas.

   Se muestra un nuevo formulario de creación de ajustes preestablecidos de salida.

1. Introduzca los detalles de configuración necesarios para el ajuste preestablecido de PDF.
1. Seleccione **Listo** para guardar la configuración del ajuste preestablecido.

## Configuración preestablecida de PDF

Las opciones de configuración varían ligeramente en función de si está configurando el ajuste preestablecido desde la consola Mapa o el panel Mapa. Algunas opciones solo se aplican al tablero de mapas, mientras que otras se aplican a ambas.

En los casos en los que la misma configuración tiene dos etiquetas de campo diferentes, un **/** los separa en la tabla siguiente. El primero representa la etiqueta en la consola Mapa y el segundo representa la etiqueta en el panel Mapa.

Por ejemplo, **Ruta de salida/Ruta de destino** - Aquí, **Ruta de salida** es la etiqueta usada en la consola Mapa, mientras que **Ruta de destino** es la etiqueta usada en el panel Mapa para la misma configuración.

| Opciones de PDF | Descripción |
| --- | --- |
| Tipo de salida (*Aplicable solo para el tablero de mapas*) | El tipo de salida que desea generar. Para generar la salida de PDF, elija la opción PDF. |
| Nombre de configuración (*Aplicable solo para el tablero de mapas*) | Asigne un nombre descriptivo a la configuración de salida de PDF que está creando. Por ejemplo, puede especificar _salida de clientes internos_ o _salida de usuarios finales_. |
| Generar PDF usando (*Aplicable solo para el panel de mapas*) | Seleccione **DITA-OT** para generar la salida de PDF. Seleccione **FrameMaker Publishing Server** si su administrador ha configurado esta opción. Algunas de las opciones de configuración varían cuando se selecciona FMPS. Además, la opción de configuración FMPS solo está disponible en el panel de mapas. |
| Ruta de salida/Ruta de destino | La ruta dentro del repositorio de AEM donde se almacena PDF.<br><br>También puede utilizar variables al establecer la ruta de destino. Para obtener más información acerca del uso de variables, vea [Usar variables para establecer las opciones Ruta de destino, Nombre de sitio o Nombre de archivo](generate-output-use-variables.md#id18BUG70K05Z). |
| Argumentos de línea de comandos DITA-OT | Especifique los argumentos adicionales que desea que DITA-OT procese durante la generación de resultados. Para obtener más información acerca de los argumentos de línea de comandos admitidos en DITA-OT, vea [documentación de DITA-OT](https://www.dita-ot.org/). |
| Nombre de transformación | Especifique el tipo de salida que desea generar. Esto es necesario si desea generar resultados con su propio complemento personalizado, que está integrado en el complemento DITA-OT. Por ejemplo, si desea generar una salida XHTML, especifique `xhtml`. Para obtener una lista de las transformaciones disponibles en DITA-OT, consulte [Transformaciones DITA-OT (formatos de salida)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) en la Guía del usuario de OASIS DITA-OT. |
| Nombre de archivo PDF/Nombre de archivo | Especifique el nombre del archivo con el que desea guardar PDF.<br><br>También puede utilizar variables al establecer el nombre de archivo de PDF. Para obtener más información acerca del uso de variables, vea [Usar variables para establecer las opciones Ruta de destino, Nombre de sitio o Nombre de archivo](generate-output-use-variables.md#id18BUG70K05Z).<br><br>**Nota**: si no proporciona un nombre de archivo, el título del mapa DITA se utilizará para generar el nombre de archivo final de PDF. Si el mapa no tiene título, se utilizará el nombre de fichero del mapa DITA para asignar el nombre a la PDF final. El nombre del archivo se sanea utilizando las reglas configuradas en el sistema para gestionar cualquier carácter no válido. |
| Filtro condicional/Aplicar condiciones usando | Seleccione una de las siguientes opciones:<br><br>* **Ninguna aplicada**: Seleccione esta opción si no desea aplicar ninguna condición en la salida publicada.<br>* **archivo DITAVal**: seleccione los archivos DITAVal para generar contenido personalizado. Puede seleccionar varios archivos DITAVal mediante el cuadro de diálogo de exploración o escribiendo la ruta del archivo. Utilice el icono en forma de cruz situado cerca del nombre del archivo para eliminarlo. Los archivos DITAVal se evalúan en el orden especificado, por lo que las condiciones especificadas en el primer archivo tienen prioridad sobre las condiciones coincidentes especificadas en archivos posteriores. Puede mantener el orden de los archivos añadiendo o eliminando archivos. Si el archivo DITAVal se mueve a otra ubicación o se elimina, no se elimina automáticamente del panel de asignaciones. Debe actualizar la ubicación en caso de que los archivos se muevan o eliminen. Puede pasar el ratón sobre el nombre del archivo para ver la ruta en el repositorio de AEM donde está almacenado el archivo. Solo puede seleccionar archivos DITAVal y se muestra un error si ha seleccionado cualquier otro tipo de archivo. FrameMaker Publishing Server no admite varios archivos DITAVAL.<br>* **Ajuste preestablecido de condición**: seleccione un ajuste preestablecido de condición en la lista desplegable para aplicar una condición al publicar la salida. La opción está visible si se ha añadido una condición presente en la ficha Ajustes preestablecidos de condición de la consola de mapa DITA. Para obtener más información acerca de los ajustes preestablecidos de condición, vea [Usar ajustes preestablecidos de condición](generate-output-use-condition-presets.md#id1825FL004PN). |
| Ejecutar flujo de trabajo posterior a generación | Al elegir esta opción, se muestra una nueva lista desplegable Flujo de trabajo de generación posterior que contiene todos los flujos de trabajo configurados en AEM. Debe seleccionar un flujo de trabajo que desee ejecutar después de completar el flujo de trabajo de generación de resultados.<br><br>**Nota**: para obtener más información acerca de cómo crear un flujo de trabajo de generación posterior a la salida personalizado, vea Personalizar el flujo de trabajo de generación posterior a la salida en Instalar y configurar Adobe Experience Manager Guides as a Cloud Service. |
| Usar línea base | Si ha creado una Línea base para el mapa DITA seleccionado, seleccione esta opción para especificar la versión que desea publicar.<br><br>Ver [Trabajar con línea de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obtener más detalles. |
| Conservar archivos temporales | Seleccione esta opción para conservar los ficheros temporales generados por DITA-OT. Si se producen errores al generar la salida mediante DITA-OT, seleccione esta opción para conservar los ficheros temporales. Puede utilizar esos archivos para solucionar errores de generación de resultados.<br> <br> Después de generar la salida, seleccione el icono **Descargar archivos temporales** ![descargar archivos temporales](images/download-temp-files-icon.png) para descargar la carpeta ZIP que contiene los archivos temporales. <br><br> **Nota**: Si las propiedades de archivo se agregan durante la generación, los archivos temporales de salida también incluyen un archivo *metadata.xml* que contiene esas propiedades. |
| Propiedades del archivo | Seleccione las propiedades que desee procesar como metadatos. Estas propiedades se definen desde la página Propiedades del fichero de mapa DITA o de mapa de libros. Las propiedades que seleccione en la lista desplegable aparecerán en el campo **Propiedades del archivo**. Seleccione el icono en forma de cruz situado junto a la propiedad para eliminarla. <br><br>Nota: también puede pasar los metadatos a la salida mediante la publicación DITA-OT. Para obtener más información, [Pase los metadatos a la salida mediante DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |


**Tema principal:**[ Explicación de los ajustes preestablecidos de salida](generate-output-understand-presets.md)
