---
title: Añadir y administrar citas en el contenido
description: Añada y administre citas en AEM Guides. Aprenda a aplicar, importar, filtrar, buscar, cambiar el estilo de las citas, editar, previsualizar, insertar, eliminar y generar resultados de contenido con citas.
exl-id: 685d747d-e017-4350-a6bf-822fd55c76e8
feature: Authoring, Features of Web Editor
role: User
source-git-commit: b8f3756e0e8f0338942efb77f00600703be8f6d8
workflow-type: tm+mt
source-wordcount: '1890'
ht-degree: 0%

---

# Añadir y administrar citas en el contenido

Las citas son referencias a la fuente de información agregada al contenido. Mediante citas, puede dar crédito a los autores de la información de origen y ayudar a los lectores a realizar un seguimiento de la información de origen. Añadir citas hace que su contenido sea más confiable y evita el plagio. También le permiten mostrar contenido bien investigado.

En Adobe Experience Manager Guides, puede añadir e importar citas y aplicarlas al contenido. Puede añadir estas citas desde cualquier fuente de libros, sitios web y diarios.


Experience Manager Guides le ayuda a editar, previsualizar y ordenar sus citas. Después de añadir las citas al contenido, puede generar la salida con Native PDF. También puede añadir la página de bibliografía o referencias en la salida nativa de PDF.

Experience Manager Guides admite varios estilos de citas, como Modern Language Association (MLA), American Psychological Association (APA), Chicago, Institute for Electrical and Electronics Engineers (IEEE) y American Heart Association (AHA). La recomendación es utilizarlas de forma clara y coherente.


>[!NOTE]
>
>Actualmente, Experience Manager Guides solo admite PDF nativo para las citas.


## Añadir citas

Para añadir citas, siga estos pasos:

1. Seleccione el icono **Citas** ![icono de citas](images/citations-icon.svg) en el panel izquierdo.

   Se abre el panel **Citas**.

   ![](images/citation-panel.png){width="350" align="left"}

1. En el panel **Citas**, seleccione ![Agregar icono](images/Add_icon.svg). Desde el menú desplegable puede elegir añadir una nueva cita o importar una cita.

1. Seleccione **Nueva cita** para agregar una nueva cita.

   Se abre el cuadro de diálogo **Agregar cita**.

   ![panel de citas en el editor web](images/citation-add.png) {width="300" align="left"}


1. Rellene los campos del cuadro de diálogo **Agregar cita**.

   >[!NOTE]
   >
   >También puede añadir el ISBN o DOI o PubMed ID. AEM Guides rellena los demás campos automáticamente.

   | Libro | Sitio web | Diario |
   | --- | ---|---|
   | **Source** <br> En la lista desplegable, seleccione el origen de la cita como un libro. | **Source**<br> En el menú desplegable, seleccione el origen de la cita como sitio web. | **Source** <br> En la lista desplegable, seleccione el origen de la cita como diario. |
   | **Buscar por** <br> Seleccione **ISBN** o **DOI** de la lista desplegable para buscar el ID digital vinculado a la cita.  <br> DOI: Identificador de objeto digital <br> ISBN: Identificador de libro numérico único | **Buscar por** <br> Seleccione **DOI** de la lista desplegable para buscar el ID digital vinculado a la cita. | **Buscar por** <br> Seleccione **DOI** o ID de PubMed de la lista desplegable para buscar el ID digital vinculado a la cita. <br>  <br> |
   | **Autor** <br> Agregue el nombre y los apellidos del autor de la cita. Seleccione ![](images/Add_icon.svg) para agregar más nombres. | **Autor** <br> Agregue el nombre y los apellidos del autor de la cita. Seleccione ![](images/Add_icon.svg) para agregar más nombres. | **Autor** <br> Agregue el nombre y los apellidos del autor de la cita. Seleccione ![](images/Add_icon.svg) para agregar más nombres. |
   | **Título** <br> Agregue el título del libro. | **Título** <br> Agregue el título de la página web. | **Título** <br> Agregue el título del artículo. |
   | **Editor** <br> Agregue el editor del libro. | **Nombre del sitio web** <br> Agregue el nombre del sitio web. | **Título del diario** <br> Agregue el título del trabajo en el que se encuentra el artículo. |
   | **Edición** <br> Agrega la edición del libro. | **URL** <br> Agregue el vínculo web del sitio web para examinar el contenido. | **Año** <br> Agregue el año en que se publica el artículo. |
   | **Ciudad** <br> Agregue la ciudad de la publicación. | **Fecha de acceso**<br> Agregue la fecha en la que se accede al contenido del sitio web. | **Volumen** <br> Agregue el volumen del trabajo en la serie. |
   | **Editor** <br> Agregue el nombre del editor del libro. | **Fecha de publicación** <br> Añada la fecha en la que se publica el contenido del sitio web. | **Número** <br> Agregue el número del volumen dentro de la serie. |
   | **Año** <br> Agrega el año en que se publica el libro. | **Fecha de actualización** <br> Añada la fecha en la que se actualiza el contenido del sitio web. | **Páginas** <br> Agregue el número de página o el intervalo de páginas en el que se encuentra el artículo. |
   | **Versión** <br> Agregue la versión del libro. | **ID único** <br> Agregue un ID único para la cita. Un ID único es un identificador único para esa cita. | **URL** <br>Agregue el vínculo web al diario. |
   | **Serie** <br>Agrega la serie del libro. |  | **ID único** <br> Agrega un ID único para la cita. Un ID único es un identificador único para esa cita. |
   | **URL** <br> Agregue el vínculo web al libro. |
   | **ID único** <br> Agregue un ID único para la cita. Un ID único es un identificador único para esa cita. |

