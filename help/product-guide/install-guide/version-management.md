---
title: Administración de versiones
description: Descubra cómo funciona la administración de versiones
exl-id: 24e44618-9c4e-4547-a00d-216ef3fb4854
feature: Version Management
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1662'
ht-degree: 0%

---

# Administración de versiones {#id181GB000XY4}

El control de versiones es un aspecto importante de cualquier sistema de gestión de contenido. Permite crear una instantánea del recurso digital en un momento específico. Con una versión de un recurso digital configurada, puede restaurar la versión requerida del recurso y actualizarla. Normalmente, para crear una versión de cualquier recurso, desprotegería y protegería el recurso requerido.

Como administrador, puede aplicar reglas que restrinjan a los usuarios la edición de un archivo sin desprotegerlo. Del mismo modo, puede asegurarse de que todos los archivos desprotegidos vuelven a protegerse para evitar la pérdida de datos.

En un entorno multiuso, también es importante asegurarse de que los usuarios no eliminen archivos del sistema. Este requisito es más importante para los archivos desprotegidos por otros usuarios. Puede permitir o impedir que los usuarios sobrescriban los archivos desprotegidos por otros usuarios. AEM Para evitar que los usuarios eliminen accidentalmente del sistema los archivos desprotegidos, Guías de usuario proporciona una configuración que puede utilizar. Además de los archivos desprotegidos, también puede controlar la eliminación de archivos que contengan referencias o a los que se haga referencia desde otros archivos. Además, también puede crear una nueva versión para el archivo cargado.

## Crear nueva versión para el archivo cargado

>[!NOTE]
>
> Esta configuración solo es aplicable durante la carga de archivos.

Para crear una nueva versión del archivo cargado, realice los siguientes pasos:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en **com.adobe.fmdita.config.ConfigManager** paquete.

1. Seleccione el **Crear nueva versión para el archivo cargado** opción.

   Esta opción está desactivada de forma predeterminada.

   Cuando se selecciona la opción, se produce un nuevo mecanismo de administración de versiones que anula el comportamiento de carga predeterminado para cualquier carga posterior, y guarda el contenido del archivo cargado como una nueva versión. AEM AEM Si la opción no está seleccionada, las guías de usuario utilizan el mecanismo de administración de versiones por defecto de la aplicación de la.

1. Haga clic en **Guardar**.


>[!NOTE]
>
> Si activa la propiedad, puede cargar archivos en lotes de 70 o menos **Crear nueva versión para el archivo cargado** \(create.ver.new.content\) y utilice el **IU de Assets** para cargar recursos de forma masiva.

## Configurar opciones para permitir la edición de archivos desprotegidos

AEM El Editor Web de guías de la aplicación permite crear y actualizar temas de DITA. Puede configurar el Editor Web para permitir la edición únicamente de los documentos que se han extraído del repositorio. Esto garantiza que ningún otro escritor sobrescriba accidentalmente un tema abierto para su edición por otro escritor. Una vez abierto un tema para su edición, un autor puede proteger el archivo en el momento de cerrarlo.

Otra regla importante es garantizar que los archivos que se han desprotegido vuelvan a desprotegerse en el sistema. Esto evita que los usuarios cierren accidentalmente los archivos sin volver a protegerlos.

Siga estos pasos para habilitar estas funciones:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** paquete.

1. Seleccione el **Desactivar la edición sin cierre de compra** opción.

   ![](assets/xml-editor-config.png){width="650" align="left"}

   Con esta opción, los usuarios no verán la opción Editar en la barra de herramientas hasta que desprotejan un archivo.

1. Seleccione el **Solicitar el registro de entrada al cerrar** opción para mostrar un mensaje de advertencia cada vez que se cierra un archivo desprotegido sin guardarlo ni volver a registrarlo en el repositorio.

1. Haga clic en **Guardar**.


>[!NOTE]
>
> Independientemente de si activa o desactiva esta función, las opciones Desproteger y Proteger archivo siempre están disponibles en una vista previa del tema.

