---
title: Notas de versión | Versión as a Cloud Service de las guías de Adobe Experience Manager, noviembre de 2022
description: Versión de noviembre de Adobe Experience Manager Guides as a Cloud Service
exl-id: 9f329ec1-dd74-47cc-8567-3fadd962584a
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1384'
ht-degree: 0%

---

# Versión de noviembre de Adobe Experience Manager Guides as a Cloud Service

## Actualización a la versión de noviembre

Actualice las guías de Adobe Experience Manager actuales as a Cloud Service (más adelante denominadas *AEM Guías de as a Cloud Service*) realizando los siguientes pasos:
1. Consulte el código Git de los Cloud Service y cambie a la rama configurada en la canalización de Cloud Service correspondiente al entorno que desea actualizar.
1. Actualizar `<dox.version>` propiedad en `/dox/dox.installer/pom.xml` de su código Git de Cloud Service a 2022.11.198.
1. Confirme los cambios y ejecute la canalización de Cloud Service AEM para actualizar a la versión de noviembre de las guías de los usuarios as a Cloud Service de la versión de noviembre de la versión de las guías de los usuarios de la aplicación de.

## AEM Pasos para indexar el contenido existente (solo si se encuentra en una versión anterior a la versión de septiembre de Guías de as a Cloud Service)

Realice los siguientes pasos para indexar el contenido existente y utilice el nuevo texto de búsqueda y reemplazo a nivel de mapa:

