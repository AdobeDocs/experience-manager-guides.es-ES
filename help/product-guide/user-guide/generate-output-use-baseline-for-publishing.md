---
title: Trabajar con línea base
description: AEM Conocer el uso de las líneas de base en las guías de. Obtenga información sobre cómo crear, ver contenido, editar, duplicar, eliminar, añadir etiquetas y exportar líneas de base traducidas.
exl-id: 0554947f-3038-4fd2-8a62-ac0d4b858e94
feature: Publishing
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1960'
ht-degree: 0%

---

# Trabajar con línea base {#id1825FI0J0PF}

La función Línea de base le permite crear una versión de los temas y recursos que luego se puede utilizar para publicar o traducir. Por ejemplo, si el mapa DITA tiene `topicA` y `imageA`, puede crear una Línea base para utilizar la tercera versión de `topicA`, pero la cuarta versión de `ImageA`. Una vez preparada una Línea de base, puede publicar o traducir temas de distintas versiones con un solo clic.

La selección de una Línea base es opcional para los ajustes preestablecidos de salida y un mapa DITA puede tener más de una Línea base. Sin embargo, cada ajuste preestablecido de salida dentro de un mapa DITA sólo puede asociarse a una única Línea base. Si no se especifica ninguna Línea de base en el momento de la publicación, el resultado se publica con la última versión del contenido.