1. Seleccione **Listo**.

   Se agrega una nueva cita al panel Cita.

>[!NOTE]
>
> Es obligatorio añadir un ID único para el campo de cita.  No puede cambiar el ID único una vez que se agrega la cita.

## Importar citas

Para importar citas, siga estos pasos:

1. En el panel izquierdo, seleccione **Citas** ![icono de citas](images/citations-icon.svg).

   Se abre el panel **Citas**.

1. En el panel **Citas**, seleccione ![Agregar icono](images/Add_icon.svg) y, a continuación, seleccione **Importar** en el menú desplegable.
1. Examine un archivo .bib de su sistema e impórtelo

   >[!TIP]
   >
   > La extensión .bib es un archivo de base de datos bibliográfica BibTeX. Es un archivo de texto especialmente formateado que enumera referencias sobre una fuente de información en particular.

   Una vez que el archivo se haya importado correctamente, puede ver las referencias en el panel de citas.

   >[!NOTE]
   > <ol><li> Experience Manager Guides importa solo las citas que son únicas y no están presentes.
    &gt; <li> Experience Manager Guides puede importar citas de un libro, una revista o un sitio web. Actualmente no admite citas de otras fuentes.

## Administrar citas

Las citas se ordenan alfabéticamente en el panel izquierdo. Busque las citas según las fuentes que se utilizarán en el tema.

### Filter

Seleccione el icono **Filter** ![](images/filter-search-icon.svg) que está junto a la barra de búsqueda y seleccione las opciones de origen en la lista desplegable para filtrar la lista de citas. Permite selecciones únicas y múltiples.

* **Todas las fuentes**: muestra una lista completa de citas, incluidas todas las fuentes.

* **Libro**: Muestra la lista de citas que provienen de libros.

* **Sitio web**: muestra la lista de citas procedentes de sitios web.

* **Diario**: muestra la lista de citas procedentes de diarios.

### Búsqueda

Busca en la cita tu contenido.

1. En el panel izquierdo, seleccione Citas.
Se abre el panel **Citas**.

1. Utilice la barra de búsqueda para buscar la cita adecuada de una lista larga.

### Cambiar estilo de cita {#change-citation-style}

El administrador del sistema puede cambiar el estilo de las citas en el menú desplegable **Citas** de la ficha **General** en **Configuración**.
Estos estilos determinan la forma en que aparecen las citas en el panel de vista previa o en la salida nativa de PDF.

Las siguientes opciones están disponibles en la lista desplegable:

| MLA | APA | Chicago | IEEE | AHA |
|---|---|---|---|---|
| Estilo de asociación de idioma moderno <br> | American Psychological Association Style | Manual de estilo de Chicago | Instituto de Ingenieros Eléctricos y Electrónicos Estilo | American Heart Association Style |
| Ejemplo: <br> Crawford, Claire, etc. *Contenido emocional de recuerdos oscuros*.Editado por Memory, vol. 16, 2010, Amsterdam. | Ejemplo: <br> Crawford, C., J., &amp;, C. (2010). *Contenido emocional de recuerdos oscuros* (505-16 ed.). 10,1080/ 09658210902067289 | Ejemplo: <br> Crawford, Claire, etc. *Contenido emocional de recuerdos oscuros*. 505-16, 2010. | Ejemplo: <br> C. Crawford, J. , y C. , *Contenido emocional de recuerdos oscuros*. Amsterdam, 2010. | Ejemplo: <br> C. Crawford, J. , y C. , *Contenido emocional de recuerdos oscuros*. Amsterdam, 2010. |


## Editar una cita

Para editar la cita, siga estos pasos:

1. Pase el ratón sobre el nombre de la cita de la lista. Seleccione ![](images/options.svg) el icono **Opciones**.

1. Seleccione **Editar**.

Se abre el cuadro de diálogo **Editar cita**.

1. Efectúe las modificaciones necesarias. Seleccione **Listo**.
La cita seleccionada se edita.

>[!NOTE]
>
>No puede cambiar el ID único una vez que se agrega la cita.

## Previsualización de una cita

Para obtener una vista previa de una cita, siga estos pasos:

Pase el ratón sobre el nombre de la cita de la lista. Seleccionar     Icono ![](images/options.svg) **Opciones**.