* Ejecute una solicitud de POST al servidor (con la autenticación correcta): `http://<server:port>/bin/guides/map-find/indexing`.
(Opcional: puede pasar rutas específicas de los mapas para indexarlas, de forma predeterminada se indexarán todas las asignaciones || Ejemplo : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Por ejemplo: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Una vez completado el trabajo, la solicitud de GET anterior responderá correctamente y mencionará si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.

## Matriz de compatibilidad

AEM En esta sección se muestra la matriz de compatibilidad para las aplicaciones de software compatibles con las guías de la aplicación de la versión de noviembre de 2022 as a Cloud Service por las Guías de.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| No compatible | Actualización 4 de 2020 y posterior |
| | |

AEM *La línea de base y las condiciones creadas en la versión de FMPS a partir de 2020.2 son compatibles con las versiones de FMPS.

### Conector de oxígeno

| AEM Versión de Guides as a Cloud de | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2022.11.0 | 2.7.13 | 2.7.13 | 2,3 | 2,3 |
|  |  |  |  |


## Nuevas funciones y mejoras

AEM En la versión de noviembre de, Guías as a Cloud Service proporciona mejoras y nuevas funciones:


### Eliminar archivos del panel del repositorio

Ahora puede eliminar fácilmente archivos (de uno en uno) de la **Opciones** menú del archivo seleccionado del panel repositorio.
<img src="assets/repository-delete-file.png" alt="Eliminar del repositorio" width="500">

Se muestra un mensaje de confirmación antes de eliminar el archivo. Si no se hace referencia al archivo desde ningún otro archivo, se elimina y se muestra un mensaje de éxito.

Si el archivo seleccionado está desprotegido, no podrá eliminarlo y aparecerá un mensaje de error. AEM Si el archivo seleccionado se agrega a una colección de favoritos o se hace referencia a él desde cualquier otro archivo, la guía comprueba la confirmación y le da la opción de eliminarlo a la fuerza. Si elimina un tema al que se hace referencia y ha abierto el archivo que contiene referencias para su edición, se mostrará el vínculo roto para el archivo al que se hace referencia.

**Nota**: también puede eliminar el archivo seleccionado utilizando la tecla Delete del teclado.


### Depuración de versiones seleccionadas de archivos

A medida que crea y mantiene el contenido, es posible que se creen muchas versiones para los archivos DITA en el repositorio. AEM Guías de permite depurar versiones anteriores de los archivos DITA del repositorio y liberar espacio en disco.

<img src="assets/preview-purge-report.png" alt="Previsualizar informe de depuración" width="500">


AEM Guías no elimina la primera versión del archivo o una versión que se incluye en una línea de base, ni tiene una etiqueta aplicada. La operación de purga ni siquiera elimina los archivos que se incluyen en una traducción o en un flujo de trabajo de revisión. Puede elegir el número de versiones que desea conservar y también decidir eliminar los archivos que sean anteriores al número de días definido.

Antes de iniciar la operación de depuración, puede obtener una vista previa del informe para ver las versiones que se van a purgar. A continuación, puede decidir iniciar o cancelar la operación de depuración.

<img src="assets/download-purge-report.png" alt="Informe de purga de PDownload" width="500">

Una vez finalizada la operación de depuración, puede comprobar el informe de depuración para ver los archivos depurados.

### Administrar ajustes preestablecidos de salida del perfil global y de carpeta

AEM Las guías de proporcionan la función para crear y administrar ajustes preestablecidos de salida para los Perfiles global y de carpeta. A continuación, puede utilizar fácilmente estos ajustes preestablecidos de salida para generar resultados para todas las asignaciones relacionadas con ese perfil global o de carpeta.

<img src="assets/add-global-output-preset.png" alt="Añadir perfil global" width="400">

**Nota** Solo los usuarios administrativos de nivel de carpeta pueden crear ajustes preestablecidos de Perfil global y de carpeta.

Estos ajustes preestablecidos globales aparecen en **Output** de todas las asignaciones relacionadas. Puede utilizarlas para generar la salida de todas las asignaciones relacionadas. Puede seleccionar el ajuste preestablecido como ajuste preestablecido por defecto del PDF para generar la salida del PDF. También puede **Editar**, **Cambiar nombre**, **Duplicar**, o **Eliminar** un ajuste preestablecido de salida existente del **Opciones** menú.

### Columna Etiqueta de versión añadida al panel de traducción

En el panel de traducción, también puede ver la columna Etiqueta de versión. Muestra la etiqueta de la versión seleccionada del archivo de origen. Esto puede ayudarle a seleccionar todos los archivos con una etiqueta específica y traducirlos de una sola vez.

<img src="assets/send-translation.png" alt="enviar para traducción" width="600">


### PDF nativo | PDF con barra de cambios que muestra la diferencia entre las versiones del documento

Ahora puede crear un PDF que muestre las diferencias de contenido entre dos versiones con la barra de cambios. Puede elegir comparar la versión actual con una línea base de la versión anterior o comparar entre las dos versiones de línea base seleccionadas.

<img src="assets/pdf-change-version.png" alt="spdf-change-version" width="600">

Aparecerá una barra de cambios en el PDF para indicar el contenido modificado, insertado o eliminado. También tiene las opciones para hacer lo siguiente:
* Mostrar el contenido insertado en color verde y subrayado
* Mostrar el contenido eliminado en color rojo y marcado con un tachado

### PDF nativo | Compatibilidad de variables con ruta de salida y nombre de archivo del PDF

Ahora también puede utilizar las siguientes variables integradas para definir la ruta de salida y el archivo del PDF. Puede utilizar una sola variable o una combinación de ellas para definir estas opciones:
* `${map_filename}`
* `${map_title}`
* `${preset_name}`
* `${language_code}`
* `${map_parentpath}` (Solo para la ruta de salida)
* `${path_after_langfolder}` (Solo para la ruta de salida)


### PDF nativo | Generación de una tabla de contenido para mapas DITA y reordenación de diseños de página

Ahora también se puede generar la tabla de contenido en mapas DITA utilizando un ajuste de PDF avanzado de la plantilla. Puede elegir habilitar o deshabilitar la visualización de los distintos diseños de página y también reordenar su posición.

## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

* PDF nativo | `conkeyref` no se resuelve en la salida del PDF generada. (10564)
* PDF nativo | Se producen problemas al acceder a los metadatos de un mapa en la salida del PDF. (10556)
* PDF nativo | Los estilos en línea se utilizan para generar etiquetas en lugar del nombre de clase.  (10498)
* El editor web carga la página en blanco de forma intermitente. (10678)
* La publicación del PDF falla si se crea un ajuste preestablecido mediante la duplicación de un ajuste preestablecido existente. (10584)
* **Ver registro** El botón no funciona cuando la generación del PDF falla en un ajuste preestablecido. (10576)
* Observe que dentro de una etiqueta para que es una conref no se muestra en la vista previa. (10559)
* Al pulsar Retroceso al final de un elemento de la lista, se elimina toda la lista. (10540)
* Al utilizar un PDF nativo, exporte el anidado `<indexterm>` no están anidadas en el índice. (10521)
* **Sangría automática** de la barra de herramientas no aparece en la vista Código fuente. (10448)
* El primer carácter de un elemento de lista se pierde mientras la lista se crea en el editor. (10447)
* Aparecen varias ventanas emergentes si se cambia y se guarda cualquier versión de recurso DITA en la ventana de edición de línea base. (10399)
* Error de aplicación al hacer clic en **Editar** después de seleccionar todos los ajustes preestablecidos de salida en el panel Generación rápida. (10388)
* Los metadatos personalizados para el tema DITA no se conservan cuando se realiza una acción de copiar y pegar desde la interfaz de usuario de Assets. (10367)
* El procesamiento posterior se bloquea para toda la carpeta de idioma cuyos recursos estén presentes en un proyecto de traducción activo. (10332)
* La pestaña Plantilla del Editor XML no es visible para los administradores de perfiles de carpeta. (10266)
* Los problemas de navegación se producen en el Editor Web después de la actualización 4.0. (10159)
* Los archivos del SVG no se muestran en el modo de vista previa. (10010)
* Si la pestaña Salida del editor contiene más ajustes preestablecidos, la sección de ajustes preestablecidos no se puede desplazar y no se muestran todos. (9787)
* **Editar** y **Anotar** las opciones de una imagen no funcionan correctamente en la vista de columna. (8758)
* El vínculo de igual a igual no se resuelve y aparece como texto normal en la salida generada. (7774)
