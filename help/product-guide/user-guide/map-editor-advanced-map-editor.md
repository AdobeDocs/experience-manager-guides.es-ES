---
title: Trabajo con el Editor de mapas avanzado
description: AEM Aprenda a trabajar con el editor de mapas avanzado en Guías de. Conozca las funciones del editor de mapas avanzado. Editar temas mediante un mapa DITA y utilizar la vista de diseño, la vista de autor y el modo de vista previa.
exl-id: e58e3705-2c3b-48cc-b2c8-2596e9751c85
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '3695'
ht-degree: 0%

---

# Trabajo con el Editor de mapas avanzado {#id1942D0S0IHS}

El editor de mapas avanzado viene con una interfaz de usuario intuitiva y es similar al editor web. Cuando se abre un fichero de mapa en el Editor Web, se obtiene una opción para editar el fichero de mapa mediante la interfaz del Editor de Mapas Avanzado. El editor de mapas avanzado permite agregar referencias temáticas, referencias clave, estructurar el contenido y mucho más.

Además de editar archivos de mapa directamente desde el Editor Web, también puede abrir archivos de tema en un mapa para editar el Editor Web. En este tema se describen las funciones del Editor de mapas avanzado y cómo se pueden abrir y editar archivos en un mapa DITA en el Editor Web.

## Adición de temas a un archivo de asignación

Realice los siguientes pasos para crear el archivo de asignación con el Editor de mapas avanzado:

1. En la interfaz de usuario de Assets, vaya al archivo de asignación que desee editar.

   >[!NOTE]
   >
   > Asegúrese de que no ha habilitado el modo de selección de recursos.

1. Para obtener un bloqueo exclusivo en el archivo de asignación, seleccione el archivo de asignación y haga clic en **Desproteger**.

   >[!NOTE]
   >
   > Una vez que tenga un bloqueo exclusivo en un archivo de mapa, los demás usuarios no podrán editar el mapa. Sin embargo, podrían trabajar en los temas dentro del archivo de mapa. Si el administrador ha configurado el Editor Web para desproteger archivos antes de editarlos, no podrá editar un archivo hasta que lo desproteja. Del mismo modo, si está configurado, se le pedirá que proteja cualquier archivo desprotegido antes de cerrarlo

1. Con el archivo de asignación seleccionado, haga clic en **Editar temas**.

   ![](images/edit-map-main-menu.png){width="800" align="left"}

   O bien, también puede seleccionar **Editar temas** en el menú de acción del archivo de asignación:

   ![](images/edit-map-action-menu.png){width="800" align="left"}

   El archivo de asignación se abre para editarlo en el Editor Web.

