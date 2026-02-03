---
title: Funciones adicionales en el editor
description: Explore otras funciones del editor en Adobe Experience Manager Guides. Aprenda a utilizar estas funciones para mejorar la creación en Experience Manager Guides.
exl-id: 1833b1e3-c7f1-4f2c-be35-235b65ba2f36
feature: Authoring, Web Editor
role: User
source-git-commit: f0ba8dce38a6eef5dedc8a81107c8e31ea6b26b3
workflow-type: tm+mt
source-wordcount: '3653'
ht-degree: 0%

---

# Funciones adicionales en el editor {#id2056B0B0YPF}

Hay otras funciones útiles en el editor que puede utilizar:

## El menú contextual funciona en la ficha de un archivo

Al abrir un archivo en el Editor, puede realizar varias acciones desde el menú contextual. Puede ver distintas opciones dependiendo de si abre un archivo multimedia, un solo archivo DITA o varios archivos.

**Archivo multimedia**

Se obtienen las siguientes funciones en el menú contextual de la pestaña de un archivo multimedia abierto:

![](images/media-file-context-menu.png){width="300" align="left"}


**Archivo DITA único**

Se obtienen las siguientes funciones en el menú contextual de la pestaña de un archivo abierto:

![](images/single-file-context-menu.png){width="400" align="left"}

**Varios archivos**

Cuando tenga varios archivos abiertos, obtendrá más opciones en el menú contextual:

![](images/multiple-files-context-menu.png){width="550" align="left"}

Las distintas opciones del menú contextual se explican a continuación:

***Guardar***: puedes elegir entre las siguientes opciones:

- **Guardar**: para guardar un archivo sin crear una nueva versión, selecciona **Guardar**. Siempre que se crea un tema nuevo, se crea en DAM una copia de trabajo del tema sin versiones. Al guardar el documento, se actualiza la copia de trabajo del documento en DAM. Guardar esta versión no crea una nueva versión de un tema. Si el tema está en revisión, al guardarlo no se concede a los revisores acceso al contenido del tema modificado.

- **Guardar todos**: si hay varios documentos abiertos en el Editor, también tiene la opción de **Guardar todos** los documentos abiertos.


***Guardar como nueva versión***

Para crear una nueva versión del archivo, seleccione **Guardar como nueva versión**. Para obtener más información sobre **Guardar** y **Guardar como nueva versión**, vea la [barra de herramientas en el editor](web-editor-toolbar.md).

***Copiar***: puede elegir entre las siguientes opciones:

- **Copiar UUID**: para copiar el UUID del archivo activo en el portapapeles, seleccione **Copiar \> Copiar UUID**.
- **Copiar ruta**: para copiar la ruta completa del archivo activo en el Portapapeles, seleccione **Copiar \> Copiar ruta**.


***Localizar en***: puede elegir entre las siguientes opciones:

- **Mapa**: Si ha abierto un mapa DITA grande y desea encontrar la ubicación exacta de un archivo en el mapa, seleccione **Buscar en \> Mapa**. Al seleccionar la opción Localizar en mapa, el archivo \(desde donde se invoca la opción\) se encuentra y se resalta en la jerarquía del mapa. Para poder utilizar esta función, debe abrir el archivo de asignación en el Editor. Si la vista de mapa está oculta, al invocar esta función se mostrará la vista de mapa y el archivo se resaltará en la jerarquía de mapas.

- **Explorador**: similar a Buscar en el mapa, el **Buscar en \> Explorador** muestra la ubicación del archivo en el Explorador \(o DAM\). La Vista del explorador se abre y el archivo seleccionado se resalta en el Explorador. Si el archivo se encuentra en una carpeta, esta se expandirá para mostrar la ubicación del archivo seleccionado en el Explorador.

  >[!NOTE]
  >
  >A partir de la versión 2025.11.0, se cambió el nombre de **Repositorio** a **Explorador**. Para la configuración On-Premise, sigue estando disponible como Repositorio hasta la versión 5.1 de Experience Manager Guides.

***Agregar a***: puede elegir entre las siguientes opciones:

