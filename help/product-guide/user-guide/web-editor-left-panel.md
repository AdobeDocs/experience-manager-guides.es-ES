---
title: Panel izquierdo del editor
description: Conozca el panel izquierdo del editor. Obtenga información acerca de la interfaz y las funciones de Editor en Adobe Experience Manager Guides.
feature: Authoring, Features of Web Editor
role: User
exl-id: 92496d39-b423-4635-8b05-c67fd6af47de
source-git-commit: ffc9a9e15f11e7059822b7cf6d4707b83d15a4f4
workflow-type: tm+mt
source-wordcount: '9323'
ht-degree: 0%

---

# Panel izquierdo del editor

El panel izquierdo le permite acceder rápidamente a las colecciones, la vista de repositorio, la vista de mapa y otras funciones. Puede expandir el panel seleccionando el icono **Expandir** ubicado en la esquina inferior izquierda de la interfaz. Una vez expandido, usa el icono **Contraer** para contraer el panel. En la vista expandida, muestra los nombres de los iconos que aparecen como información sobre herramientas en la vista contraída.

>[!NOTE]
>
> Se puede cambiar el tamaño del panel izquierdo. Para cambiar el tamaño del panel, coloque el cursor sobre el límite del panel, el cursor cambiará a una flecha de dos puntas, seleccione y arrastre para cambiar el tamaño del ancho del panel.

El panel izquierdo le permite acceder a las siguientes funciones:

