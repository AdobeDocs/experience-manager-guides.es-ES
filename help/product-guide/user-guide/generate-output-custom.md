---
title: Personalizado
description: Aprenda a crear ajustes preestablecidos personalizados desde el editor web y el panel de asignaciones. AEM Configure un ajuste preestablecido de salida personalizado en las guías de la.
exl-id: 1bb14411-ec94-4960-92ba-3b2ff7a29932
feature: Publishing
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '934'
ht-degree: 2%

---

# Personalizado {#id205BEF00PX0}

Los ajustes preestablecidos de salida personalizados están disponibles para los complementos DITA-OT personalizados. Puede crear un ajuste preestablecido de salida DITA-OT personalizado para publicar la salida mediante el complemento DITA-OT personalizado.

Puede crear el ajuste preestablecido Personalizado de dos formas:

**Desde el editor web:** En el panel Repositorio, abra el fichero de mapa DITA en la vista Mapa y, a continuación, en la ficha Salida, seleccione el icono + para crear un ajuste preestablecido de salida y, a continuación, seleccione Personalizado en la lista desplegable Tipo del cuadro de diálogo Añadir ajuste preestablecido.

En el editor web, las configuraciones se han organizado en las pestañas General y Avanzadas:

**General**

El **General** La pestaña contiene las siguientes configuraciones:

- Argumentos de línea de comandos DITA-OT
- Nombre de transformación
- Nombre de archivo
- Ruta de salida
- Aplicar condiciones con \(Si las condiciones están definidas para un mapa\)
- Utilizar Línea base \(Si se crea una línea base para un mapa\)
- Flujo de trabajo de generación posterior

**Avanzado**

La pestaña Advanced contiene las siguientes configuraciones:

- Limpiar archivos temporales DITA-OT
- Propiedades

