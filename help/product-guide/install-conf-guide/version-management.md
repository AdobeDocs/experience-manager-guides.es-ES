---
title: Administración de versiones
description: Obtenga información sobre cómo administrar versiones
feature: Version Management
role: Admin
level: Experienced
source-git-commit: b416334318a83e882c32318bc4769d24268cdd1c
workflow-type: tm+mt
source-wordcount: '2293'
ht-degree: 0%

---

# Administración de versiones {#id181GB000XY4}

El control de versiones es un aspecto importante de cualquier sistema de gestión de contenido. Permite crear una instantánea del recurso digital en un momento específico. Con una versión de un recurso digital configurada, puede restaurar la versión requerida del recurso y actualizarla. Normalmente, para crear una versión de cualquier recurso, desprotegería y protegería el recurso requerido.

Como administrador, puede aplicar reglas que restrinjan a los usuarios la edición de un archivo sin desprotegerlo. Del mismo modo, puede asegurarse de que todos los archivos desprotegidos vuelven a protegerse para evitar la pérdida de datos.

En un entorno multiuso, también es importante asegurarse de que los usuarios no eliminen archivos del sistema. Este requisito es más crítico para los archivos desprotegidos por otros usuarios. Para evitar que los usuarios eliminen accidentalmente archivos desprotegidos del sistema, AEM Guides proporciona una configuración que puede utilizar. Además de los archivos desprotegidos, también puede controlar la eliminación de archivos que contengan referencias o a los que se haga referencia desde otros archivos.

## Crear nueva versión para el archivo cargado

>[!NOTE]
>
> Esta configuración solo es aplicable durante la carga de archivos.

Las siguientes pestañas proporcionan instrucciones para habilitar la opción **Crear nueva versión para el archivo cargado** según la configuración de Experience Manager Guides: Cloud Service o Local.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración.
1. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar la opción **Crear nueva versión para el archivo cargado**:


   | PID | Clave de propiedad | Valor de propiedad |
   |---|------------|--------------|
   | `com.adobe.fmdita.confi g.ConfigManager` | `create.ver.new.content` | Booleano \(true/false\).<br> **Valor predeterminado**: `true` |

>[!NOTE]
>
> Cuando se selecciona la opción, se produce un nuevo mecanismo de administración de versiones que anula el comportamiento de carga predeterminado que se aplica a cualquier carga posterior, se guarda el contenido del archivo cargado como una nueva versión. Si la opción no está seleccionada, AEM Guides utiliza el mecanismo de administración de versiones predeterminado de AEM.

>[!TAB Local]

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.config.ConfigManager**.

1. Seleccione la opción **Crear nueva versión para el archivo cargado**.

   Esta opción está desactivada de forma predeterminada.

   Cuando se selecciona la opción, se produce un nuevo mecanismo de administración de versiones que anula el comportamiento de carga predeterminado para cualquier carga posterior, y guarda el contenido del archivo cargado como una nueva versión. Si la opción no está seleccionada, AEM Guides utiliza el mecanismo de administración de versiones predeterminado de AEM.

1. Haga clic en **Guardar**.


>[!NOTE]
>
> Puede cargar archivos en lotes de 70 o menos si habilita la propiedad **Crear nueva versión para el archivo cargado** \(create.ver.new.content\) y usa la **interfaz de usuario de Assets** para cargar recursos de forma masiva.

>[!ENDTABS]


## Configurar opciones para permitir la edición de archivos desprotegidos

AEM Guides Web Editor permite crear y actualizar temas DITA. Puede configurar el Editor Web para permitir la edición únicamente de los documentos que se han extraído del repositorio. Esto garantiza que ningún otro escritor sobrescriba accidentalmente un tema abierto para su edición por otro escritor. Una vez abierto un tema para su edición, un autor puede proteger el archivo en el momento de cerrarlo.

