---
title: Generar PDF
description: Obtenga información sobre cómo crear un ajuste preestablecido de PDF desde el editor web y el panel de mapas. Configure el ajuste preestablecido de salida del PDF AEM en las guías del.
exl-id: f12c91fd-3f95-478e-a9cd-68d037206ee8
feature: Publishing
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 1%

---

# PDF {#id205BE600HAH}

Puede crear el ajuste preestablecido de PDF de dos formas:

**Desde el editor web:** En el panel Repositorio, abra el fichero de mapa DITA en la vista Mapa y, a continuación, en la ficha Salida, seleccione el icono + para crear un ajuste preestablecido de salida y, a continuación, seleccione PDF en la lista desplegable Tipo del cuadro de diálogo Añadir ajuste preestablecido.

>[!NOTE]
>
> Puede elegir el método para generar el PDF mediante DITA-OT, PDF nativo o FMPS \(si el administrador del sistema lo ha configurado\).

En el editor web, las configuraciones se han organizado en las pestañas General y Avanzadas:

**General**

El **General** La pestaña contiene las siguientes configuraciones:

- Ruta de salida
- Argumentos de línea de comandos DITA-OT
- Nombre de transformación
- Nombre de archivo del PDF
- Aplicar condiciones con \(Si las condiciones están definidas para un mapa\)
- Utilizar Línea base \(Si se crea una línea base para un mapa\)
- Flujo de trabajo de generación posterior

**Avanzado**

La pestaña Advanced contiene las siguientes configuraciones:

- Activar control de versiones
- Limpiar archivos temporales DITA-OT

