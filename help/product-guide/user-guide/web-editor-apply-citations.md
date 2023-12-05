---
title: Añadir y administrar citas en el contenido
description: AEM Añada y administre citas en Guías de. Aprenda a aplicar, importar, filtrar, buscar, cambiar el estilo de las citas, editar, previsualizar, insertar, eliminar y generar resultados de contenido con citas.
exl-id: 685d747d-e017-4350-a6bf-822fd55c76e8
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1887'
ht-degree: 0%

---

# Añadir y administrar citas en el contenido

Las citas son referencias a la fuente de información agregada al contenido. Mediante citas, puede dar crédito a los autores de la información de origen y ayudar a los lectores a realizar un seguimiento de la información de origen. Añadir citas hace que su contenido sea más confiable y evita el plagio. También le permiten mostrar contenido bien investigado.

AEM En las guías de la, puede agregar e importar citas y aplicarlas al contenido. Puede añadir estas citas desde cualquier fuente de libros, sitios web y diarios.


AEM Guías le ayuda a editar, previsualizar y ordenar sus citas. Después de añadir las citas al contenido, puede generar el resultado con el PDF nativo. También puede añadir la página de bibliografía o referencias en la salida del PDF nativo.

AEM Las guías de la comunidad de datos admiten múltiples estilos de citas, como la Asociación de Lenguaje Moderno (MLA), la Asociación Psicológica Americana (APA), Chicago, el Instituto de Ingenieros Eléctricos y Electrónicos (IEEE) y la Asociación Americana del Corazón (AHA). La recomendación es utilizarlas de forma clara y coherente.


>[!NOTE]
>
>AEM Actualmente, Guías de la solo admite PDF nativos para las citas.


## Añadir citas

Para añadir citas, siga estos pasos:

1. Seleccione el **Citas** ![icono de citas](images/citations-icon.svg) en el panel izquierdo.
El **Citas** se abre el panel.

   ![](images/citation-panel.png){width="300" align="left"}

1. En el **Citas** panel, seleccionar ![Icono Agregar](images/Add_icon.svg). Desde el menú desplegable puede elegir añadir una nueva cita o importar una cita.

1. Seleccionar **Nueva cita** para agregar una nueva cita.
El **Añadir cita** se abre el cuadro de diálogo.

   ![panel de citas en el editor web](images/citation-add.png) {width="300" align="left"}


1. Rellene los campos del **Añadir cita** Cuadro de diálogo.

   >[!NOTE]
   >
   >También puede añadir el ISBN, el DOI o el ID de PubMed. AEM Guías de usuario rellena automáticamente los demás campos de.

   | Libro | Sitio web | Diario |
   | --- | ---|---|
   | **Origen** <br> En la lista desplegable, seleccione la fuente de la cita como un libro. | **Origen**<br> En la lista desplegable, seleccione la fuente de la cita como sitio web. | **Origen** <br> En la lista desplegable, seleccione el origen de la cita como Journal. |
   | **Buscar por** <br> Seleccionar **ISBN** o **DOI** en la lista desplegable para buscar el ID digital vinculado a la cita.  <br> DOI: Identificador de objeto digital <br> ISBN: Identificador numérico único de libro | **Buscar por** <br> Seleccionar **DOI** en la lista desplegable para buscar el ID digital vinculado a la cita. | **Buscar por** <br> Seleccionar **DOI** o PubMed ID de la lista desplegable para buscar el ID digital vinculado a la cita. <br>  <br> |
   | **Autor** <br> Añada el nombre y los apellidos del autor de la cita. Seleccionar ![](images/Add_icon.svg) para agregar más nombres. | **Autor** <br> Añada el nombre y los apellidos del autor de la cita. Seleccionar ![](images/Add_icon.svg)  para agregar más nombres. | **Autor** <br> Añada el nombre y los apellidos del autor de la cita. Seleccionar ![](images/Add_icon.svg)para agregar más nombres. |
   | **Título** <br> Añada el título del libro. | **Título** <br> Añada el título de la página web. | **Título** <br> Añada el título del artículo. |
   | **Editor** <br> Añada el editor del libro. | **Nombre del sitio web** <br> Añada el nombre del sitio web. | **Título del diario** <br> Añada el título del trabajo en el que se encuentra el artículo. |
   | **Edición** <br> Añada la edición del libro. | **URL** <br> Añada el vínculo web del sitio web para examinar el contenido. | **Año** <br> Añada el año en que se publica el artículo. |
   | **Ciudad** <br> Añada la ciudad de la publicación. | **Fecha de acceso**<br> Añada la fecha en la que se accede al contenido del sitio web. | **Volumen** <br> Agregue el volumen del trabajo en la serie. |
   | **Editor** <br> Añada el nombre del editor del libro. | **Fecha de publicación** <br> Añada la fecha de publicación del contenido del sitio web. | **Número** <br> Agregue el número del volumen dentro de la serie. |
   | **Año** <br> Añada el año en que se publica el libro. | **Fecha de actualización** <br> Añada la fecha en la que se actualiza el contenido del sitio web. | **Páginas** <br> Agregue el número de página o el intervalo de páginas en el que se encuentra el artículo. |
   | **Versión** <br> Añada la versión del libro. | **ID único** <br> Añada un ID único para la cita. Un ID único es un identificador único para esa cita. | **URL** <br>Añada el vínculo web al historial. |
   | **Series** <br>Añada la serie del libro. |  | **ID único** <br> Agregue un ID único para la cita. Un ID único es un identificador único para esa cita. |
   | **URL**  <br>  Añada el vínculo web al libro. |
   | **ID único** <br> Añada un ID único para la cita. Un ID único es un identificador único para esa cita. |