1. Haga clic en **Editar** icono.

   ![](images/edit-map-icon.png){width="550" align="left"}

   El mapa se abre en la interfaz del Editor de mapas avanzado. Si ha abierto un nuevo archivo de mapa, solo se muestra el título del mapa en el editor.

   ![](images/new-map-file-in-editor.png){width="800" align="left"}

   - **A** - \(*Barra de herramientas principal*\): Es similar a la barra de herramientas principal del Editor Web. Consulte [Barra de herramientas principal](web-editor-features.md#id2051EA0G05Z) en el Editor web para obtener más información.

   - **B** - \(*Barra secundaria*\) Esta es la barra de herramientas Secundaria que le permite trabajar con archivos de asignación. Para obtener más información sobre las funcionalidades disponibles a través de la barra de herramientas secundaria, consulte [Funciones disponibles en la barra de herramientas del Editor de mapas avanzado](#id205DEC0005Z).

   - **C** - \(*Vistas de mapas*\): Permite cambiar el Editor de mapas entre Diseño, Autor, Origen y Vista previa. El **Diseño** permite organizar los temas en un mapa DITA. Esto proporciona la vista de árbol o jerárquica del mapa. El **Autor** Esta vista permite editar los temas en el Editor de mapas. Esto también proporciona la vista WYSIWYG del archivo de mapa. El **Origen** La vista permite trabajar con el XML subyacente del archivo de asignación. La vista previa le ofrece una vista consolidada de todos los temas y subasignaciones dentro del archivo de asignación. El **Cerrar** link cierra el archivo de asignación.

   - **D** - \(*Panel izquierdo*\): otorga acceso al panel izquierdo, que le permite acceder a Favoritos, Repositorio, Mapa, Esquema y otras funciones. Puede expandirlo o contraerlo si hace clic en el icono Expandir barra lateral \(![](images/sidebar-expand-icon.svg)\). Para obtener más información sobre las funciones disponibles en el panel izquierdo, consulte [Panel izquierdo](web-editor-features.md#id2051EA0M0HS) en el Editor web.

   - **E** - \(*Área central*\): Asignar área de edición de contenido.

   - **F** - \(*Panel derecho*\): otorga acceso al panel Propiedades. Puede ver las propiedades de contenido y las propiedades de asignación del tema o mapa seleccionado. Para obtener más información sobre las funcionalidades disponibles en este panel, consulte [Panel derecho](web-editor-features.md#id2051EB003YK) en el Editor web.

1. En el panel izquierdo, cambie a **Vista de repositorio**.

1. AEM En el repositorio de, vaya a la carpeta que contiene los temas o las asignaciones secundarias que desea agregar.

1. Seleccione el tema o el archivo de asignación en la **Vista de repositorio** y arrástrelo y suéltelo en el área de edición de contenido del mapa \(middle\).

   El tema se añade en el mapa.

   ![añadir tema del editor de mapas](images/map-editor-add-topic.png){width="800" align="left"}

1. Para agregar temas subsiguientes o un submapa, arrastre y suelte el tema o submapa en la ubicación requerida del mapa.

   Tenga en cuenta los siguientes puntos al crear el archivo de mapa:

   - El archivo se agrega en una ubicación en la que la barra horizontal aparece en el área de edición del mapa. En la siguiente captura de pantalla, la variable *Información general* se agregará un tema entre las etiquetas *Descripción general* y *Sitio de lanzamiento y aterrizaje* temas.

     ![](images/horizontal-line-in-adv-map-editor.png){width="350" align="left"}

   - Para reemplazar un tema, colóquelo en la parte superior, izquierda o derecha del tema que desee reemplazar. Una barra vertical a la izquierda o a la derecha de un tema indica que se reemplazará con el tema que se coloca en él.

     ![](images/vertical-bar-left-right.png){width="550" align="left"}

     Sin embargo, antes de reemplazar un tema, aparece un mensaje de confirmación. El tema solo se reemplaza después de que proporcione la confirmación.

     ![](images/replace-topic-confirm.png){width="300" align="left"}

   - Si se añade un submapa al mapa DITA, este se mostrará como un vínculo en el mapa DITA. Para ver todos los temas del submapa, Ctrl+clic en el vínculo del submapa. El contenido del submapa se muestra en una nueva pestaña. Del mismo modo, para abrir un tema desde el mapa DITA, pulse Ctrl+clic en el vínculo del tema y se abrirá en la nueva pestaña.

   - Puede utilizar las teclas de método abreviado CTRL+Z y CTRL+Y o sus respectivos iconos en la barra de herramientas para deshacer o rehacer cualquier cambio en el mapa.

   - Para cambiar la posición de un tema, seleccione el tema \(haciendo clic en el icono del tema\) y, a continuación, arrástrelo y suéltelo en la ubicación deseada en el archivo de mapa. Asegúrese de que la barra horizontal esté visible en la ubicación donde desee colocar el tema. En la siguiente captura de pantalla, el tema *Sitio de lanzamiento y aterrizaje* se mueve después de que *Información general* tema.

     ![](images/move-topic-adv-map-editor.png){width="350" align="left"}

   - Para comprobar las propiedades del archivo de mapa, haga clic con el botón derecho en cualquier lugar del área de edición del mapa y elija **Propiedades** en el menú contextual. AEM En función de su versión de la, puede ver propiedades como metadatos, programación \(de\)activación, referencias, estado del documento y más.

1. Haga clic en **Guardar**.


## Funciones disponibles en la barra de herramientas del Editor de mapas avanzado {#id205DEC0005Z}

La barra de herramientas del Editor de mapas avanzado es similar al tema Editor web. Las operaciones básicas como cambiar el panel izquierdo, guardar el mapa, crear una nueva versión del mapa, deshacer/rehacer la última operación y eliminar los elementos seleccionados son comunes en ambos editores. Para obtener información detallada sobre cómo funcionan estas operaciones, consulte [Conozca las funciones del editor web](web-editor-features.md#) sección.

Las siguientes operaciones específicas del mapa también están disponibles en la barra de herramientas de las vistas Diseño y Autor:

## Vista Presentación {#id205DEC0005Z_layout_view}

Cuando se abre un mapa para editarlo, se abre la vista Presentación del Editor de mapas. La vista Presentación muestra la jerarquía del mapa en una vista de árbol y permite organizar los temas en un mapa.

>[!NOTE]
>
> La vista Presentación sólo muestra las referencias presentes en un mapa. Si hay referencias rotas, se mostrará un símbolo de cruz pequeño a la izquierda de la referencia

Puede realizar las siguientes tareas en la vista Presentación:

**Insertar referencia de tema** - ![](images/insert-topic-reference.png)

Muestra el cuadro de diálogo de búsqueda del tema. Desplácese hasta el tema o archivo de asignación que desee insertar y haga clic en Seleccionar para añadirlo al mapa.
![](images/insert-topic-reference-dialog.png){width="800" align="left"}


**Insertar grupo de temas** - ![](images/insert-topic-group.png)

Inserte el `topicgroup` Elemento. Para obtener más información sobre la agrupación de temas, consulte la [grupo de temas](https://docs.oasis-open.org/dita/v1.0/langspec/topicgroup.html) documentación en Especificación del lenguaje DITA de OASIS.

**Insertar definición de clave** - ![](images/Key_icon.svg)

Muestra el cuadro de diálogo Insertar definición de clave. Utilice este cuadro de diálogo para definir cualquier definición de clave que desee utilizar en el mapa.

![](images/insert-key-definition-dialog.png){width="300" align="left"}

**Insertar antes/Insertar después** - ![](images/insert_element_before_icon.svg) / ![](images/insert_element_after_icon.svg)

Muestra el cuadro de diálogo Insertar elemento. Seleccione el elemento que desea insertar en el mapa. Según la operación, el nuevo elemento se inserta antes o después del elemento actual en el mapa.

**Insertar materia frontal** - ![](images/frontmatter.svg)

Este icono se muestra al abrir un mapa de libro para editarlo. Puede insertar componentes al principio del libro, como una tabla de contenido, un índice y una lista de tablas.

**Insertar materia posterior** - ![](images/backmatter.svg)

Este icono se muestra al abrir un mapa de libro para editarlo. Puede insertar componentes para un final del libro, como un índice, un glosario y una lista de ilustraciones.

**Mover el elemento seleccionado a la izquierda o a la derecha** - ![](images/left-arrow-icon.png) / ![](images/right-arrow-icon.png)

Haga clic en la flecha izquierda para mover el tema hacia el lado izquierdo de la jerarquía. Esto promociona esencialmente el tema correspondiente un nivel arriba en la jerarquía. Por ejemplo, si hace clic en la flecha izquierda mientras se selecciona un tema secundario, conviértalo en el elemento secundario del tema situado encima. Del mismo modo, si hace clic en la flecha derecha, el tema se inserta en el lado derecho, lo que lo convierte en el elemento secundario del tema situado encima.

**Mover arriba/abajo el elemento seleccionado![](images/arrowup.svg)** - / ![](images/arrowdown.svg)

Haga clic en los iconos de flecha arriba o abajo para mover el tema hacia arriba o hacia abajo en la jerarquía.

>[!NOTE]
>
> También puede arrastrar y soltar las referencias para moverlas en un mapa.

**Bloquear/Desbloquear** - ![](images/LockClosed_icon.svg) / ![](images/LockOpen_icon.svg)

Obtiene un bloqueo en el archivo de asignación y libera el bloqueo. Si tiene cambios sin guardar en el fichero de asignación, en el momento de liberar el bloqueo, se le pedirá que guarde el fichero de asignación. Los cambios se guardan en la versión actual del archivo de asignación.

**Combinar** - ![](images/merge-icon.svg)

Para obtener más información sobre la combinación de contenido de una versión diferente del mismo archivo o de uno diferente, consulte [Combinar](web-editor-features.md#id205DF04E0HS) en el Editor web.

**Historial de versiones** - ![](images/version-history-web-editor-ico.svg)

Compruebe las versiones y etiquetas disponibles del tema activo y vuelva a cualquier versión desde el propio editor.

**Etiqueta de versión** - ![](images/version-label-icon.svg)

Muestra el cuadro de diálogo Administración de etiquetas de versión. Seleccione una versión en la lista desplegable. Seleccione la etiqueta que desee aplicar a la versión seleccionada y haga clic en **Agregar etiqueta** para agregarlo.

**Opciones de vista** - ![](images/view-options.svg)

Muestra un menú desplegable que le da la opción de Mostrar números de línea, Mostrar casilla de verificación y Mostrar nombre de archivo.

- **Mostrar números de línea**

Muestra u oculta el número de línea de cada tema. Los números de línea se muestran según el nivel de la jerarquía.

- **Mostrar casilla de verificación**

Muestra u oculta una casilla de verificación para cada tema. Puede utilizar la casilla de verificación para seleccionar los temas y realizar diversas tareas mediante el menú Opciones. Para obtener más información, consulte la [Opciones](#id228ID8006H8) menú.

- **Mostrar nombre de archivo**

Muestra el nombre de archivo de los títulos de los temas.

>[!NOTE]
>
> Cuando pasa el puntero sobre el título de un tema, se muestra la ruta del archivo.


**Ver temas basados en filtros condicionales** Si ha aplicado alguna condición a un tema, se muestra un icono de filtro a la derecha del tema. Cuando pasa el puntero sobre un icono de filtro, se muestra la condición aplicada y su valor de atributo.

**Menú Opciones en la vista Presentación**

Además de organizar los temas en el archivo de asignación, también puede realizar las siguientes acciones utilizando el menú Opciones disponible para un elemento en la vista Presentación:

![](images/map-editor-options-menu.png){width="650" align="left"}

- **Añadir**: puede elegir añadir un nuevo tema o una referencia vacía desde el Editor de mapas:
   - **Referencia vacía**: esta opción permite añadir una referencia vacía en el mapa DITA. Puede hacer doble clic en la referencia vacía insertada más adelante y agregar los detalles del Tema. Para obtener más información, consulte la [Crear un tema](web-editor-features.md#id228ICI0105U) en el Editor web.
   - **Nuevo tema**: Cuando elija crear un nuevo tema desde el menú, aparece el cuadro de diálogo Crear nuevo tema. En el cuadro de diálogo Crear nuevo tema, proporcione los detalles necesarios y haga clic en Crear. Para obtener más información, consulte la [Crear un tema](web-editor-features.md#id228ICI0105U) en el Editor web.
- **Mover**: Puede elegir mover un tema hacia arriba/abajo/derecha/izquierda en la jerarquía. También puede arrastrar y soltar un tema o un mapa desde el panel del repositorio al mapa abierto en el Editor de mapas.
- **Deshacer**: Deshacer la última operación en la vista Presentación.
- **Rehacer**: rehaga la última operación en la vista Presentación.
- **Copiar**: copie la referencia seleccionada del archivo de asignación.

  >[!NOTE]
  >
  > Puede mostrar y, a continuación, seleccionar las casillas de verificación para copiar varias referencias.

- **Pegar**: pegue las referencias copiadas en la ubicación actual de la jerarquía.
- **Eliminar**: elimine las referencias seleccionadas del archivo de asignación.

  >[!NOTE]
  >
  > Puede mostrar y, a continuación, seleccionar las casillas de verificación para eliminar varias referencias.


## Panel derecho en el editor de mapas

El panel derecho muestra las Propiedades de contenido y las Propiedades de mapa en la vista Diseño del Editor de mapas.

**Propiedades del contenido**

El panel Propiedades del contenido contiene información sobre el tipo de tema seleccionado actualmente en el mapa, su dirección URL del vínculo y sus atributos. Para obtener más información, consulte [Propiedades del contenido](web-editor-features.md#id228IDB00HMM) en el Editor web.

- **Otros atributos** Si el administrador ha creado un perfil para atributos, obtendrá esos atributos junto con sus valores configurados. Con el panel de propiedades de contenido, puede elegir esos atributos y asignarlos al contenido relevante del tema. También puede asignar atributos configurados por el administrador en la variable **Mostrar atributos** pestaña en la configuración del editor. Los atributos definidos para un elemento se muestran en las vistas Diseño y Esquema. Esto le ayuda a echar un vistazo rápido a todos los temas de un mapa para los que se ha definido un atributo en particular. Por ejemplo, todos los temas que tienen el atributo de plataforma definido como &quot;Android&quot;.

  ![vista de diseño](images/layout-inline-attributes.png){width="650" align="left"}


  Para obtener más información, consulte la *Mostrar atributos* dentro de *Configuración del editor* descripción de la función en [Panel izquierdo](web-editor-features.md#id2051EA0M0HS) sección.

- **Metadatos** Con los metadatos , puede establecer la información de los metadatos. Puede definir el Título de navegación, el Texto del vínculo, la Descripción breve y las Palabras clave.

Para obtener más información sobre el tema estándar atributos y metadatos, consulte la [topicref](https://docs.oasis-open.org/dita/v1.2/os/spec/langref/topicref.html) documentación en Especificación del lenguaje DITA de OASIS.

**Asignar propiedades**

Muestra el cuadro de diálogo Propiedades del mapa, donde puede establecer los atributos y la información de metadatos del mapa.

## Vista de autor {#id205DEC0005Z_author_view}

El **Autor** Esta vista permite editar el mapa DITA en el Editor Web. Esto muestra la vista WYSIWYG del Editor de mapas y algunos de los iconos que se muestran en la vista Autor son los mismos que la vista Presentación. Para obtener más información, consulte [Vista Presentación](#id205DEC0005Z_layout_view). Además, puede ver los iconos siguientes y realizar las tareas relacionadas desde la vista Autor:

**Insertar antes/Insertar después** - ![](images/insert_element_before_icon.svg) / ![](images/insert_element_after_icon.svg)

Muestra el cuadro de diálogo Insertar elemento. Seleccione el elemento que desea insertar en el mapa. Según la operación, el nuevo elemento se inserta antes o después del elemento actual en el mapa.

**Insertar elemento** - ![](images/Add_icon.svg)

Muestra el cuadro de diálogo Insertar elemento. Seleccione el elemento que desea insertar. Puede utilizar el teclado para desplazarse por la lista de elementos y pulsar Intro para insertar el elemento requerido. También puede hacer clic directamente en el elemento para insertarlo en el mapa.

**Insertar tabla de relaciones** - ![](images/relationship_table_icon.svg)

Inserta una tabla de relaciones en el mapa. Como el concepto de trabajar con la tabla de relaciones es el mismo que se explica en la sección Editor de mapas básico, consulte [Trabajo con tablas de relación en el Editor de mapas básico](map-editor-basic-map-editor.md#id1944B0I0COB) para obtener más información.

**Insertar contenido reutilizable** - ![](images/content-reuse-icon.png)

Muestra el diálogo Reutilizar contenido. Utilice este cuadro de diálogo para insertar el contenido que desea reutilizar en el mapa.

**Actualizar atributo de título de navegación** - ![](images/navtitle-refresh-icon.svg)

Sincroniza el `title` de un archivo al que se hace referencia en un mapa con el valor especificado en su `@navtitle` atributo. Se pueden añadir distintos tipos de ficheros de referencia en un mapa, por ejemplo, mapas de tema, de referencia, de tarea, \(sub\), etc. La mayoría de estos archivos admiten el `@navtitle` atributo. Si un archivo contiene la variable `@navtitle` , luego el atributo `@navtitle` se actualiza el atributo para el mismo archivo en el mapa. En caso de que la `@navtitle` no está presente, el atributo `@navtitle` se añade a ese archivo de referencia y su `title` también se actualiza para mostrar el `@navtitle`.

>[!NOTE]
>
> El administrador puede configurar la adición automática `@navtitle` a cada fichero de referencia que se añada a un mapa. Para obtener más información sobre la configuración de la adición automática `@navtitle` atributo, consulte *Incluir @navtitle atributo de forma predeterminada* en Instalar y configurar las guías de Adobe Experience Manager as a Cloud Service.

Haga clic en el icono Actualizar atributo de título de navegación para sincronizar el `title` y del elemento `@navtitle` valores del atributo.

**Alternar vista de etiquetas** - ![](images/Label_icon.svg)

Muestra u oculta las etiquetas XML. Las etiquetas sirven como indicaciones visuales que indican el límite de un elemento. En este modo, si desea insertar una referencia de tema/mapa, arrastre y suelte el archivo deseado antes o después de la etiqueta. La barra horizontal no se muestra en el modo Vista de etiquetas.

**Habilitar/deshabilitar el seguimiento de cambios** - ![](images/track-change-icon.svg)

Puede realizar un seguimiento de todas las actualizaciones realizadas en el archivo de asignación activando el modo Control de cambios. Después de habilitar el seguimiento de cambios, todas las inserciones y eliminaciones se capturan en el documento. Para obtener más información, consulte [Habilitar/deshabilitar el seguimiento de cambios](web-editor-features.md#id205DF0203Y4) en el Editor web.

**Crear tarea de revisión** - ![](images/create-review-task-icon.svg)

Puede crear una tarea de revisión del tema o archivo de asignación actual directamente desde el Editor Web. Abra el archivo para el que desea crear la tarea de revisión y haga clic en Crear tarea de revisión para iniciar el proceso de creación de la revisión. Siga las instrucciones indicadas en la [Revisar temas o mapas](review.md#) para obtener más información.

## Edición de temas mediante el mapa DITA {#id17ACJ0F0FHS}

La edición de un tema individual no proporciona el contexto completo al autor. Un autor no tendría información sobre dónde se coloca un tema en un mapa DITA. Sin esta información contextual, se vuelve un poco difícil para los autores crear contenido.

AEM Guías de permite a los autores abrir un mapa DITA en el Editor Web y ver la ubicación de los temas en el mapa. Esto ayuda a los autores a saber dónde se coloca exactamente el tema en el mapa y crear contenido más relevante. Además, si hay varios autores trabajando en un proyecto, pueden saber cuáles son todos los temas disponibles en el mapa y reutilizar el contenido, donde sea necesario.

Para editar temas a través de un mapa DITA, realice los siguientes pasos:

1. En la interfaz de usuario de Assets, vaya al mapa DITA que contiene los temas que desea editar.
1. Haga clic en el mapa DITA para abrirlo en la consola de mapas DITA.
1. Seleccione el **Temas** para ver una lista de los temas disponibles en el mapa DITA.

   >[!TIP]
   >
   > La pestaña Temas ofrece la opción de descargar el archivo de asignación con sus dependientes. Para obtener más información, consulte [Exportación de un fichero de mapa DITA](authoring-download-assets.md#id218UBA00IXA).

1. En la barra de herramientas principal, haga clic en **Editar temas**.

   El mapa DITA se abre en el Editor Web.

   >[!NOTE]
   >
   > También puede seleccionar el fichero de mapa DITA en la interfaz de usuario de Assets y pulsar en **Editar temas** en la barra de herramientas principal para iniciar el Editor Web.

   ![](images/web-editor-map-view_cs.png){width="350" align="left"}

1. \(*Opcional*\) También puede seleccionar un tema del mapa y retirar el archivo antes de editarlo. Para retirar archivos\(s\), seleccione uno o más archivos en el panel izquierdo y haga clic en **Finalizar compra**. También puede liberar el bloqueo de cualquier archivo seleccionando el archivo desprotegido y haciendo clic en el botón **Cancelar cierre de compra y desbloquear** en la vista Mapa.

   >[!IMPORTANT]
   >
   > Si el administrador ha configurado la variable **Desactivar la edición sin cierre de compra** , debe retirar el archivo antes de editar. Si no desprotege el archivo, el documento se abrirá en el editor en modo de solo lectura.

   La siguiente captura de pantalla resalta los iconos de Cierre de compra y Bloqueo \(A\), Cancelar cierre de compra y Desbloquear \(B\), Guardar como nueva versión y Desbloquear \(C\), Editar \(D\), Vista previa \(E\), diferentes iconos que muestran diferentes tipos de archivos DITA \(F\) y archivos que están retirados \(G\).

   ![](images/file-checkout-map-editor.png){width="550" align="left"}

1. Haga clic en cualquier vínculo de tema para abrirlo en el Editor web y editarlo.

   Puede abrir varios temas en el editor, y cada tema se abre en una nueva pestaña del editor. Incluso si el mapa DITA contiene submapas, los temas de los submapas también se abren en una nueva pestaña para su edición. Si desea ver los temas de un submapa, puede hacer clic en y expandir el submapa.

   ![](images/web-editor-multiple-topics.png){width="800" align="left"}

   Si hace clic en un archivo de mapa, el mapa se abre en una nueva pestaña del explorador web.

1. Una vez que haya terminado de editar los temas, puede hacer lo siguiente:

   - Puede guardarlos de forma individual. Si hace clic en **Cerrar sin guardar** En los temas, verá un cuadro de diálogo que le pedirá que guarde los temas no guardados:

     ![](images/save-multiple-topics.PNG){width="550" align="left"}

     Puede elegir guardar todos los temas seleccionados o anular la selección de los temas que no desee guardar.

   - Puede incorporar el tema mediante las opciones **Guardar como nueva versión y desbloquear** botón. Al guardar una revisión del tema, se crea una nueva revisión y también se libera el bloqueo.
   - Si el administrador ha activado la opción de proteger archivos al cerrar, se le mostrará un mensaje para guardar los archivos cada vez que se cierren los archivos desprotegidos. Con esta opción habilitada, al cerrar el editor con archivos modificados, se muestra la lista de archivos desprotegidos que deben guardarse. Los archivos retirados se muestran con un icono de bloqueo:

     ![](images/save-on-close.PNG){width="550" align="left"}

      - Haciendo clic en **Cerrar sin guardar** cierra los archivos sin guardar los cambios.

      - Haciendo clic en **Guardar** guarda los cambios, pero no protege los archivos.

      - Selección de la **Comprobando archivos** y luego haciendo clic en la opción **Guardar** button protege los archivos \(crea otra versión\) y también guarda los archivos.


## Previsualización de un mapa

Además de poder ver la posición de cada archivo de tema dentro de un mapa, es deseable ver el contenido del mapa en un flujo consecutivo. La función Vista previa de mapa permite ver todo el contenido del archivo de mapa con un solo clic. No es necesario generar una salida del archivo de asignación para ver el aspecto que tendrá todo el mapa una vez publicado. Simplemente puede acceder a la vista previa del mapa y todos los temas y submapas se representan en forma de libro.

Puede acceder a la vista previa de un mapa desde:

- **IU de Assets**: en la interfaz de usuario de Assets, vaya a la ubicación del mapa, seleccione el archivo de mapa y elija **Previsualizar mapa** en la barra de herramientas. La vista previa del mapa se muestra en una nueva pestaña. Puede ver el contenido de todos los temas en el modo de vista previa. En esta vista, no se puede editar ningún tema.

  >[!NOTE]
  >
  > Si la variable *Previsualizar mapa* La opción no está visible en la barra de herramientas principal. Puede que se haya movido debajo de **Más** menú de barra de herramientas.

- **Editor de mapas avanzado**: en el editor de mapas avanzado, haga clic en el icono de previsualización para ver la previsualización del mapa actual.

  ![](images/map-preview-icon.png){width="350" align="left"}

  Puede realizar las siguientes tareas adicionales en el modo de vista previa:

   - Haga clic con el botón derecho en un tema y seleccione **Editar** para abrir el tema y editarlo en una nueva pestaña.

     >[!NOTE]
     >
     > Si no tiene derechos de edición, el tema se abrirá en modo de solo lectura.

   - Para ir al tema deseado, haga clic en el título del tema en el árbol de mapas \(en el panel izquierdo\).

   - El tema actual en la vista previa del mapa también se resalta en el árbol del mapa.


**Tema principal:**[ Trabajo con el editor de mapas](map-editor.md)
