---
title: Personalizado
description: Obtenga información sobre cómo crear ajustes preestablecidos personalizados desde la consola de mapas y el panel de mapas. Configure un ajuste preestablecido de salida personalizado en Experience Manager Guides.
exl-id: 1bb14411-ec94-4960-92ba-3b2ff7a29932
feature: Publishing
role: User
source-git-commit: a953de289530457b257259bda3d9af2b68790592
workflow-type: tm+mt
source-wordcount: '1267'
ht-degree: 0%

---

# Personalizado {#id205BEF00PX0}

Los ajustes preestablecidos de salida personalizados están disponibles para los complementos DITA-OT personalizados. Puede crear un ajuste preestablecido de salida DITA-OT personalizado para publicar la salida mediante el complemento DITA-OT personalizado.

Puede crear el ajuste preestablecido Personalizado de dos formas:

- [Cree el ajuste preestablecido personalizado desde la consola Mapa](#create-the-custom-preset-from-the-map-console)
- [Crear el ajuste preestablecido personalizado desde el panel de mapas](#create-the-custom-preset-from-the-map-dashboard)

## Cree el ajuste preestablecido personalizado desde la consola Mapa

Realice los siguientes pasos para crear el ajuste preestablecido personalizado desde la consola Mapa:

1. [Abra un archivo de mapa DITA en la consola de mapas](./open-files-map-console.md).

   También puede obtener acceso al archivo de asignación desde el widget **Archivos recientes** en la [sección Información general](./intro-home-page.md#overview). El archivo de mapa seleccionado se abriría en la consola de mapas.
1. En la pestaña **Ajustes preestablecidos de salida**, seleccione el icono + para crear un ajuste preestablecido de salida.
1. Seleccione **Personalizado** del menú desplegable Tipo en el cuadro de diálogo **Nuevo ajuste preestablecido de salida**.
1. En el campo **Nombre**, proporcione un nombre para este ajuste preestablecido.
1. Seleccione la opción **Agregar al perfil de carpeta actual** para crear un ajuste preestablecido de salida dentro del perfil de carpeta actual. El ![icono de perfil de carpeta](images/global-preset-icon.svg) indica un ajuste preestablecido de nivel de perfil de carpeta.

   Obtenga más información sobre [Administrar ajustes preestablecidos de salida de perfil global y de carpeta](./web-editor-manage-output-presets.md).

1. Seleccione **Añadir**.

   Se crea el ajuste preestablecido personalizado.

   ![](images/custom-preset-dialog.png){width="300" align="left"}

En la consola Mapa, las opciones de configuración preestablecidas están organizadas en las pestañas **General** y **Avanzado**.

![](images/custom-preset-config.png){align="left"}

La ficha **General** contiene las siguientes opciones de configuración:

- Argumentos de línea de comandos DITA-OT
- Nombre de transformación
- Nombre de archivo
- Ruta de salida
- Filtro condicional \(Si las condiciones están definidas para un mapa\)
- Usar línea de base \(Si se crea una línea de base para un mapa\)
- Flujo de trabajo de generación posterior

**Avanzado**

La pestaña Advanced contiene las siguientes opciones de configuración:

- Conservar archivos temporales
- Propiedades del archivo

Para obtener más información sobre las opciones de configuración preestablecidas, consulte la sección [Configuración preestablecida personalizada](#custom-preset-configuration).


## Cree el ajuste preestablecido personalizado desde el panel de mapas

Siga estos pasos para crear el ajuste preestablecido personalizado desde el panel de mapas:

1. En la interfaz de usuario de Assets, desplácese hasta el mapa DITA y selecciónelo para abrirlo en el panel Mapa.
1. Asegúrese de que la ficha **Ajustes preestablecidos de salida** esté seleccionada.
1. Seleccione **Crear** en la barra de herramientas.

   Se muestra un nuevo formulario de creación de ajustes preestablecidos de salida.

   ![](images/new-output-preset-map-dashboard.png){width="650" align="left"}

1. Introduzca los detalles de configuración necesarios para el ajuste preestablecido personalizado.
1. Seleccione **Listo** para guardar la configuración del ajuste preestablecido.

Para obtener más información sobre las opciones de configuración preestablecidas, consulte la sección [Configuración preestablecida personalizada](#custom-preset-configuration).

## Configuración personalizada de ajustes preestablecidos

Las opciones de configuración varían ligeramente en función de si está configurando el ajuste preestablecido desde la consola Mapa o el panel Mapa. Algunas opciones solo se aplican al tablero de mapas, mientras que otras se aplican a ambas.

En los casos en los que la misma configuración tiene dos etiquetas de campo diferentes, un **/** los separa en la tabla siguiente. El primero representa la etiqueta en la consola Mapa y el segundo representa la etiqueta en el panel Mapa.

Por ejemplo, **Ruta de salida/Ruta de destino** - Aquí, **Ruta de salida** es la etiqueta usada en la consola Mapa, mientras que **Ruta de destino** es la etiqueta usada en el panel Mapa para la misma configuración.

| Opciones de salida personalizadas | Descripción |
| --- | --- |
| Tipo de salida (*Aplicable solo para el tablero de mapas*) | El tipo de salida que desea generar. Para generar resultados mediante el complemento DITA-OT personalizado, elija la opción Personalizado. |
| Nombre de configuración (*Aplicable solo para el tablero de mapas*) | Asigne un nombre descriptivo a la configuración de salida que está creando. Por ejemplo, puede especificar _salida de clientes internos_ o _salida de usuarios finales_. |
| Argumentos de línea de comandos DITA-OT | Especifique los argumentos adicionales que desea que DITA-OT procese durante la generación de resultados. Para obtener más información acerca de los argumentos de línea de comandos admitidos en DITA-OT, vea [documentación de DITA-OT](https://www.dita-ot.org/). |
| Nombre de transformación | Especifique el tipo de salida que desea generar. Esto es necesario si desea generar resultados con su propio complemento personalizado, que está integrado en el complemento DITA-OT. Por ejemplo, si desea generar una salida XHTML, especifique `xhtml`. Para obtener una lista de las transformaciones disponibles en DITA-OT, consulte [Transformaciones DITA-OT (formatos de salida)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) en la Guía del usuario de OASIS DITA-OT. |
| Nombre de archivo | Especifique el nombre de archivo con el que desea guardar la salida.<br><br>**Nota**: si no proporciona un nombre de archivo, el título del mapa DITA se utilizará para generar el nombre final del archivo de salida. Si el mapa no tiene título, se utilizará el nombre de fichero del mapa DITA para asignar el nombre a la salida final. El nombre del archivo se sanea utilizando las reglas configuradas en el sistema para gestionar cualquier carácter no válido. |
| Filtro condicional/Aplicar condiciones utilizando | Seleccione una de las siguientes opciones:<br><br>* **Ninguna aplicada**: Seleccione esta opción si no desea aplicar ninguna condición en la salida publicada.<br>* **archivo DITAVAL**: seleccione los archivos DITAVAL para generar contenido personalizado. Puede seleccionar varios archivos DITAVAL mediante el cuadro de diálogo de exploración o escribiendo la ruta del archivo. Utilice el icono en forma de cruz situado cerca del nombre del archivo para eliminarlo. Los archivos DITAVAL se evalúan en el orden especificado, por lo que las condiciones especificadas en el primer archivo tienen prioridad sobre las condiciones coincidentes especificadas en archivos posteriores. Puede mantener el orden de los archivos añadiendo o eliminando archivos. Si el archivo DITAVAL se mueve a otra ubicación o se elimina, no se elimina automáticamente del panel de mapas. Debe actualizar la ubicación en caso de que los archivos se muevan o eliminen. Puede pasar el ratón sobre el nombre del archivo para ver la ruta en el repositorio de AEM donde está almacenado el archivo. Solo puede seleccionar archivos DITAVAL y se muestra un error si ha seleccionado cualquier otro tipo de archivo.<br>* **Ajuste preestablecido de condición**: seleccione un ajuste preestablecido de condición en la lista desplegable para aplicar una condición al publicar la salida. La opción está visible si se ha añadido una condición presente en la ficha Ajustes preestablecidos de condición de la consola de mapa DITA. Para obtener más información acerca de los ajustes preestablecidos de condición, vea [Usar ajustes preestablecidos de condición](generate-output-use-condition-presets.md#id1825FL004PN). |
| Ruta de salida/Ruta de destino | Ruta de acceso dentro del repositorio de AEM en la que se almacena la salida de EPUB. La ruta de acceso de salida se establece a través de la variable `${base_output_path}`, que configura el administrador. Para configurar la ruta de salida, vea [Configurar la ubicación de salida base para Cloud Services](../native-pdf/configure-base-location-cs.md) o [Configurar la ubicación de salida base para On-Premise Services](../native-pdf/configure-base-output-location.md) según los servicios que esté usando. |
| Conservar archivos temporales | Seleccione esta opción para conservar los ficheros temporales generados por DITA-OT. Si se producen errores al generar la salida mediante DITA-OT, seleccione esta opción para conservar los ficheros temporales. Puede utilizar esos archivos para solucionar errores de generación de resultados.<br> <br> Después de generar la salida, seleccione el icono **Descargar archivos temporales** ![descargar archivos temporales](images/download-temp-files-icon.png) para descargar la carpeta ZIP que contiene los archivos temporales. <br><br> **Nota**: Si las propiedades de archivo se agregan durante la generación, los archivos temporales de salida también incluyen un archivo *metadata.xml* que contiene esas propiedades. |
| Ejecutar flujo de trabajo de generación posterior | Al elegir esta opción, se muestra una nueva lista desplegable Flujo de trabajo de generación posterior que contiene todos los flujos de trabajo configurados en AEM. Debe seleccionar un flujo de trabajo que desee ejecutar después de completar el flujo de trabajo de generación de resultados.<br><br>**Nota**: para obtener más información acerca de cómo crear un flujo de trabajo de generación posterior a la salida personalizado, vea _Personalizar el flujo de trabajo de generación posterior a la salida_ en Instalar y configurar Adobe Experience Manager Guides as a Cloud Service. |
| Usar línea base | Si ha creado una Línea base para el mapa DITA seleccionado, seleccione esta opción para especificar la versión que desea publicar.<br><br> Ver [Trabajar con línea de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obtener más detalles. |
| Propiedades/propiedades del archivo | Seleccione las propiedades que desee procesar como metadatos. Estas propiedades se definen desde la página Propiedades del fichero de mapa DITA o de mapa de libros. Las propiedades que seleccione en la lista desplegable aparecerán en el campo **Propiedades del archivo**. Seleccione el icono en forma de cruz situado junto a la propiedad para eliminarla. <br><br>**Nota**: también puede pasar los metadatos a la salida mediante la publicación DITA-OT. Para obtener más información, [Pase los metadatos a la salida mediante DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Tema principal:**&#x200B;[&#x200B; Explicación de los ajustes preestablecidos de salida](generate-output-understand-presets.md)

