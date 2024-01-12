---
title: JSON
description: Aprenda a crear ajustes preestablecidos de JSON desde el editor web y el panel de mapas. AEM Configure el ajuste preestablecido de salida JSON en las guías del.
exl-id: 9eb426fc-ca0a-4932-8a55-fea731281a0a
feature: Publishing
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 1%

---

# JSON {#id231KK0180T4}

Puede crear el ajuste preestablecido JSON desde el Editor web:

En el panel Repositorio, abra el fichero de mapa DITA en la vista Mapa y, a continuación, en la ficha Salida, seleccione el icono + para crear un ajuste preestablecido de salida y, a continuación, seleccione JSON en la lista desplegable Tipo del cuadro de diálogo Añadir ajuste preestablecido.

En el editor web, las siguientes configuraciones se han organizado en la variable **General** pestaña:

- Ruta de salida
- Archivo de índice
- Aplicar condiciones con \(Si las condiciones están definidas para un mapa\)
- Utilizar Línea base \(Si se crea una línea base para un mapa\)
- Propiedades para propagar en la salida
- Flujo de trabajo de generación posterior

Para obtener más información, consulte [Configuración de JSON](#id231KJA00REJ).

**Desde el panel de mapas**

Para abrir los ajustes preestablecidos de salida para el PDF, haga clic en un archivo de mapa DITA en la interfaz de usuario de Assets, haga clic en Ajustes preestablecidos de salida y, a continuación, haga clic en la opción HTML 5. En el tablero de mapas, haga clic en **Editar** en la parte superior para actualizar las distintas configuraciones y, a continuación, haga clic en **Guardar**.

**Configuración de JSON**

Las siguientes opciones están disponibles para el ajuste preestablecido JSON:

>[!NOTE]
>
> También puede editar el archivo JSON en el Editor web.

| Opciones de JSON | Descripción |
| --- | --- |
| Ruta de salida | AEM Ruta de acceso del repositorio de en la que se almacena la salida JSON. |
| Archivo de índice | Puede dar un nombre al archivo de índice que está creando para la salida JSON. De forma predeterminada, selecciona el nombre de fichero del mapa DITA y añade un sufijo (como `map_filename_index.json`).<br><br>También puede utilizar variables al configurar el archivo de índice. Para obtener más información sobre el uso de variables, consulte [Utilice variables para establecer las opciones Ruta de destino, Nombre del sitio o Nombre de archivo](generate-output-use-variables.md#id18BUG70K05Z). |
| Aplicación de condiciones mediante | Seleccione una de las siguientes opciones:<br><br>* **Ninguno aplicado**: seleccione esta opción si no desea aplicar ninguna condición en la salida publicada.<br>* **Archivo DITAVAL**: seleccione los archivos DITAVAL para generar contenido personalizado. Puede seleccionar varios archivos DITAVAL mediante el cuadro de diálogo de exploración o escribiendo la ruta del archivo. Utilice el icono en forma de cruz situado cerca del nombre del archivo para eliminarlo. Los archivos DITAVAL se evalúan en el orden especificado, por lo que las condiciones especificadas en el primer archivo tienen prioridad sobre las condiciones coincidentes especificadas en archivos posteriores. Puede mantener el orden de los archivos añadiendo o eliminando archivos. Si el archivo DITAVAL se mueve a otra ubicación o se elimina, no se elimina automáticamente del panel de mapas. Debe actualizar la ubicación en caso de que los archivos se muevan o eliminen. AEM Puede pasar el ratón sobre el nombre del archivo para ver la ruta en el repositorio de donde se almacena el archivo. Solo puede seleccionar archivos DITAVAL y se muestra un error si ha seleccionado cualquier otro tipo de archivo.<br>* **Ajuste preestablecido de condición**: Seleccione un ajuste preestablecido de condición en la lista desplegable para aplicar una condición al publicar la salida. La opción está visible si se ha añadido una condición presente en la ficha Ajustes preestablecidos de condición de la consola de mapa DITA. Para obtener más información sobre los ajustes preestablecidos de condición, consulte [Usar ajustes preestablecidos de condición](generate-output-use-condition-presets.md#id1825FL004PN). |
| Usar línea base | Si ha creado una Línea base para el mapa DITA seleccionado, seleccione esta opción para especificar la versión que desea publicar.<br><br>Consulte [Trabajar con línea base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obtener más información. |
| Propiedades para propagar en la salida | Seleccione las propiedades que desee procesar como metadatos. Estas propiedades se definen desde la página Propiedades del fichero de mapa DITA o de mapa de libros. Las propiedades que seleccione en la lista desplegable se enumeran debajo del campo Propiedades.<br><br>**Nota**: también puede definir propiedades personalizadas y pasar los metadatos a la salida mediante la publicación DITA-OT. Para obtener más información, consulte [Trabajo con metadatos](metadata-dita.md#id21BJ00QD0XA). |
| Flujo de trabajo de generación posterior | AEM Al elegir esta opción, se muestra una nueva lista desplegable Flujo de trabajo de generación de publicaciones que contiene todos los flujos de trabajo configurados en el flujo de trabajo de creación de flujos de trabajo de creación de flujos de trabajo de la. Debe seleccionar un flujo de trabajo que desee ejecutar después de completar el flujo de trabajo de generación de resultados.<br><br>**Nota**: para obtener más información sobre la creación de un flujo de trabajo de generación posterior a la salida personalizado, consulte _Personalizar flujo de trabajo de generación posterior a la salida_ en la guía as a Cloud Service Instalar y configurar las guías de Adobe Experience Manager. |

**Tema principal:**[ Explicación de los ajustes preestablecidos de salida](generate-output-understand-presets.md)