Para obtener más información, consulte [Configuración personalizada](#id231KJA00REJ).

**Desde el panel de mapas**

Para abrir los ajustes preestablecidos de salida para el PDF, haga clic en un archivo de mapa DITA en la interfaz de usuario de Assets, haga clic en Ajustes preestablecidos de salida y, a continuación, haga clic en la opción HTML 5. En el tablero de mapas, haga clic en **Editar** en la parte superior para actualizar las distintas configuraciones y, a continuación, haga clic en **Guardar**.

**Configuración personalizada**

Las siguientes opciones están disponibles para el ajuste preestablecido de salida personalizado:

| Opciones de salida personalizadas | Descripción |
| --- | --- |
| Tipo de salida | El tipo de salida que desea generar. Para generar resultados mediante el complemento DITA-OT personalizado, elija la opción Personalizado. |
| Nombre de la configuración | Asigne un nombre descriptivo a la configuración de salida que está creando. Por ejemplo, puede especificar _Salida de clientes internos_ o _salida de usuarios finales_. |
| Argumentos de línea de comandos DITA-OT | Especifique los argumentos adicionales que desea que DITA-OT procese durante la generación de resultados. Para obtener más información acerca de los argumentos de línea de comandos admitidos en DITA-OT, consulte [Documentación de DITA-OT](https://www.dita-ot.org/). |
| Nombre de transformación | Especifique el tipo de salida que desea generar. Esto es necesario si desea generar resultados con su propio complemento personalizado, que está integrado en el complemento DITA-OT. Por ejemplo, si desea generar una salida XHTML, especifique `xhtml`. Para obtener una lista de las transformaciones disponibles en DITA-OT, consulte [Transformaciones DITA-OT (formatos de salida)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) en la Guía del usuario de OASIS DITA-OT. |
| Nombre de archivo | Especifique el nombre de archivo con el que desea guardar la salida.<br><br>**Nota**: si no se proporciona un nombre de fichero, se utilizará el título del mapa DITA para generar el nombre final del fichero de salida. Si el mapa no tiene título, se utilizará el nombre de fichero del mapa DITA para asignar el nombre a la salida final. El nombre del archivo se sanea utilizando las reglas configuradas en el sistema para gestionar cualquier carácter no válido. |
| Aplicación de condiciones mediante | Seleccione una de las siguientes opciones:<br><br>* **Ninguno aplicado**: seleccione esta opción si no desea aplicar ninguna condición en la salida publicada.<br>* **Archivo DITAVal**: seleccione los archivos DITAVal para generar contenido personalizado. Puede seleccionar varios archivos DITAVal mediante el cuadro de diálogo de exploración o escribiendo la ruta del archivo. Utilice el icono en forma de cruz situado cerca del nombre del archivo para eliminarlo. Los archivos DITAVal se evalúan en el orden especificado, por lo que las condiciones especificadas en el primer archivo tienen prioridad sobre las condiciones coincidentes especificadas en archivos posteriores. Puede mantener el orden de los archivos añadiendo o eliminando archivos. Si el archivo DITAVal se mueve a otra ubicación o se elimina, no se elimina automáticamente del panel de asignaciones. Debe actualizar la ubicación en caso de que los archivos se muevan o eliminen. AEM Puede pasar el ratón sobre el nombre del archivo para ver la ruta en el repositorio de donde se almacena el archivo. Solo puede seleccionar archivos DITAVal y se muestra un error si ha seleccionado cualquier otro tipo de archivo.<br>* **Ajuste preestablecido de condición**: Seleccione un ajuste preestablecido de condición en la lista desplegable para aplicar una condición al publicar la salida. La opción está visible si se ha añadido una condición presente en la ficha Ajustes preestablecidos de condición de la consola de mapa DITA. Para obtener más información sobre los ajustes preestablecidos de condición, consulte [Usar ajustes preestablecidos de condición](generate-output-use-condition-presets.md#id1825FL004PN). |
| Ruta de destino | AEM La ruta dentro del repositorio de donde se almacena la salida de EPUB. |
| Limpiar archivos temporales DITA-OT | Seleccione esta opción para limpiar los archivos temporales generados por DITA-OT. La ubicación donde DITA-OT almacena los archivos temporales se encuentra en el registro de generación de salida.<br><br>Si se producen errores al generar la salida mediante DITA-OT, se puede anular la selección de esta opción para conservar los ficheros temporales. A continuación, puede utilizar esos archivos para solucionar errores de generación de resultados. |
| Ejecutar flujo de trabajo posterior a generación | AEM Al elegir esta opción, se muestra una nueva lista desplegable Flujo de trabajo de generación de publicaciones que contiene todos los flujos de trabajo configurados en el flujo de trabajo de creación de flujos de trabajo de creación de flujos de trabajo de la. Debe seleccionar un flujo de trabajo que desee ejecutar después de completar el flujo de trabajo de generación de resultados.<br><br>**Nota**: para obtener más información sobre la creación de un flujo de trabajo de generación posterior a la salida personalizado, consulte _Personalizar flujo de trabajo de generación posterior a la salida_ en Instalar y configurar las guías de Adobe Experience Manager as a Cloud Service. |
| Usar línea base | Si ha creado una Línea base para el mapa DITA seleccionado, seleccione esta opción para especificar la versión que desea publicar.<br><br>Consulte [Trabajar con línea base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obtener más información. |
| Propiedades | Seleccione las propiedades que desee procesar como metadatos. Estas propiedades se definen desde la página Propiedades del fichero de mapa DITA o de mapa de libros. Las propiedades que seleccione en la lista desplegable aparecerán en la **Propiedades** field. Seleccione el icono en forma de cruz situado junto a la propiedad para eliminarla. <br><br>**Nota**: también puede pasar los metadatos a la salida mediante la publicación DITA-OT. Para obtener más información, consulte [Pasar los metadatos a la salida utilizando DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Tema principal:**[ Explicación de los ajustes preestablecidos de salida](generate-output-understand-presets.md)