1. Seleccionar **Listo**.

   Se agrega una nueva cita al panel Cita.

>[!NOTE]
>
> Es obligatorio añadir un ID único para el campo de cita.  No puede cambiar el ID único una vez que se agrega la cita.

## Importar citas

Para importar citas, siga estos pasos:

1. En el panel izquierdo, seleccione **Citas** ![icono de citas](images/citations-icon.svg).

   El **Citas** se abre el panel.

1. En el **Citas** panel, seleccionar ![Icono Agregar](images/Add_icon.svg), y luego seleccione **Importar** en el menú desplegable.
1. Examine un archivo .bib de su sistema e impórtelo

   >[!TIP]
   >
   > La extensión .bib es un archivo de base de datos bibliográfica BibTeX. Es un archivo de texto especialmente formateado que enumera referencias sobre una fuente de información en particular.

   Una vez que el archivo se haya importado correctamente, puede ver las referencias en el panel de citas.

   >[!NOTE]
   > <ol><li> AEM Las guías de datos solo importan las citas que son únicas y no están presentes.
    &gt; <li> AEM Las guías pueden importar citas de un libro, diario o sitio web. Actualmente no admite citas de otras fuentes.

## Administrar citas

Las citas se ordenan alfabéticamente en el panel izquierdo. Busque las citas según las fuentes que se utilizarán en el tema.

### Filter

Seleccione el **Filtrar** ![](images/filter-search-icon.svg) junto a la barra de búsqueda y seleccione las opciones de origen en la lista desplegable para filtrar la lista de citas. Permite selecciones únicas y múltiples.

* **Todos los orígenes**: Muestra una lista completa de citas, incluidas todas las fuentes.

* **Libro**: Muestra la lista de citas extraídas de libros.

* **Sitio web**: Muestra la lista de citas procedentes de sitios web.

* **Diario**: Muestra la lista de citas procedentes de diarios.

### Búsqueda

Busca en la cita tu contenido.

1. En el panel izquierdo, seleccione Citas.
El **Citas** se abre el panel.

1. Utilice la barra de búsqueda para buscar la cita adecuada de una lista larga.

### Cambiar estilo de cita {#change-citation-style}

El administrador del sistema puede cambiar el estilo de las citas desde el **Citas**  menú desplegable en **Configuración general** en la pestaña **Configuración del editor**.
Estos estilos determinan la forma en que aparecen las citas en el panel de vista previa o en la salida del PDF nativo.

Las siguientes opciones están disponibles en la lista desplegable:

| MLA | APA | Chicago | IEEE | AHA |
|---|---|---|---|---|
| Estilo de asociación de idioma moderno <br> | American Psychological Association Style | Manual de estilo de Chicago | Instituto de Ingenieros Eléctricos y Electrónicos Estilo | American Heart Association Style |
| Ejemplo:<br> Crawford, Claire, et al. *Contenido emocional de recuerdos oscuros*.Editado por Memory, vol 16, 2010, Amsterdam. | Ejemplo: <br> Crawford, C., J. y C. (2010). *Contenido emocional de recuerdos oscuros* (505-16 ed.). 10,1080/ 09658210902067289 | Ejemplo: <br> Crawford, Claire, et al. *Contenido emocional de recuerdos oscuros*. 505-16, 2010. | Ejemplo: <br> C. Crawford, J. , y C. , *Contenido emocional de recuerdos oscuros*. Amsterdam, 2010. | Ejemplo: <br> C. Crawford, J. , y C. , *Contenido emocional de recuerdos oscuros*. Amsterdam, 2010. |


## Editar una cita

Para editar la cita, siga estos pasos:

1. Pase el ratón sobre el nombre de la cita de la lista. Seleccionar  ![](images/options.svg) el **Opciones** icono.

1. Seleccionar  **Editar**.

El **Editar cita** se abre el cuadro de diálogo.