1. Seleccionar **vista previa**.
Puede obtener una vista previa del contenido y el formato de la cita en el panel de vista previa.

   >[!NOTE]
   >
   >La vista previa se basa en el estilo de cita que el administrador haya seleccionado en **Configuración**.

1. Seleccione cualquier lugar de la pantalla para cerrar el cuadro de vista previa.

   ![](images/citation-preview.png){width="550" align="left"}

>[!NOTE]
>
> También puede obtener una vista previa de una cita insertada en un tema desde la interfaz de usuario de Assets o la pestaña Vista previa del editor.

## Inserción de citas

Siga estos pasos para insertar citas a un tema:
1. Seleccione el tema en el panel del repositorio y, a continuación, haga doble clic para abrirlo en la ventana de edición.
1. Coloque el cursor en la ubicación del tema donde desee agregar la cita.



Puede insertar citas al tema desde la barra de herramientas principal o el panel izquierdo.

### Desde la barra de herramientas principal

1. Seleccione el icono de **citas** ![citas ](images/citations-icon.svg) en la barra de herramientas principal.
1. En el cuadro de diálogo **Citas**, elija la cita. También puede seleccionar varias citas.
   ![cuadro de diálogo de cita](images/citation-dialog-main-toolbar.png){width="300" align="left"}
1. Puede filtrar las citas escribiendo los primeros alfabetos en el panel de búsqueda del cuadro de diálogo **Cita**.

1. Seleccione **Listo**.
La cita seleccionada se agrega en la ubicación del cursor en el tema.


### Desde el panel izquierdo

>[!NOTE]
> 
>Para ver el icono **Citas** desde el panel izquierdo, el administrador del sistema debe habilitar la opción **Citas** en la pestaña **Paneles** en **Configuración**.

1. Seleccione **Citas** ![icono de citas ](images/citations-icon.svg) en el panel izquierdo.
1. Arrastre la cita del panel **Citas** y suéltela en el lugar apropiado del tema.

   También puede seleccionar **Insertar** de ![](images/options.svg) **Opciones** para insertar una cita.

   ![insertar citas](images/citation-panel-insert.png)
1. Para seleccionar varias citas, haga clic con el botón derecho en una cita del tema y seleccione **Modificar cita** en el menú contextual.
1. Seleccione las citas que desee insertar en el cuadro de diálogo **Cita**.
1. Seleccione **Listo** para agregarlos al tema.

Una vez insertadas las citas en el tema, puede obtener una vista previa de las mismas en el Editor Web. También puede publicar contenido con citas mediante PDF nativo.



## Eliminar una cita

Puede eliminar una cita del panel Citas o de un tema en el que haya insertado.

### Eliminar una cita del panel Citas

Para eliminar una cita del panel Citas, siga estos pasos:

1. Pase el ratón sobre el nombre de la cita de la lista.
1. Seleccione el icono ![](images/options.svg) **Opciones**.
1. Seleccione el   **Eliminar** ![](images/Delete_icon.svg).
Se abrirá el cuadro de diálogo de confirmación.
1. Seleccione **Sí**.
La cita seleccionada se elimina del panel de citas.



### Eliminar una cita de un tema

Para eliminar una cita que ya se haya utilizado en el tema, siga estos pasos:

En el tema, coloque el cursor al final de la cita.

1. Haga clic con el botón derecho en una cita del tema y seleccione **Modificar cita** en el menú contextual. Se abre el cuadro de diálogo Cita.
   ![menú contextual de una cita](./images/modify-citation.png)

1. Puede elegir las citas que desee insertar en el documento.

   >[!NOTE]
   >
   >Las citas que ya se utilizan en el tema se sustituyen por las citas que seleccione en el cuadro de diálogo.


1. Seleccione **Listo**.

## Generar salida de contenido con citas

Una vez que haya insertado citas en el tema, puede publicar contenido con citas mediante PDF nativo.

En la salida nativa de PDF, las citas aparecen dentro del contenido en el que las ha insertado. También puede crear una página Bibliografía. Al seleccionar una cita, se le redirige a la página de bibliografía.

Crea un diseño de página de **citas** en las plantillas de PDF e inclúyalo en tu documento. Todas las citas utilizadas en el libro aparecen en una página que aparece en la salida de PDF. Para obtener más información sobre cómo crear un diseño de página, vea [Crear un diseño de página](../native-pdf/components-pdf-template.md#create-page-layout).


Para cambiar la vista y el funcionamiento de la página de citas, vea [Personalizar plantillas de PDF](../native-pdf/pdf-template.md).


### Aplicar estilo de contenido a una cita

Aplique formato a la cita cuando se añada al tema.

1. Seleccione **Hojas de estilo** en el panel **Plantillas** de un ajuste preestablecido de salida de PDF nativo.   Abre el panel **STYLES** que contiene todas las opciones de estilo.

1. En el panel Buscar, busque `<cite>`.

Para obtener más información acerca de los estilos, vea [Trabajar con los estilos de contenido comunes](../native-pdf/stylesheet.md).