## Sobrescribir archivo retirado al cargar

>[!NOTE]
>
> Esta configuración solo es aplicable cuando se crean archivos desde la interfaz de usuario de Assets y no cuando se cargan archivos mediante la herramienta WebDAV.

Para permitir que los usuarios sobrescriban el archivo durante la carga que hayan desprotegido ellos u otros usuarios, realice los siguientes pasos:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en **com.adobe.fmdita.config.ConfigManager** paquete.

1. Seleccione el **Sobrescribir archivo retirado al cargar** opción.

   Esta opción está activada de forma predeterminada. Con esta opción seleccionada, los usuarios podrán sobrescribir los archivos desprotegidos. Si no se selecciona la opción, se impide que el archivo se sobrescriba si lo ha desprotegido él u otro usuario.

1. Haga clic en **Guardar**.


## Impedir la eliminación de archivos desprotegidos

Para evitar que los usuarios eliminen accidentalmente archivos que ellos u otros usuarios hayan desprotegido, realice los siguientes pasos:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** paquete.

1. Seleccione el **Impedir la eliminación del contenido extraído** opción.

   Esta opción está activada de forma predeterminada. Con esta opción seleccionada, los usuarios no podrán eliminar los archivos desprotegidos.

1. Haga clic en **Guardar**.


Para admitir esta función, se ha agregado una nueva propiedad de índice `drivelock` se añade en `oak:index`:

`/oak:index/damAssetLucene/indexRules/dam:Asset/properties/drivelock`

![](assets/index-property-oak-index-drivelock.png){width="800" align="left"}

Además de la nueva propiedad index, asegúrese de que las siguientes propiedades están configuradas en `/oak:index/damAssetLucene`:

- `jcr:primaryType`=`"oak:QueryIndexDefinition"`
- `async`=`"async"`
- `compatVersion`=`"{Long}2"`
- `evaluatePathRestrictions`=`"{Boolean}true"`
- `reindex`=`"{Boolean}false"`
- `reindexCount`=`"{Long}3"` *\(este es el recuento de cuántas veces se ha realizado la reindexación, se ha sustituido por la instalación del paquete\)*
- `type`=`"lucene"`

>[!NOTE]
>
> Puede cambiar el valor de `reindex` hasta `"{Boolean}true"`. Esto permitirá obtener resultados de búsqueda más rápidos para los archivos desprotegidos dentro de una jerarquía de carpetas.

## Impedir la eliminación de archivos referenciados

AEM Como administrador, puede controlar quién puede eliminar archivos del repositorio de la. Específicamente, si un archivo contiene referencias o si otro archivo hace referencia a él, puede definir quién puede eliminar dichos archivos.

Con esta configuración, puede permitir o impedir que todos los usuarios eliminen archivos, o permitir que solo un grupo de usuarios específico elimine archivos. Si se permite la eliminación de archivos, se sigue el siguiente proceso:

- Si está eliminando una carpeta, que contiene todos los archivos a los que se hace referencia y que hacen referencia, se eliminarán todos los archivos. El proceso eliminará primero todos los archivos que no contengan referencias, seguidos de los archivos que contienen referencias o a los que se hace referencia.

- Si está eliminando una carpeta y un archivo que no pertenece a ella hace referencia a cualquier archivo de la carpeta, se le pedirá que quite la referencia antes de eliminar el archivo.


Para definir quién puede eliminar un archivo que contenga referencias o al que otros archivos hagan referencia, realice los siguientes pasos:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en **com.adobe.fmdita.config.ConfigManager** paquete.

1. Busque el **Bloquear eliminación de recursos referenciados** opción.