- [Colecciones](#collections)
- [Repositorio](#repository)
- [Mapa](#map)
- [Contenido reutilizable](#reusable-content)
- [Descripción](#outline)

Algunas de las características del panel izquierdo están disponibles en la sección **Más**. Seleccione el icono Más ![](images/Smock_MoreSmallList_18_N.svg) para acceder a las siguientes funciones:

- [Glosario](#glossary)
- [Condiciones](#conditions)
- [Régimen del sujeto](#subject-scheme)
- [Fragmentos de código](#snippets)
- [Plantillas](#templates)
- [Citas](#citations)
- [Idioma variables](#language-variables)
- [Variables](#variables)
- [Buscar y reemplazar](#find-and-replace)
- [Plantillas PDF](#pdf-templates)
- [Revisión](#review)


También se muestra en el panel izquierdo una opción adicional etiquetada como **Workfront** si está configurado Adobe Systems Workfront.

Para obtener más información, consulte vista [integración](./workfront-integration.md) con Workfront.

>[!NOTE]
>
> Las funciones disponibles en el panel izquierdo son administradas por su administrador, lo que les permite habilitar o deshabilitar las funciones individuales presentes en el panel izquierdo. En el panel izquierdo solo se muestran las funciones habilitadas. Para obtener más información, vista la sección Paneles **de la** barra de [fichas](./web-editor-tab-bar.md).

La explicación detallada de las características del panel izquierdo es la siguiente:

## Colecciones

Si trabaja en un conjunto de archivos o carpetas, puede agregarlos a su lista de favoritos para acceder a ellos rápidamente. **Colecciones** muestran la lista de documentos que ha agregado y otra lista de documentos de acceso público de los otros usuarios.

De forma predeterminada, puede ver los archivos por títulos. Al pasar el ratón por encima de un archivo, puede ver el título y la ruta del archivo como información sobre herramientas.

>[!NOTE]
>
> Como administrador, también puede elegir ver la lista de archivos por nombres de archivo en el Editor. Seleccione la opción **Nombre de archivo** de la sección **Archivos del editor muestran la configuración** en **Preferencias de usuario**.

<details>
    <summary> Crear una nueva colección </summary>


Para crear una nueva colección, seleccione el icono + situado junto al panel Colecciones para que aparezca el cuadro de **diálogo Nuevo colección** :

![](images/favorite-new-collection.PNG){width="300" align="left"}

Introduzca un título y una descripción para la colección que desea crear. Si selecciona **Público**, este favorito también se mostrará a otros usuarios.

>[!NOTE]
>
> También puede crear una colección desde la página principal de Experience Manager Guides. Abra la página principal, vaya al widget **Colecciones** en la [sección Información general](./intro-home-page.md#overview) y seleccione **Nueva colección**.

</details>

<details>
    <summary> Añadir un archivo a las colecciones </summary>


Para añadir un archivo a las colecciones, utilice cualquiera de los siguientes métodos:

- Desplácese al archivo o carpeta requerido en el vista Repositorio, seleccione el icono Opciones ** para abrir el menú contextual y elija **añadir >** **colecciones**. En el cuadro de **diálogo añadir a colecciones** , puede elegir agregar el archivo o carpeta a un favorito existente o crear uno nuevo.

  ![](images/favorite-add-file-folder.png){width="300" align="left"}

- Haga clic con el botón derecho en el pestaña de un archivo en la editor para abrir el menú contextual. Elija **añadir >** **colecciones** para agregar el archivo a sus lista favoritos.

  ![](images/favorite-add-from-file-context-menu_cs.png){align="left"}


>[!NOTE]
>
> - Para eliminar un elemento del lista favoritos, seleccione el icono de Opciones situado junto al elemento en un colección Favoritos y elija **Quitar de las colecciones**.
> - Para previsualización el archivo sin abrirlo, seleccione un archivo y, a continuación, seleccione **Vista previa** en el menú Opciones.

</details>

**Menú de opciones para una colección**

También puede realizar muchas acciones utilizando el menú Opciones disponible para una colección:

![](images/favorites-options.png){width="650" align="left"}

- **Cambiar nombre**: cambie el nombre de la colección seleccionada.
- **Eliminar**: elimine la colección seleccionada.
- **Actualizar**: obtenga una lista nueva de archivos y carpetas del repositorio.
- **Ver en la interfaz de usuario de Assets**: muestra el contenido del archivo o carpeta en la interfaz de usuario de Assets.

>[!NOTE]
>
> También puede actualizar la lista con el icono Actualizar de la parte superior.


## Repositorio

Al seleccionar el icono Repositorio, se obtiene una lista de archivos y carpetas disponibles en DAM. De forma predeterminada, puede ver los archivos por títulos. Al pasar el ratón por encima de un archivo, puede ver el título y el nombre del archivo como información sobre herramientas.

>[!NOTE]
>
> Como administrador, también puede elegir ver la lista de archivos por nombres de archivo en el Editor. Seleccione la opción **Nombre de archivo** de la sección **Archivos del editor muestran la configuración** en **Preferencias de usuario**.

Se cargan 75 archivos a la vez. Cada vez que selecciona **Cargar más**... se cargan 75 archivos y el botón deja de mostrarse cuando se han enumerado todos los archivos. Esta carga por lotes es eficiente y puede acceder a los archivos más rápido en comparación con cargar todos los archivos existentes en una carpeta.

Puede navegar fácilmente al archivo requerido dentro de DAM y abrirlo en el Editor. Si tiene el acceso necesario para editar el archivo, puede hacerlo.

También puede seleccionar y reproducir un archivo de audio o vídeo en el Editor. Puede cambiar el volumen o
la vista del vídeo. En el menú contextual también tiene las opciones para descargar, cambiar la reproducción
velocidad o vea la imagen en la imagen.

Seleccione un mapa y pulse Intro o haga doble clic para abrirlo en la **vista Mapa**. Para obtener más información, vea la descripción de la característica **Vista de mapa** en el panel izquierdo. Seleccione un tema y presione Intro o haga doble clic para abrirlo en el [área de edición de contenido](./web-editor-content-editing-area.md). La posibilidad de desplazarse por un archivo y abrirlo directamente desde el Editor ahorra tiempo y aumenta la productividad.

**Filtrar la búsqueda en el repositorio**

El Editor proporciona filtros mejorados para buscar texto. Puede buscar y filtrar un texto en los archivos presentes en la ruta seleccionada del repositorio de Adobe Experience Manager. Busca en el título, el nombre de archivo y el contenido de los archivos.


![búsqueda de archivos en la vista del repositorio](images/repository-filter-search.png){width="300" align="left"}

*Aplicar filtros para buscar los archivos que contienen el texto`personal spaceship.`*

Seleccione el icono **Filtro de búsqueda** \(![Icono de filtro de búsqueda](images/filter-search-icon.svg)\) para abrir la ventana emergente Filtro.

>[!NOTE]
>
> Cuando busca texto o filtra archivos, aparece un punto azul en el icono **Filtrar búsqueda** \(![Icono de filtro de búsqueda](images/filter-search-icon.svg)\) para indicar que estamos en el panel de búsqueda y que se han aplicado algunos filtros.


Tiene las siguientes opciones para filtrar los archivos y limitar la búsqueda en el repositorio de Adobe Experience Manager:

- **Archivos DITA**: Puede buscar todos los **temas DITA** y **mapas DITA** presentes en la ruta seleccionada. Están seleccionadas de forma predeterminada.
- **Archivos que no son DITA**: puede buscar **archivos Ditaval**, **archivos de imagen**, **multimedia**, **documentos** y **JSON** en la ruta seleccionada.

  ![filtro de búsqueda rápida ](images/repository-filter-search-quick.png) {width="300" align="left"}

  *Utilice los filtros rápidos para buscar archivos DITA y no DITA.*

**Filtro avanzado**

Seleccione el icono de **filtro avanzado de filtrado** ![Avanzadas para vista el cuadro de diálogo Filtro ****](images/advanced-filter-gear-icon.svg)Avanzadas.

Puede vista las siguientes opciones en las fichas **General** y **Avanzadas** .

![Cuadro de diálogo Filtro avanzado](images/repository-filter-search-advanced.png) {width="650" align="left"}


**General**

- **Search resultados con**: Search para algún texto en los archivos presentes en la ruta seleccionada de la repositorio Adobe Experience Manager. El texto se busca en el título, el nombre de archivo y el contenido de los archivos.

Esto está en sincronizar con el cuadro búsqueda en la ventana repositorio. Por ejemplo, si escribe `general purpose` el cuadro búsqueda en el panel repositorio, también aparece en el cuadro de **diálogo Filtro** Avanzadas y viceversa.

- **Search en**: Seleccione la ruta donde desea búsqueda los archivos presentes en el repositorio Adobe Experience Manager.

**Avanzado**

- **Elementos** DITA: También puede búsqueda valores específicos en los atributos de los elementos DITA especificados.
   - Seleccione **añadir elemento** para agregar los elementos, atributos y valores.
   - Aplique los filtros seleccionados.

- Seleccione **Borrar todo** para borrar todos los filtros aplicados.


- Seleccione el icono **Cerrar filtro** ![cerrar icono](images/close-icon.svg) para cerrar el filtro y volver a la vista de árbol del repositorio.

  >[!NOTE]
  >
  >El administrador del sistema también puede configurar los filtros de texto y mostrar u ocultar otros filtros. Para obtener más información, vea la sección *Configuración de filtros de texto* en Instalar y configurar Adobe Experience Manager Guides as a Cloud Service.
  >
  >Se muestra la lista de archivos filtrados que contienen el texto buscado. Por ejemplo, los archivos que contienen el texto `personal spaceship` se muestran en la captura de pantalla anterior. Puede seleccionar varios archivos de la lista filtrada para arrastrarlos y soltarlos en un mapa abierto para su edición.

**Menú de opciones**

Además de abrir archivos desde el panel izquierdo, también puede realizar muchas acciones mediante el menú Opciones disponible en la vista Repositorio. Verá diferentes opciones, dependiendo de si elige una carpeta, un archivo de tema o un archivo multimedia.

**Opciones para una carpeta**

Puede realizar las siguientes acciones mediante el menú Opciones disponible para una *carpeta* en la vista Repositorio:

![](images/options-menu-folder_cs.PNG){width="550" align="left"}


- **Nuevo**: crea un nuevo tema, mapa o carpeta DITA.

<details>
    <summary> Pasos para crear un tema nuevo </summary>

Pasos para crear un tema nuevo:
1. Seleccione **Nuevo** tema >****.
2. Aparecerá **el cuadro de diálogo Nuevo tema** .

   ![](images/create-topic-dialog.png){width="300" align="left"}

3. En el cuadro de diálogo tema **Nuevo** , proporcione los siguientes detalles:
   - Título del tema.
   - \(Opcional\)* El nombre de archivo del tema. El nombre del archivo se sugiere automáticamente en función del tema Título. Si el administrador ha habilitado nombres de archivo automáticos basados en la configuración de UUID, no verá el campo Nombre.
   - Una plantilla en la que se basará el tema. Por ejemplo, para una configuración predeterminada, puede elegir entre las plantillas en blanco, Concepto, DITAVAL, Referencia, Tarea, Tema, Markdown, Glosario y Solución de problemas. Si la carpeta tiene un perfil de carpeta configurado, solo verá las plantillas de temas que estén configuradas en el perfil de carpeta.

   - Ruta de acceso donde desea guardar el archivo de tema. De forma predeterminada, la ruta de la carpeta seleccionada actualmente en el repositorio se muestra en el campo Ruta.
4. Seleccione **Crear**. El tema se crea en la ruta de acceso especificada. Además, el tema se abre en el Editor para editarlo.

</details>

<details>
<summary> Pasos para crear un nuevo mapa DITA </summary>


Pasos para crear un nuevo mapa DITA:

1. Seleccione **Nuevo** > **mapa DITA**.
2. Se muestra el cuadro de diálogo **Nuevo mapa**.

   ![](images/create-map-dialog.png){width="300" align="left"}

3. En el cuadro de diálogo **Nuevo mapa**, proporcione los siguientes detalles:
   - Título del mapa.
   - *\(Opcional\)* El nombre de archivo para el mapa. El nombre del archivo se sugiere automáticamente en función del título del mapa. Si el administrador ha habilitado nombres de archivo automáticos basados en la configuración de UUID, no verá el campo Nombre.
   - Una plantilla en la que se basará el mapa. Por ejemplo, para una configuración predeterminada, puede elegir entre las plantillas de mapa de libro o de mapa DITA.
   - Ruta de acceso donde desea guardar el archivo de asignación. De forma predeterminada, la ruta de la carpeta seleccionada actualmente en el repositorio se muestra en el campo Ruta.
4. Seleccione **Crear**. El mapa se crea y se añade dentro de la carpeta especificada en el campo Ruta. Además, el mapa se abre en la vista Mapa. Puede abrir el archivo de asignación en el Editor de mapas y agregarle un tema. Para obtener más información sobre cómo agregar temas a un archivo de asignación, vea [Crear un mapa](map-editor-create-map.md#). También puede seleccionar **Abrir en la consola de mapas** para abrir el mapa en la consola de mapas.
</details>

<details>
<summary> Pasos para crear una carpeta nueva </summary>

Pasos para crear una carpeta nueva:

1. Seleccione **Nueva** > **Carpeta**.
2. Se muestra el cuadro de diálogo **Nueva carpeta**.

   ![](images/new-folder-dialog_cs.png){width="300" align="left"}

3. En el cuadro de diálogo **Nueva carpeta**, proporcione los siguientes detalles:
   - Un Título para la carpeta, que se convierte automáticamente en el nombre de la carpeta.
   - Ruta de acceso donde desea guardar la carpeta. De forma predeterminada, la ruta de la carpeta seleccionada actualmente en el repositorio se muestra en el campo Ruta.
4. Seleccione **Crear**. La carpeta se crea y se añade dentro de la carpeta desde la que se ejecutó la opción create folder.

</details>

- **Cargar Assets**: cargue un archivo de su sistema local a la carpeta seleccionada en el repositorio de Adobe Experience Manager. También puede arrastrar y soltar archivos desde su sistema local en su tema de trabajo actual. Esto es muy útil si desea insertar imágenes de su sistema local en su tema.

  ![](images/upload-assets.png){width="300" align="left"}

  Puede seleccionar una carpeta donde desee cargar el archivo y también se muestra un previsualización de la imagen. Si desea cambiar el nombre del archivo, puede hacerlo en el cuadro de texto Nombre de archivo. Seleccione **Cargar** para completar el proceso cargar archivo. Si ha arrastrado y soltado un archivo de imagen sobre un tema, el archivo de imagen se agrega en el artículo y también se carga.

  Si su administrador ha habilitado la opción UUIDs en *XMLEditorConfig*, vista el UUID de la imagen cargada en el **Origen** Propiedad.

  ![](images/uuid-in-source-upload-image_cs.png){align="left"}

- **Buscar archivos en la carpeta**: cambia el enfocar a repositorio búsqueda en que puede introducir el término búsqueda. El búsqueda se realiza en la carpeta seleccionada de la repositorio. También puede aplicar un filtro para devolver Archivos DITA, Imagen Archivos o ambos.

  ![](images/find-files-in-folders-repo-view_cs.png){width="300" align="left"}

  También puede buscar utilizando el UUID de un archivo. En ese caso, los resultados del búsqueda muestran el título del archivo DITA/XML y, en caso de que el archivo sea un archivo de imagen, se muestra el UUID del archivo. En el siguiente ejemplo de búsqueda, se busca el UUID de una archivo de imagen y en los resultados del búsqueda se muestra el UUID del archivo de imagen original y el título del tema del archivo al que se hace referencia a esa imagen.

  ![](images/uuid-repo-search-image-topic-file_cs.png){width="300" align="left"}

- **Contraer**: contrae la carpeta seleccionada en el repositorio.

  >[!NOTE]
  >
  > Utilice el **icono \>** junto a una carpeta para expandirla.

- **añadir a colecciones: agrega la carpeta seleccionada a favoritos**. Puede elegir agregarlo a un colección nuevo o existente.

- **Actualizar**: obtenga una lista nueva de archivos y carpetas del repositorio.
- **Ver en la interfaz de usuario de Assets**: muestra el contenido de la carpeta en la interfaz de usuario de Assets.

**Opciones para un archivo**

Obtenga acceso a distintas opciones en el menú Opciones, dependiendo de si selecciona un archivo multimedia o un archivo DITA. Algunas opciones comunes disponibles para los archivos multimedia y DITA son las siguientes:

- Editar
- Abrir en FrameMaker
- Duplicado
- Bloquear/desbloquear
- Vista previa
- Mover a
- Cambiar nombre
- Eliminar
- Generar
- Descargar como PDF
- Agregar a
- Copiar
- Ver en la IU de Assets
- Propiedades


![menú de opciones de un archivo en la vista del repositorio](images/options-menu-repo-view-file-level.png){width="550" align="left"}

Las distintas opciones del menú Opciones se explican a continuación:

- **Editar**: abra el archivo para editarlo. Si se trata de un archivo .ditamap/.bookmap, se abrirá en el [Editor de mapas](map-editor-advanced-map-editor.md#) para su edición.

- **Duplicate**: utilice esta opción para crear un duplicado o una copia del archivo seleccionado. También tiene la opción de cambiar el nombre del archivo duplicado en la solicitud de recursos duplicados. De forma predeterminada, el archivo se crea con un sufijo \(como nombre de archivo\_1.extensión\). El título del archivo sigue siendo el mismo que el del archivo de origen y el nuevo archivo comienza con la versión 1.0. Todas las referencias, etiquetas y metadatos se copian, mientras que las líneas de base no se copian en el archivo duplicado.
- **Bloquear**: bloquea el archivo seleccionado para editarlo. Si el archivo está bloqueado, al pasar el puntero del mouse (ratón) sobre el icono de bloqueo, se muestra **Bloqueado por usted** si lo ha bloqueado, o **Bloqueado por [nombre de usuario]** si otro usuario lo ha bloqueado.

- **Vista previa**: obtenga una vista previa rápida del archivo (.dita, .xml, audio, vídeo o imagen) sin abrirlo. Puede cambiar el tamaño del panel de vista previa. Si el contenido contiene `<xref>` o `<conref>`, puede seleccionarlo para abrirlo en una nueva pestaña. El título del archivo aparece en la ventana. Si no hay ningún título, aparece el nombre de archivo. Para cerrar el panel **Vista previa**, puede seleccionar el icono de cerrar o seleccionar cualquier lugar fuera del panel.

  ![](images/quick-preview_cs.png){align="left"}

- **Cambiar nombre**: utilice esta opción para cambiar el nombre del archivo seleccionado. Escriba el nombre del nuevo archivo en el cuadro de diálogo **Cambiar nombre del recurso**.
   - Puede cambiar el nombre de un archivo de cualquier tipo.
   - No se puede cambiar la extensión de un archivo.
   - Dos archivos no pueden tener el mismo nombre. Por lo tanto, no puede cambiar el nombre de un archivo por uno que ya exista. Se muestra un error.

- **Mover a**: utilice esta opción para mover el archivo seleccionado a otra carpeta.
   - Puede escribir el nombre de la carpeta de destino o elegir **Seleccionar ruta** para seleccionar la carpeta de destino.
   - Puede mover un archivo de cualquier tipo a cualquier destino dentro de la carpeta Contenido.
   - Dos archivos no pueden tener el mismo nombre. Por lo tanto, no puede mover un archivo a una carpeta en la que ya existe un archivo con el mismo nombre.

  Si intenta mover un archivo a una carpeta en la que existe un archivo con el mismo nombre pero con un título diferente, se muestra el cuadro de diálogo Cambiar nombre y mover archivo y debe cambiar el nombre del archivo antes de moverlo. El archivo movido en la carpeta de destino tiene el nuevo nombre de archivo.

  ![](images/rename-move-asset.png){width="550" align="left"}

  >[!NOTE]
  >
  > También puede arrastrar y soltar un archivo en otra carpeta de destino.

  **Escenarios de exclusión**

  Experience Manager Guides no permite cambiar el nombre de un archivo ni moverlo en los siguientes casos:

   - No puede mover ni cambiar el nombre de un archivo si forma parte de un flujo de trabajo de revisión o traducción.

   - Si cualquier otro usuario bloquea el archivo, no puede cambiarle el nombre ni moverlo, no verá la opción Cambiar nombre o Mover a del archivo.

  >[!NOTE]
  >
  > Si el administrador le ha concedido los permisos sobre una carpeta, solo entonces se mostrarán las opciones **Rename** o **Move to**.

  <details>
    <summary> Cloud Services </summary>

  Al cambiar el nombre o mover cualquier archivo, no se rompen las referencias existentes desde o hacia el archivo, ya que cada archivo tiene un UUID único.
  </details>

- **Eliminar**: utilice esta opción para eliminar el archivo seleccionado. Se muestra un mensaje de confirmación antes de eliminar el archivo.

   - Se muestra un mensaje de confirmación antes de eliminar el archivo.
   - Si no se hace referencia al archivo desde ningún otro archivo, se elimina y se muestra un mensaje de éxito.
   - Si el archivo está bloqueado, no podrá eliminarlo y aparecerá un mensaje de error.

     >[!NOTE]
     >
     > Si el administrador ha impedido la eliminación de archivos bloqueados, solo entonces se muestra el mensaje de error. Para obtener más información, vea la sección *Impedir la eliminación de archivos desprotegidos* en Instalar y configurar Adobe Experience Manager Guides as a Cloud Service.

   - Si el archivo se agrega a una colección, se muestra el cuadro de diálogo **Forzar eliminación** y puede eliminarlo a la fuerza.
   - Si se hace referencia al archivo desde cualquier otro archivo, se **muestra Forzar Eliminar** cuadro de diálogo con el mensaje de confirmación y puede eliminar el archivo por la fuerza:

     ![](images/options-menu-force-delete.png){width="300" align="left"}

     >[!NOTE]
     >
     > Si el administrador ha dado el permiso de eliminación del archivo, se **habilita Forzar Eliminar** . Si no, **se deshabilita Forzar Eliminar** y se muestra un mensaje que indica que no tiene permiso para eliminar los archivos a los que se hace referencia. Para obtener más información, vista *sección Impedir la eliminación de archivos a los que* se hace referencia en la sección Instalar y configurar las guías de Adobe Experience Manager como un Cloud Service.

   - Si elimina un tema al que se hace referencia y ha abierto el archivo que contiene las referencias para su edición, se mostrará la vincular rota del archivo al que se hace referencia.

  >[!NOTE]
  >
  > También puede eliminar el archivo seleccionado de forma similar utilizando la tecla Supr del teclado.

- **Copiar**: puede elegir entre las siguientes opciones:

   - **Copiar UUID**: copie el UUID del archivo seleccionado en el portapapeles.

   - **Copiar ruta**: copie la ruta completa del archivo seleccionado al Portapapeles.

- **Agregar a**: puede elegir entre las siguientes opciones:
   - **Colecciones**: Añade el archivo seleccionado a Colecciones. Puede elegir agregarlo a una colección existente o nueva.

   - **Contenido reutilizable**: agrega el archivo seleccionado a la lista Contenido reutilizable del panel izquierdo.

- **Propiedades**: utilice esta opción para abrir la página de propiedades del archivo seleccionado. También se puede acceder a esta página de propiedades desde la interfaz de usuario de Assets seleccionando un archivo y, a continuación, el icono Propiedades en la barra de herramientas.

- **Abrir en el tablero de mapas**: Si el archivo seleccionado es un mapa DITA, esta opción abre el tablero de mapas.

- **Abrir en la consola** de mapas: En caso de que el archivo seleccionado sea un mapa DITA, esta opción abre la consola de mapas.

- **Editar en Oxygen**: Seleccione esta opción para editar el archivo seleccionado en el plug-in del conector Oxygen. El archivo se abre para su edición.

  >[!NOTE]
  >
  >Póngase en contacto con el equipo de éxito del cliente para activar esta función en el entorno. Esto no está habilitado como parte del soporte predeterminado. Para obtener más información, vista la [sección Configurar la opción para editar en Oxygen](../cs-install-guide/conf-edit-in-oxygen.md) de la Guía de instalación y configuración.


- **Ver en Assets IU**: Utilice esta opción para mostrar un previsualización de un archivo .dita/.xml en el IU Assets. En el caso de un archivo .ditamap/.bookmap, todos los archivos de temas dentro del mapa se muestran en un único Página unificado por vista de página.

- **Descargar como PDF**: Use la opción para generar la salida de PDF y descargarla.

- **Generar**: Utilice la opción para publicar un mapa o temas dentro de un mapa en una página de Sites, un fragmento de contenido o un fragmento de experiencia.

## Mapa

Cuando se selecciona el icono de vista Mapa, se muestra la vista Mapa donde se muestra una lista de temas dentro del fichero de mapa. Si no ha abierto ningún fichero de mapa, la vista Mapa aparecerá en blanco. Al hacer doble clic en cualquier fichero de mapa, se abre el fichero de mapa en esta vista. Puede hacer doble clic en cualquier archivo del mapa para abrirlo en el Editor.

De forma predeterminada, puede ver los archivos por títulos. Al pasar el ratón por encima de un archivo, puede ver el título y la ruta del archivo como información sobre herramientas.

>[!NOTE]
>
>Como administrador, también puede elegir ver el nombre de archivo del mapa principal que está abierto actualmente en la vista de mapa. Seleccione la opción **Nombre de archivo** de la sección **Archivos del editor muestran la configuración** en **Preferencias de usuario**.


Cuando se abre un mapa en la vista de mapa, el título del mapa actual se muestra en el centro de la barra de pestañas. Si el título es demasiado largo, se muestran puntos suspensivos y también puede pasar el ratón por encima del título para ver el título completo en la información del objeto.

Al definir atributos clave para el tema o las referencias de mapa, puede ver el título, el icono correspondiente y la clave en el panel izquierdo. La clave se muestra como `keys=<key-name>`.

![claves en la vista de mapa](images/view-key-title-map-view.png){width="300" align="left"}

Si tiene derechos de edición sobre los archivos de mapa, también podrá editar los archivos. Para obtener más información acerca de cómo abrir y editar un tema a través del mapa DITA, vea [Editar temas a través del mapa DITA](map-editor-advanced-map-editor.md#id17ACJ0F0FHS).

Las siguientes opciones están disponibles para un archivo de asignación en la vista Mapa:

- **Abrir en la consola de mapas**: Abre el archivo de asignación en la consola de mapas.
- **Editar**: abre el archivo de asignación para su edición.
- **Opciones**: abre el menú contextual del archivo de asignación seleccionado.

Puede realizar las siguientes acciones mediante el menú Opciones del archivo de asignación:

![](images/options-menu-map-view_cs.png){align="left"}

- **Editar**: Abra el archivo de mapa para editarlo en el Editor de mapas.

- **Seleccionar todo**: selecciona todos los archivos del mapa.

- **Borrar selección**: anule la selección de los archivos seleccionados en el mapa.

- **Bloquear**: obtenga un bloqueo en los archivos seleccionados en el mapa.

- **Desbloquear**: desbloquea el archivo de mapa y lo pone a disposición para su edición. No revierte los cambios a la versión anterior.

- **Guardar como nueva versión y desbloquear**: crea una versión más reciente y libera el bloqueo de los archivos seleccionados en el mapa.

- **Vista previa**: abre una vista previa del archivo de mapa. En esta vista, todos los archivos de tema del mapa se muestran en una sola vista página a página unificada.

- **Copiar**: puede elegir entre las siguientes opciones:
   - **Copiar UUID**: copie el UUID del archivo de asignación al portapapeles.
   - **Copiar ruta**: copie la ruta completa del archivo de asignación al Portapapeles.

- **Ubicar en el repositorio**: Muestra la ubicación del archivo de asignación en el repositorio \(o DAM\).

- **Agregar a**: puede elegir entre las siguientes opciones:
   - **Colecciones**: agrega el archivo de asignación a las colecciones. Puede elegir agregarlo a una colección existente o nueva.

   - **Contenido reutilizable**: agrega el archivo de asignación a la lista Contenido reutilizable en el panel izquierdo.

- **Propiedades**: utilice esta opción para abrir la página de propiedades del archivo de asignación. También se puede acceder a esta página de propiedades desde la interfaz de usuario de Assets seleccionando un archivo y el icono Propiedades en la barra de herramientas.

- **Abrir tablero de mapas**: abre el tablero de mapas.

- **Ver en la interfaz de usuario de Assets**: úselo para mostrar una vista previa del archivo de mapa en la interfaz de usuario de Assets. En esta vista, todos los archivos de tema del mapa se muestran en una sola vista página a página unificada.
- **Descargar mapa**: Seleccione esta opción para abrir el cuadro de diálogo **Descargar mapa**.

  En el cuadro de diálogo **Descargar mapa**, puede elegir las siguientes opciones:

  **Usar Línea de base**: seleccione esta opción para obtener una lista de las líneas base creadas para el mapa DITA. Si desea descargar el archivo de mapa y su contenido en función de un Línea de base específico, seleccione el Línea de base del menú desplegable lista. Para obtener más información sobre el trabajo con líneas base, vista [Trabajar con Línea de base](./generate-output-use-baseline-for-publishing.md).

  **Aplanar Archivo jerarquía**: Seleccione esta opción para guardar todos los temas y archivos de medios a los que se hace referencia en una sola carpeta.

  También puede descargar el archivo de asignación sin seleccionar ninguna opción. En ese caso, se descargan las últimas versiones persistentes de los temas a los que se hace referencia y los archivos multimedia.

  Después de seleccionar el botón **Descargar**, la solicitud del paquete de exportación de asignación se pone en cola. El cuadro de diálogo **Éxito** se muestra si el paquete se ha creado correctamente.  Puede seleccionar el botón **Descargar** del cuadro de diálogo **Éxito**.

  Recibirá la notificación de mapa listo para descarga si el mapa está listo para descargarse. En caso de que la descarga falle, recibirá la notificación de que la descarga del mapa ha fallado.

  Puede acceder al vínculo de descarga desde la bandeja de entrada de notificaciones de Adobe Experience Manager. Seleccione el notificación de mapa generado en la bandeja de entrada para descargar el mapa en .zip formato.

  >[!NOTE]
  >
  >  De forma predeterminada, las asignaciones descargadas permanecen durante cinco días en la Bandeja de entrada de notificaciones de Adobe Experience Manager.

- **Cerrar contexto de asignación**: Cierra el archivo de asignación.

La siguiente captura de pantalla muestra el menú Opciones de un archivo en la vista de mapa:

![](images/options-menu-file_cs.PNG){align="left"}

Puede realizar las siguientes acciones mediante el menú Opciones:

- **Editar**: abra el archivo para editarlo. En el caso de un archivo .ditamap/.bookmap, se abre en el [Editor](map-editor-advanced-map-editor.md#) de mapas para su edición.

- **Bloquear**: bloquea el archivo seleccionado. Para un archivo bloqueado, esta opción cambia a **Desbloquear**.



  >[!NOTE]
  >
  > - Si un archivo está bloqueado por un usuario, al pasar el puntero del ratón sobre el icono de candado se muestra el usuario \(nombre\) que ha bloqueado el archivo.
  > - Cuando protege un archivo, le pide que guarde los cambios. Si no guarda los cambios, solo se registrará el archivo.

- **Vista previa**: obtenga una previsualización rápida del archivo (.dita, .xml, audio, video o imagen) sin abrirlo. Puede cambiar el tamaño del panel de vista previa. Si el contenido contiene `<xref>` o `<conref>`, puede seleccionarlo para abrirlo en una nueva pestaña.  El título del archivo aparece en la ventana. Si no hay ningún título, aparece el nombre de archivo. Para cerrar el panel **Vista previa**, puede seleccionar el icono de cerrar o seleccionar cualquier lugar fuera del panel.
- **Copiar**: puede elegir entre las siguientes opciones:
   - **Copiar UUID**: copie el UUID del archivo seleccionado en el portapapeles.
   - **Copiar ruta**: copie la ruta completa del archivo seleccionado al Portapapeles.


- **Buscar en el repositorio**: Muestra la ubicación del archivo seleccionado en el repositorio \(o DAM\).
- **Expandir todo**: expanda todos los temas de los archivos de asignación.

- **Contraer todo**: Contraer todos los temas que forman parte del archivo de asignación actual.

- **Agregar a**: puede elegir entre las siguientes opciones:
   - **Colecciones**: agrega el archivo seleccionado a las colecciones. Puede elegir agregarlo a una colección existente o nueva.

   - **Contenido reutilizable**: agrega el archivo seleccionado a la lista Contenido reutilizable del panel izquierdo.

- **Propiedades**: utilice esta opción para abrir la página de propiedades del archivo seleccionado. También se puede acceder a esta página de propiedades desde la interfaz de usuario de Assets seleccionando un archivo y el icono Propiedades en la barra de herramientas.

- **Vista en la interfaz de usuario de Assets**: utilícela para mostrar una vista previa de un archivo .dita/.xml en la interfaz de usuario de Assets. En el caso de un archivo .ditamap/.bookmap, todos los archivos de tema dentro del mapa se muestran en una sola vista página a página unificada.

- **Generar**: genera el resultado del archivo seleccionado en la página de Sites, el fragmento de contenido o el fragmento de experiencia.

>[!NOTE]
>
> También puede abrir y editar las propiedades de los temas seleccionados en un mapa DITA desde el menú **Más opciones** en Referencias.

## Contenido reutilizable

Una de las principales características de DITA es la capacidad de reutilizar contenido. El **panel contenido** reutilizable puede tienda sus archivos DITA desde donde generalmente inserta contenido reutilizables. Una vez añadidos, los archivos DITA permanecen en el panel de contenido reutilizables durante todas las sesiones. Esto significa que no tiene que volver a añadir sus archivos DITA para acceder a ellos más tarde.

Simplemente puede arrastrar y soltar contenido reutilizables desde el panel a su tema actual y se inserta fácil y rápidamente. También puede obtener un previsualización del contenido antes de insertarlo en su documento.

De forma predeterminada, puede vista los archivos por títulos. Al desplazar el cursor sobre un archivo, puede vista el título y la ruta del archivo como información sobre herramientas.

>[!NOTE]
>
> Como administrador, también puede elegir ver la lista de archivos por nombres de archivo en el Editor. Seleccione la opción **Nombre de archivo** de la sección **Archivos del editor muestran la configuración** en **Preferencias de usuario**.

Para añadir un fichero DITA al panel Contenido reutilizable, utilice cualquiera de los métodos siguientes:

- Seleccione el icono **+** junto a Contenido reutilizable para abrir el cuadro de diálogo Examinar archivo. Seleccione el archivo que desea agregar y, a continuación, seleccione **Agregar** para completar el proceso.

- En la vista Repositorio, seleccione el icono **Opciones** del archivo deseado y elija **Agregar a** > **Contenido reutilizable** del menú contextual.

- Haga clic con el botón derecho en la ficha de un archivo en el editor para abrir el menú contextual y elija **Agregar a** > **Contenido reutilizable**.


Una vez agregado el archivo, puede ver todos los elementos de contenido reutilizables del archivo en el panel Contenido reutilizable. El contenido reutilizable se muestra con sus ID y nombres de elementos.

Cuando se agrega un archivo a la lista Contenido reutilizable, se muestra el título del archivo en lugar del UUID del archivo. Para comprobar el UUID del archivo, pase el ratón sobre el título del archivo y el UUID del archivo se mostrará en la información del objeto.

![](images/uuid-reusable-content-file-title_cs.png){width="400" align="left"}

>[!NOTE]
>
> Puede agregar varios archivos a la lista de contenido reutilizable. A continuación, puede insertar el contenido deseado desde el panel Contenido reutilizable en el documento.

**Actualizar**: vuelve a comprobar todo el contenido reutilizable y muestra una lista nueva de contenido reutilizable.

Para insertar contenido desde el panel Contenido reutilizable, utilice cualquiera de los siguientes métodos:

- Pase el puntero del ratón sobre el elemento que quiera insertar, seleccione el icono **Opciones** y elija **Insertar contenido reutilizable** en el menú desplegable.

  ![](images/insert-reusable-content_cs.png){width="400" align="left"}

  >[!NOTE]
  >
  > Seleccione un archivo y, a continuación, seleccione **Vista previa** en el menú **Opciones** para obtener una vista previa del archivo sin abrirlo. También puede obtener una vista previa de las referencias presentes en un tema. La ID de referencia aparece en la ventana.
  >
  > La **opción Vista previa** también está disponible en el **menú Opciones** de un elemento, lo que le proporciona una previsualización rápida del elemento antes de insertarlo.

- Arrastre y suelte el elemento de contenido reutilizable desde el panel en la ubicación deseada de su documento.

## Contorno

Al seleccionar el icono Contorno ****, se obtiene la vista jerárquica de los elementos utilizados en el documento.

![](images/outline-view_cs.png){width="300" align="left"}

La vista de esquema ofrece las siguientes funciones:

- Vista de árbol de todos los elementos utilizados en el documento.

- Si un elemento tiene un ID, un atributo y un texto, puede visualizarlos junto con el elemento.

- Acceda a la vista Esquema en las vistas Autor y Source.

- Utilice la lista desplegable de filtros para mostrar todos los elementos o solo las referencias rotas:

- Al elegir un elemento en la vista Esquema, se selecciona el contenido del elemento en la vista Autor o Source. La vista Esquema permanece sincronizada con la vista Autor y Source. Si realiza cambios en cualquier vista, puede vista en el vista de esquemas. Por ejemplo, si agrega un párrafo o actualiza un elemento en la vista de Autor, se muestra en el vista Esquema.

  ![](images/select-element-content-outline-view_cs.png){width="650" align="left"}

- Arrastre y suelte los elementos. Puede reemplazar fácilmente un elemento soltando otro elemento sobre él. Si arrastra y suelta un elemento sobre otro elemento y ve un cuadro de rectángulo discontinuo alrededor del elemento, esto indica que el elemento será reemplazado. Reemplaza el elemento en el que se coloca el elemento.

  ![](images/replace-element-outline-view_cs.png){align="left"}

  Si arrastra y suelta un elemento, un rectángulo discontinuo indica que el elemento se puede colocar en la ubicación actual. Si la operación de arrastrar y soltar no es válida, se muestra un mensaje de error para indicar que la operación no está permitida.

  ![](images/drop-element-outline-view_cs.png){align="left"}

- El **menú Opciones** del *vista de esquema* permite realizar operaciones genéricas como: Cortar, copiar, Eliminar, generar ID, insertar elemento antes o después del elemento actual, Cambiar nombre o reemplazar un elemento, ajustar un elemento, desajustar un elemento y crear un fragmento del elemento seleccionado.

>[!NOTE]
>
>Para obtener más información sobre Generar ID, Insertar elemento antes o después del elemento actual y Desajustar un elemento vista [Otras funciones del Editor](web-editor-other-features.md#).

**Ver configurar**

Con la **opción Configurar** de Ver, puede elegir vista lo siguiente:

- **ID** de Mostrar: muestra el identificador del elemento.
- **Mostrar atributo**: muestra el atributo junto con su valor.
- **Mostrar texto**: muestra el texto. Si el texto tiene más de 20 caracteres, se muestran puntos suspensivos.

Si un elemento de bloque tiene su propio texto, se muestra junto con ese elemento de bloque. Si no tiene texto propio, el texto del primer elemento secundario se muestra junto con ese elemento de bloque.

![](images/outline-view-block-element.png){width="550" align="left"}

Si el administrador ha creado un perfil para atributos, obtendrá esos atributos junto con sus valores configurados. También puede asignar atributos de visualización configurados por el administrador en la ficha **Atributos de visualización** en **Configuración**. Los atributos definidos para un elemento se muestran en las vistas Diseño y Esquema.


Para obtener más información, vea los *atributos de visualización* en la descripción de la característica *Configuración* del panel izquierdo.

**Característica de búsqueda**

Con la función búsqueda, puede búsqueda para un elemento por su nombre, ID, texto o valor de atributo.

La búsqueda distingue entre mayúsculas y minúsculas y coincide exactamente con la cadena. Los resultados de la búsqueda se ordenan según la posición del elemento en el documento.

Puede buscar una cadena en el elemento si se muestra en la vista **Esquema**. Por ejemplo, si la cadena &quot;Adobe&quot; está presente en el texto del elemento y se muestra en el panel Vista de esquema (como seleccionó **Mostrar texto** en la lista desplegable Opciones de vista), se filtrará el elemento que lo contiene. Sin embargo, si el texto no se muestra en el panel Vista de esquema (ya que no ha seleccionado **Mostrar texto** en la lista desplegable Opciones de vista), el elemento que lo contiene no se filtra. Del mismo modo, encontrará la cadena en el ID o atributos si los ha seleccionado.

## Glosario

Experience Manager Guides le permite crear y utilizar fácilmente documentos del tipo glosario. Puede crear archivos de temas del glosario y luego incluirlos en un mapa del glosario común. Una vez agregado este mapa como mapa raíz, las entradas del glosario se muestran en el panel Glosario.

![](images/glossary-panel.png){width="650" align="left"}

Para insertar un término del glosario, simplemente arrastre y suelte la entrada desde el panel a la ubicación deseada en el tema. El menú Opciones de un término de glosario le permite obtener una **vista previa** rápida del término de entrada, **copiar la ruta** del archivo del término de entrada o localizar el archivo del término de entrada en el repositorio.

<details>
    <summary> Pasos para buscar y reemplazar texto en las abreviaciones del glosario </summary>

Realice los pasos siguientes para búsqueda términos de texto y reemplazarlos por abreviaturas de glosario:

1. Abra el tema o mapa DITA en el que desea búsqueda y convertir el texto o los términos.
1. Seleccione el panel Glosario para vista los términos del glosario presentes en el mapa raíz. Puede arrastrar y soltar estos términos para agregarlos al tema abierto.
1. Seleccione el **punto interactivo** herramienta \( ![](images/hotspot-icon.svg)\) en el panel Glosario para búsqueda y convertir términos de texto específicos a abreviaturas de glosario vinculadas. Además, viceversa, puede usarlo para búsqueda abreviaturas de glosario y convertir a términos de texto.

</details>


Puede configurar las siguientes opciones de la herramienta Punto interactivo:

![](images/glossary-hotspot-tool.png){width="300" align="left"}


- **Claves de glosario**: seleccione las claves de glosario del mapa DITA que desee utilizar para la búsqueda en el tema seleccionado. Las claves seleccionadas se muestran a continuación. Para quitar una clave seleccionada, seleccione el icono **Quitar**.

- **Temas**: elige el **Tema actual** abierto en el Editor, todos los **Temas abiertos** en el mapa actual o el **Mapa actual** que se está editando en el Editor de mapas para buscar los términos.
- **Filtrar temas por estado**: puede optar por limitar la búsqueda a los temas que tengan el estado de documento seleccionado. Los temas pueden estar en estado Borrador, Editar, En revisión, Aprobado, Revisado, Listo o en cualquiera de los estados configurados por la organización.
- **Acción**: puede elegir buscar las claves del glosario **Manualmente para cada tema** o **Automáticamente para todos los temas**. Si elige **Manualmente para cada tema**, se le pedirá que confirme antes de convertir cada término en cada tema. Si elige **Automáticamente para todos los temas**, convertirá automáticamente todos los términos de todos los temas.
- **Convertir**: puede convertir un **texto buscado en un término de glosario** o **término de glosario en texto.**
- **Opciones**: puede seleccionar entre las siguientes opciones:
   - **Coincidencia que distingue entre mayúsculas y minúsculas**: busca un término para encontrar la coincidencia que tiene la misma coincidencia. Por ejemplo, &quot;USB&quot; no coincidirá con &quot;usb&quot;.
   - **Convertir solo la primera instancia**: si hay varias instancias del término buscado en un tema, solo se convierte la primera instancia.
   - **Bloquear archivo antes de la conversión**: el archivo buscado está bloqueado antes de que se conviertan los términos.
   - **Crear una nueva versión después de la conversión**: se crea una nueva versión del tema una vez completada la conversión de términos.
- El botón **Siguiente** aparece si selecciona la opción **Manualmente para cada tema**. Seleccione **Siguiente** para convertir los términos de cada tema en función de la configuración seleccionada. Solicita la conversión de términos en cada tema y se mueve al siguiente archivo. Puede elegir convertir un término u omitirlo y pasar al siguiente.

  ![](images/manual-convert-skip.png){width="300" align="left"}

- **Convertir** botón aparece si selecciona **la opción Automáticamente para todos los temas** . Seleccione **Convertir** para convertir todos los términos que se encuentran en la documento a las abreviaturas del glosario vinculadas.

Se muestra un lista de los **temas actualizados** con los términos convertidos y **los temas con Error** . Pase el ratón sobre el icono de información cerca de Temas con Error para vista los detalles del error.

>[!NOTE]
>
> Actualizar el tema para vista los términos convertidos.

## Condiciones

El panel Condiciones muestra los atributos condicionales definidos por el administrador en el perfil global o de nivel de carpeta. Puede añadir condiciones al contenido simplemente arrastrando y soltando la condición deseada. El contenido condicional se resalta con el color definido para la condición para facilitar la identificación.

También puede aplicar varias condiciones a un elemento arrastrando y soltando varias condiciones en un elemento. Cuando se aplican varias condiciones a un elemento, el panel Propiedades muestra las condiciones aplicadas separadas con una coma.

![](images/multiple-conditions-applied_cs.png){align="left"}

Sin embargo, en el Vista de código las condiciones se separan mediante un delimitador de espacio. Cuando agregue o edite una condición en Vista de código, asegúrese de que haya varias condiciones separadas por un espacio.

>[!IMPORTANT]
>
> La siguiente captura de pantalla es de un usuario con privilegios administrativos. Como usuario con privilegios administrativos, puede agregar, editar y eliminar condiciones. De lo contrario, como autor normal, solo tendrá la opción de aplicar condiciones.

![](images/conditional-content-through-panel_cs.png){align="left"}

Para añadir o definir una condición, seleccione el icono + situado junto al panel Condiciones para que aparezca el cuadro de diálogo Definir condición:

![](images/conditional-panel-create-cond.png){width="400" align="left"}

En la lista Atributo, seleccione el atributo condicional que desea definir, introduzca un valor para la condición y, a continuación, especifique la etiqueta que se muestra en el panel Condiciones. Defina un grupo para la condición. Puede agregar varias condiciones a una grupo. También puede definir un color para la condición. Este color se establece como el color de fondo de la contenido en la que se aplica la condición.

Puede grupo las condiciones y estructurarlas en carpetas anidadas. Los grupos ayudan a crear condiciones en varios niveles y a organizarlas mejor para utilizarlas al contenido.

Por ejemplo, puede crear grupos de condiciones de productos gustar *Acrobat* y *AEM guías*. Puede seleccionar los atributos condicionales para ambos grupos. En cada grupo, puede tener valores específicos gustar Usuario, Administrador, Revisor *y* Autor *.*****

>[!NOTE]
>
> Escriba para crear un nuevo grupo o seleccione un grupo existente para un atributo en particular.

Puede utilizar `/` y definir subgrupos gustar `AEM Guides/Cloud Service`.



![Condtions organizadas en un jerarquía anidado](images/conditions-nested-hierarchy.png){width="300" align="left"}


Para editar una condición, elija **Editar** en el menú Opciones. Se muestra el cuadro de diálogo Condición Editar:

![](images/conditional-panel-edit-cond.png){width="400" align="left"}

Especifique los detalles del mismo modo que se configuraron al definir una nueva condición.

## Régimen del sujeto

Los mapas de esquema de sujeto son una forma especializada de mapas DITA que se utilizan para definir sujetos taxonómicos y valores controlados. Según sus necesidades, puede crear un mapa de esquema de temas y hacer referencia a él dentro del archivo de mapa raíz. Experience Manager Guides le permite definir la jerarquía de nivel anidada de las definiciones de temas en el esquema de temas.

Puede crear y, a continuación, utilizar fácilmente el esquema de asignaturas en un mapa de esquema de asignaturas. Una vez agregado este mapa como mapa raíz, el esquema del asunto se muestra en el panel Esquema del asunto. El panel Esquema del asunto muestra el esquema del asunto disponible de forma anidada o jerárquica.

Experience Manager Guides también admite mapas de esquema de asunto de nivel anidado y puede tener varios esquemas de asunto definidos en el mapa de esquema de asunto raíz.

<details>
    <summary> Uso del esquema de temas en Experience Manager Guides </summary>
El siguiente ejemplo muestra cómo utilizar el esquema de asunto en Experience Manager Guides.

1. Cree un archivo de esquema de temas en una herramienta de su elección. El siguiente código XML crea un esquema de asunto que enlaza los valores del atributo `platform`.

   ```XML
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE subjectScheme PUBLIC "-//OASIS//DTD DITA Subject Scheme Map//EN" "subjectScheme.dtd">
   <subjectScheme id="GUID-4f942f63-9a20-4355-999f-eab7c6273270">
       <title>rw</title>
       <!-- Define new OS values that are merged with those in the unixOS scheme -->
       <subjectdef keys="os">
           <subjectdef keys="linux">    </subjectdef>
           <subjectdef keys="mswin">    </subjectdef>
           <subjectdef keys="zos">    </subjectdef>
       </subjectdef>
       <!-- Define application values -->
       <subjectdef keys="app" navtitle="Applications">
           <subjectdef keys="apacheserv">    </subjectdef>
           <subjectdef keys="mysql">    </subjectdef>
       </subjectdef>
       <!-- Define an enumeration of the platform attribute, equal to       each value in the OS subject. This makes the following values       valid for the platform attribute: linux, mswin, zos -->
       <enumerationdef>
           <attributedef name="platform">    </attributedef>
           <subjectdef keyref="os">    </subjectdef>
       </enumerationdef>
       <!-- Define an enumeration of the otherprops attribute, equal to       each value in the application subjects.       This makes the following values valid for the otherprops attribute:       apacheserv, mysql -->
       <enumerationdef>
           <attributedef name="otherprops">    </attributedef>
           <subjectdef keyref="app">    </subjectdef>
       </enumerationdef>
   </subjectScheme>
   ```

   ![](images/subject-scheme-panel-new.png){width="300" align="left"}

1. Guarde el archivo con la extensión a.ditamap y cárguelo en cualquier carpeta de DAM.

   >[!NOTE]
   >
   > Se puede añadir una referencia al fichero de esquema de asunto en el mapa DITA padre.

   ![](images/subject-scheme-root-map-new.png){width="550" align="left"}

1. Establezca el mapa principal como el mapa raíz en **Preferencias de usuario**. Una vez añadido este mapa como mapa raíz, el esquema de asunto se muestra en el panel Esquema de asunto.

   ![](images/subject-scheme-user-preferences-new.png){width="650" align="left"}


1. En el Editor, abra el archivo donde desee utilizar las definiciones del esquema de temas.
1. Aplicar el esquema de asignatura a su contenido simplemente arrastrando y soltando el esquema de asignatura deseado en su contenido. A continuación, el contenido se resalta con el color definido.
</details>

<details>
    <summary> Gestión de definiciones jerárquicas de definiciones de sujeto y enumeraciones </summary>

Además de manejar las enumeraciones y las definiciones de temas presentes en el mismo mapa, Experience Manager Guías también proporciona la función para definir enumeraciones y definiciones de temas en dos mapas separados. Puede definir una o más definiciones de sujeto en un mapa y las definiciones de lista desglosada en otro mapa y, a continuación, agregar la referencia de mapa. Por ejemplo, el siguiente código XML crea definiciones de tema y definiciones de lista desglosada en dos asignaciones independientes.

Las definiciones del asunto se definen en `subject_scheme_map_1.ditamap`


```XML
  <?xml version="1.0" encoding="UTF-8"?> 
    <!DOCTYPE subjectScheme PUBLIC "-//OASIS//DTD DITA Subject Scheme Map//EN" "../dtd/libs/fmdita/dita_resources/DITA-1.3/dtd/subjectScheme/dtd/subjectScheme.dtd"> 
    <subjectScheme id="subject-scheme.ditamap_f0bfda58-377b-446f-bf49-e31bc87792b3"> 

    <title>subject_scheme_map_1</title> 
    
    <subjectdef keys="os" navtitle="Operating system">
        <subjectdef keys="linux" navtitle="Linux">
        <subjectdef keys="redhat" navtitle="RedHat Linux">
        </subjectdef>
        <subjectdef keys="suse" navtitle="SuSE Linux">
        </subjectdef>
        </subjectdef>
        <subjectdef keys="windows" navtitle="Windows">
        </subjectdef>
        <subjectdef keys="zos" navtitle="z/OS">
        </subjectdef>
        </subjectdef>
        <subjectdef keys="deliveryTargetValues">
        <subjectdef keys="print">
        </subjectdef>
        <subjectdef keys="online">
        </subjectdef>
    </subjectdef>
    <subjectdef keys="mobile" navtitle="Mobile">
        <subjectdef keys="android" navtitle="Android">
        </subjectdef>
        <subjectdef keys="ios" navtitle="iOS">
    </subjectdef>
    </subjectdef>
    <subjectdef keys="cloud" navtitle="Cloud">
        <subjectdef keys="aws" navtitle="Amazon Web Services">
        </subjectdef>
        <subjectdef keys="azure" navtitle="Microsoft Azure">
        </subjectdef>
        <subjectdef keys="gcp" navtitle="Google Cloud Platform">
        </subjectdef>
    </subjectdef>
    </subjectScheme>
```

La definición de la enumeración está presente en    subject_scheme_map_2.ditamap.

```XML
    ?xml version="1.0" encoding="UTF-8"?> 
        <!DOCTYPE subjectScheme PUBLIC "-//OASIS//DTD DITA Subject Scheme Map//EN" "../dtd/libs/fmdita/dita_resources/DITA-1.3/dtd/subjectScheme/dtd/subjectScheme.dtd"> 
        <subjectScheme id="subject-scheme.ditamap_17c433d9-0558-44d4-826e-3a3373a4c5ae"> 
        <title>subject_scheme_map_2</title> 
        <mapref format="ditamap" href="subject_scheme_map_1.ditamap" type="subjectScheme"> 
        </mapref> 
        <enumerationdef>
        <attributedef name="platform">
        </attributedef>
        <subjectdef keyref="mobile">
        </subjectdef>
        <subjectdef keyref="cloud">
        </subjectdef>
        </enumerationdef>
        </subjectScheme>
```

Aquí las definiciones de asunto se definen en `subject_scheme_map_1.ditamap` mientras que la definición de enumeración está presente en `subject_scheme_map_2.ditamap`. La referencia a `subject_scheme_map_1.ditamap` también se agregó en `subject_scheme_map_2.ditamap`.

>[!NOTE]
>
> Como se hace referencia entre sí a `subject_scheme_map_1.ditamap` y `subject_scheme_map_2.ditamap`, los esquemas de asunto se están resolviendo.

Las referencias de enumeración de temas se resuelven en el siguiente orden de prioridad:

1. Mismo mapa
1. Mapa de referencia


Las referencias no se resuelven si la enumeración no se encuentra en el mismo mapa y en el mapa al que se hace referencia.

</details>

<details>
    <summary> Restringir los valores a un elemento específico </summary>


También puede restringir las condiciones a algunos elementos dentro de un tema. Utilice la etiqueta `<elementdef>` para definir el elemento y la etiqueta `<attributedef>` para definir la condición que se puede aplicar al elemento.  Si no agrega la etiqueta `<elementdef>`, puede aplicar las condiciones a todos los elementos.
Por ejemplo, utilice la siguiente enumeración para restringir el atributo `@platform` al elemento `<shortdesc>`.  Las demás condiciones son visibles para todos los elementos.

```XML
<enumerationdef>
    <elementdef name="shortdesc">
    </elementdef>
    <attributedef name="platform">
    </attributedef>
    <subjectdef keyref="deliveryTargetValues">
    </subjectdef>
    <subjectdef keyref="os">
    </subjectdef>
  </enumerationdef>
```

</details>


Lista desplegable de **Atributos**

También puede cambiar el valor del esquema del asunto mediante la lista desplegable **Atributos** del panel **Propiedades del contenido** en la vista **Autor**.

Siga estos pasos para cambiar el valor:

1. Seleccione un atributo del menú desplegable **Atributo**.
1. Seleccione **Editar**.
1. Seleccione el valor requerido de la lista desplegable **Valor**.
1. Seleccione **Actualizar**.

También puede aplicar valores para un atributo seleccionando varios valores en la lista desplegable.

**Vista de Source**

También puede cambiar los valores de la lista desplegable del atributo en la vista de Source. La vista de Source también evita que añada valores incorrectos.

![](images/subject-scheme-code-error.png){width="550" align="left"}

**Ver y aplicar el esquema de asunto desde el panel Condiciones**

También puede ver y aplicar el esquema de asunto desde el panel Condiciones.

Para vista el esquema sujeto desde el panel Condiciones, el administrador del sistema debe seleccionar el **esquema sujeto Mostrar en la opción Panel Condiciones** bajo el pestaña General en Configuración. Para obtener más información, vea la sección **Configuración** en la [barra de fichas](./web-editor-tab-bar.md).

El panel Condiciones muestra la estructura vertical plana de las definiciones de asunto dentro del esquema de asunto.

Puede añadir condiciones al contenido arrastrando y soltando la condición deseada en el contenido. El contenido condicional se resalta con el color definido para la condición.

## Fragmentos de código

Los fragmentos de código son pequeños fragmentos de contenido que se pueden reutilizar en varios temas del proyecto de documentación. El panel Fragmentos de código muestra una colección de contenido fragmentos de código creados. Para insertar un fragmento de código, arrastre el fragmento del panel a la ubicación deseada del tema. El panel Fragmentos de código le permite agregar, editar, eliminar, previsualización e insertar un fragmento de código.

>[!IMPORTANT]
>
> El siguiente captura de pantalla es de un usuario con privilegios administrativos. Como usuario con privilegios administrativos, puede agregar, editar y eliminar fragmentos de código. De lo contrario, como autor normal, solo obtendrá las opciones para previsualización e insertar un fragmento.

![](images/snippets-panel_cs.png){align="left"}

Para agregar un fragmento de código, utilice uno de los métodos siguientes:

- Seleccione el **icono +** junto a Fragmentos para abrir el **cuadro de diálogo Fragmento** Nuevo.

  ![](images/snippet-new-dialog.png){width="300" align="left"}

  En el cuadro de diálogo Fragmento de Nuevo, proporcione un título que aparezca en el panel Fragmentos, una descripción y un código XML del contenido de fragmento que desea crear. Seleccione **Crear** para guardar y crear el fragmento de código.

- En el área de edición de contenido, haga clic con el botón derecho en el ruta del elemento que desea usar como fragmento y elija **Crear fragmento** en el menú contextual. Aparece el cuadro de diálogo Fragmento de Nuevo con el código XML del elemento seleccionado relleno en el **campo Contenido** . Introduzca el Título y la **Descripción** del fragmento y seleccione **Crear** para guardar **el fragmento.**

- En el área de edición de contenido, haga clic con el botón secundario en cualquier lugar del contenido que desee usar como fragmento y elija **Crear fragmento** en el menú contextual. Aparece el cuadro de diálogo Nuevo fragmento con el código XML del elemento seleccionado rellenado en el campo **Contenido**. Escriba **Title** y **Description** para el fragmento y seleccione **Create** para guardar el fragmento.

  La siguiente captura de pantalla resalta la ruta de exploración y el área de contenido desde donde puede invocar el menú contextual.

  ![](images/snippet-create-from-breadcrumb-content.png){width="350" align="left"}


Para insertar un fragmento de código, utilice cualquiera de los métodos siguientes:

- Seleccione un fragmento de código del panel Fragmentos de código y arrástrelo y suéltelo en la ubicación deseada del tema.

- Sitúe el punto de inserción donde desee insertar el fragmento de código; en el menú Opciones del fragmento de código requerido, elija Insertar fragmento de código.


>[!NOTE]
>
> En el menú contextual de una entrada de fragmento de código, también puede elegir Editar, Eliminar, Obtener una vista previa o Insertar un fragmento de código.

## Plantillas

El panel Plantillas solo está disponible para administradores. Con este panel, el administrador puede crear y administrar fácilmente plantillas que luego los autores pueden utilizar. De manera predeterminada, las plantillas se clasifican en las plantillas de tipo *map* y *topic*.

![](images/templates-panel_cs.png){width="300" align="left"}

De forma predeterminada, puede ver los archivos por títulos. Al pasar el ratón por encima de una plantilla, puede ver el título y el nombre del archivo como información sobre herramientas.

>[!NOTE]
>
> Como administrador, también puede elegir ver la lista de archivos en el Editor. Seleccione la opción **Nombre de archivo** de la sección **Archivos del editor muestran la configuración** en **Preferencias de usuario**.

Para aprender a crear plantillas personalizadas, vea [Crear asignaciones basadas en plantillas personalizadas](./create-maps-customized-templates.md).

## Citas

En Experience Manager Guides, puede añadir e importar citas y aplicarlas al contenido. Puede agregar estas citas de cualquier fuente de libros, sitios web y revistas.

Para obtener más detalles, vista [añadir y administrar citas en su contenido](./web-editor-apply-citations.md).

## Idioma variables

Experience Manager Guías proporciona la función para utilizar variables de idioma en la salida PDF nativa. Puede utilizar variables de idioma para definir cadenas localizadas en la salida del PDF o para localizar cualquier texto estático en las plantillas de salida. Puede utilizar estilos CSS para localizar las cadenas procedentes de una CSS.

Para obtener más información, vea [Compatibilidad con variables de idioma](../native-pdf/native-pdf-language-variables.md).

## Variables

Experience Manager Guides le permite crear y administrar variables para la publicación nativa de PDF. Para obtener más información, vea [Variables en la salida de PDF](../native-pdf/native-pdf-variables.md).


## Buscar y reemplazar

El icono Buscar y reemplazar se encuentra en la parte inferior del panel izquierdo. El panel Buscar y reemplazar permite buscar y reemplazar texto en los archivos de un mapa o una carpeta dentro del repositorio. Puede buscar y reemplazar en todos los temas de un mapa, así como los temas presentes en los submapas dentro del mapa.

![](images/map-find-replace.png){align="left"}

De forma predeterminada, puede ver los archivos por títulos. Al pasar el ratón por encima de un archivo, puede ver el título y la ruta del archivo como información sobre herramientas.

>[!NOTE]
>
> Como administrador, también puede elegir ver la lista de nombres de archivo en el Editor. Seleccione la opción **Nombre de archivo** de la sección **Archivos del editor muestran la configuración** en **Preferencias de usuario**.

<details>
    <summary> Realice la búsqueda global y reemplace </summary>


Para realizar el búsqueda y el reemplazo globales, realice los pasos siguientes:

1. Abra el panel global **Buscar y reemplazar** .
1. Seleccione el **menú desplegable Look en** y seleccione una de las siguientes opciones para realizar la búsqueda.

   - **Mapa** actual: Para búsqueda en el mapa abierto actualmente

     >[!NOTE]
     >
     > Esta opción aparece si ya ha abierto un mapa para editarlo.

   - **Ruta**: para búsqueda en la ruta seleccionada
   - **Seleccionar mapa**: Para búsqueda en el mapa seleccionado

1. Puede utilizar la **lista desplegable Opciones** y elegir entre las siguientes opciones:

   - **Bloquear archivo antes de reemplazar**: seleccione esta opción si desea bloquear un archivo automáticamente antes de reemplazar el término búsqueda. Esta opción es más relevante en caso de que el administrador haya habilitado la configuración para bloquear un archivo antes de editarlo. Con la configuración de back-end habilitada, debe seleccionar esta opción. Evitará que el cuadro de diálogo de bloqueo de archivos le solicite que bloquee todos los archivos antes de realizar cualquier cambio. Si no selecciona esta opción, aparecerá un mensaje antes de que se abra un archivo para editarlo.
   - **Sólo palabras completas**: seleccione esta opción si desea buscar toda la cadena de búsqueda. Por ejemplo, si introduce &quot;over&quot; en la cadena de búsqueda, el resultado de la búsqueda devolverá todos los archivos que contengan palabras como &quot;over&quot; e &quot;overview&quot;. Si desea restringir la búsqueda para que devuelva el término exacto introducido, seleccione esta opción.
   - **Crear nueva versión después de reemplazar**: seleccione esta opción si desea crear una nueva versión del tema en el que decida reemplazar el texto. También puede proporcionar comentarios sobre la versión que se agregarán con cada archivo actualizado.

     Si no selecciona esta opción, los cambios se guardan en la versión actual del tema y no se crea ninguna nueva versión.

   - **Incluir referencias indirectas**: seleccione esta opción si desea buscar la cadena en las referencias indirectas también dentro del mapa DITA. De forma predeterminada, esta opción está desactivada, por lo que la búsqueda solo se realiza en las referencias directas.

1. Introduzca el término o texto búsqueda que desee encontrar.
1. Introduzca el texto con el que desea reemplazar el término búsqueda.
1. Pulse Intro o seleccione el icono **Buscar** \( ![](images/search-icon.svg)\) para realizar la búsqueda.
1. Seleccione un archivo de la lista de resultados de la búsqueda. El archivo se abre en el área de edición de contenido con el término buscado resaltado en el contenido.

1. Seleccione **Reemplazar una sola aparición** \( ![](images/replace-icon.svg)\) para reemplazar el término de búsqueda resaltado actualmente en el tema o seleccione Coincidencia siguiente ![](images/next-match-in-search.png) o ![](images/previous-match-in-search.png) Coincidencia anterior para pasar a la siguiente o anterior aparición del texto.
1. Seleccione **Reemplazar todo** \( ![](images/replace-all-in-file-icon.svg)\)para reemplazar todas las apariciones del término buscado en un solo archivo con el término de reemplazo en un solo clic. Se le mostrará un notificación después de reemplazar todas las ocurrencias en el archivo seleccionado.

Para habilitar el icono Reemplazar **todos** , el administrador del sistema debe seleccionar la opción **Habilitar Reemplazar todos** en la **pestaña general** en **Configuración**.

    >[! NOTA]
    >
    > Desplácese sobre un archivo desde la lista de resultado de búsqueda para vista Reemplazar todo en Archivo icono a la derecha. También aparece el icono Ignorar Archivo para eliminar el archivo del resultado de búsqueda. Los archivos que ignora se eliminan de la lista y el término buscado no se reemplaza en ellos.

Solo se puede realizar una operación de reemplazo de todas a la vez en todo el sistema, y hasta que se realice la operación, vista estado &quot;Reemplazar todo en progreso&quot;. También puede anular la operación Reemplazar todo entre medias o ver el informe de registro. Si anula la operación, recibirá una notificación al respecto en la Bandeja de entrada. Se le mostrará una notificación de éxito después de reemplazar todas las ocurrencias en el archivo seleccionado.

![](images/replace-all-in-progress.png){width="300" align="left"}

También puede usar la opción **Buscar en mapa** del menú **Opciones** de un mapa para buscar y reemplazar texto en un mapa. Esta opción aparece para un mapa abierto en el panel del repositorio o en la vista del mapa.

![](images/map-options-menu.png){width="550" align="left"}

</details>

## PDF templates

Permite trabajar con varias plantillas PDF. Para obtener más información, vista [plantillas PDF](../native-pdf/pdf-template.md).

## Revisión

Experience Manager Guías proporciona la función para mostrar todas las tareas de revisión en sus proyectos. Puede vista todos los proyectos de revisión y las tareas de revisión activas dentro de los proyectos de revisión, de los que forma parte desde el **panel de revisión** .  A continuación, puede abrir las tareas de revisión para vista la comentarios de los distintos revisores.

El panel de revisión muestra las tareas de revisión. De forma predeterminada, puede vista los archivos por títulos. Al desplazar el cursor sobre un archivo, puede vista el título y la ruta del archivo como información sobre herramientas.

>[!NOTE]
>
> Como administrador, también puede elegir vista la lista de archivos por nombres de archivo en el Editor. Seleccione la **opción Archivo nombre** de la **sección de configuración** de visualización de archivos del editor en **preferencias** de usuario.

Como autor, puede abordar los comentarios de un tema mediante el Editor.

<details>
    <summary> Pasos para revisar comentarios </summary>


Para vista el comentarios de revisión en las tareas de revisión activas que están presentes en sus proyectos, realice los siguientes pasos:

1. Seleccione Revisar en el panel izquierdo. Se abre el **panel de revisión** .  Se muestran todos los proyectos de revisión y las tareas de revisión activas dentro de los proyectos de revisión de los que forma parte.

   ![](images/web-editor-review-panel.png){width="300" align="left"}
1. Seleccione un proyecto de revisión y, a continuación, seleccione una tarea de revisión de la lista para abrirla.
1. También puede filtrar sus proyectos de las siguientes maneras:

   - Escriba el término de búsqueda o el texto que desee encontrar en el título del proyecto. A continuación, pulse Intro para realizar la búsqueda. Por ejemplo, puede buscar todos los proyectos con el término &quot;espacio&quot; en el título.

   - Seleccione ![](images/filter-search-icon.svg) para abrir el cuadro de diálogo **Filtro**. Puede seleccionar todos los proyectos o solo los específicos. Los proyectos seleccionados se enumeran en el panel **Revisar**.

     ![](images/active-review-select-project.png){width="300" align="left"}

     Habilite la opción **Tareas iniciadas por mí** para ver solamente las tareas que ha iniciado. El estado de alternancia de esta opción se mantiene incluso después de actualizar la página. Habilite la opción **Mostrar solo las tareas activas** para filtrar la lista de proyectos y mostrar las tareas que estén activas actualmente.

1. De forma predeterminada, en el proyecto de revisión verá una lista plana de temas que tienen comentarios asociados. Aplique los filtros necesarios del carril izquierdo para filtrar los temas en función de los comentarios de revisión presentes en ellos:

   - **Ver todos los temas**: enumera todos los temas presentes en los proyectos.
   - **Ver temas con comentarios**: enumera solamente los temas que contienen comentarios de revisión.
1. También puede introducir el término de búsqueda o el texto que desee encontrar en el título del tema o en la ruta de archivo. Se enumeran los temas que contienen el término en el título o la ruta de acceso del archivo.
1. Haga doble clic en cualquier tema para abrirlo en la vista Autor. Puede ver los comentarios en el panel **Comentarios**.

   ![](images/active-review-task-comments.png){align="left"}

   >[!NOTE]
   > 
   > El panel **Revisar** y el panel **Comentarios** están sincronizados en todo momento. En el panel Comentarios, los comentarios se cargan en función de la tarea de revisión cargada en el panel Revisar.
   >Puede vista las tareas de revisión cerradas en el carril izquierdo del Panel de revisión junto con las tareas de revisión activas.
   >Además, para un tarea de revisión cerrada, puede vista el comentarios de revisión en el panel Comentarios de la derecha, pero los **botones Importar Comentarios** y **Revertir Versión** están desactivados.
   >Para obtener más información acerca de cómo abordar el comentarios, vista [Revisión de direcciones comentarios](review-address-review-comments.md#).

</details>

**Tema principal:**[ Introducción al editor](web-editor.md)