Para obtener más información, consulte [Configuración del PDF](#id231KIM004X1).

**Desde el panel de mapas**

Para abrir los ajustes preestablecidos de salida para el PDF, haga clic en un archivo de mapa DITA en la interfaz de usuario de Assets, haga clic en Ajustes preestablecidos de salida y, a continuación, haga clic en la opción PDF. En el tablero de mapas, haga clic en **Editar** en la parte superior para actualizar las distintas configuraciones y, a continuación, haga clic en **Guardar**.

**Configuración del PDF**

Las siguientes opciones están disponibles para la salida del PDF:

| Opciones del PDF | Descripción |
| --- | --- |
| Tipo de salida | El tipo de salida que desea generar. Para generar la salida del PDF, seleccione la opción PDF. |
| Nombre de la configuración | Asigne un nombre descriptivo a la configuración de salida del PDF que está creando. Por ejemplo, puede especificar _Salida de clientes internos_ o _salida de usuarios finales_. |
| Argumentos de línea de comandos DITA-OT | Especifique los argumentos adicionales que desea que DITA-OT procese durante la generación de resultados. Para obtener más información acerca de los argumentos de línea de comandos admitidos en DITA-OT, consulte [Documentación de DITA-OT](https://www.dita-ot.org/). |
| Aplicación de condiciones mediante | Seleccione una de las siguientes opciones:<br><br>* **Ninguno aplicado**: seleccione esta opción si no desea aplicar ninguna condición en la salida publicada.<br>* **Archivo DITAVal**: seleccione los archivos DITAVal para generar contenido personalizado. Puede seleccionar varios archivos DITAVal mediante el cuadro de diálogo de exploración o escribiendo la ruta del archivo. Utilice el icono en forma de cruz situado cerca del nombre del archivo para eliminarlo. Los archivos DITAVal se evalúan en el orden especificado, por lo que las condiciones especificadas en el primer archivo tienen prioridad sobre las condiciones coincidentes especificadas en archivos posteriores. Puede mantener el orden de los archivos añadiendo o eliminando archivos. Si el archivo DITAVal se mueve a otra ubicación o se elimina, no se elimina automáticamente del panel de asignaciones. Debe actualizar la ubicación en caso de que los archivos se muevan o eliminen. AEM Puede pasar el ratón sobre el nombre del archivo para ver la ruta en el repositorio de donde se almacena el archivo. Solo puede seleccionar archivos DITAVal y se muestra un error si ha seleccionado cualquier otro tipo de archivo. El FrameMaker Publishing Server no admite varios archivos DITAVAL.<br>* **Ajuste preestablecido de condición**: Seleccione un ajuste preestablecido de condición en la lista desplegable para aplicar una condición al publicar la salida. La opción está visible si se ha añadido una condición presente en la ficha Ajustes preestablecidos de condición de la consola de mapa DITA. Para obtener más información sobre los ajustes preestablecidos de condición, consulte [Usar ajustes preestablecidos de condición](generate-output-use-condition-presets.md#id1825FL004PN). |
| Generar PDF Utilizando | Seleccione DITA-OT para generar el PDF. |
| Ejecutar flujo de trabajo posterior a generación | AEM Al elegir esta opción, se muestra una nueva lista desplegable Flujo de trabajo de generación de publicaciones que contiene todos los flujos de trabajo configurados en el flujo de trabajo de creación de flujos de trabajo de creación de flujos de trabajo de la. Debe seleccionar un flujo de trabajo que desee ejecutar después de completar el flujo de trabajo de generación de resultados.<br><br>**Nota**: para obtener más información sobre la creación de un flujo de trabajo de generación posterior a la salida personalizado, consulte Personalizar flujo de trabajo de generación posterior a la salida en Instalar y configurar guías de Adobe Experience Manager as a Cloud Service. |
| Nombre de transformación | Especifique el tipo de salida que desea generar. Esto es necesario si desea generar resultados con su propio complemento personalizado, que está integrado en el complemento DITA-OT. Por ejemplo, si desea generar una salida XHTML, especifique `xhtml`. Para obtener una lista de las transformaciones disponibles en DITA-OT, consulte [Transformaciones DITA-OT (formatos de salida)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) en la Guía del usuario de OASIS DITA-OT. |
| Nombre de archivo | Especifique el nombre de archivo con el que desea guardar el PDF.<br><br>También puede utilizar variables al establecer el Nombre de archivo del PDF. Para obtener más información sobre el uso de variables, consulte [Utilice variables para establecer las opciones Ruta de destino, Nombre del sitio o Nombre de archivo](generate-output-use-variables.md#id18BUG70K05Z).<br><br>**Nota**: si no se proporciona un nombre de fichero, se utilizará el título del mapa DITA para generar el nombre de fichero final del PDF. Si el mapa no tiene título, se utilizará el nombre de fichero del mapa DITA para nombrar al PDF final. El nombre del archivo se sanea utilizando las reglas configuradas en el sistema para gestionar cualquier carácter no válido. |
| Ruta de destino | AEM La ruta dentro del repositorio de la en la que se almacena el PDF.<br><br>También puede utilizar variables al establecer la Ruta de destino. Para obtener más información sobre el uso de variables, consulte [Utilice variables para establecer las opciones Ruta de destino, Nombre del sitio o Nombre de archivo](generate-output-use-variables.md#id18BUG70K05Z). |
| Limpiar archivos temporales DITA-OT | Seleccione esta opción para limpiar los archivos temporales generados por DITA-OT. La ubicación donde DITA-OT almacena los archivos temporales se encuentra en el registro de generación de salida.<br><br>Si se producen errores al generar la salida mediante DITA-OT, se puede anular la selección de esta opción para conservar los ficheros temporales. A continuación, puede utilizar esos archivos para solucionar errores de generación de resultados. |
| Usar línea base | Si ha creado una Línea base para el mapa DITA seleccionado, seleccione esta opción para especificar la versión que desea publicar.<br><br>Consulte [Trabajar con línea base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obtener más información. |
| Propiedades | Seleccione las propiedades que desee procesar como metadatos. Estas propiedades se definen desde la página Propiedades del fichero de mapa DITA o de mapa de libros. Las propiedades que seleccione en la lista desplegable aparecerán en la **Propiedades** field. Seleccione el icono en forma de cruz situado junto a la propiedad para eliminarla. <br><br>Nota: También se pueden transferir los metadatos a la salida mediante la publicación DITA-OT. Para obtener más información, consulte [Pasar los metadatos a la salida utilizando DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Tema principal:**[ Explicación de los ajustes preestablecidos de salida](generate-output-understand-presets.md)