1. En función de a quién desee conceder acceso para su eliminación, especifique una de las siguientes constantes:

   - allow\_unsafe\_delete\_for\_all: conceder permiso a todos los usuarios para eliminar archivos. En este caso, si el archivo\(s\) contiene(n) referencias o es referenciado(s) por otros archivos, también puede eliminar a la fuerza dicho archivo\(s\). Antes de eliminar el archivo, se le mostrará un mensaje con las referencias, puede cancelar la operación de eliminación, quitar las referencias y, finalmente, eliminar el archivo\(s\). O bien, puede eliminar a la fuerza el archivo sin eliminar las referencias.

     ![](assets/allow_unsafe_delete-force-delete.PNG){width="550" align="left"}

   - allow\_unsafe\_delete\_for\_delete\_assets\_group: un administrador o un usuario que pertenece a *delete-assets* El grupo puede eliminar archivos. Si algún otro usuario intenta eliminar archivos con referencias, no se le permitirá eliminar dichos archivos hasta que se eliminen todas las referencias. La siguiente captura de pantalla aparece cuando un usuario, que no tiene permisos de, intenta eliminar archivos.

     ![](assets/allow_unsafe_delete_for_delete_assets_group.PNG){width="550" align="left"}

   - block\_unsafe\_delete\_for\_all: Impedir que todos los usuarios \(incluidos los administradores\) eliminen archivos hasta que se eliminen las referencias al archivo y desde él.

1. Haga clic en **Guardar**.


## Depuración de versiones anteriores de archivos DITA

Al actualizar contenido y crear nuevas versiones, las versiones anteriores de los ficheros DITA se mantienen en el repositorio. Es posible que se creen muchas versiones para los archivos DITA durante un periodo y que, colectivamente, ocupen una gran cantidad de espacio en el repositorio. AEM Guías de le permite configurar las versiones anteriores que deben eliminarse del repositorio.

Puede acceder a esta utilidad mediante la URL determinada si tiene derechos administrativos:

`<server folder path> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`

La versión de un fichero DITA que cumple cualquiera de los criterios dados se mantiene y no se depura:

- Es la primera versión de un archivo
- Se incluye en una línea de base
- Se incluye en cualquier flujo de trabajo de traducción o revisión
- Tiene una etiqueta aplicada
- Cumple los criterios de edad o número de versión definidos

Siga estos pasos para purgar las versiones anteriores:

1. Introduzca los siguientes detalles sobre los archivos que desea depurar:

   ![](assets/preview-purge-report.png){width="350" align="left"}

1. 
   - **Número de versiones que se conservarán de la última versión**: introduzca el número de versiones que deben conservarse y no depurarse. Por ejemplo, si se introduce 5, se conservan las últimas 5 versiones y las versiones anteriores a ellas pueden depurarse en caso de que se cumplan otras condiciones de depuración.
- **Conservar Versiones Creadas Dentro Del Periodo \(En Días\)**: introduzca la antigüedad máxima de una versión en días. Las versiones anteriores al número determinado de días pueden depurarse si se cumplen otras condiciones de depuración. Por ejemplo, si se introduce 100, todas las versiones creadas antes de 100 días cumplen los requisitos para ser depuradas en caso de que se cumplan otras condiciones de depuración.
- **Ruta**: seleccione la ruta del archivo o la carpeta cuyos archivos desea purgar.

  >[!NOTE]
  >
  > Sólo se pueden depurar ficheros DITA.

1. Clic **Previsualizar informe de purga**.

   >[!NOTE]
   >
   > Solo puede haber una tarea de depuración a la vez. No puede iniciar otra operación de depuración de versiones si hay una en proceso.

   Se genera el informe de depuración de versiones.

1. Descargue el informe de purga de versiones y compruebe los archivos y las versiones que se purgarán.
1. Puede elegir entre **Cancelar purga** o **Iniciar purga**.

   ![](assets/download-purge-report.png){width="350" align="left"}

   Se muestra el estado de depuración.

   Clic **Descargar informe de purga de versiones** para ver las versiones depuradas. Este informe proporciona el estado de depuración de todas las versiones, junto con los motivos por los que se retuvo una versión en particular o por los que se depuró.


>[!NOTE]
>
> El informe se descarga en la siguiente ubicación: /var/dxml/versionpurge
