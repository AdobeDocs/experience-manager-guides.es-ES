---
title: Ajuste preestablecido de ePub
description: Obtenga información sobre cómo crear un ajuste preestablecido de EPUB desde el panel de mapas. Configure el ajuste preestablecido de salida de EPUB en AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: 1d914a5f-df1f-45eb-86ac-72485fdf07fe
source-git-commit: 1426cdaecdd358f06e76908b09330e65997e8452
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 1%

---

# EPUB {#id205BED020YT}

Puede crear el ajuste preestablecido de EPUB desde el panel de mapas.

>[!NOTE]
>
> Puede elegir el método para generar HTML5 con DITA-OT o FMPS \(si el administrador del sistema lo ha configurado\).

Para abrir los ajustes preestablecidos de salida para EPUB, haga clic en un archivo de mapa DITA, a continuación, haga clic en Ajustes preestablecidos de salida y, por último, haga clic en la opción EPUB. Las siguientes opciones están disponibles para la salida de EPUB:

| Opciones de ePub | Descripción |
| --- | --- |
| Tipo de salida | El tipo de salida que desea generar. Para generar la salida de EPUB, elija la opción EPUB. |
| Nombre de configuración | Asigne un nombre descriptivo a la configuración de salida de EPUB que está creando. Por ejemplo, puede especificar _salida de clientes internos_ o _salida de usuarios finales_. |
| Argumentos de línea de comandos DITA-OT | Especifique los argumentos adicionales que desea que DITA-OT procese durante la generación de resultados. Para obtener más información acerca de los argumentos de línea de comandos admitidos en DITA-OT, consulte [documentación de DITA-OT](https://www.dita-ot.org/). |
| Generación de EPUB con | Seleccione DITA-OT para generar la salida de EPUB. |
| Aplicación de condiciones mediante | Seleccione una de las siguientes opciones:<br><br>* **Ninguna aplicada**: Seleccione esta opción si no desea aplicar ninguna condición en la salida publicada.<br>* **archivo DITAVal**: seleccione los archivos DITAVal para generar contenido personalizado. Puede seleccionar varios archivos DITAVal mediante el cuadro de diálogo de exploración o escribiendo la ruta del archivo. Utilice el icono en forma de cruz situado cerca del nombre del archivo para eliminarlo. Los archivos DITAVal se evalúan en el orden especificado, por lo que las condiciones especificadas en el primer archivo tienen prioridad sobre las condiciones coincidentes especificadas en archivos posteriores. Puede mantener el orden de los archivos añadiendo o eliminando archivos. Si el archivo DITAVal se mueve a otra ubicación o se elimina, no se elimina automáticamente del panel de asignaciones. Debe actualizar la ubicación en caso de que los archivos se muevan o eliminen. Puede pasar el ratón sobre el nombre del archivo para ver la ruta en el repositorio de AEM donde está almacenado el archivo. Solo puede seleccionar archivos DITAVal y se muestra un error si ha seleccionado cualquier otro tipo de archivo. FrameMaker Publishing Server no admite varios archivos DITAVAL.<br>* **Ajuste preestablecido de condición**: seleccione un ajuste preestablecido de condición en la lista desplegable para aplicar una condición al publicar la salida. La opción está visible si se ha añadido una condición presente en la ficha Ajustes preestablecidos de condición de la consola de mapa DITA. Para obtener más información sobre los ajustes preestablecidos de condición, consulte [Usar ajustes preestablecidos de condición](generate-output-use-condition-presets.md#id1825FL004PN). |
| Ruta de destino | Ruta de acceso dentro del repositorio de AEM en la que se almacena la salida de EPUB. |
| Nombre de archivo | Especifique el nombre del archivo con el que desea guardar la salida de EPUB.<br><br>**Nota**: si no proporciona un nombre de archivo, el título del mapa DITA se utilizará para generar el nombre de archivo de salida final de EPUB. Si el mapa no tiene título, se utilizará el nombre de fichero del mapa DITA para nombrar la salida final de EPUB. El nombre del archivo se sanea utilizando las reglas configuradas en el sistema para gestionar cualquier carácter no válido. |
| Nombre de transformación | Especifique el tipo de salida que desea generar. Esto es necesario si desea generar resultados con su propio complemento personalizado, que está integrado en el complemento DITA-OT. Por ejemplo, si desea generar una salida XHTML, especifique `xhtml`. Para obtener una lista de las transformaciones disponibles en DITA-OT, consulte [Transformaciones DITA-OT (formatos de salida)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.md) en la Guía del usuario de OASIS DITA-OT. |
| Limpiar archivos temporales DITA-OT | Seleccione esta opción para limpiar los archivos temporales generados por DITA-OT. La ubicación donde DITA-OT almacena los archivos temporales se encuentra en el registro de generación de salida.<br><br>Si se producen errores al generar la salida mediante DITA-OT, puede anular la selección de esta opción para conservar los archivos temporales. A continuación, puede utilizar esos archivos para solucionar errores de generación de resultados. |
| Ejecutar flujo de trabajo posterior a generación | Al elegir esta opción, se muestra una nueva lista desplegable Flujo de trabajo de generación posterior que contiene todos los flujos de trabajo configurados en AEM. Debe seleccionar un flujo de trabajo que desee ejecutar después de completar el flujo de trabajo de generación de resultados.<br><br>**Nota**: para obtener más información sobre cómo crear un flujo de trabajo de generación posterior a la salida personalizado, consulte _Personalizar el flujo de trabajo de generación posterior a la salida_ en Instalar y configurar Adobe Experience Manager Guides as a Cloud Service. |
| Usar línea base | Si ha creado una Línea base para el mapa DITA seleccionado, seleccione esta opción para especificar la versión que desea publicar.<br><br>Vea [Trabajar con línea de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obtener más detalles. |
| Propiedades | Seleccione las propiedades que desee procesar como metadatos. Estas propiedades se definen desde la página Propiedades del fichero de mapa DITA o de mapa de libros. Las propiedades que seleccione en la lista desplegable se enumeran debajo del campo Propiedades y se eliminan de la lista desplegable. Una vez configuradas, estas propiedades también se copian en los temas del mapa.<br><br>**Nota**: también puede pasar los metadatos a la salida mediante la publicación DITA-OT. Para obtener más información, consulte [Pasar los metadatos a la salida mediante DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Tema principal:**&#x200B;[&#x200B; Explicación de los ajustes preestablecidos de salida](generate-output-understand-presets.md)