Otra regla importante es garantizar que los archivos que se han desprotegido vuelvan a desprotegerse en el sistema. Esto evita que los usuarios cierren accidentalmente los archivos sin volver a protegerlos.

Las siguientes pestañas proporcionan instrucciones para configurar los ajustes que permiten editar los archivos desprotegidos en función de la configuración de Experience Manager Guides: Cloud Service o Local.

>[!BEGINTABS]

>[!TAB Cloud Service]

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar la edición de los archivos desprotegidos:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.autocheckout` | Booleano \(true/false\).<br> **Valor predeterminado**: `false` |

Además, también puede configurar para que se muestre un mensaje de advertencia cada vez que se cierre un archivo desprotegido sin guardarlo ni volver a registrarlo en el repositorio.

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.checkin` | Booleano \(true/false\).<br> **Valor predeterminado**: `false` |

>[!NOTE]
>
> Independientemente de si activa o desactiva esta función, las opciones Desproteger y Proteger archivo siempre están disponibles en una vista previa del tema.

>[!TAB Local]

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Seleccione la opción **Deshabilitar edición sin desprotección**.

   ![](assets/xml-editor-config.png){width="650" align="left"}

   Con esta opción, los usuarios no verán la opción Editar en la barra de herramientas hasta que desprotejan un archivo.

1. Seleccione la opción **Pedir protección al cerrar** para mostrar un mensaje de advertencia cada vez que se cierre un archivo desprotegido sin guardarlo ni volver a protegerlo en el repositorio.

1. Haga clic en **Guardar**.

>[!NOTE]
>
> Independientemente de si activa o desactiva esta función, las opciones Desproteger y Proteger archivo siempre están disponibles en una vista previa del tema.

>[!ENDTABS]

## Sobrescribir archivo retirado al cargar

>[!NOTE]
>
> *Esta configuración solo es aplicable cuando crea archivos desde la interfaz de usuario de Assets y no cuando carga archivos mediante la herramienta WebDAV.*

Las siguientes pestañas proporcionan instrucciones para permitir a los usuarios sobrescribir el archivo en la carga que han desprotegido ellos o algún otro usuario según la configuración de Experience Manager Guides: Cloud Service o local.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración.
1. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar la opción **Sobrescribir archivo desprotegido al cargar**:


| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `overwrite.checkout.onupload` | Booleano \(true/false\).<br> **Valor predeterminado**: `false` |

>[!NOTE]
>
> Esta opción está desactivada de forma predeterminada. Con esta opción seleccionada, los usuarios podrán sobrescribir los archivos desprotegidos. Si no se selecciona la opción, se impide que el archivo se sobrescriba si lo ha desprotegido él u otro usuario.

>[!TAB Local]

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.config.ConfigManager**.

1. Seleccione la opción **Sobrescribir archivo desprotegido al cargar**.

   Esta opción está activada de forma predeterminada. Con esta opción seleccionada, los usuarios podrán sobrescribir los archivos desprotegidos. Si no se selecciona la opción, se impide que el archivo se sobrescriba si lo ha desprotegido él u otro usuario.

1. Haga clic en **Guardar**.

>[!ENDTABS]


## Impedir la eliminación de archivos desprotegidos

