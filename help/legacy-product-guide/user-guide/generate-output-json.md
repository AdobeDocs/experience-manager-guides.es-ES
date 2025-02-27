---
title: JSON
description: Aprenda a crear ajustes preestablecidos de JSON desde el editor web y el panel de mapas. Configure el ajuste preestablecido de salida JSON en AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: dbc082e9-e75e-414d-a1d1-41f919b345af
source-git-commit: 1426cdaecdd358f06e76908b09330e65997e8452
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 0%

---

# JSON {#id231KK0180T4}

Puede crear el ajuste preestablecido JSON desde el Editor web:

En el panel Repositorio, abra el fichero de mapa DITA en la vista Mapa y, a continuación, en la ficha Salida, seleccione el icono + para crear un ajuste preestablecido de salida y, a continuación, seleccione JSON en la lista desplegable Tipo del cuadro de diálogo Añadir ajuste preestablecido.

En el editor web, se han organizado las siguientes configuraciones en la pestaña **General**:

- Ruta de salida
- Archivo de índice
- Aplicar condiciones con \(Si las condiciones están definidas para un mapa\)
- Utilizar Línea base \(Si se crea una línea base para un mapa\)
- Conservar archivos temporales
- Propiedades para propagar en la salida
- Flujo de trabajo de generación posterior

Para obtener más información, consulte [Configuración de JSON](#id231KJA00REJ).


**Configuración de JSON**

Las siguientes opciones están disponibles para el ajuste preestablecido JSON:

>[!NOTE]
>
> También puede editar el archivo JSON en el Editor web.

| Opciones de JSON | Descripción |
| --- | --- |
| Ruta de salida | Ruta de acceso dentro del repositorio de AEM donde se almacena la salida JSON. |
| Archivo de índice | Puede dar un nombre al archivo de índice que está creando para la salida JSON. De forma predeterminada, selecciona el nombre de archivo del mapa DITA y agrega un sufijo (como `map_filename_index.json`).<br><br>También puede utilizar variables al configurar el archivo de índice. Para obtener más información acerca del uso de variables, vea [Usar variables para establecer las opciones Ruta de destino, Nombre de sitio o Nombre de archivo](generate-output-use-variables.md#id18BUG70K05Z). |
| Aplicación de condiciones mediante | Seleccione una de las siguientes opciones:<br><br>* **Ninguna aplicada**: Seleccione esta opción si no desea aplicar ninguna condición en la salida publicada.<br>* **archivo DITAVAL**: seleccione los archivos DITAVAL para generar contenido personalizado. Puede seleccionar varios archivos DITAVAL mediante el cuadro de diálogo de exploración o escribiendo la ruta del archivo. Utilice el icono en forma de cruz situado cerca del nombre del archivo para eliminarlo. Los archivos DITAVAL se evalúan en el orden especificado, por lo que las condiciones especificadas en el primer archivo tienen prioridad sobre las condiciones coincidentes especificadas en archivos posteriores. Puede mantener el orden de los archivos añadiendo o eliminando archivos. Si el archivo DITAVAL se mueve a otra ubicación o se elimina, no se elimina automáticamente del panel de mapas. Debe actualizar la ubicación en caso de que los archivos se muevan o eliminen. Puede pasar el ratón sobre el nombre del archivo para ver la ruta en el repositorio de AEM donde está almacenado el archivo. Solo puede seleccionar archivos DITAVAL y se muestra un error si ha seleccionado cualquier otro tipo de archivo.<br>* **Ajuste preestablecido de condición**: seleccione un ajuste preestablecido de condición en la lista desplegable para aplicar una condición al publicar la salida. La opción está visible si se ha añadido una condición presente en la ficha Ajustes preestablecidos de condición de la consola de mapa DITA. Para obtener más información sobre los ajustes preestablecidos de condición, consulte [Usar ajustes preestablecidos de condición](generate-output-use-condition-presets.md#id1825FL004PN). |
| Usar línea base | Si ha creado una Línea base para el mapa DITA seleccionado, seleccione esta opción para especificar la versión que desea publicar.<br><br>Vea [Trabajar con línea de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obtener más detalles. |
| Conservar archivos temporales | Seleccione esta opción para conservar los ficheros temporales generados por DITA-OT. Si se producen errores al generar la salida mediante DITA-OT, seleccione esta opción para conservar los ficheros temporales. Puede utilizar esos archivos para solucionar errores de generación de resultados.<br> <br> Después de generar la salida, seleccione el icono **Descargar archivos temporales** ![descargar archivos temporales](images/download-temp-files-icon.png) para descargar la carpeta ZIP que contiene los archivos temporales. <br><br> **Nota**: Si las propiedades de archivo se agregan durante la generación, los archivos temporales de salida también incluyen un archivo *metadata.xml* que contiene esas propiedades. |
| Propiedades para propagar en la salida | Seleccione las propiedades que desee procesar como metadatos. Estas propiedades se definen desde la página Propiedades del fichero de mapa DITA o de mapa de libros. Las propiedades que seleccione en la lista desplegable se enumeran debajo del campo Propiedades.<br><br>**Nota**: también puede definir propiedades personalizadas y pasar los metadatos a la salida mediante la publicación DITA-OT. Para obtener más información, vea [Trabajar con metadatos](metadata-dita.md#id21BJ00QD0XA). |
| Flujo de trabajo de generación posterior | Al elegir esta opción, se muestra una nueva lista desplegable Flujo de trabajo de generación posterior que contiene todos los flujos de trabajo configurados en AEM. Debe seleccionar un flujo de trabajo que desee ejecutar después de completar el flujo de trabajo de generación de resultados.<br><br>**Nota**: para obtener más información sobre cómo crear un flujo de trabajo de generación posterior a la salida personalizado, consulte _Personalizar el flujo de trabajo de generación posterior a la salida_ en la guía Instalar y configurar Adobe Experience Manager Guides as a Cloud Service. |

**Tema principal:**[ Explicación de los ajustes preestablecidos de salida](generate-output-understand-presets.md)