Del mismo modo, la selección de una Línea base para traducir contenido es opcional. Sin embargo, si decide traducir el contenido mediante una Línea de base, el contenido de la Línea de base también se guarda junto con las copias traducidas. A continuación, puede utilizar la línea de base traducida para realizar más operaciones, como compartirla con editores externos o archivarla. Para obtener más información sobre la exportación de una instantánea traducida, consulte [Exportar línea base traducida](#id196SE600GHS).

>[!TIP]
>
> Consulte la *Línea base* de la guía de prácticas recomendadas para prácticas recomendadas sobre el trabajo con líneas de base.

El administrador puede configurar la pestaña Línea base en el panel de asignaciones. Para obtener más información, consulte *Configuración de la ficha Línea base en el tablero de mandos de asignación DITA* de la Guía de instalación y configuración.

Para acceder a la función Línea base, realice los pasos siguientes:

1. En la interfaz de usuario de Assets, vaya al archivo de mapa DITA y haga clic en él.
1. Vaya a la **Líneas bases** pestaña.

En la pestaña Líneas bases, puede realizar las siguientes acciones:

- [Crear una línea base](#id195FI0I0MUQ)
- [Ver contenido de una línea base](#id195FI0I0TLN)
- [Editar, duplicar o eliminar líneas bases](#id195FI0I0YJL)
- [Agregar etiquetas a una línea de base](#id184KD0T305Z)

## Crear una línea base {#id195FI0I0MUQ}

Puede crear una Línea base con una versión específica de los temas y contenido referenciado disponible en una fecha y hora específicas, o con una etiqueta definida para una versión de los temas. Puede especificar individualmente las versiones de los temas seleccionados en una Línea base para que cada vez que aplique la Línea base en el flujo de trabajo de publicación o traducción, los temas seleccionados y sus versiones correspondientes se incluyan para la generación o traducción de resultados.

Realice los siguientes pasos para crear una línea base:

1. En la página Líneas Base, haga clic en **Crear**.
1. Introduzca un nombre para la Línea base en **Nombre de línea base**.
   ![crear una línea base](images/create-baseline.png){width="800" align="left"}
1. Entrada **Establecer la versión en función de**, seleccione una de las siguientes opciones:

   - **Etiqueta**: seleccione esta opción para elegir los temas según la etiqueta aplicada a ellos. Introduzca una etiqueta para filtrar la lista en función de la cadena introducida. En la lista filtrada, puede elegir una etiqueta para seleccionar temas y otros recursos que tengan la etiqueta especificada.

   Al seleccionar **Etiqueta**, también se le proporcionará una opción adicional para utilizar la versión más reciente de temas que no tengan aplicada la etiqueta especificada. Si no selecciona esta opción y hay algún tema o archivo multimedia que no tenga la etiqueta especificada en él, el proceso de creación de la línea base fallará. Para obtener más información sobre cómo añadir etiquetas, consulte [Uso de etiquetas](web-editor-use-label.md#).

   - **Versión el** &lt;*marca de tiempo*\>: selecciona la versión de los temas en la fecha y hora especificadas. AEM Tenga en cuenta que la hora que especifique aquí corresponde a la zona horaria del servidor de la. Si el servidor se encuentra en una zona horaria diferente, los temas se recogerán según la zona horaria del servidor y no según la zona horaria local.

   Una vez seleccionada una etiqueta o versión como en la fecha, todos los temas a los que se hace referencia y los archivos multimedia dentro del mapa se seleccionan según corresponda. Esta selección de temas no se muestra en la interfaz de usuario, pero se guarda en el servidor.

   >[!NOTE]
   >
   >Se recomienda no utilizar el **Examinar todos los temas** al crear una línea base.

1. Haga clic en **Guardar**.

## Ver contenido de una línea base {#id195FI0I0TLN}

Para ver el contenido de una instantánea existente, pulse en la ficha Líneas base y seleccione la versión de instantánea que desee en la lista. La página Líneas bases se divide en tres partes: fichero de mapa DITA, contenido o temas del mapa y contenido referenciado. Si el mapa contiene submapas, los temas a los que se hace referencia en el submapa también se muestran en la sección Contenido. A continuación se describen las distintas columnas de la página Línea Base:

- **Nombre**: muestra el mapa DITA, el título del tema o el nombre del recurso, como el nombre de archivo de una imagen.

- **Tipo**: enumera la clase o el tipo de recurso del mapa, como un mapa DITA, un tema DITA o un formato de imagen.

- **Versión**: enumera la versión del recurso disponible en la Línea base.

- **Fecha y hora de versión**: enumera la fecha y hora de creación del recurso para la versión seleccionada.

- **Última**: Indica si se utiliza la versión más reciente del recurso en la Línea base.

- **Mapa principal**: Si el archivo de mapa contiene submapas, esta columna contiene el nombre del mapa en el que se hace referencia a un tema.

- **Etiqueta**: enumera las etiquetas aplicadas a la versión del tema.

- **Referido por**: esta columna solo está disponible para el contenido referenciado. Indica el tema principal del recurso al que se hace referencia. Si se hace referencia a un recurso mediante varios temas, estos se separarán mediante comas.

## Editar, duplicar o eliminar líneas bases {#id195FI0I0YJL}

**Editar líneas base**

Realice los siguientes pasos para editar una línea base existente:

1. Seleccione la Línea base y haga clic en **Editar**.
1. Realice los cambios necesarios en la línea de base. Puede cambiar el nombre y la versión del tema o el contenido al que se hace referencia.
1. Si desea utilizar una versión diferente para uno o más temas, puede seleccionarlos manualmente. Clic **Examinar tema**, seleccione el tema para el que desea utilizar una versión diferente. En la lista desplegable Seleccionar una versión para el tema seleccionado, seleccione una versión del tema que desee utilizar en la línea de base y haga clic en **OK**.

   ![](images/baseline-select-version-drop-down.png){width="800" align="left"}

   La información sobre el tema y su versión seleccionada se almacenan en el servidor. Puede repetir este paso para cambiar la versión seleccionada de varios temas.

1. Para cargar todos los temas y archivos multimedia a los que se hace referencia desde el mapa DITA, pulse en **Examinar todos los temas** vínculo. El UUID de los temas y archivos multimedia también se muestra debajo del título del tema o del nombre del archivo \(media\).

   >[!NOTE]
   >
   > Si tiene un gran conjunto de archivos en el mapa DITA, con mapas y temas anidados, hacer clic en Examinar todos los temas podría tardar algún tiempo en cargar todos los archivos.

   El contenido del mapa se presenta en las tres secciones: el archivo de mapa, Contenido \(referencias de temas\) y Contenido de referencia \(temas anidados, mapas y otros recursos\). Una vez que tenga disponible todo el contenido al que se hace referencia, puede seleccionar individualmente la versión del tema que desee utilizar en la línea de base.

   El **Versión** La lista desplegable muestra las versiones disponibles de los temas o el contenido al que se hace referencia. Para el contenido al que se hace referencia, tiene la opción de elegir una versión automáticamente.

   Si elige **Seleccionar automáticamente** para el contenido referenciado, el sistema selecciona automáticamente la versión del contenido referenciado correspondiente a la versión del contenido en el que se hace referencia. Por ejemplo, supongamos que un tema A hace referencia a una imagen B. Cuando se creó la versión 1.5 del tema A, la versión de la imagen B era 1.2 en el repositorio. Ahora, cuando se crea una línea de base con la versión 1.5 del tema A con la imagen B configurada como **Seleccionar automáticamente**, el sistema seleccionará automáticamente la versión 1.2 de la imagen B.

   Si crea una línea base utilizando las etiquetas, **Seleccionar automáticamente** se aplica a la versión de todo el contenido referenciado.

   Si el contenido o los recursos a los que se hace referencia \(tema, submapas, imágenes o vídeos\) no tienen versiones \(como, contenido recién cargado\), al crear una línea de base se creará una versión para dichos archivos. Sin embargo, si se crean versiones de los archivos, no se creará ninguna versión incremental para esos archivos. Este comportamiento se controla mediante la configuración de creación automática de versiones, que está habilitada de forma predeterminada. Esto también es necesario para traducir contenido, donde el proceso de traducción espera que todos los archivos tengan una versión.

   >[!NOTE]
   >
   > Si desea especificar una versión diferente para un recurso en particular, puede hacerlo eligiendo la versión deseada de la **Versión** lista desplegable.
1. Haga clic en **Guardar**.

**Duplicar líneas base**

Seleccione la Línea base y haga clic en **Duplicar** para crear una copia de una instantánea existente. Especifique un nombre diferente para la línea base, elija el número de versión de los temas y del contenido referenciado y haga clic en **Guardar**.

**Quitar líneas base**

Seleccione la versión de las líneas base y haga clic en **Eliminar** para quitar una Línea base.

## Agregar etiquetas a una línea de base {#id184KD0T305Z}

Añadir etiquetas a cada tema puede llevar mucho tiempo. AEM Las guías de datos proporcionan un mecanismo de un solo clic que permite añadir etiquetas a varios temas y a contenido referenciado en un mapa DITA.

Realice los siguientes pasos para agregar una etiqueta a varios temas y contenido referenciado en un mapa DITA:

1. En la página Líneas bases, seleccione una línea base que contenga los temas y el contenido referenciado al que desea agregar una etiqueta.

   >[!NOTE]
   >
   > Asegúrese de que la línea de base no tenga la última versión de ningún tema o recurso. Una etiqueta solo se puede agregar a un tema o recurso con versiones.

1. Clic **Añadir etiquetas**.

   ![](images/add-label-baseline-uuid.png){width="800" align="left"}

1. En el **Agregar etiqueta** , especifique una etiqueta única para asociar con esta línea base.

   Si el administrador ha configurado etiquetas predefinidas, estas se muestran en una lista desplegable. Debe elegir una etiqueta de la lista.

1. Si desea aplicar la etiqueta a los temas a los que se hace referencia desde las subasignaciones, seleccione **Aplicar etiqueta a asignaciones secundarias y dependientes** opción.

   - Clic **Añadir**.
La etiqueta especificada se añade al mapa DITA y a los temas y contenido a los que se hace referencia.

     ![](images/label-added-baseline-uuid.png){width="650" align="left"}


## Exportar línea base traducida {#id196SE600GHS}

Puede utilizar Línea de base para traducir contenido. Por ejemplo, puede crear una Línea base para la versión 1.1 que esté lista para su traducción al francés. En la pestaña Traducción, debe utilizar Línea de base para filtrar el contenido y, a continuación, seleccionar la Línea de base para la versión 1.1 del contenido. El uso de Línea de base para traducir contenido facilita la administración del contenido.

Una vez traducido el contenido, puede exportar la línea de base traducida para archivarla o compartirla con diferentes equipos de su organización. Debe tener en cuenta los siguientes puntos antes de exportar una instantánea traducida:

- Exportar una línea de base solo es posible después de traducir el contenido de la línea de base. Si intenta exportar una línea de base para la que la traducción no se ha iniciado o no se ha completado, obtendrá un error.
- Solo puede transferir Línea base para una versión que ya está traducida. Por ejemplo, si ha creado una Línea base para la versión 1.1 del contenido y se traduce lo mismo, puede exportar esta línea base. Sin embargo, si ha creado una Línea base para la versión 1.2, que no está traducida, no puede exportar esta Línea base.
- Si ya se ha exportado una instantánea, se puede sobrescribir la instantánea existente seleccionando la opción *Sobrescribir línea base existente* opción al exportar.

Realice los siguientes pasos para exportar una línea base traducida:

1. Abra el mapa DITA que contiene la instantánea traducida.

1. En el **Traducción** , expanda la pestaña **Línea base** opción disponible en el carril izquierdo.

   ![](images/export-baseline.png){width="800" align="left"}

1. Seleccione el **Usar línea base** y seleccione la instantánea que desea exportar.

1. Clic **Exportar línea base**.

   Se muestra el estado de exportación. Si el proceso se realiza correctamente, aparecerá un mensaje en el que se indica el idioma para el que se exporta la Línea base. En caso de error, se muestra la causa del error.

   Si intenta exportar la instantánea que ya se ha exportado, también aparecerá el mensaje de error de creación de instantánea.

1. \(Opcional\) Para exportar una instantánea que ya se ha exportado, seleccione **Sobrescribir línea base existente** y luego haga clic en **Exportar línea base**.


**Tema principal:**[ Generación de salida](generate-output.md)