- **Colecciones**: para agregar el archivo seleccionado a las colecciones, seleccione **Agregar a \> Colecciones**. Para obtener más información, vea la descripción de la característica **Colecciones** en la sección [Panel izquierdo](web-editor-left-panel.md).

- **Contenido reutilizable**: para copiar el archivo seleccionado en la lista de contenido reutilizable, seleccione **Agregar a \> Contenido reutilizable**. Para obtener más información, vea la descripción de la característica **Contenido reutilizable** en la sección [Panel izquierdo](web-editor-left-panel.md).

***Propiedades***

Para ver la página de propiedades de AEM del archivo seleccionado, seleccione **Propiedades**.

***Split***: puede elegir entre las siguientes opciones:

**Arriba, Abajo, Izquierda o Derecha**

De forma predeterminada, el Editor permite ver un tema a la vez. Podría haber casos en los que desee ver dos o más temas al mismo tiempo. Dividir la pantalla del editor permite ver varios temas al mismo tiempo. Por ejemplo, si tiene dos temas: A y B abiertos en el editor. Al hacer clic con el botón derecho en el tema B y elegir **Dividir \> arriba**, la ventana del editor se divide en dos partes. El tema B se muestra en la mitad superior y el tema A en la mitad inferior. Del mismo modo, también puede dividir la pantalla horizontalmente seleccionando **Dividir \> Izquierda** o **Dividir \> Derecha**. Puede mover los documentos de una pantalla a otra arrastrando la ficha de archivo y soltándola en la pantalla en la que desee colocarla. Del mismo modo, también puede reordenar las pestañas de archivo arrastrándolas y moviéndolas según sus preferencias.



<!--------------------------------------------

***Quick Generate***