Las siguientes pestañas proporcionan instrucciones para evitar que los usuarios eliminen accidentalmente archivos que hayan desprotegido ellos o algún otro usuario según la configuración de Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(propiedad\) para evitar que los usuarios eliminen accidentalmente archivos que se han desprotegido:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.preventcheckedoutcontentdeletion` | Booleano \(true/false\). <br> **Valor predeterminado**: `true` |

>[!TAB Local]

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Seleccione la opción **Impedir la eliminación del contenido desprotegido**.

   Esta opción está activada de forma predeterminada. Con esta opción seleccionada, los usuarios no podrán eliminar los archivos desprotegidos.

1. Haga clic en **Guardar**.


Para admitir esta característica, se agrega una nueva propiedad de índice `drivelock` en `oak:index`:

`/oak:index/damAssetLucene/indexRules/dam:Asset/properties/drivelock`

![](assets/index-property-oak-index-drivelock.png){width="800" align="left"}

Además de la nueva propiedad index, asegúrese de que las siguientes propiedades están establecidas en `/oak:index/damAssetLucene`:

- `jcr:primaryType`=`"oak:QueryIndexDefinition"`
- `async`=`"async"`
- `compatVersion`=`"{Long}2"`
- `evaluatePathRestrictions`=`"{Boolean}true"`
- `reindex`=`"{Boolean}false"`
- `reindexCount`=`"{Long}3"` *\(este es el recuento de cuántas veces se ha realizado la reindexación, se ha reemplazado por la instalación de nuestro paquete\)*
- `type`=`"lucene"`

>[!NOTE]
>
> Puede cambiar el valor de `reindex` a `"{Boolean}true"`. Esto permitirá obtener resultados de búsqueda más rápidos para los archivos desprotegidos dentro de una jerarquía de carpetas.

>[!ENDTABS]

## Impedir la eliminación de archivos referenciados

Como administrador, puede controlar quién puede eliminar archivos del repositorio de AEM. Específicamente, si un archivo contiene referencias o si otro archivo hace referencia a él, puede definir quién puede eliminar dichos archivos.

Con esta configuración, puede permitir o impedir que todos los usuarios eliminen archivos, o permitir que solo un grupo de usuarios específico elimine archivos. Si se permite la eliminación de archivos, se sigue el siguiente proceso:

- Si está eliminando una carpeta, que contiene todos los archivos a los que se hace referencia y que hacen referencia, se eliminarán todos los archivos. El proceso eliminará primero todos los archivos que no contengan referencias, seguidos de los archivos que contienen referencias o a los que se hace referencia.

- Si está eliminando una carpeta y un archivo que no pertenece a ella hace referencia a cualquier archivo de la carpeta, se le pedirá que quite la referencia antes de eliminar el archivo.

Las siguientes pestañas proporcionan instrucciones para definir quién puede eliminar un archivo que contiene referencias o al que hacen referencia otros archivos en función de la configuración de Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para definir quién puede eliminar un archivo que contenga referencias o al que hagan referencia otros archivos:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `block.unsafe.delete` | Valores posibles: <br> - allow\_unsafe\_delete\_for\_all <br> -   allow\_unsafe\_delete\_for\_delete\_assets\_group <br> - block\_unsafe\_delete\_for\_all <br> **Valor predeterminado**: `allow_unsafe_delete_for_delete_assets_group` <br> A continuación se proporcionan los detalles de estas constantes. |

En función de a quién desee conceder acceso para su eliminación, especifique una de las siguientes constantes:

- allow\_unsafe\_delete\_for\_all: conceder permiso a todos los usuarios para eliminar archivos. En este caso, si el archivo\(s\) contiene(n) referencias o es referenciado(s) por otros archivos, también puede eliminar a la fuerza dicho archivo\(s\). Antes de eliminar el archivo, se le mostrará un mensaje con las referencias, puede cancelar la operación de eliminación, quitar las referencias y, finalmente, eliminar el archivo\(s\). O bien, puede eliminar a la fuerza el archivo sin eliminar las referencias.

  ![](assets/allow_unsafe_delete-force-delete.PNG)

- allow\_unsafe\_delete\_for\_delete\_assets\_group: Un administrador o un usuario que pertenezca al grupo *delete-assets* tiene permiso para eliminar archivos. Si algún otro usuario intenta eliminar archivos con referencias, no se le permitirá eliminar dichos archivos hasta que se eliminen todas las referencias. La siguiente captura de pantalla aparece cuando un usuario, que no tiene permisos de, intenta eliminar archivos.

  ![](assets/allow_unsafe_delete_for_delete_assets_group.PNG)

- block\_unsafe\_delete\_for\_all: Impedir que todos los usuarios \(incluidos los administradores\) eliminen archivos hasta que se eliminen las referencias al archivo y desde él.

>[!TAB Local]

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.config.ConfigManager**.

1. Busque la opción **Bloquear eliminación para Assets de referencia**.

1. En función de a quién desee conceder acceso para su eliminación, especifique una de las siguientes constantes:

   - allow\_unsafe\_delete\_for\_all: conceder permiso a todos los usuarios para eliminar archivos. En este caso, si el archivo\(s\) contiene(n) referencias o es referenciado(s) por otros archivos, también puede eliminar a la fuerza dicho archivo\(s\). Antes de eliminar el archivo, se le mostrará un mensaje con las referencias, puede cancelar la operación de eliminación, quitar las referencias y, finalmente, eliminar el archivo\(s\). O bien, puede eliminar a la fuerza el archivo sin eliminar las referencias.

     ![](assets/allow_unsafe_delete-force-delete.PNG){width="550" align="left"}

   - allow\_unsafe\_delete\_for\_delete\_assets\_group: Un administrador o un usuario que pertenezca al grupo *delete-assets* tiene permiso para eliminar archivos. Si algún otro usuario intenta eliminar archivos con referencias, no se le permitirá eliminar dichos archivos hasta que se eliminen todas las referencias. La siguiente captura de pantalla aparece cuando un usuario, que no tiene permisos de, intenta eliminar archivos.

     ![](assets/allow_unsafe_delete_for_delete_assets_group.PNG){width="550" align="left"}

   - block\_unsafe\_delete\_for\_all: Impedir que todos los usuarios \(incluidos los administradores\) eliminen archivos hasta que se eliminen las referencias al archivo y desde él.

1. Haga clic en **Guardar**.

>[!ENDTABS]

## Depuración de versiones anteriores de archivos DITA

Al actualizar contenido y crear nuevas versiones, las versiones anteriores de los ficheros DITA se mantienen en el repositorio. Es posible que se creen muchas versiones para los archivos DITA durante un periodo y que, colectivamente, ocupen una gran cantidad de espacio en el repositorio. AEM Guides le permite configurar las versiones anteriores que deben eliminarse del repositorio.

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

   ![](assets/preview-purge-report.png)

1. 
   - **Número de versiones que se deben conservar de la última versión**: escriba el número de versiones que se deben conservar y no purgar. Por ejemplo, si se introduce 5, se conservan las últimas 5 versiones y las versiones anteriores a ellas pueden depurarse en caso de que se cumplan otras condiciones de depuración.
   - **Conservar versiones creadas dentro del intervalo de tiempo \(en días\)**: escriba la antigüedad máxima de una versión en días. Las versiones anteriores al número determinado de días pueden depurarse si se cumplen otras condiciones de depuración. Por ejemplo, si se introduce 100, todas las versiones creadas antes de 100 días cumplen los requisitos para ser depuradas en caso de que se cumplan otras condiciones de depuración.
   - **Ruta**: seleccione la ruta de acceso del archivo o carpeta cuyos archivos desea purgar.

     >[!NOTE]
     >
     > Sólo se pueden depurar ficheros DITA.

1. Haga clic en **Previsualizar informe de purga**.

   >[!NOTE]
   >
   > Solo puede haber una tarea de depuración a la vez. No puede iniciar otra operación de depuración de versiones si hay una en proceso.

   Se genera el informe de depuración de versiones.

1. Descargue el informe de purga de versiones y compruebe los archivos y las versiones que se purgarán.
1. Puede elegir **Cancelar purga** o **Iniciar purga**.

   ![](assets/download-purge-report.png)

   Se muestra el estado de depuración.

   Haga clic en **Descargar informe de purga de versiones** para ver las versiones purgadas. Este informe proporciona el estado de depuración de todas las versiones, junto con los motivos por los que se retuvo una versión en particular o por los que se depuró.


>[!NOTE]
>
> El informe se ha descargado en la siguiente ubicación: `/var/dxml/versionpurge`