1. Efectúe las modificaciones necesarias. Seleccionar **Listo**.
La cita seleccionada se edita.

>[!NOTE]
>
>No puede cambiar el ID único una vez que se agrega la cita.

## Previsualización de una cita

Para obtener una vista previa de una cita, siga estos pasos:

Pase el ratón sobre el nombre de la cita de la lista. Seleccionar     ![](images/options.svg) **Opciones** icono.

1. Seleccionar **Previsualizar**.
Puede obtener una vista previa del contenido y el formato de la cita en el panel de vista previa.

   >[!NOTE]
   >
   >La vista previa se basa en el estilo de cita que el administrador haya seleccionado en la **Configuración del editor**.

1. Haga clic en cualquier lugar de la pantalla para cerrar el cuadro de vista previa.

   ![](images/citation-preview.png){width="550" align="left"}

>[!NOTE]
>
> También puede obtener una vista previa de una cita insertada en un tema desde la interfaz de usuario de Assets o la pestaña Vista previa del editor web.

## Inserción de citas

Siga estos pasos para insertar citas a un tema:
1. Seleccione el tema en el panel del repositorio y, a continuación, haga doble clic para abrirlo en la ventana de edición.
1. Coloque el cursor en la ubicación del tema donde desee agregar la cita.



Puede insertar citas al tema desde la barra de herramientas principal o el panel izquierdo.

### Desde la barra de herramientas principal

1. Seleccione el **Citas** ![icono de citas ](images/citations-icon.svg) en la barra de herramientas principal.
1. En el **Citas** diálogo, elija la cita. También puede seleccionar varias citas.
   ![diálogo de cita](images/citation-dialog-main-toolbar.png){width="300" align="left"}
1. Puede filtrar las citas escribiendo los primeros alfabetos en el panel de búsqueda del **Cita** Cuadro de diálogo.

1. Clic **Listo**.
La cita seleccionada se agrega en la ubicación del cursor en el tema.


### Desde el panel izquierdo

>[!NOTE]
> 
>Para ver la **Citas** en el panel izquierdo, el administrador del sistema debe seleccionar el icono **Citas** en la opción **Paneles** pestaña en **Configuración del editor**.

1. Seleccionar **Citas** ![icono de citas ](images/citations-icon.svg) en el panel izquierdo.
1. Arrastre la cita desde el **Citas** y suéltelo en la ubicación adecuada del tema.

   También puede seleccionar **Insertar** de  ![](images/options.svg) **Opciones** para insertar una cita.

   ![insertar citas](images/citation-panel-insert.png)
1. Para seleccionar varias citas, haga clic con el botón derecho en una cita del tema y seleccione **Modificar cita** en el menú contextual.
1. Seleccione las citas que desee insertar desde el **Cita** diálogo.
1. Seleccionar **Listo** para agregarlos al tema.

Una vez insertadas las citas en el tema, puede obtener una vista previa de las mismas en el Editor Web. También puede publicar contenido con citas utilizando el PDF nativo.



## Eliminar una cita

Puede eliminar una cita del panel Citas o de un tema en el que haya insertado.

### Eliminar una cita del panel Citas

Para eliminar una cita del panel Citas, siga estos pasos:

1. Pase el ratón sobre el nombre de la cita de la lista.
1. Seleccione el ![](images/options.svg) **Opciones** icono.
1. Seleccione el   **Eliminar** ![](images/Delete_icon.svg).
Se abrirá el cuadro de diálogo de confirmación.
1. Seleccionar **Sí**.
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


1. Seleccionar **Listo**.

## Generar salida de contenido con citas

Una vez que haya insertado citas en el tema, puede publicar contenido con citas mediante el PDF nativo.

En la salida del PDF nativo, las citas aparecen dentro del contenido donde las ha insertado. También puede crear una página Bibliografía. Al hacer clic en cualquier cita, se le redirige a la página de bibliografía.

Crear un **Citas** diseño de página en las plantillas de PDF e inclúyalo en el documento. Todas las citas utilizadas en el libro aparecen en una página que aparece en la salida del PDF. Para obtener más información sobre la creación de un diseño de página, consulte [Crear un diseño de página](../native-pdf/components-pdf-template.md#create-page-layout).


Para cambiar la vista y el aspecto de la página de citas, consulte [Personalizar plantillas de PDF](../native-pdf/pdf-template.md).



### Aplicar estilo de contenido a una cita

Aplique formato a la cita cuando se añada al tema.

1. Seleccionar **Hojas de estilo** en el **Plantillas** panel de un ajuste preestablecido de salida de PDF nativo.   Se abre el **ESTILOS** panel que contiene todas las opciones de estilo.

1. En el panel Buscar, busque `<cite>`.

Para obtener más información sobre los estilos, consulte [Trabajar con los estilos de contenido comunes](../native-pdf/stylesheet.md).