Generate the output for the selected file. Output can be generated only for files that are a part of an output preset. For more details, view [Article-based publishing from the Web Editor](web-editor-article-publishing.md#id218CK0U019I).

--->

***Cerrar***: puede elegir entre las siguientes opciones:

**Cerrar**, **Cerrar otros** o **Cerrar todo**

Si desea cerrar el archivo desde el que invocó el menú contextual, seleccione **Cerrar \> Cerrar**. Use **Cerrar \> Cerrar otros** para cerrar todos los demás archivos abiertos excepto el archivo activo. Para cerrar todos los archivos abiertos, seleccione la opción **Cerrar \> Cerrar todo** en el menú contextual o también puede cerrar el Editor. Si hay archivos sin guardar en la sesión, se le pedirá que los guarde.

**Cerrar archivo y guardar escenarios**

Cuando intenta cerrar un archivo abierto en el Editor con el botón **Cerrar** de la ficha del archivo o con la opción **Cerrar** del menú Opciones, Experience Manager Guides le pide que guarde las ediciones y desbloquee un archivo bloqueado.

Las solicitudes se basan en las siguientes configuraciones seleccionadas por el administrador:

- **Pedir desbloqueo al cerrar:** Cuando cierre el editor, tendrá la opción de desbloquear el archivo \(que ha bloqueado\).
- **Solicitar nueva versión al cerrar**: se le da la opción de guardar el archivo \(que ha editado\) como una nueva versión al cerrar el editor.

La experiencia de guardado de archivos dependerá de los tres escenarios siguientes, en los que tenga:

- No se han realizado cambios en el contenido.
- Editó el contenido y guardó los cambios.
- Se editó el contenido, pero no se guardaron los cambios.

Puede ver las siguientes opciones en función de si el archivo está bloqueado/desbloqueado y tiene cambios guardados o no guardados:

- **Desbloquear y cerrar**: se libera el bloqueo del archivo y éste se cierra.
- **Guardar como nueva versión**: esto guardará los cambios realizados en el contenido y creará una nueva versión del archivo. También puede agregar etiquetas y comentarios para la versión recién guardada. Para obtener más información acerca de cómo guardar una nueva versión, vea [Guardar como nueva versión](web-editor-toolbar.md#version-information-and-save-as-new-version).

- **Desbloquear el archivo**: Si decide desbloquear un archivo, liberará el bloqueo del archivo y los cambios se guardarán en la versión actual del archivo.

  >[!NOTE]
  >
  > Si anula la selección de la opción para desbloquear el archivo, también obtiene una opción para cerrar el archivo sin guardar los cambios.

  Por ejemplo, uno de los indicadores se muestra en la siguiente captura de pantalla:

  ![](images/file-close-save-changes-unlock.png){width="400" align="left"}

**Señales visuales para referencias rotas**

Si el tema contiene referencias cruzadas rotas o referencias de contenido, se muestran en texto rojo.

**Copiar y pegar de forma inteligente**

Puede copiar y pegar fácilmente contenido dentro de los temas y entre ellos. La estructura del elemento de origen se mantiene en el destino. Además, si el contenido copiado contiene referencias de contenido, incluso esas se copian.

**Recordar la última ubicación examinada**

El editor proporciona un cuadro de diálogo de exploración inteligente de archivos. El editor recuerda la última ubicación utilizada al insertar una referencia o contenido. La primera vez que invoque el cuadro de diálogo de exploración de archivos \(a través de Insertar referencia o Insertar contenido reutilizado\), se le redirigirá a la ubicación donde se guarde el documento actual. En la misma sesión, si intenta insertar otra referencia, el cuadro de diálogo de exploración de archivos se desplaza automáticamente a la ubicación desde la que insertó la última referencia.

>[!NOTE]
>
> En el caso de un archivo de imagen, audio o vídeo, el cuadro de diálogo de exploración de archivos toma como valor predeterminado la ubicación del archivo y no la última utilizada.

## Examen de archivos y carpetas en Experience Manager Guides

Experience Manager Guides proporciona cuadros de diálogo intuitivos - **Seleccionar archivo** y **Seleccionar ruta** - para ayudarle a examinar y elegir archivos o carpetas dentro del repositorio de contenido de forma eficaz.

>[!NOTE]
>
> El explorador de rutas de archivos y carpetas se introdujo con una interfaz de usuario renovada en la versión 2601 de Experience Manager Guides as a Cloud Service. La nueva interfaz está habilitada de forma predeterminada. Si prefiere seguir utilizando la interfaz de usuario existente sin estas actualizaciones, póngase en contacto con el equipo de éxito del cliente para que se deshabilite esta nueva mejora.

### Exploración de archivos en Experience Manager Guides

El explorador de rutas de archivos permite localizar y seleccionar rápidamente archivos específicos dentro del repositorio de contenido. Esta función está disponible para tareas como añadir un tema a un mapa, vincular una imagen o referencia cruzada, crear contenido reutilizable, etc.

![](images/select-file-dialog-new.png){width="350" align="left"}

Al iniciar el explorador de archivos, se abrirá el cuadro de diálogo **Seleccionar archivo**. Este cuadro de diálogo incluye dos fichas: **Repositorio** y **Colecciones**. La pestaña Repositorio está seleccionada de forma predeterminada.

![](images/select-file.png){width="650" align="left"}

**Funciones disponibles en la ficha Repositorio para examinar archivos**

**Vista tabular de archivos y carpetas**

La pestaña Repositorio proporciona una vista tabular de los archivos y carpetas del repositorio de contenido, lo que facilita la búsqueda de la ruta de archivo correcta. También puede utilizar las rutas de exploración en la parte superior y el panel de navegación de carpetas en la parte izquierda para desplazarse por las carpetas.

![](images/select-file-dialog-navigate-files.png){width="650" align="left"}

**Selección de un solo archivo y de varios**

Para usar un archivo, simplemente selecciónelo y elija **Seleccionar**.

![](images/select-file-single-file-selection.png){width="650" align="left"}

En algunos casos, también puede seleccionar varios archivos en este cuadro de diálogo del explorador de rutas. Por ejemplo, al examinar archivos para buscar contenido reutilizable, puede seleccionar varios archivos y convertirlos en parte del contenido reutilizable.

![](images/select-file-multiple-file-selection.png){width="650" align="left"}

Actualmente, hay disponible una selección múltiple de archivos para contenido reutilizable, referencias de temas, Schematron, ajustes preestablecidos de salida (mediante DITAVAL) y Workfront.

>[!NOTE]
>
> Al seleccionar archivos desde el cuadro de diálogo del explorador de rutas, algunas carpetas pueden aparecer deshabilitadas. Este comportamiento restringe el acceso a tipos de archivo específicos para garantizar que las selecciones sean válidas. Por ejemplo, al crear contenido reutilizable, solo se deben utilizar archivos de tema y de mapa. Para evitar el uso de un tipo de archivo no válido, como una imagen, los archivos correspondientes no se muestran o permanecen desactivados para su selección en el explorador de rutas.

**Previsualizar archivos seleccionados**

Puede obtener una vista previa de los archivos que ha seleccionado mediante el botón **Vista previa**, como se muestra a continuación:

![](images/select-file-preview-button.png){width="650" align="left"}

La vista previa del archivo seleccionado se muestra a la derecha.

![](images/select-file-dialog-preview.png){width="650" align="left"}

Para varias selecciones, se muestra una vista previa de todos los archivos seleccionados en el panel Vista previa para facilitar la revisión.

![](images/reusable-content-selection-left-panel.png){width="650" align="left"}

También puede usar el icono **Quitar** para anular la selección de algunos archivos de la vista previa.

![](images/resusable-content-remove-preview.png){width="650" align="left"}

**Buscar y filtrar la experiencia**

Al examinar los archivos del Repositorio, puede buscar archivos por nombre, título o contenido dentro de la ruta seleccionada. Puede utilizar uno, dos o los tres criterios para la búsqueda. Si no se selecciona ninguno de los criterios, los resultados incluyen elementos comunes a los tres criterios.

![](images/select-file-search.png){width="650" align="left"}

Seleccione el icono **Filtrar búsqueda** \(![Icono de filtro de búsqueda](images/filter-search-icon.svg)\) para abrir el panel Filtro a la derecha.

![](images/select-file-filters.png){align="left"}

Tiene las siguientes opciones para filtrar los archivos y limitar la búsqueda:

- **Buscar en**: seleccione la ruta de acceso en la que desea buscar los archivos presentes en el repositorio.

- **Tipo de archivo**: filtre la búsqueda según un tipo de archivo específico. Las opciones disponibles son: **Tema**, **Mapa**, **DITAVAL**, **Imagen**, **Multimedia**, **Documento** y **Otros**.

  >[!NOTE]
  >
  > En algunos casos, el filtro **Tipo de archivo** se aplica previamente en tipos de archivo específicos según la tarea y no se puede cambiar. Por ejemplo, al buscar una imagen, el filtro se configura para mostrar solo archivos de imagen y, al crear contenido reutilizable, se configura para mostrar solo archivos de tema y de mapa. Puede seguir ajustando otros filtros, como el estado del documento, las etiquetas o la fecha de la última modificación, para restringir los resultados de búsqueda.

- **Estado del documento**: puede filtrar la búsqueda según el estado actual del documento de los archivos. Los valores de filtro disponibles se definen en el campo `repositoryFilters` de `ui_config.json file` y están asociados al perfil de carpeta que está utilizando actualmente.

  Esto significa lo siguiente:

   - Si utiliza el Perfil global, se aplican los valores de filtros configurados en el Perfil global.
   - Si selecciona un perfil de carpeta específico, se recuperan los valores de los filtros definidos en ese perfil.

  Los valores de filtro predeterminados disponibles para el estado del documento son: Borrador, Editar, En revisión, Aprobado, Revisado y Listo. Para obtener detalles sobre cómo personalizar los valores de filtro para los estados de documento, vea [Configurar filtros de estado de documento](../cs-install-guide/config-doc-state-filters.md).

- **Bloqueado por**: muestra una lista de usuarios. La lista se pagina y se carga asincrónicamente, mostrando un conjunto limitado de usuarios a la vez y recuperando más a medida que se desplaza o navega. Esto mejora la velocidad de carga y el rendimiento general, especialmente cuando se trabaja con un gran número de usuarios.

- **Última modificación**: filtre el contenido en función de la fecha de modificación. Seleccione un intervalo de fechas del calendario o elija una de las siguientes opciones de lapso de tiempo:
   - En la última semana
   - En el último mes
   - En el último año

- **Etiquetas**: filtre el contenido según las etiquetas.

- **Elementos DITA**: filtre el contenido en función de varios elementos DITA.

Después de aplicar todos los filtros necesarios, selecciona **Aplicar** en la esquina inferior derecha del panel Filtros.

**Funciones disponibles en la ficha Colecciones para examinar archivos**

La pestaña **Colecciones** proporciona una vista revisada de los archivos disponibles en sus colecciones para acceder y reutilizar rápidamente. A diferencia de la pestaña Repositorio, que muestra la jerarquía de carpetas completa, las colecciones permiten seleccionar temas, mapas e imágenes utilizados con frecuencia sin desplazarse por varias carpetas.

![](images/select-file-collections.png)

En la pestaña Colecciones, puede:

- Utilice las rutas de exploración de la parte superior y el panel de navegación de carpetas de la derecha para navegar fácilmente por sus colecciones.

  ![](images/collections-folder-navigation-panel.png)
- Seleccione los archivos presentes en una ruta de colecciones específica y previsualícela en el panel derecho.

  ![](images/collections-file-preview.png)



### Carpetas del explorador dentro del repositorio

La exploración de carpetas mediante el cuadro de diálogo **Seleccionar carpeta** se centra en seleccionar la ruta de carpeta correcta dentro del Repositorio para tareas como la creación de nuevos temas o la especificación de ubicaciones de salida para el contenido publicado. Ofrece una vista clara y estructurada en árbol de las carpetas, lo que hace que la navegación sea intuitiva y garantiza que el contenido se coloque en la ubicación correcta.

![](images/select-path-dialog-new.png){width="300" align="left"}


## Compatibilidad con la publicación basada en artículos

Desde el Editor, se puede generar la salida para uno o varios temas o para todo el mapa DITA. Es necesario crear ajustes preestablecidos de salida para el mapa DITA y, a continuación, generar fácilmente la salida para uno o más temas. Si ha actualizado algunos temas en el mapa, también puede generar el resultado solo para esos temas desde el Editor. Para obtener más información, vea [Publicación basada en artículos](web-editor-article-publishing.md#id218CK0U019I).

## Compatibilidad con documentos de Markdown

El editor permite utilizar documentos de Markdown \(.md\) junto con documentos DITA. Se puede crear y previsualizar fácilmente un documento Markdown en el editor y añadirlo en el fichero de mapa mediante el editor de mapas DITA. Para obtener más información, vea [Documentos de Markdown del autor desde el editor](web-editor-markdown-topic.md#).

## Compatibilidad con el tema de términos del glosario DITA

El editor admite términos del glosario DITA que se pueden insertar agregando `term` o `abbreviated-form` elementos.

## Trabajo con ecuaciones de MathML

### Insertar ecuaciones de MathML

Experience Manager Guides le ofrece compatibilidad para insertar ecuaciones de MathML mediante la integración con la aplicación [MathType Web](https://docs.wiris.com/en/mathtype/mathtype_web/intro). Para insertar una ecuación de MathML, seleccione el icono **Elemento** y escriba mathml. Cuando selecciona un elemento matemático de la lista, aparece el cuadro de diálogo **Insertar MathML**:

![insertar ecuación matemática en el editor de matemáticas](images/insert-mathml-equation.png){width="550" align="left"}

Con las herramientas de ecuaciones de MathML, cree la ecuación y seleccione **Insertar** para agregarla al documento. La ecuación se inserta con un fondo gris claro.

En cualquier momento puedes actualizar una ecuación haciendo clic con el botón derecho en una ecuación existente y seleccionando **Editar MathML** en el menú contextual.

### Validación de ecuaciones en el editor de MathML

Experience Manager Guides valida las ecuaciones de MathML cuando se guarda un tema que las contiene.
Cuando se inserta una ecuación con el editor de MathML, Experience Manager Guides resalta la ecuación en rojo si hay algún problema de sintaxis. Puede corregirla antes de insertarla. Si no hace ningún cambio pero selecciona **Insertar**, se muestra una advertencia.

![validar ecuación matemática](images/validate-mathml-equation.png){width="400" align="left"}

Si inserta la ecuación de MathML que contiene un error de sintaxis, se produce un error de validación al intentar guardar el tema.


## Insertar notas al pie

Insertar nota al pie en el contenido usando el elemento `fn`. En el modo Autor, el valor de la nota al pie se muestra alineado con el contenido. Sin embargo, cuando cambia al modo Vista previa o publica el documento, la nota al pie aparece al final del tema.


## Cambiar el nombre o reemplazar un elemento

El editor muestra la ruta de exploración del elemento en la parte inferior izquierda del tema. Si desea intercambiar o reemplazar un elemento por otro, puede hacerlo desde el menú contextual de la ruta de exploración. Por ejemplo, puede intercambiar el elemento `p` por `note` o cualquier otro elemento válido en el contexto.

![](images/rename-element.png){width="400" align="left"}

En la ruta de exploración, haga clic con el botón secundario en el nombre de un elemento que desee reemplazar y, a continuación, seleccione Cambiar nombre de elemento en el menú contextual. El cuadro de diálogo Cambiar nombre de elemento muestra todos los elementos válidos permitidos en la ubicación actual. En el cuadro de diálogo Cambiar nombre de elemento, seleccione el elemento que desee utilizar. El elemento original se reemplaza por el nuevo.

Además del menú contextual de la ruta de exploración, también se puede acceder al cuadro de diálogo Cambiar nombre de elemento desde otras ubicaciones:

- Seleccione el nombre del elemento en la ruta de exploración para seleccionar el contenido del elemento y haga clic con el botón derecho en el contenido seleccionado para que aparezca el menú contextual.

- Habilite la vista Etiquetas, seleccione la etiqueta de apertura de cualquier elemento y, a continuación, haga clic con el botón derecho en el contenido seleccionado para que aparezca el menú contextual.

- Puede acceder al cuadro de diálogo Cambiar nombre de elemento invocando el menú Opciones de un elemento del panel Esquema.

## Ajuste y desajuste de un elemento

### Ajustar un elemento

- El ajuste de un elemento permite agregar una etiqueta de elemento al texto seleccionado. El texto se puede ajustar a cualquier elemento secundario según los estándares DITA. Por ejemplo, si tiene texto bajo un elemento `note`, puede ajustar el texto a un elemento `p`.

- La opción **Justificar elemento** está disponible en el menú contextual de la ruta de exploración del tema. Para envolver un elemento, haga clic con el botón derecho en el elemento y abra el menú contextual. Seleccione el elemento del cuadro de diálogo **Justificar elemento**. El texto aparece en el nuevo elemento.

- También puede seleccionar el texto o el elemento del contenido y, a continuación, seleccionar la opción **Justificar elemento** en el menú contextual.

### Desenvolver un elemento

Al desajustar un elemento, puede quitar la etiqueta del elemento del texto seleccionado y combinarlo con su elemento principal. Por ejemplo, si tiene un elemento `p` dentro de un elemento `note`, puede desenvolver el elemento `p` para combinar el texto directamente dentro del elemento `note`. La opción **Desenvolver elemento** está disponible en el menú contextual de la ruta de exploración del tema. Para desenvolver un elemento, haga clic con el botón derecho en el elemento para abrir el menú contextual y, finalmente, seleccione **Desenvolver elemento** para quitar el elemento y combinar el texto del elemento con su elemento principal.

## Gestión de espacios en blanco para elementos DITA

En XML, los espacios en blanco incluyen espacios, tabulaciones, retornos de carro y líneas en blanco. Experience Manager Guides convierte varios espacios en blanco consecuentes en un espacio. Esto le ayuda a conservar la vista de WYSIWYG del Editor.

>[!NOTE]
>
> En algunos elementos en los que es necesario conservar los espacios en blanco según las reglas DITA, se conservan los múltiples espacios en blanco consiguientes. Por ejemplo, `<pre>` y `<codeblock>` elementos.


## Conservación de saltos de línea y sangría

Los elementos DITA que contienen saltos de línea y espacios son compatibles y se representan según su definición en los modos Autor, Source o Vista previa, y también en la salida publicada final. La siguiente captura de pantalla muestra el contenido dentro del elemento `msgblock` en el que se han conservado los saltos y espacios de línea \(sangría\):

![](images/new-line-support_cs.png){align="left"}



## Administrar espacios de no separación en el editor

- Puede insertar espacios de no separación en el documento mediante el icono **Symobol** ![](images/symbol-icon.svg) o las teclas de método abreviado **Alt** + **Espacio**.  Estos espacios de no separación aparecen como un indicador mientras edita un tema en el Editor. Puede desactivar la visualización de los espacios de no separación con la opción **Mostrar indicador de espacio de no separación en el modo Autor** de la pestaña **Apariencia** de [Preferencias de usuario](./intro-home-page.md#user-preferences).

- Si copia y pega contenido con un espacio de no separación de cualquier origen externo en la vista **Autor**, el espacio de no separación se convierte en un espacio.
Sin embargo, si copia y pega contenido con un espacio de no separación de la vista **Autor**, se conservará.


## ID de elemento generado automáticamente

Se pueden generar automáticamente ID para los elementos del tema DITA. Estos ID son únicos dentro de un tema DITA. Por ejemplo, si genera ID para un elemento de párrafo, los ID serán p\_1, p2, p\_3, etc. Puede seleccionar varios elementos y generar ID para cada elemento seleccionado.

Haga lo siguiente para generar automáticamente el ID para uno o varios elementos:

1. Abra el tema en el Editor.
1. Seleccione el contenido al que desea asignar los ID.
1. Haga clic con el botón derecho y seleccione **Generar ID** en el menú contextual.

También puede hacer clic con el botón derecho en la ruta de exploración y seleccionar **Generar ID**.

## Identificación de ID duplicados para elementos en un mapa o tema dentro de la vista Autor

Si un tema o un mapa determinado contiene elementos con ID duplicados, aparecerá el botón **ID duplicados** en la esquina inferior derecha del área de edición de contenido junto a las vistas del editor.

![](images/duplicate-element-IDs.png){width="350" align="left"}

Al seleccionar **ID duplicados**, se abre una ventana emergente con todos los ID duplicados. Puede seleccionar el ID mostrado en la ventana emergente para navegar hasta el elemento correspondiente y actualizarlo con un ID único.

>[!NOTE]
>
> El botón **Identificadores duplicados** solo está disponible en la vista **Autor**, y se permiten identificadores de elementos similares en diferentes temas anidados.


## Gestión de archivos grandes en el editor

A continuación se mencionan las funciones principales destinadas a mejorar el manejo de archivos grandes:

- Para mejorar el rendimiento, se desactivan determinadas funciones como deshacer, rehacer, el panel de contorno y el marcador sucio. Se recomienda desglosar los temas en temas más pequeños para una experiencia óptima.

- Se muestra un mensaje de alerta en la parte superior para los archivos grandes, como se muestra en el siguiente fragmento. Esta alerta resalta el número de elementos en función del valor especificado en el parámetro **largeFileTagCount** del archivo uiconfig.json. De manera predeterminada, **largeFileTagCount** está establecido en 2500.

![](images/add-toast-notification.png){width="600" align="left"}


- Además, el recuento de etiquetas se muestra en la barra inferior de la interfaz. Cuando pasa el ratón sobre este valor de recuento de etiquetas, aparece información del objeto. Al seleccionar la ficha **Más información** se proporcionan detalles sobre cómo administrar archivos grandes.

![](images/add-toast-tag-count.png){width="600" align="left"}


- El mensaje de alerta solo está disponible para archivos DITA y es visible en todas las vistas: Autor, Source y Diseño.

**Tema principal:**[ Introducción al editor](web-editor.md)
