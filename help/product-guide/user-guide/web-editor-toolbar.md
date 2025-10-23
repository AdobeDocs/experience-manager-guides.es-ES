---
title: Barra de herramientas en el editor
description: Conozca la Barra de herramientas en el Editor. Obtenga información acerca de la interfaz y las funciones de Editor en Adobe Experience Manager Guides.
feature: Authoring, Features of Web Editor
role: User
exl-id: 059ba78a-dbda-4276-bff2-847787ea41b1
source-git-commit: fd4612037581d1d554c9dc144b998ba8a2ab8ccf
workflow-type: tm+mt
source-wordcount: '5962'
ht-degree: 0%

---

# Barra de herramientas en el editor

La barra de herramientas aparece cuando se abre un tema o un mapa para editarlo en el Editor. Las funciones disponibles en la barra de herramientas son las siguientes:

- [Menú desplegable](#menu-dropdown)
- [Opciones de inserción de contenido](#content-insertion-options)
- [Información de la versión y botón Guardar como nueva versión](#version-information-and-save-as-new-version)
- [Bloquear/desbloquear](#lockunlock)

>[!NOTE]
>
> Las funciones enumeradas anteriormente solo se aplican a los archivos de tema. Al trabajar con un archivo de mapa, se muestran diferentes opciones en la barra de herramientas en función de la vista actual del editor de mapas. Obtenga información acerca de las opciones de la barra de herramientas del editor de mapas en el documento [Funciones del editor de mapas](./map-editor-advanced-map-editor.md).

## Menú desplegable

La lista desplegable Menú proporciona acceso a las acciones de edición, Buscar y reemplazar, Historial de versiones, Etiqueta de versión, Combinar, Crear tarea de revisión y Menú Mostrar (que incluye Rastrear cambios, Etiquetas, Espacio de no separación).

![Menú desplegable para la barra de herramientas del editor](images/editor-toolbar-menu-dropdown-new.png){width="350" align="left"}

La explicación detallada de estas funciones es la siguiente:

**Editando acciones**

Al editar un tema en el editor, accede a las distintas acciones de edición como **Cortar** o ***Ctrl***+***X*** , **Copiar** o ***Ctrl***+***C*** , **Deshacer** o ***Ctrl***+***Z*** , **Rehacer** o ***Ctrl***+***Y*** y **Eliminar** está presente en el menú desplegable.


**Buscar y reemplazar**

La característica **Buscar y reemplazar** está disponible en los modos de vista Autor y Source. Cuando está habilitada, la barra de texto Buscar y reemplazar aparece en la parte inferior del área de edición del tema. Puede usar las teclas de método abreviado **CTRL**+**F** para invocar la barra Buscar y reemplazar.

![](images/find-replace-bar.png){align="left"}

Con el icono de configuración \(![](images/settings-find-replace-icon.svg)\), puede alternar las opciones de búsqueda **Ignorar mayúsculas y minúsculas** y **Sólo palabras completas**. Para realizar la búsqueda sin distinción entre mayúsculas y minúsculas, active \(o seleccione\) la opción **Ignorar mayúsculas y minúsculas**. De lo contrario, si desea realizar la búsqueda que distingue entre mayúsculas y minúsculas, desactive \(o deseleccione\) la opción **Ignorar mayúsculas y minúsculas**. También puede elegir buscar una palabra entera.

La búsqueda es instantánea, lo que significa que a medida que escribe la frase o palabra de búsqueda en el campo **Buscar**, el término se busca y selecciona inmediatamente en el tema. Del mismo modo, para reemplazar un texto en el tema, escribe el término de búsqueda y su reemplazo en los campos respectivos y selecciona el botón **Reemplazar** o **Reemplazar todo**.

En la vista de Source, la característica **Buscar y reemplazar** es extremadamente útil para buscar un elemento o atributo específico. Por ejemplo, si desea reemplazar el valor del atributo `@product`, se puede realizar fácilmente desde la vista de Source. La vista Autor no permite buscar basándose en un atributo o elemento. Sin embargo, debe tener cuidado al usar la característica **Reemplazar todo**, ya que podría sobrescribir el código XML.

**Historial de versiones**

La característica **Historial de versiones** del Editor permite comprobar las versiones disponibles de los archivos DITA, compararlos y revertirlos a cualquier versión desde el propio Editor. Puede comparar el contenido y los metadatos de la versión actual (que también puede ser una copia de trabajo) con cualquier versión anterior del mismo archivo. También puede ver las etiquetas y los comentarios de las versiones comparadas.

>[!NOTE]
>
> Las opciones del Historial de versiones sólo aparecen si hay cambios realizados en la primera versión del tema o asignación.


<details>
    <summary> Pasos para acceder al historial de versiones </summary>


1. Abra un tema en el Editor.
1. Seleccione **Historial de versiones** del menú desplegable **Menú**.

   Aparece el cuadro de diálogo **Historial de versiones**.

   ![Cuadro de diálogo Historial de versiones](images/version-history-dialog-web-editor.png){width="550" align="left"}

   *Obtener una vista previa de los cambios en las distintas versiones de un tema.*

1. Elija una versión del tema con la que quiera comparar o revertir en la lista desplegable **Comparar con**.

   >[!NOTE]
   >
   > Si una versión tiene etiquetas aplicadas, también se muestran \(entre corchetes\) junto con el número de versión.

1. Habilite la opción **Ver etiquetas y comentarios** para ver las etiquetas y los comentarios aplicados a las versiones actuales y comparadas.
1. También puede ver la siguiente información en el cuadro de diálogo **Historial de versiones**:

   Pestaña **Vista previa**: el contenido recién agregado está en fuente verde y el contenido eliminado está en fuente roja.

   Pestaña **Metadatos**: los metadatos agregados recientemente están en fuente verde y los metadatos eliminados están en fuente roja.

   ![Diferencia de metadatos para las versiones ](images/metadata-version-diff.png){width="550" align="left"}

   *Comparar los metadatos de distintas versiones en el historial de versiones.*

   >[!NOTE]
   >
   > El administrador del sistema puede cambiar los metadatos que se mostrarán en la ficha Metadatos en **Configuración**. Para obtener más información, consulte la sección **Más acciones** de la [barra de fichas](./web-editor-tab-bar.md).

   También puede ver los detalles de usuario y hora de la versión actual y la comparada.

   Una vez que elija una versión de la lista desplegable, estará disponible la opción **Revertir a la versión seleccionada**. La ventana de vista previa muestra las diferencias entre la versión actual y la seleccionada del tema.

1. Seleccione **Revertir a la versión seleccionada** para revertir la copia de trabajo con la versión seleccionada del tema.

   Aparecerá el cuadro de diálogo Revertir versión.

   ![](images/version-history-revert-dialog-save-working-copy.png){width="550" align="left"}

1. \(*Opcional*\) Proporcione un motivo para revertir a una versión anterior. También puede crear una nueva versión de la copia de trabajo activa del tema.

1. Seleccione **Confirmar**.

   La copia de trabajo del archivo se revierte a la versión seleccionada. Si decide crear una nueva versión de la copia de trabajo activa, también se creará una nueva versión del fichero con todos los cambios de trabajo.

   Al volver a una versión anterior, se muestra una señal visual que indica que la versión en la que está trabajando no es la más reciente.

   ![](images/older-version-visual-cue.png){align="left"}

</details>


**Etiquetas de versión**

Las etiquetas ayudan a identificar la fase en la que un tema en particular se encuentra en el DLC \(Ciclo de vida de desarrollo de documentos\). Por ejemplo, cuando esté trabajando en un tema, puede establecer la etiqueta como &quot;Aprobado&quot;. Una vez que se publica un tema y se pone a disposición de los clientes, se le puede asignar la etiqueta &quot;Publicado&quot;.

Experience Manager Guides permite especificar etiquetas en formato de texto de forma libre o utilizar un conjunto de etiquetas predefinidas. La etiqueta personalizada permitiría a cualquier autor del sistema especificar una etiqueta según su elección. Esto proporciona flexibilidad; sin embargo, introduce etiquetas incoherentes en el sistema. Para resolver este problema, los administradores pueden configurar un conjunto de etiquetas predefinidas. Para obtener más información acerca de cómo configurar etiquetas predefinidas, vea *Configurar y personalizar el Editor Web XML* en Instalar y configurar Adobe Experience Manager Guides as a Cloud Service.

Estas etiquetas se muestran a los autores en forma de lista desplegable siempre que necesiten especificar una etiqueta. Esto garantiza que solo se utilicen etiquetas predefinidas y coherentes en el sistema.

Existen diferentes métodos para aplicar etiquetas a los temas: el panel [Historial de versiones](web-editor-use-label.md) en la interfaz de usuario de Assets, la interfaz de usuario de [Líneas bases](/help/product-guide/user-guide/generate-output-use-baseline-for-publishing.md) y el editor. La función Etiqueta de versión del Editor ofrece a los autores una forma rápida y sencilla de asignar etiquetas a sus temas.

<details>
    <summary> Pasos para agregar etiquetas al tema desde el Editor </summary>

1. Abra un tema en el Editor.

1. Seleccione **Etiquetas de versión** en el menú desplegable.

   Aparece el cuadro de diálogo Administración de etiquetas de versión.

   ![](images/version-label-management-dialog.png){width="350" align="left"}

   El cuadro de diálogo Administración de etiquetas de versión se divide en dos partes: el panel izquierdo tiene una lista de versiones disponibles para el tema junto con la lista desplegable de etiquetas \(o un cuadro de texto para introducir una etiqueta\) y el panel derecho con una vista previa del tema.

1. Seleccione la versión a la que desee aplicar las etiquetas.

   Cuando elige una versión diferente del tema en la lista de versiones, el panel de vista previa muestra los cambios entre la versión actual y la seleccionada del tema

   >[!NOTE]
   >
   > Si ya se ha aplicado una etiqueta a una versión, esta se muestra junto al número de versión en la lista desplegable y debajo de la lista Seleccionar versión. Para quitar una etiqueta existente, seleccione el icono \(**x**\) que hay junto a la etiqueta.

1. Si el administrador ha definido una lista de etiquetas, se le mostrará una lista desplegable de las etiquetas desde la que puede elegir las etiquetas que desea aplicar. Puede seleccionar varias etiquetas en la lista desplegable.

   De lo contrario, se muestra un cuadro de texto, en el que puede introducir las etiquetas que desee agregar al tema.

   >[!NOTE]
   >
   > No se puede aplicar la misma etiqueta en varias versiones de un tema. Si intenta asociar una etiqueta existente, se le proporcionará una opción para eliminarla de la versión existente y aplicarla en la versión seleccionada del tema.

1. Seleccione **Agregar etiqueta**.

1. En el mensaje de confirmación Aplicar etiqueta, seleccione la opción **Mover etiqueta(si se usa en otra versión)** para mover las etiquetas de una versión existente a la versión seleccionada. Si no selecciona esta opción y hay etiquetas asignadas a una versión diferente del tema, no se mueven a la versión del tema seleccionado. Estas etiquetas se omiten en el proceso de aplicación de etiquetas.

</details>

**Combinar**

Cuando se trabaja en un entorno de varios autores, resulta difícil realizar el seguimiento de los cambios realizados por los demás autores en un tema o mapa. La función Combinar le proporciona más control no sólo sobre la visualización de los cambios, sino también sobre los cambios que se conservan en la última versión del documento.

<details>
    <summary> Combinar archivos de tema </summary>

Para combinar los cambios de un tema, realice los siguientes pasos:

1. Abra un tema en el Editor.

1. Seleccione **Combinar**.

   Aparecerá el cuadro de diálogo Combinar.

   ![](images/merge-changes-in-topic.png){width="550" align="left"}

1. *\(Opcional\)* También puede examinar y seleccionar un nuevo archivo de otra ubicación del repositorio.

1. Seleccione la versión del archivo con la que desea comparar la versión actual del archivo.

1. En Opciones, elija:

   - **Rastrear cambios de la versión seleccionada**: esta opción muestra todas las actualizaciones de contenido en forma de cambios rastreados. A continuación, puede elegir aceptar o rechazar los cambios del documento de uno en uno o todos en una sola vez.

   - **Revertir a la versión seleccionada**: esta opción revierte la versión actual del documento a la versión seleccionada. Esta opción no le proporciona ningún control sobre qué contenido se acepta o rechaza.

1. Seleccione **Listo**.

1. Si seleccionó la opción **Rastrear cambios de la versión seleccionada**, todos los cambios de la versión seleccionada se mostrarán en la característica Rastreo de cambios del panel derecho.

   Puede elegir aceptar o rechazar todos los comentarios del panel Cambios realizados o aceptar o rechazar comentarios individuales.
</details>

<details>
    <summary> Combinación de archivos de asignación </summary>

Para combinar los cambios en un archivo de asignación, realice los siguientes pasos:

1. Abra un mapa en el Editor.

1. Seleccione **Combinar**.

   Aparecerá el cuadro de diálogo Combinar.

   ![](images/merge-changes-in-map.png){width="550" align="left"}

1. *\(Opcional\)* También puede examinar y seleccionar un nuevo archivo de otra ubicación del repositorio.

1. Seleccione la versión del archivo con la que desea comparar la versión actual del archivo.

1. En Opciones, elija:

   - **Rastrear cambios de la versión seleccionada**: esta opción muestra todas las actualizaciones de contenido en forma de cambios de seguimiento. A continuación, puede elegir aceptar o rechazar los cambios del documento de uno en uno o todos en una sola vez.

   - **Revertir a la versión seleccionada**: esta opción revierte la versión actual del documento a la versión seleccionada. Esta opción no le proporciona ningún control sobre qué contenido se acepta o rechaza.

1. Seleccione **Listo**.

1. Si seleccionó la opción **Rastrear cambios de la versión seleccionada**, todos los cambios de la versión seleccionada se mostrarán en el panel Cambios rastreados \(a la derecha\).

   Puede elegir entre aceptar o rechazar todos los cambios del panel Cambios realizados o aceptar o rechazar cambios individuales en el archivo de asignación.

</details>

**Crear tarea de revisión**

Puede [crear una tarea de revisión](./review-send-topics-for-review.md) del tema o archivo de asignación actual directamente desde el Editor. Abra el archivo para el que desea crear la tarea de revisión y seleccione **Crear tarea de revisión** del menú desplegable para iniciar el proceso de creación de la revisión.

**Mostrar menú**

El menú Mostrar consta de las siguientes funciones:

- **Control de cambios:** Para realizar un seguimiento de todas las actualizaciones realizadas en un documento, habilite el modo Control de cambios. Después de habilitar el seguimiento de cambios, todas las inserciones y eliminaciones se capturan en el documento. Todo el contenido eliminado se resalta con Tachado y todas las inserciones se resaltan en texto de color verde. Además, también se obtienen las barras de cambios en el borde de la página del tema. De nuevo, se muestra una barra roja para el contenido eliminado y una barra verde para el contenido añadido. En caso de que haya una adición y eliminación en la misma línea, se muestran las barras verde y roja.
La siguiente captura de pantalla resalta el contenido eliminado e insertado junto con las barras de cambio:
  ![](images/track-changes-content.png){width="650" align="left"}

  Un caso de uso típico del seguimiento de cambios en un documento puede ser para realizar una revisión por pares. Puede habilitar la función de seguimiento de cambios y compartir el documento para su revisión, y el revisor realizará los cambios con la función de seguimiento de cambios activada. Cuando reciba el documento, deberá disponer de un mecanismo para ver las actualizaciones sugeridas junto con una forma cómoda de aceptar o rechazar los cambios.

  Experience Manager Guides proporciona la característica Cambios realizados que contiene información sobre las actualizaciones realizadas en el documento. La función Cambios rastreados proporciona información sobre qué actualizaciones se realizaron, quién las hizo y a qué hora. Con la función Cambios realizados, también puede aceptar o rechazar fácilmente las actualizaciones sugeridas en el documento.

  Para acceder a la función, seleccione el icono **Rastrear cambios** en el panel derecho.

  ![](images/changes-panel_cs.png){width="300" align="left"}

  Al seleccionar un cambio controlado, se selecciona el contenido modificado en el documento. Puede aceptar un cambio seleccionando el icono Aceptar cambio o rechazarlo seleccionando el botón Rechazar cambio.

  Si desea aceptar o rechazar todos los cambios con un solo clic, seleccione **Aceptar todos los cambios** o **Rechazar todos los cambios**.

  >[!NOTE]
  >
  > El modo Vista previa permite ver el documento con o sin las marcas del contenido modificado. Para obtener más información, vea el modo [Vista previa](web-editor-views.md#preview-mode).

- **Etiquetas:** La característica **Etiquetas** del Editor es un botón de alternancia que controla la visibilidad de los elementos DITA. Cuando está activada, muestra etiquetas estructurales dentro del contenido, lo que permite ver y gestionar los elementos DITA subyacentes de forma más eficaz. Cuando está desactivado, el editor oculta estas etiquetas, lo que proporciona un entorno de creación más limpio y centrado.

  La siguiente captura de pantalla muestra un documento con la vista Etiquetas habilitada:

  ![](images/tags-view.png){width="650" align="left"}

  Las siguientes operaciones se pueden realizar en un documento con etiquetas:

   - **Seleccionar un elemento**: seleccione la etiqueta de apertura o cierre de un elemento para seleccionar su contenido.

   - **Expandir o contraer etiquetas**: seleccione el signo + o - en una etiqueta para expandirla o contraerla.

   - **Usar el menú contextual**: El menú contextual proporciona opciones para cortar, copiar o pegar el elemento seleccionado. También puede insertar un elemento antes o después del elemento seleccionado. Las demás opciones le permiten Generar ID o abrir el panel Propiedades del elemento seleccionado.

   - **Arrastrar y soltar elementos**: seleccione la etiqueta de un elemento y arrástrela y suéltela fácilmente en el documento. Si la ubicación de colocación es una ubicación válida donde el elemento está permitido, el elemento se coloca en la ubicación de colocación.


  >[!NOTE]
  >
  > Si un usuario habilita la vista Etiquetas desde el Editor, permanecerá habilitada incluso en todas las sesiones. Esto significa que no es necesario volver a habilitar la vista Etiquetas para acceder a ella más adelante. El valor predeterminado de la vista Etiquetas para la sesión de un nuevo usuario está determinado por la propiedad `tagsView` del archivo `ui\_config.json`. Para obtener más información, vea la sección [Configurar el valor predeterminado de la vista de etiquetas](../cs-install-guide/configure-default-value-tags-view.md) en Instalar y configurar Adobe Experience Manager Guides as a Cloud Service.

- **Espacio de no separación:** Active esta opción para mostrar un indicador de los espacios de no separación al editarlo en el Editor. Solo está visible en la vista **Autor** para el tema DITA y los mapas DITA.

## Opciones de inserción de contenido

**Elemento** - ![](images/Add_icon.svg)

Inserta un elemento válido en la ubicación válida actual o siguiente. También puede usar el método abreviado de teclado ***Alt***+***Enter*** para abrir el cuadro de diálogo Elemento. Por ejemplo, si está editando un párrafo, en el cuadro de diálogo **Elemento** aparecerá una lista de elementos que se pueden insertar en el párrafo. Seleccione el elemento que desea insertar. Puede usar el teclado para desplazarse por la lista de elementos y presionar ***Intro*** para insertar el elemento requerido.

Puede ver dos tipos de elementos válidos:

- **Elementos válidos en la ubicación actual**: La lista muestra los elementos que puede insertar en la propia ubicación del cursor actual.

- **Elementos válidos fuera de la ubicación actual**: La lista muestra los elementos que puede insertar después de cualquiera de los elementos primarios del elemento actual dentro de la jerarquía de elementos.

Por ejemplo, si se encuentra dentro del elemento `<b>` en línea, puede insertar elementos como `<u>`, `<xref>`, `<i>` en la ubicación actual. Por el contrario, puede insertar elementos como `<table>` y `<topic>` fuera de la ubicación actual.

También puede escribir un carácter o cadena en el cuadro de búsqueda y buscar los elementos que comienzan con él.

![insertar elemento](images/insert-element.png){width="300" align="left"}

*Escriba &#39;t&#39; para buscar todos los elementos válidos que comiencen por &#39;t&#39;.*

Si está trabajando dentro de un elemento de bloque como `note`, utilice el icono Insertar elemento para insertar un nuevo elemento después del elemento `note`. En la siguiente captura de pantalla, se ha insertado un elemento de nota dentro del elemento p \(párrafo\):

![Insertar elemento en un elemento de bloque](images/note-in-para-insert-element_cs.png){align="left"}

Si pulsa Intro en el elemento de nota, se creará un nuevo párrafo dentro del propio elemento de nota. Para insertar un nuevo elemento fuera de la nota, seleccione el elemento p \(resaltado en la captura de pantalla\) en la ruta de exploración de elementos y, a continuación, seleccione el icono Elemento o pulse ***Alt***+***Entrar*** para abrir el cuadro de diálogo Insertar elemento. A continuación, seleccione el elemento deseado y pulse Intro para insertar el elemento seleccionado después del elemento de nota.

También puede añadir un elemento entre dos elementos cuando aparezca un cursor de bloque parpadeante.


![](images/Block-cursor.png){width="300" align="left"}

Por ejemplo, si está trabajando en un tema DITA y el cursor de bloque parpadea entre la descripción breve y el cuerpo, puede agregar el elemento `prolog` y, a continuación, agregar copyright, autor y otros detalles.

Otra forma de introducir un nuevo elemento es mediante el menú contextual. Haga clic con el botón derecho en cualquier lugar del documento para invocar el menú contextual. En este menú, elija **Insertar elemento** para mostrar el cuadro de diálogo **Insertar elemento** y elija el elemento que desea insertar.

![](images/insert-element-before-after.png){width="300" align="left"}

**Párrafo** - ![](images/Paragraph_icon.svg)

Insertar elemento de párrafo en la ubicación válida actual o siguiente.

**Lista con viñetas** - ![](images/BulletList_icon.svg)

Crea una lista con viñetas en la ubicación válida actual o siguiente. Si está en una lista con viñetas y selecciona este icono, el elemento se convierte en un párrafo normal.

**Lista numerada** - ![](images/TextNumbered_icon.svg)

Crea una lista numerada en la ubicación válida actual o siguiente. Si está en una lista numerada y selecciona este icono, el elemento se convierte en un párrafo normal.

>[!NOTE]
>
>También puede seleccionar la opción **Split list** en el menú contextual de un elemento de lista para dividir la lista actual y comenzar una nueva lista en el mismo nivel.

**Tabla** - ![](images/Table_icon.svg)

Inserta una tabla en la ubicación válida actual o siguiente. Seleccione el icono Tabla para abrir el cuadro de diálogo Insertar tabla simple.

![](images/table-properties.png){width="550" align="left"}

>[!NOTE]
>
> También puede copiar una tabla de MS Word o Excel y pegarla en el archivo de temas de Experience Manager Guides. La tabla copiada se pegará como `<simpletable>` o `<tgroup>` según la configuración del Editor XML. Para obtener más información, vea [Configurar la visualización de las tablas pegadas](../cs-install-guide/conf-pasted-tables.md).

Puede especificar el número de filas y columnas necesarias en la tabla. Si desea mantener la primera fila como encabezado de tabla, seleccione la opción **Establecer la primera fila como encabezado**. Para añadir un título a la tabla, introdúzcalo en el campo Título.

Una vez insertada una tabla, puede modificarla mediante el menú contextual.

![](images/table-context-menu_cs.png){width="550" align="left"}



Mediante el menú contextual de la tabla, puede:

- Insertar celdas, filas o columnas

- Combinar celdas en las direcciones derecha y abajo

- Dividir celdas horizontal o verticalmente

- Eliminar celdas, filas o columnas

- Generación de ID

<details>
    <summary> Definir atributos en varias celdas, filas completas o columnas de una tabla </summary>

También puede definir atributos en varias celdas, filas completas o columnas de una tabla. Por ejemplo, para alinear la celda de la tabla, arrastre y seleccione la celda requerida. En el panel Propiedades de contenido (a la derecha), la propiedad **Type** cambia a **entry**.

1. En la sección **Atributos**, seleccione **+Agregar**.
1. Seleccione el atributo `@valign` de la lista desplegable **Atributo**.
1. En la lista desplegable de valores, seleccione la alineación de texto que desee aplicar en las celdas de la tabla seleccionada.
1. Seleccionar **Agregar.**

![](images/align-table-cell_cs.png){align="left"}

</details>

**Imagen** - ![](images/Image_icon.svg)

Inserta una imagen en la ubicación válida actual o siguiente. Seleccione el icono Imagen para abrir el cuadro de diálogo Insertar imagen y, a continuación, busque y seleccione la imagen que desee insertar.

>[!NOTE]
>
> También puede agregar una imagen arrastrándola y soltándola desde el sistema local en el artículo. En este caso, el archivo de imagen se agrega mediante el flujo de trabajo **Cargar Assets**.  Para obtener más información, vea el flujo de trabajo **Cargar Assets** en la sección [Panel izquierdo](./web-editor-left-panel.md).


![](images/insert-image-new-dialog.png){width="300" align="left"}

Puede agregar un título de imagen/figura y texto alternativo para la imagen en el cuadro de diálogo Insertar imagen.

>[!NOTE]
>
> Al insertar una imagen y especificar un texto alternativo para la misma, se agrega dentro del elemento `<alt>` de acuerdo con los estándares DITA más recientes. El uso del atributo `@alt` para texto alternativo está en desuso, pero sigue siendo compatible con versiones DITA anteriores.

Con la opción **Seleccionar archivo**, puede buscar el archivo de imagen requerido por nombre de archivo. También puede filtrar los resultados de búsqueda por Ruta \(para buscar\), Colecciones, Tipo de archivo y Etiquetas. Cuando encuentre el archivo de imagen necesario, selecciónelo y elija **Seleccionar** para insertar la imagen en el documento. Puede insertar varios formatos de archivos de imagen, como `.png`, `.svg`, `.gif`, `.jpg`, `.eps`, `.ai`, `.psd`, etc.

Una vez insertada una imagen, puede cambiar la altura, la anchura, la ubicación y los atributos en el panel Propiedades de contenido. Seleccione el archivo de imagen y, a continuación, realice cambios en el panel de propiedades Contenido del panel derecho.

![](images/image-properties.png){align="left"}

El campo Source muestra el UUID del archivo de imagen insertado. Puede encontrar la ruta completa del archivo de imagen insertado pasando el puntero del ratón sobre el campo Source. La ruta se muestra en la información del objeto.

Puede cambiar el tamaño de una imagen proporcionando el valor Altura o Anchura para el archivo de imagen. La proporción de aspecto de la imagen se mantiene automáticamente. Si lo desea, también puede optar por no mantener la proporción de aspecto del archivo de imagen seleccionando el icono de candado \(de Mantener proporción de aspecto\) y proporcionando los valores de Altura y Anchura.

También puede especificar la configuración Ubicación para la imagen como En línea o Salto. Si decide utilizar la opción Colocación de rotura, puede elegir dónde alinear la imagen (izquierda, centro o derecha).

También puede agregar otras propiedades para un archivo de imagen seleccionando las propiedades requeridas en el campo **Atributos**.

>[!NOTE]
>
>También puede definir las áreas \(mapa de imagen\) en las que puede hacer clic en la imagen. Para obtener más información, vea la descripción de la característica **Insertar/Editar mapa de imagen** en la sección [Panel izquierdo](web-editor-left-panel.md).

**Menú contextual para archivos de imágenes o multimedia**

También puede realizar algunas operaciones comunes para imágenes y archivos multimedia mediante el menú contextual. Haga clic con el botón derecho en cualquier lugar de la imagen para invocar el menú contextual.

El menú contextual proporciona opciones para cortar, copiar o pegar la imagen o el medio. Puede insertar un elemento antes o después del elemento seleccionado. También tiene la opción de cambiar el nombre o de anular el ajuste de un elemento. Puede localizar la imagen o el medio seleccionado en el repositorio o ver la vista previa del archivo en la interfaz de usuario de Assets.

Las demás opciones del menú contextual permiten copiar una ruta, editar un mapa de imagen, cambiar el nombre de un elemento, crear un fragmento o generar ID para el elemento seleccionado.

**Insertar/Editar mapa de imagen**

Inserta un mapa de imagen en la imagen seleccionada. Una imagen con áreas en las que se puede hacer clic y que vinculan temas o páginas web se denomina mapa de imagen.

Seleccione una imagen en el tema actual y seleccione el icono Insertar/Editar mapa de imagen para abrir el cuadro de diálogo Insertar mapa de imagen.

![](images/insert-image-map.png){width="650" align="left"}

Elija la forma preferida Rectángulo ![](images/imagemap-rectangle-toolbar.png), Círculo ![](images/imagemap-circle-toolbar.png) o Polígono ![](images/imagemap-polygon-toolbr.png) para definir un área sobre una imagen que desee utilizar como vínculo. Después de definir un área, aparece el cuadro de diálogo Referencia en el que debe especificar el vínculo al contenido interno o externo:

![](images/reference-dialog.png){width="650" align="left"}

Si las áreas se superponen, puede hacer que la forma avance o retroceda haciendo clic en el icono correspondiente de la barra de herramientas. También puede quitar un área seleccionándola y haciendo clic en el icono Eliminar. Al hacer doble clic en un área, se abre el cuadro de diálogo Referencia, en el que puede cambiar el vínculo de destino. Una vez que haya marcado las áreas requeridas en la imagen, guarde los cambios seleccionando **Listo**.


**Multimedia**

Inserta diferentes tipos de archivos multimedia. Seleccione el icono desplegable Multimedia y elija el tipo de archivo que desea insertar. Los formatos multimedia admitidos son:

- Archivo de audio
- Archivo de vídeo
- YouTube
- Vimeo

Al seleccionar la opción Archivo de audio o vídeo, se muestra la vista del repositorio para buscar y seleccionar el archivo deseado. Si elige YouTube o Vimeo, aparece el cuadro de diálogo Insertar multimedia. Pegue el vínculo del archivo de vídeo en el campo Web Link y seleccione Insert para añadir el vídeo a la ubicación válida actual o siguiente del documento.

>[!NOTE]
>
> Al agregar un vínculo de vídeo de YouTube, debe reemplazar la cadena `watch?v=` por `embed` en la dirección URL. Por ejemplo, para agregar un vínculo de vídeo de YouTube: `https://www.youtube.com/**watch?v**=WlIKQOrmZcs`, debe agregarlo como: `https://www.youtube.com/**embed/**WlIKQOrmZcs`. Este cambio garantiza que el vídeo se incruste en el sitio de AEM y en la salida de PDF.

También puede agregar el archivo de audio o vídeo desde el cuadro de diálogo Insertar multimedia. Seleccione la opción Archivo de audio/vídeo y, a continuación, seleccione el icono Examinar para iniciar la vista del repositorio. Seleccione el archivo de audio o vídeo del repositorio y seleccione **Seleccionar** para agregar el vínculo del archivo en el campo Archivo de audio o vídeo. Si elige un archivo de vídeo, también se mostrará una vista previa del archivo en el área de Vista previa. Puede reproducir el archivo de vídeo para ver su previsualización.

![](images/insert-multimedia.png){width="650" align="left"}

**Referencia cruzada**

Insertar referencias de tipo: referencia de contenido, referencia de clave de contenido, referencia de clave, referencia de archivo, vínculo web o vínculo de correo electrónico.

Seleccione el icono **Seleccionar archivo** \(para referencia de contenido y referencia de archivo\) o el icono **Seleccionar mapa raíz** \(para referencia de clave de contenido y referencia de clave\) y seleccione el archivo o contenido deseado al que desee vincular.

![](images/insert-references.png){width="650" align="left"}

En el documento se agrega un vínculo de la referencia seleccionada. El menú contextual del vínculo le ofrece las siguientes opciones:

- **Insertar elemento**: muestra una lista de elementos válidos que puede insertar en un contexto determinado.
- **Copiar UUID**: copia el UUID de la referencia insertada.
- **Copiar ruta**: copia la ruta de acceso completa de la referencia insertada.
- **Generar ID**: genera un ID único para la referencia insertada.

También puede buscar utilizando el UUID del archivo al que desee hacer referencia. En los vínculos Contenido y Referencia clave, introduzca el UUID del archivo al que desea vincular y el archivo se buscará y mostrará automáticamente en la sección Vista previa. Cuando especifique el UUID del archivo, no es necesario mencionar explícitamente la extensión de archivo para los archivos .xml. La extensión .xml se anexa automáticamente al UUID.

![](images/insert-content-using-uuid-search.png){width="650" align="left"}

Si el administrador ha habilitado la opción UUIDs en *XMLEditorConfig*, verá el UUID del contenido referenciado en la propiedad **Link**.

![](images/ref-link-uuid_cs.png){align="left"}

>[!NOTE]
>
> Si la opción **Habilitar UUIDs** no está habilitada, se muestra la ruta relativa del contenido al que se hace referencia.

>[!IMPORTANT]
>
> Aunque la ruta relativa del contenido al que se hace referencia se muestra en la propiedad **Link**, internamente el vínculo se crea mediante el UUID del contenido al que se hace referencia.

>[!TIP]
>
> Consulte la sección Referencias en la guía de prácticas recomendadas para conocer las prácticas recomendadas sobre las referencias al contenido.

**Filtrar búsqueda**

Puede buscar texto en los archivos presentes en la ruta seleccionada del repositorio de AEM. Por ejemplo, &quot;general&quot; se busca en la siguiente captura de pantalla. También puede limitar la búsqueda mediante filtros mejorados. Puede buscar todos los ficheros DITA, como los temas DITA y los mapas DITA, presentes en la ruta seleccionada.

Puede buscar archivos que no sean DITA, como los archivos de imagen, multimedia y documentos de la ruta seleccionada. También se pueden buscar valores específicos en los atributos de elementos DITA. También puede buscar archivos que el usuario especificado haya desprotegido.

![](images/reference-search-filters.png){width="650" align="left"}

>[!NOTE]
>
> El administrador del sistema también puede configurar los filtros de texto y mostrar u ocultar otros filtros. Para obtener más información, vea la sección *Configuración de filtros de texto* en Instalar y configurar Adobe Experience Manager Guides as a Cloud Service.

Se muestra la lista de archivos filtrados que contienen el texto buscado. Por ejemplo, en la captura de pantalla anterior se enumeran los archivos que contienen el texto &quot;general&quot;. También puede obtener una vista previa del contenido del archivo.


**Contenido reutilizable** - ![](images/reusable-content.svg)

Reutilice el contenido de cualquier otro documento del proyecto. Puede insertar contenido vinculándolo directamente al contenido de un archivo o usando una referencia de clave, ver [Resolver referencias de clave](map-editor-other-features.md#id176GD01H05Z). Al seleccionar el icono Contenido reutilizable, aparece el cuadro de diálogo Reutilizar contenido:

![](images/reuse-content-dialog.png){width="650" align="left"}

En el cuadro de diálogo Reutilizar contenido (Reuse Content), seleccione el fichero DITA para referencias de fichero o el fichero de mapa DITA que contiene las referencias de clave. Una vez seleccionado, el tema o las referencias clave se muestran en el cuadro de diálogo. Puede seleccionar la clave o el identificador del tema que desee insertar y seleccionar **Listo** para insertar el contenido en el tema.

Para insertar una referencia de contenido, también puede introducir el UUID del archivo y el contenido reutilizable de ese archivo se muestra en la sección Vista previa.

En función de la configuración para insertar vínculos, puede ver el UUID del contenido insertado o la ruta relativa en el panel Propiedades o en la vista de código de Source. El vínculo siempre se crea con el UUID del contenido al que se hace referencia. Vea *Configurar vínculos basados en UUID* en la instalación y configuración de Adobe Experience Manager Guides as a Cloud Service.

>[!NOTE]
>
> Para agregar contenido antes o después del contenido referido, usa las teclas de flecha *Alt*+*Izquierda* o Alt+*Derecha* para mover el cursor a la ubicación deseada.

También puede incrustar el contenido referido dentro del tema haciendo clic con el botón secundario en el contenido referido y eligiendo **Reemplazar referencia por contenido** del menú contextual.

**Símbolo** - ![](images/symbol-icon.svg)

Inserta caracteres especiales en el tema. Seleccione el icono Símbolo para abrir el cuadro de diálogo Insertar carácter especial.

>[!NOTE]
>
> Experience Manager Guides proporciona cuadros de diálogo móviles y de tamaño variable. Se puede cambiar el tamaño de los cuadros de diálogo que tienen dos líneas cruzadas en la esquina inferior derecha. A continuación, se muestran las líneas cruzadas del cuadro de diálogo Carácter especial.

![](images/insert-special-char.png){width="350" align="left"}

En el cuadro de diálogo Insertar carácter especial, puede buscar un carácter especial utilizando su nombre. Todos los caracteres especiales se almacenan en varias categorías. Utilice la lista desplegable Seleccionar categoría y seleccione una categoría. Se muestran los caracteres especiales disponibles en la categoría seleccionada. Puede desplazarse por la lista de caracteres especiales con las teclas de dirección o seleccionar el carácter que desee insertar. El nombre y el código hexadecimal del carácter especial seleccionado se muestran debajo de la lista. Seleccione **Insertar** para insertar el carácter seleccionado en el documento.

**Palabra clave** - ![](images/Keyword_icon.svg)

Palabra clave Insert definida en el mapa DITA. Seleccione la opción Palabra clave para abrir el cuadro de diálogo Referencia de clave.

![](images/insert-keyword.png){width="550" align="left"}

Las palabras clave se muestran en orden alfabético y también puede buscar palabra clave\(s\) escribiendo una cadena de búsqueda en el cuadro Buscar. El resultado de la búsqueda devolverá las palabras clave que contienen la cadena en ID o Value. Las palabras clave definidas en el mapa DITA se muestran en este cuadro de diálogo. Elija la palabra clave que desee insertar y seleccione **Insertar**.

También puede cambiar los atributos de la palabra clave insertada haciendo clic con el botón derecho en la palabra clave y seleccionando la opción Atributos. Se abrirá el cuadro de diálogo **Atributos para palabra clave:

![](images/attributes-for-keyword.png){width="550" align="left"}

Puede cambiar los atributos de la palabra clave o agregar un nuevo atributo a la palabra clave.

**Fragmentos** - ![](images/insert-snippet-icon.svg)

Insertar un fragmento en la ubicación válida actual o siguiente. Para que esta función funcione, debe tener fragmentos definidos en el sistema. Para obtener más información sobre cómo agregar un fragmento, vea la descripción de la característica **Fragmento** en la sección [Panel izquierdo](./web-editor-left-panel.md).

Al seleccionar la opción Fragmentos de código, se muestra el catálogo Insertar fragmento de código. El catálogo distingue entre contextos, lo que indica que sólo mostrará los fragmentos si están permitidos en la ubicación actual.

En el siguiente ejemplo se muestran dos fragmentos preconfigurados: Advertencia y Error que se pueden insertar en la ubicación actual del documento.

![](images/insert-snippet.png){width="300" align="left"}

Al elegir un fragmento de la lista, éste se inserta en la ubicación válida actual o siguiente del documento. La siguiente captura de pantalla muestra el fragmento de error insertado en el documento:

![](images/error-snippet.png){width="400" align="left"}

**Citas** - ![](images/Citations_icon.svg)

Cree citas y agréguelas a su contenido. Aprenda a [agregar y administrar citas en su contenido](./web-editor-apply-citations.md).

**Datos de consulta** - ![](images/data-sources-new-icon.svg)

Conéctese con la fuente de datos y utilice los datos para crear contenido. Obtenga información sobre cómo [utilizar datos de la fuente de datos](./web-editor-content-snippet.md).

## Información de la versión y Guardar como nueva versión

La característica **Información de la versión y Guardar como nueva versión** combina el seguimiento de versiones y el guardado de contenido en una sola funcionalidad.

- La información de versión muestra la versión actual del tema o asignación. Aparece un asterisco (*) junto al número de versión para indicar que no se han guardado los cambios.

  El número de versión cambia con cada nueva versión que se crea para el tema o el archivo de asignación. Si está trabajando en un documento recién creado, la información de la versión se mostrará como **none**.

  ![](images/version-information.png){align="left"}


- **Guardar como nueva versión** es un botón que guarda los cambios realizados en el tema y también crea una nueva versión del mismo.

  ![](images/save-as-new-version.png){align="left"}


Cuando elige guardar un tema o asignación mediante **Guardar como nueva versión**, aparece el siguiente cuadro de diálogo:

![](images/save-as-new-version-dialog.PNG){width="300" align="left"}

Escriba comentarios y etiquetas de versión para identificar los cambios y seleccione **Guardar** para crear una nueva versión del archivo.

Al elegir la opción **Guardar como nueva versión**, la primera versión del tema se crea en DAM, que también se convierte en la versión activa del tema en ese momento. Posteriormente, si vuelve a una versión anterior del tema, esta se convierte en la versión activa actual del tema.

Si el administrador tiene etiquetas de versión preconfiguradas, verá esas etiquetas en una lista desplegable. Puede elegir una etiqueta de la lista de etiquetas disponibles y guardar el documento.

![](images/web-editor-pre-defined-labels.PNG){width="300" align="left"}

Al guardar un tema, puede agregar un comentario que especifique los cambios realizados en el tema. Este comentario se muestra en el Historial de versiones del tema.

Si el tema está en revisión, los revisores recibirán una notificación que indica que hay disponible una versión más reciente del tema. Pueden acceder fácilmente a la última revisión del documento y seguir revisando la última versión del tema.

Cuando pasa el puntero sobre el título de un tema, se muestra el título del archivo, la ruta de acceso del archivo y el número de versión.

![](images/mouse-hover-on-title_cs.png){align="left"}

>[!NOTE]
>
> Una vez que haya disponible una versión del tema, también puede agregarle etiquetas. Estas etiquetas se pueden utilizar para crear una línea de base para publicar una versión específica del documento. Para obtener más información acerca del uso de etiquetas en los temas, vea [Usar etiquetas](web-editor-use-label.md#).

## Bloquear/desbloquear

Bloquea o desbloquea el archivo actual. Bloquear un archivo le proporciona acceso de escritura exclusivo al archivo. Esto restringe a otros usuarios de la edición del archivo. Desbloquee el archivo si desea que otros usuarios tengan acceso de edición. Cuando el archivo está desbloqueado, los cambios se guardan en la versión actual del archivo.

![](images/web-editor-lock-button.png){align="left"}

Si está en la vista Mapa y expande el mapa principal, puede bloquear todos los archivos del mapa con un solo clic. Simplemente expanda el archivo de asignación principal y seleccione el archivo principal, lo que resulta en la selección de todos los archivos dentro del mapa. A continuación, puede seleccionar **Bloquear** ![](images/LockClosed_icon.svg) para bloquear todos los archivos del mapa.

En el panel Repositorio, los archivos bloqueados se muestran con un icono de bloqueo. Cuando pasa el ratón por encima de este icono de bloqueo, el nombre de usuario o bloqueado por usted se muestra como información sobre herramientas.

![](images/web-editor-locked-by-icon-new.png){width="350" align="left"}

Si un archivo está bloqueado por otro usuario, al pasar el ratón por encima del icono de bloqueo del Repositorio, se muestra el nombre del usuario que lo ha bloqueado. En este caso, el archivo se abre en modo de solo lectura, con **acceso de solo lectura** junto a la información de la versión.

Como administrador, también obtienes acceso a la función **Forzar desbloqueo** que te permite desbloquear el archivo bloqueado por otros usuarios. Utilice esta función para acceder a los derechos de edición de un archivo bloqueado por otros usuarios.

![](images/web-editor-force-unlock-new.png){width="350" align="left"}
**Tema principal:**[ Introducción al editor](web-editor.md)
