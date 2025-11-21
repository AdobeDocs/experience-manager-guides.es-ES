---
title: Usar HTML5
description: Obtenga información sobre cómo crear un ajuste preestablecido de HTML5 desde la consola de mapas y el panel de mapas. Configure el ajuste preestablecido de salida HTML5 en AEM Guides.
exl-id: b54bf3a0-7a13-41a0-ae72-cdf2caf8d974
feature: Publishing
role: User
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1516'
ht-degree: 0%

---

# HTML5 {#id205BE700XO1}

Puede crear el ajuste preestablecido de salida HTML5 para publicar la salida mediante DITA-OT y FMPS (si lo ha configurado el administrador).

Puede crear el ajuste preestablecido de HTML5 de dos formas:

- [Cree el ajuste preestablecido de salida HTML5 desde la consola Mapa](#create-html5-output-preset-from-the-map-console)
- [Cree el ajuste preestablecido de salida HTML5 desde el panel Mapa](#create-html5-output-preset-from-the-map-dashboard)

## Cree el ajuste preestablecido de salida HTML5 desde la consola Mapa

Siga estos pasos para crear el ajuste preestablecido de HTML5 desde la consola Mapa:

1. [Abra un archivo de mapa DITA en la consola de mapas](./open-files-map-console.md).

   También puede obtener acceso al archivo de asignación desde el widget **Archivos recientes** en la [sección Información general](./intro-home-page.md#overview). El archivo de mapa seleccionado se abriría en la consola de mapas.
1. En la pestaña **Ajustes preestablecidos de salida**, seleccione el icono + para crear un ajuste preestablecido de salida.
1. Seleccione **HTML5** del menú desplegable Tipo en el cuadro de diálogo **Nuevo ajuste preestablecido de salida**.
1. En el campo **Nombre**, proporcione un nombre para este ajuste preestablecido.
1. En el campo **Generar HTML con**, seleccione DITA-OT.
1. Seleccione la opción **Agregar al perfil de carpeta actual** para crear un ajuste preestablecido de salida dentro del perfil de carpeta actual. El ![icono de perfil de carpeta](images/global-preset-icon.svg) indica un ajuste preestablecido de nivel de perfil de carpeta.

   Obtenga más información sobre [Administrar ajustes preestablecidos de salida de perfil global y de carpeta](./web-editor-manage-output-presets.md).

1. Seleccione **Añadir**.

   Se crea el ajuste preestablecido para HTML5.

   ![](images/html5-preset-dialog-new.png){width="300" align="left"}

En la consola Mapa, las opciones de configuración preestablecidas están organizadas en las pestañas **General** y **Avanzado**.

La ficha **General** contiene las siguientes opciones de configuración:

- Ruta de salida
- Argumentos de línea de comandos DITA-OT
- Nombre de archivo
- Filtro condicional \(Si las condiciones están definidas para un mapa\)
- Usar línea de base \(Si se crea una línea de base para un mapa\)
- Flujo de trabajo de generación posterior

**Avanzado**

La pestaña Advanced contiene las siguientes opciones de configuración:

- Nombre de transformación
- Conservar archivos temporales
- Acoplar jerarquía de archivos
- Propiedades del archivo

Para obtener más información sobre las opciones de configuración preestablecidas, consulte la sección [Configuración preestablecida de HTML5](#html5-preset-configuration).

## Cree el ajuste preestablecido de salida HTML5 desde el panel Mapa

Siga estos pasos para crear el ajuste preestablecido de HTML5 desde el panel de mapas:

1. En la interfaz de usuario de Assets, desplácese hasta el mapa DITA y selecciónelo para abrirlo en el panel Mapa.
1. Asegúrese de que la ficha **Ajustes preestablecidos de salida** esté seleccionada.
1. Seleccione **Crear** en la barra de herramientas.

   Se muestra un nuevo formulario de creación de ajustes preestablecidos de salida.

1. Introduzca los detalles de configuración necesarios para el ajuste preestablecido de HTML5.
1. Seleccione **Listo** para guardar la configuración del ajuste preestablecido.

Para obtener más información sobre las opciones de configuración preestablecidas, consulte la sección [Configuración preestablecida de HTML5](#html5-preset-configuration).

## Configuración preestablecida de HTML5

Las opciones de configuración varían ligeramente en función de si está configurando el ajuste preestablecido desde la consola Mapa o el panel Mapa. Algunas opciones solo se aplican al tablero de mapas, mientras que otras se aplican a ambas.

En los casos en los que la misma configuración tiene dos etiquetas de campo diferentes, un **/** los separa en la tabla siguiente. El primero representa la etiqueta en la consola Mapa y el segundo representa la etiqueta en el panel Mapa.

Por ejemplo, **Ruta de salida/Ruta de destino** - Aquí, **Ruta de salida** es la etiqueta usada en la consola Mapa, mientras que **Ruta de destino** es la etiqueta usada en el panel Mapa para la misma configuración.

| Opciones de HTML5 | Descripción |
| --- | --- |
| Tipo de salida (*Aplicable solo para el tablero de mapas*) | El tipo de salida que desea generar. Para generar la salida de HTML5, elija la opción HTML5. |
| Nombre de configuración (*Aplicable solo para el tablero de mapas*) | Asigne un nombre descriptivo a la configuración de salida de HTML5 que está creando. Por ejemplo, puede especificar _salida de clientes internos_ o _salida de usuarios finales_. |
| Generar interactivo con (*Aplicable solo para el panel de mapas*) | Seleccione **DITA-OT** para generar la salida de HTML5. Seleccione **FrameMaker Publishing Server** si su administrador ha configurado esta opción. Algunas de las opciones de configuración varían cuando se selecciona FMPS. |
| Ruta de salida/Ruta de destino | Ruta dentro del repositorio de AEM donde se almacena la salida de HTML5. La ruta de acceso de salida se establece a través de la variable `${base_output_path}`, que configura el administrador. Para configurar la ruta de salida, vea [Configurar la ubicación de salida base para Cloud Services](../native-pdf/configure-base-location-cs.md) o [Configurar la ubicación de salida base para On-Premise Services](../native-pdf/configure-base-output-location.md) según el servicio que esté usando. |
| Argumentos de línea de comandos DITA-OT | Especifique los argumentos adicionales que desea que DITA-OT procese durante la generación de resultados. <br><br> NOTA: a partir de la versión 2502 de Experience Manager Guides, el parámetro `generate.copy.outer` ya no se administra internamente. Este cambio significa que si el contenido de HTML5 reside fuera del directorio de asignación, debe establecer explícitamente el parámetro `-Dgenerate.copy.outer=3` en el campo **Argumentos de línea de comandos DITA-OT**. Esto garantiza que el contenido se procese correctamente y se incluya en la salida. Para obtener más información sobre la administración de contenido fuera del directorio de asignación, vea [Documentación de DITA-OT](https://www.dita-ot.org/dev/parameters/generate-copy-outer#:~:text=The%20generate.,located%20outside%20the%20map%20directory/). |
| Nombre de archivo | Especifique el nombre de archivo con el que desea guardar la salida de HTML5.<br><br>**Nota**: si no proporciona un nombre de archivo, el título del mapa DITA se utilizará para generar el nombre de archivo de salida final de HTML5. Si el mapa no tiene título, se utilizará el nombre de fichero del mapa DITA para nombrar la salida final de HTML5. El nombre del archivo se sanea utilizando las reglas configuradas en el sistema para gestionar cualquier carácter no válido. |
| Condicionamiento del filtrado/Aplicación de condiciones mediante | Seleccione una de las siguientes opciones:<br><br>* **Ninguna aplicada**: Seleccione esta opción si no desea aplicar ninguna condición en la salida publicada.<br>* **archivo DITAVAL**: seleccione los archivos DITAVAL para generar contenido personalizado. Puede seleccionar varios archivos DITAVAL mediante el cuadro de diálogo de exploración o escribiendo la ruta del archivo. Utilice el icono en forma de cruz situado cerca del nombre del archivo para eliminarlo. Los archivos DITAVAL se evalúan en el orden especificado, por lo que las condiciones especificadas en el primer archivo tienen prioridad sobre las condiciones coincidentes especificadas en archivos posteriores. Puede mantener el orden de los archivos añadiendo o eliminando archivos.<br>También puede aplicar marcas dentro de un archivo DITAVAL para marcar visualmente el contenido. Cada indicador puede incluir una imagen y tener un estilo con formato como negrita o cursiva. Para obtener más información sobre cómo personalizar estilos de indicación o resolver conflictos de formato, vea [Usar el editor DITAVAL](../user-guide/ditaval-editor.md). Si el archivo DITAVAL se mueve a otra ubicación o se elimina, no se elimina automáticamente del panel de mapas. Debe actualizar la ubicación en caso de que los archivos se muevan o eliminen. Puede pasar el ratón sobre el nombre del archivo para ver la ruta en el repositorio de AEM donde está almacenado el archivo. Solo puede seleccionar archivos DITAVAL y se muestra un error si ha seleccionado cualquier otro tipo de archivo. FrameMaker Publishing Server no admite varios archivos DITAVAL.<br>* **Ajuste preestablecido de condición**: seleccione un ajuste preestablecido de condición en la lista desplegable para aplicar una condición al publicar la salida. La opción está visible si se ha añadido una condición presente en la ficha Ajustes preestablecidos de condición de la consola de mapa DITA. Para obtener más información acerca de los ajustes preestablecidos de condición, vea [Usar ajustes preestablecidos de condición](generate-output-use-condition-presets.md#id1825FL004PN).<br><br>**Nota**: FrameMaker Publishing Server no admite varios archivos DITAVAL. |
| Flujo de trabajo de generación posterior | Al elegir esta opción, se muestra una nueva lista desplegable Flujo de trabajo de generación posterior que contiene todos los flujos de trabajo configurados en AEM. Debe seleccionar un flujo de trabajo que desee ejecutar después de completar el flujo de trabajo de generación de resultados.<br><br>**Tenga en cuenta**:For más información sobre la creación de un flujo de trabajo de generación posterior a la salida personalizado, vea _Personalizar el flujo de trabajo de generación posterior a la salida_ en Instalar y configurar Adobe Experience Manager Guides as a Cloud Service. |
| Nombre de transformación | Especifique el tipo de salida que desea generar. Esto es necesario si desea generar resultados con su propio complemento personalizado, que está integrado en el complemento DITA-OT. Por ejemplo, si desea generar una salida XHTML, especifique `xhtml`. Para obtener una lista de las transformaciones disponibles en DITA-OT, consulte [Transformaciones DITA-OT (formatos de salida)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) en la Guía del usuario de OASIS DITA-OT. |
| Conservar archivos temporales | Seleccione esta opción para conservar los ficheros temporales generados por DITA-OT. Si se producen errores al generar la salida mediante DITA-OT, seleccione esta opción para conservar los ficheros temporales. Puede utilizar esos archivos para solucionar errores de generación de resultados.<br> <br> Después de generar la salida, seleccione el icono **Descargar archivos temporales** ![descargar archivos temporales](images/download-temp-files-icon.svg) para descargar la carpeta ZIP que contiene los archivos temporales. Los archivos descargados también incluirían `system_config.xml` archivo que le brinda información sobre la URL del autor, la URL local y la URL de publicación. Estas direcciones URL se configuran en la configuración de externalización de AEM y se reflejan en el archivo `system_config.xml`. <br><br> **Nota**: Si las propiedades de archivo se agregan durante la generación, los archivos temporales de salida también incluyen un archivo *metadata.xml* que contiene esas propiedades. |
| Usar línea base | Si ha creado una Línea base para el mapa DITA seleccionado, seleccione esta opción para especificar la versión que desea publicar.<br><br>Ver [Trabajar con línea de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obtener más detalles. |
| Acoplar jerarquía de archivos | Seleccione la opción para generar la salida de HTML5 en una jerarquía de carpetas plana. Todo el contenido se publica en formato de salida HTML5 en una jerarquía de archivos plana y se guarda en una sola carpeta. <br> Si anula la selección de esta opción, el resultado se generará en una jerarquía de carpetas anidada y se replicará toda la estructura de carpetas. |
| Propiedades de archivo | Seleccione las propiedades que desee procesar como metadatos. Estas propiedades se definen desde la página Propiedades del fichero de mapa DITA o de mapa de libros. Las propiedades que seleccione en la lista desplegable aparecerán en el campo **Propiedades del archivo**. Seleccione el icono en forma de cruz situado junto a la propiedad para eliminarla. <br><br>**Nota**: también puede pasar los metadatos a la salida mediante la publicación DITA-OT. Para obtener más información, [Pase los metadatos a la salida mediante DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |







**Tema principal:**&#x200B;[&#x200B; Explicación de los ajustes preestablecidos de salida](generate-output-understand-presets.md)
