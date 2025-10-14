---
title: Ajuste preestablecido de ePub
description: Obtenga información sobre cómo crear un ajuste preestablecido de EPUB desde el panel de mapas. Configure el ajuste preestablecido de salida de EPUB en Experience Manager Guides.
exl-id: b6fb5483-064e-4552-84c7-b6723b79d8c5
feature: Publishing
role: User
source-git-commit: a953de289530457b257259bda3d9af2b68790592
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 1%

---

# EPUB {#id205BED020YT}

Puede crear el ajuste preestablecido de EPUB desde el panel de mapas.

>[!NOTE]
>
> Puede elegir el método para generar EPUB mediante DITA-OT o FMPS \(si el administrador del sistema lo ha configurado\).

Siga estos pasos para crear el ajuste preestablecido de EPUB desde el panel de asignaciones:

1. En la interfaz de usuario de Assets, desplácese hasta el mapa DITA y selecciónelo para abrirlo en el panel de mapas.
1. Asegúrese de que la ficha **Ajustes preestablecidos de salida** esté seleccionada.
1. Seleccione **Crear** en la barra de herramientas.

   Se muestra un nuevo formulario de creación de ajustes preestablecidos de salida.

1. Introduzca los detalles de configuración necesarios para el ajuste preestablecido de EPUB.
1. Seleccione **Listo** para guardar la configuración del ajuste preestablecido.

Las siguientes opciones de configuración están disponibles para los ajustes preestablecidos de EPUB:

| Opciones de ePub | Descripción |
| --- | --- |
| Tipo de salida | El tipo de salida que desea generar. Para generar la salida de EPUB, elija la opción EPUB. |
| Nombre de configuración | Asigne un nombre descriptivo a la configuración de salida de EPUB que está creando. Por ejemplo, puede especificar _salida de clientes internos_ o _salida de usuarios finales_. |
| Argumentos de línea de comandos DITA-OT | Especifique los argumentos adicionales que desea que DITA-OT procese durante la generación de resultados. Para obtener más información acerca de los argumentos de línea de comandos admitidos en DITA-OT, vea [documentación de DITA-OT](https://www.dita-ot.org/). |
| Generación de EPUB con | Seleccione DITA-OT para generar la salida de EPUB. |
| Aplicación de condiciones mediante | Seleccione una de las siguientes opciones:<br><br>* **Ninguna aplicada**: Seleccione esta opción si no desea aplicar ninguna condición en la salida publicada.<br>* **archivo DITAVAL**: seleccione los archivos DITAVAL para generar contenido personalizado. Puede seleccionar varios archivos DITAVAL mediante el cuadro de diálogo de exploración o escribiendo la ruta del archivo. Utilice el icono en forma de cruz situado cerca del nombre del archivo para eliminarlo. Los archivos DITAVAL se evalúan en el orden especificado, por lo que las condiciones especificadas en el primer archivo tienen prioridad sobre las condiciones coincidentes especificadas en archivos posteriores. Puede mantener el orden de los archivos añadiendo o eliminando archivos. Si el archivo DITAVAL se mueve a otra ubicación o se elimina, no se elimina automáticamente del panel de mapas. Debe actualizar la ubicación en caso de que los archivos se muevan o eliminen. Puede pasar el ratón sobre el nombre del archivo para ver la ruta en el repositorio de AEM donde está almacenado el archivo. Solo puede seleccionar archivos DITAVAL y se muestra un error si ha seleccionado cualquier otro tipo de archivo. FrameMaker Publishing Server no admite varios archivos DITAVAL.<br>* **Ajuste preestablecido de condición**: seleccione un ajuste preestablecido de condición en la lista desplegable para aplicar una condición al publicar la salida. La opción está visible si se ha añadido una condición presente en la ficha Ajustes preestablecidos de condición de la consola de mapa DITA. Para obtener más información acerca de los ajustes preestablecidos de condición, vea [Usar ajustes preestablecidos de condición](generate-output-use-condition-presets.md#id1825FL004PN). |
| Ruta de destino | Ruta de acceso dentro del repositorio de AEM en la que se almacena la salida de EPUB. La ruta de acceso de salida se establece a través de la variable `${base_output_path}`, que configura el administrador. Para configurar la ruta de salida, vea [Configurar la ubicación de salida base para Cloud Services](../native-pdf/configure-base-location-cs.md) o [Configurar la ubicación de salida base para On-Premise Services](../native-pdf/configure-base-output-location.md) según los servicios que esté usando. |
| Nombre de archivo | Especifique el nombre del archivo con el que desea guardar la salida de EPUB.<br><br>**Nota**: si no proporciona un nombre de archivo, el título del mapa DITA se utilizará para generar el nombre de archivo de salida final de EPUB. Si el mapa no tiene título, se utilizará el nombre de fichero del mapa DITA para nombrar la salida final de EPUB. El nombre del archivo se sanea utilizando las reglas configuradas en el sistema para gestionar cualquier carácter no válido. |
| Nombre de transformación | Especifique el tipo de salida que desea generar. Esto es necesario si desea generar resultados con su propio complemento personalizado, que está integrado en el complemento DITA-OT. Por ejemplo, si desea generar una salida XHTML, especifique `xhtml`. Para obtener una lista de las transformaciones disponibles en DITA-OT, consulte [Transformaciones DITA-OT (formatos de salida)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.md) en la Guía del usuario de OASIS DITA-OT. |
| Limpiar archivos temporales DITA-OT | Seleccione esta opción para limpiar los archivos temporales generados por DITA-OT. La ubicación donde DITA-OT almacena los archivos temporales se encuentra en el registro de generación de salida.<br><br>Si se producen errores al generar la salida mediante DITA-OT, puede anular la selección de esta opción para conservar los archivos temporales. A continuación, puede utilizar esos archivos para solucionar errores de generación de resultados. |
| Ejecutar flujo de trabajo posterior a generación | Al elegir esta opción, se muestra una nueva lista desplegable Flujo de trabajo de generación posterior que contiene todos los flujos de trabajo configurados en AEM. Debe seleccionar un flujo de trabajo que desee ejecutar después de completar el flujo de trabajo de generación de resultados.<br><br>**Nota**: para obtener más información acerca de cómo crear un flujo de trabajo de generación posterior a la salida personalizado, vea _Personalizar el flujo de trabajo de generación posterior a la salida_ en Instalar y configurar Adobe Experience Manager Guides as a Cloud Service. |
| Usar línea base | Si ha creado una Línea base para el mapa DITA seleccionado, seleccione esta opción para especificar la versión que desea publicar.<br><br>Ver [Trabajar con línea de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obtener más detalles. |
| Propiedades | Seleccione las propiedades que desee procesar como metadatos. Estas propiedades se definen desde la página Propiedades del fichero de mapa DITA o de mapa de libros. Las propiedades que seleccione en la lista desplegable se enumeran debajo del campo Propiedades y se eliminan de la lista desplegable. Una vez configuradas, estas propiedades también se copian en los temas del mapa.<br><br>**Nota**: también puede pasar los metadatos a la salida mediante la publicación DITA-OT. Para obtener más información, [Pase los metadatos a la salida mediante DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Tema principal:**&#x200B;[&#x200B; Explicación de los ajustes preestablecidos de salida](generate-output-understand-presets.md)
