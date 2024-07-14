---
title: Administración de versiones
description: Obtenga información sobre cómo administrar versiones
exl-id: f7638cb3-faca-4170-9a8c-f6362e174c18
feature: Version Management
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1502'
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

Para habilitar la opción **Crear nueva versión para el archivo cargado**, realice los siguientes pasos:

1. Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración.
1. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar la opción **Crear nueva versión para el archivo cargado**:


   | PID | Clave de propiedad | Valor de propiedad |
   |---|------------|--------------|
   | `com.adobe.fmdita.confi g.ConfigManager` | `create.ver.new.content` | Booleano \(true/false\).<br> **Valor predeterminado**: `true` |

>[!NOTE]
>
> Cuando se selecciona la opción, se produce un nuevo mecanismo de administración de versiones que anula el comportamiento de carga predeterminado que se aplica a cualquier carga posterior, se guarda el contenido del archivo cargado como una nueva versión. Si la opción no está seleccionada, AEM Guides AEM utiliza el mecanismo de administración de versiones predeterminado del.

## Configurar opciones para permitir la edición de archivos desprotegidos

AEM Guides Web Editor permite crear y actualizar temas DITA. Puede configurar el Editor Web para permitir la edición únicamente de los documentos que se han extraído del repositorio. Esto garantiza que ningún otro escritor sobrescriba accidentalmente un tema abierto para su edición por otro escritor. Una vez abierto un tema para su edición, un autor puede proteger el archivo en el momento de cerrarlo.

Otra regla importante es garantizar que los archivos que se han desprotegido vuelvan a desprotegerse en el sistema. Esto evita que los usuarios cierren accidentalmente los archivos sin volver a protegerlos.

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar la edición de los archivos desprotegidos:

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

## Sobrescribir archivo retirado al cargar

>[!NOTE]
>
> *Esta configuración solo es aplicable cuando crea archivos desde la interfaz de usuario de Assets y no cuando carga archivos mediante la herramienta WebDAV.*

Para permitir que los usuarios sobrescriban el archivo durante la carga que hayan desprotegido ellos u otros usuarios, realice los siguientes pasos:

1. Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración.
1. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar la opción **Sobrescribir archivo desprotegido al cargar**:


| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.confi g.ConfigManager` | `overwrite.checkout.onupload` | Booleano \(true/false\).<br> **Valor predeterminado**: `false` |

>[!NOTE]
>
> Esta opción está desactivada de forma predeterminada. Con esta opción seleccionada, los usuarios podrán sobrescribir los archivos desprotegidos. Si no se selecciona la opción, se impide que el archivo se sobrescriba si lo ha desprotegido él u otro usuario.

## Impedir la eliminación de archivos desprotegidos

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(propiedad\) para evitar que los usuarios eliminen accidentalmente archivos que se han desprotegido:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.preventcheckedoutcontentdeletion` | Booleano \(true/false\). <br> **Valor predeterminado**: `true` |

## Impedir la eliminación de archivos referenciados

AEM Como administrador, puede controlar quién puede eliminar archivos del repositorio de la. Específicamente, si un archivo contiene referencias o si otro archivo hace referencia a él, puede definir quién puede eliminar dichos archivos.

Con esta configuración, puede permitir o impedir que todos los usuarios eliminen archivos, o permitir que solo un grupo de usuarios específico elimine archivos. Si se permite la eliminación de archivos, se sigue el siguiente proceso:

- Si está eliminando una carpeta, que contiene todos los archivos a los que se hace referencia y que hacen referencia, se eliminarán todos los archivos. El proceso eliminará primero todos los archivos que no contengan referencias, seguidos de los archivos que contienen referencias o a los que se hace referencia.

- Si está eliminando una carpeta y un archivo que no pertenece a ella hace referencia a cualquier archivo de la carpeta, se le pedirá que quite la referencia antes de eliminar el archivo.


Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para definir quién puede eliminar un archivo que contenga referencias o al que hagan referencia otros archivos:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `block.unsafe.delete` | Valores posibles: <br> - allow\_unsafe\_delete\_for\_all <br> -   allow\_unsafe\_delete\_for\_delete\_assets\_group <br> - block\_unsafe\_delete\_for\_all <br> **Valor predeterminado**: `allow_unsafe_delete_for_delete_assets_group` <br> A continuación se proporcionan los detalles de estas constantes. |

En función de a quién desee conceder acceso para su eliminación, especifique una de las siguientes constantes:

- allow\_unsafe\_delete\_for\_all: conceder permiso a todos los usuarios para eliminar archivos. En este caso, si el archivo\(s\) contiene(n) referencias o es referenciado(s) por otros archivos, también puede eliminar a la fuerza dicho archivo\(s\). Antes de eliminar el archivo, se le mostrará un mensaje con las referencias, puede cancelar la operación de eliminación, quitar las referencias y, finalmente, eliminar el archivo\(s\). O bien, puede eliminar a la fuerza el archivo sin eliminar las referencias.

  ![](assets/allow_unsafe_delete-force-delete.PNG)

- allow\_unsafe\_delete\_for\_delete\_assets\_group: Un administrador o un usuario que pertenezca al grupo *delete-assets* tiene permiso para eliminar archivos. Si algún otro usuario intenta eliminar archivos con referencias, no se le permitirá eliminar dichos archivos hasta que se eliminen todas las referencias. La siguiente captura de pantalla aparece cuando un usuario, que no tiene permisos de, intenta eliminar archivos.

  ![](assets/allow_unsafe_delete_for_delete_assets_group.PNG)

- block\_unsafe\_delete\_for\_all: Impedir que todos los usuarios \(incluidos los administradores\) eliminen archivos hasta que se eliminen las referencias al archivo y desde él.


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
