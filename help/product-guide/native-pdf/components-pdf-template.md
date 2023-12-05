---
title: Función de publicación nativa de PDF | Componentes de una plantilla de PDF
description: Conozca los distintos componentes de una plantilla de PDF y cómo personalizarlos y configurarlos.
exl-id: 0ddb3b81-42ca-4a66-be7d-051a5175d53a
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '4975'
ht-degree: 0%

---

# Componentes de una plantilla de PDF {#components-pdf-template}

Una plantilla de PDF tiene cuatro componentes: Diseños de página, Hojas de estilo, Recursos y Configuración. Puede crear una plantilla personalizando estos componentes individuales y asociando la plantilla con un ajuste preestablecido de salida mientras genera una salida de PDF. Las secciones siguientes tratan en detalle estos componentes y su proceso de personalización.


## Creación y personalización de diseños de página {#create-customize-page-layout}

La configuración del componente Diseños de página permite diseñar la estructura de una página definiendo el encabezado, el pie de página y el área de contenido de una página. Con el editor de diseños de página WYSIWYG, puede crear un diseño de página para diferentes secciones de un PDF, como las páginas de portada y de contraportada, el capítulo, la tabla de contenido (TDC), el índice, la página en blanco, las páginas de materia principal, las páginas de materia secundaria, la lista de figuras (LOF), la lista de tablas (LOT) y el glosario, o crear un diseño para una página personalizada. En la Configuración de la plantilla del PDF, puede asignar un diseño de página con diferentes secciones dentro de un PDF, que luego se utilizan para generar la salida del PDF.

### Crear un nuevo diseño de página {#create-page-layout}

>[!NOTE]
>
>Hay diseños de página de muestra que se envían predefinidos. Puede personalizarlos o crear nuevos diseños de página.

1. En el Editor Web, vaya a **Output** pestaña.
1. Expanda la barra lateral izquierda y haga clic en **Plantillas**.
1. Abra la plantilla con la que desee trabajar.

   >[!NOTE]
   >
   >Puede abrir una plantilla haciendo doble clic en su nombre o haciendo clic en el icono > junto a su nombre.

1. Para crear un nuevo diseño de página, siga uno de estos procedimientos:

   * Pase el ratón sobre **Diseños de página** y haga clic en el icono (*Opciones* icon) **...** y elija **Nuevo diseño de página**.


   * En el **Plantillas** , haga clic en **+** junto a **Plantillas** y elija **Diseño de página** en el menú contextual.


     Esto abre el **Agregar diseño** diálogo.

     <img src="assets/add-layout-2.png" alt="Cuadro de diálogo Agregar diseño" width="250">

1. Especifique un nombre para el nuevo diseño de página.
   >[!NOTE]
   >
   >Evite utilizar caracteres especiales al dar nombre a un diseño de página. Un espacio en el nombre se reemplaza con un guion bajo &quot;_&quot;.

1. Haga clic en **Listo**.

   El nuevo diseño se crea y se agrega en Diseños de página.


### Duplicación de un diseño de página {#duplicate-page-layout}

1. En el **Plantillas** de la plantilla que desea duplicar, haga doble clic en  **Diseños de página** o haga clic en **>** icono antes **Diseños de página**.

   Esto muestra la lista de diseños de página dentro de la plantilla.

1. Pase el ratón sobre el diseño de página que quiera duplicar y haga clic en el icono (*Opciones* icon) **...** y seleccione **Duplicar** en el menú contextual.

1. En el _Duplicar diseño_ , introduzca un nombre para el diseño de página.

1. Clic **Listo**.
Se crea una copia del diseño de página seleccionado y se agrega en Diseños de página.

### Personalizar un diseño de página {#customize-page-layout}

1. En el **Plantillas** de la plantilla que desea editar, haga doble clic en **Diseños de página** o haga clic en **>** icono antes **Diseños de página**.

   Esto muestra la lista de diseños de página dentro de la plantilla.
1. Para personalizar cualquier diseño de página, siga uno de estos procedimientos:
   * Haga doble clic en cualquier diseño de página.
   * Pase el ratón sobre cualquier diseño de página y haga clic en el icono (*Opciones* icon) **...** y seleccione **Editar** en el menú contextual.

   Esto abre el editor de diseño de página para la personalización.
1. Cuando haya realizado los cambios deseados, haga clic en *Guardar todo* (o `Crl+S`).

   Para obtener más información sobre la definición de elementos de diseño individuales como encabezado, pie de página, número de página, título, etc., consulte [Diseño de una página](design-page-layout.md).

## Uso de hojas de estilo para personalizar el PDF {#stylesheet-customization}

La configuración del componente Hojas de estilo permite aplicar estilo a los componentes del diseño de página y al contenido DITA mediante el editor WYSIWYG o trabajar directamente con el archivo CSS. Puede crear sus propios estilos o personalizar las propiedades de estilo predeterminadas. El editor WYSIWYG le permite acceder a la mayoría de las propiedades que necesita para aplicar estilo al diseño de página o al contenido DITA. Para realizar personalizaciones avanzadas, puede trabajar directamente en la vista Código fuente.

### Crear nueva hoja de estilos {#create-stylesheet}

Aunque los archivos CSS se proporcionan para el contenido y el diseño, puede crear una nueva hoja de estilo para aplicar varias personalizaciones a un tipo de estilo específico que luego se pueda aplicar a un componente de destino. De forma predeterminada, los archivos CSS de ejemplo están empaquetados dentro del producto. Estos archivos CSS están pensados para ayudarle a organizar la información de estilo en el contenido y los diseños. Puede elegir combinar estos estilos en un solo archivo CSS o en varios archivos.

De forma predeterminada, cada vez que se crea un nuevo diseño de página, la variable `layout.css` se incluye dentro del nuevo diseño de página. Si desea que el diseño de página contenga estilos de un archivo CSS diferente, simplemente puede arrastrar y soltar el archivo CSS deseado en el área de edición de contenido del nuevo diseño de página. Para comprobar si el archivo CSS se ha incrustado en el diseño de página, cambie a la vista Código fuente y encontrará un vínculo al archivo CSS en la `<head>` Elemento.


Para crear una hoja de estilo, siga los siguientes pasos:
1. En el **Plantillas** , realice una de las siguientes acciones:
   * Pase el ratón sobre **Hojas de estilo** y haga clic en el icono (*Opciones* icon) **...** y elija **Nueva hoja de estilos**.
   * Haga clic en **+** junto a **Plantillas** y elija **Hoja de estilo** en el menú contextual.

   Se abrirá el cuadro de diálogo Agregar hoja de estilo.

   <img src="assets/add-stylesheet.png" alt="Añadir hoja de estilos" width="250">
1. Especifique un nombre para la nueva hoja de estilo.
1. Haga clic en **Listo**.

   Se crea una nueva hoja de estilo y se añade en la sección Hojas de estilo.

### Crear un nuevo estilo {#create-style}

De forma predeterminada, los archivos CSS proporcionados con la plantilla contienen estilos para el encabezado, el párrafo, el carácter, el hipervínculo, la imagen, la tabla, el div, la página y otros estilos. Puede anular el formato de estilo predeterminado o crear uno nuevo.


Puede crear un nuevo estilo para utilizarlo en el diseño de página de la plantilla o aplicar un estilo personalizado para cualquier elemento DITA. Para aplicar estos estilos personalizados al elemento DITA, debe asegurarse de que el nombre de clase del estilo sea el mismo que el nombre del elemento DITA o el `outputclass` atributo.  Por ejemplo, `<div>` en DITA se rige por el `.div {}` en CSS o su `outputclass` atributo. Si usted solicita `<div outputclass="my-div">` en DITA, se rige por el `.div {}` o `.my-div {}` en CSS.



Para crear un nuevo estilo, siga los siguientes pasos:
1. Expanda la barra lateral izquierda y haga doble clic en la plantilla en la que desea crear el estilo.
1. Expanda el **Hojas de estilo** sección. Se abre el **Estilos** panel que contiene todas las opciones de estilo.
1. Seleccione el icono + para añadir un nuevo estilo.

   **Añadir estilo** se abre el cuadro de diálogo.


   <img src="assets/add-style.png" alt="Añadir nuevo estilo" width="500"/>

1. Especifique un **Clase** nombre. Para aplicar un estilo al elemento DITA, asegúrese de que el nombre de clase del estilo es el mismo que el nombre del elemento DITA o el `outputclass` atributo.
1. En el **Etiqueta** (opcional), elija una etiqueta para la que desee crear un nuevo estilo.


1. Seleccione una **Pseudoclase** para aplicar estilo a un elemento. Una pseudoclase le ayuda a definir un estado especial del elemento. Por ejemplo, utilice la pseudoclase para aplicar estilo a un elemento cuando pase el ratón sobre él o cuando se centre sobre él. También puede seleccionar varias pseudoclases. Por ejemplo, puede utilizar la pseudoclase `a::visited {color: blue;}` para aplicar estilo a los vínculos visitados.

1. Añada el selector para el nuevo estilo. El **Selector** Este campo le ayuda a añadir selectores personalizados además de la combinación de Clase, Etiqueta y Pseudoclase. Por ejemplo, puede crear `table a.link` para todos los hipervínculos de una tabla.

   Para obtener más información sobre las etiquetas CSS, consulte [Consulte la gramática de estilo CSS](https://www.w3.org/TR/CSS21/syndata.html#characters).

1. Haga clic en **Listo**.

   Se crea un nuevo estilo y se agrega a la lista de estilos.

### Personalizar un estilo predefinido o nuevo {#customize-style}

Una vez que haya creado un nuevo archivo CSS con estilos predeterminados o desee personalizar estilos en un archivo CSS existente, puede utilizar el editor de estilos para hacerlo.

Para personalizar un estilo, siga los siguientes pasos:
1. Doble clic **Hojas de estilo** o haga clic en **>** icono antes **Hojas de estilo**.

   Muestra los archivos CSS predeterminados (contenido y diseño) y personalizados.
1. Abra una hoja de estilo para editarla.

   Para abrir una hoja de estilo para editarla, siga uno de estos procedimientos:
   * Haga doble clic en el nombre de la hoja de estilo.
   * Pase el ratón sobre el nombre de la hoja de estilo, haga clic en (icono Opciones) ... y seleccione Editar.

   Se abrirá la hoja de estilos para editarla y se mostrará la lista de estilos en el panel Estilos.

   <img src="assets/customize-style.png" alt="Personalizar estilo" width="800">

1. Para personalizar un estilo, selecciónelo para verlo y personalizarlo con el editor Estilos.


### Propiedades de los estilos

En el panel central, puede editar las propiedades, pero puede resultar difícil obtener una instantánea de todos los valores presentes.  El **Propiedades** Este panel proporciona una vista rápida de todos los atributos y valores del estilo.

En el panel central, puede editar las propiedades que se utilizan con más frecuencia, pero no todas las que admite CSS. En el **Propiedades** , puede editar todas las propiedades compatibles con CSS y previsualizarlas. No es necesario cambiar a la vista Código fuente para editar ninguna propiedad.


Obtenga más información acerca del uso del editor de estilos para [trabajar con los estilos de contenido comunes](stylesheet.md).

## Trabajo con recursos {#work-with-resources}

Este es un contenedor para todos los recursos utilizados para diseñar una plantilla. Puede considerarlo como una carpeta, que contiene recursos como imágenes de fondo, fuentes personalizadas, logotipos y mucho más. Cada vez que se añade un recurso a la plantilla, se carga o se registra en la carpeta de recursos. A continuación, puede utilizar estos recursos para personalizar o diseñar las plantillas de PDF.

Para agregar un archivo de recursos a la carpeta Recursos, siga los siguientes pasos:

1. Pase el ratón sobre la pestaña de la carpeta Recursos y haga clic en (icono Opciones) ... y seleccione Importar.

   Se abrirá el cuadro de diálogo Cargar recursos.

   <img src="assets/resources-import-assets.png" alt="Carga de activos" width="300">

   La ruta donde se cargará el archivo de recursos se muestra en la **Seleccionar carpeta de recursos** field.
   >[!NOTE]
   >
   >No puede cambiar la ruta para cargar recursos. De forma predeterminada, todos los recursos se almacenan en la variable `/content/dam/dita-templates/pdf/<PDF-template-name>` carpeta.

1. Clic **Elegir archivos** para examinar el archivo de recursos desde el equipo local

1. Clic **Cargar**.
El archivo seleccionado se importa y se enumera en la carpeta Recursos.

## Configuración avanzada del PDF {#advanced-pdf-settings}

Utilice la sección Configuración para definir la configuración avanzada del diseño de página de PDF, iniciando PDF desde página impar o par, formatos para las referencias cruzadas y habilitando marcas de impresión en el PDF final que se genera con la plantilla.

Para configurarlo, haga clic en **Configuración** en el **Plantillas** para ver las siguientes opciones:

### General

Defina los valores de configuración básicos para iniciar un capítulo desde una página impar o par, la estructura de la tabla de contenido y el formato de línea directriz para las entradas de la tabla de contenido. Puede definir la siguiente configuración:

* **Iniciar cualquier capítulo nuevo desde**: Permite definir cómo se publica cada capítulo en el PDF final. Puede elegir entre una **Nueva página**, **Página impar**, **Página par**, o **Página actual**  opciones. Si decide iniciar un nuevo capítulo desde una página impar, se inserta una página en blanco después de un capítulo que termina en una página impar. Por ejemplo, si el capítulo termina en la página número 15, el proceso de publicación insertará un 16 en blanco<sup>th</sup> para que el nuevo capítulo pueda comenzar desde el 17<sup>th</sup> página.  Si elige la **Página actual** , todos los capítulos se publican como continuación sin saltos de página. Por ejemplo, si un capítulo termina en mitad de la página 15, el capítulo siguiente también se inicia desde la propia página 15.

* **Iniciar cada tema desde una nueva página**: Si desea que cada tema del capítulo comience desde una página nueva, seleccione **Iniciar cada tema desde una nueva página** opción. Si desea que los temas continúen sin espacios en la página, anule la selección de esta opción.

* **Estructura del índice**: permite personalizar la jerarquía de la tabla de contenido. Utiliza la siguiente configuración adicional:

   * **Usar encabezados hasta el nivel**: Permite ajustar el número de niveles de encabezado que se mostrarán en la estructura de TDC del PDF.
   * **No mostrar el número de página del primer nivel en el índice**: seleccione esta opción para ocultar los números de página correspondientes para todos los capítulos que contengan temas anidados o secundarios. Consideremos el siguiente ejemplo en el que se crea una salida sin seleccionar esta opción.

  <img src="assets/page-number-in-toc.png" alt="Carga de activos" width="250">

  En el ejemplo anterior, Configuración avanzada del PDF, Apéndice y Legal son los encabezados de tema o títulos de capítulo de primer nivel. Se asigna un número de página a todos estos encabezados.

  Ahora, si selecciona esta opción y genera la salida, obtendrá la siguiente tabla de contenido:

  <img src="assets/page-number-missing-in-toc.png" alt="Carga de activos" width="250">

  Aquí puede observar que a la configuración del PDF avanzado del primer capítulo no se le asigna ningún número de página, ya que tiene temas anidados o secundarios. Mientras que un número de página si se asigna a Apéndice y Legal porque son temas independientes sin ningún tema secundario.

* **No mostrar el número de capítulo en el índice** : seleccione esta opción para mostrar los nombres de capítulo sin los números de capítulo en la TDC.   De forma predeterminada, los números de capítulo se muestran en la tabla de contenido de la salida del PDF.
* **Formato de directriz**: utilice la lista desplegable para seleccionar líneas directrices de puntos, sólidos o de espacio para conectar los niveles de encabezado a sus números de página correspondientes.
Para aplicar la estructura del índice y los niveles de encabezado de estilo, consulte [Añadir un índice de capítulo](design-page-layout.md#add-chapter-toc).

  >[!NOTE]
  >
  >Si es desarrollador de CSS, puede definir el formato de relleno directamente en el archivo CSS.

* **Usar marcador de continuación de tabla**: seleccione esta opción para definir los marcadores de las tablas largas que se distribuyen en varias páginas.
Puede definir el texto que aparecerá antes y después del salto. Por ejemplo, una tabla se divide en la página 5 y usted define `<Continued on page %page-num%>` para **Texto antes del salto**.  El texto muestra &quot;Continúa en la página 6&quot; al final de la página 5.

  Utilice variables de idioma para definir el texto del marcador de continuación antes y después del salto. Según el idioma elegido, el valor localizado se selecciona automáticamente en la salida del PDF. Por ejemplo, puede publicar `Continued on page %page-num%` como texto en inglés y `Fortsetzung auf Seite %page-num%` en alemán.

  Pase el ratón sobre <img src="./assets/info-details.svg" alt= "icono de información" width="25"> cerca de la opción para ver más detalles al respecto.
* **Vincular términos del glosario a la página del glosario**: seleccione esta opción para mostrar los términos del glosario como hipervínculos en el contenido y vincularlos a los términos de la página del glosario. Esto ayuda a los lectores a ver rápidamente la definición de un término definido en el glosario.

  Para convertir los términos del glosario en hipervínculos, debe:
   * Activar **Glosario** en el **Orden de diseño de página** para un mapa DITA.
   * Agregue el glosario en las páginas de contenido posterior de un mapa del libro.

  Si no habilita la página Glosario, los términos del Glosario del contenido no se convierten en hipervínculos en la salida del PDF.
  <!--For more information on using table continuation markers, see Use table continuation markers.-->

### Diseños de página {#page-layouts}

La configuración de Diseños de página le proporciona un control completo sobre cómo especificar qué diseño de página se utilizará para una sección específica del documento. Por ejemplo, para seleccionar un diseño para la tabla de contenido, haga clic en el menú desplegable situado debajo del campo TDC y seleccione el diseño que ha diseñado para generar la tabla de contenido.

Es importante tener en cuenta que la configuración del mapa de libros tiene prioridad sobre la configuración del diseño de página.

Las siguientes configuraciones están disponibles en la sección Diseño de página:

<img src="assets/template-page-layout.png" alt="Diseños de página" width="550">


**Diseño de página predeterminado**: seleccione un diseño de página que actúe como el diseño predeterminado para todas las páginas del PDF. Este es el diseño de página base que se aplica en las secciones o temas en los que no se ha creado un diseño de página dedicado.

**Diseño de página para diferentes secciones**: puede asignar un diseño de página con las siguientes secciones de la salida del PDF. Si ha diseñado un diseño de página para la sección relacionada, selecciónelo en la lista desplegable. Si no se ha creado ningún diseño de página para una sección específica, se aplica el diseño de página predeterminado.

* **Capítulos y temas**: Puede especificar el diseño de página del para el capítulo y los temas. El diseño seleccionado se aplicará a todos los capítulos y temas.

* **TDC**: Si ha diseñado el diseño de página de la tabla de contenido, seleccione **TDC** en la lista desplegable, y todas las páginas del índice del documento tendrán el diseño de página del índice.

* **Lista de figuras y lista de tablas**: también puede especificar el diseño de página para ilustraciones y tablas. El diseño seleccionado se aplicará a todas las figuras y tablas.

* **Índice**: si ha diseñado un diseño de página Índice, asígnelo a la opción Índice. Con las hojas de estilo, se puede aplicar estilo a diferentes elementos de índice en la salida del PDF. Uso de los estilos de índice `.idx-header`, `.idx-footer`, `.idx-body`, `.idx-title`, `.idx-keyword-group`, `.idx-unit`,  `.idx-keyword`, `.idx-name`, `.idx-link` y `.idx-child` para personalizar los estilos de los elementos del índice.

* **Glosario**: si tiene un diseño de página Glosario, asígnelo a la opción Glosario.

  Los términos del glosario de la salida del PDF siempre se ordenan en orden alfabético.

  También puede añadir la etiqueta `sort-as` para definir un criterio de ordenación para los términos del glosario. A continuación, las guías del Experience Manager utilizan el criterio de ordenación para ordenar los términos del glosario en lugar de los términos del glosario. Si no ha definido el criterio de ordenación, utiliza los términos del glosario para ordenar. Por ejemplo, puede añadir la etiqueta `sort-as` a la `glossterm` y establezca su valor en `A` para el término &quot;USB&quot; (por ejemplo, `<glossterm>USB<sort-as>A</sort-as></glossterm>`). Del mismo modo, puede agregar lo siguiente `sort-as` y establezca su valor en `B` por el término &quot;Pen Drive&quot;. Al ordenar estos términos del glosario, el criterio de ordenación `A` para el glosario, el término &quot;USB&quot; aparece antes del criterio de ordenación `B` para el glosario &quot;Pen Drive&quot;. Por lo tanto, en la salida del PDF, &quot;USB&quot; viene antes de &quot;Pen Drive&quot; en la página del glosario.

  Con las hojas de estilo, puede aplicar estilo a diferentes elementos del glosario en la salida del PDF. Uso de los estilos del glosario `.glo-header`, `.glo-footer`, `.glo-body`, `.glo-title`, `.glo-unit`, `.glo-link`, y `.glo-term` para personalizar los estilos de los elementos del glosario.

  Obtenga más información acerca del uso del editor de estilos para [trabajar con los estilos de contenido comunes](stylesheet.md).

* **Páginas de materia principal y Páginas de materia secundaria**: estos diseños de página definen el estilo de las páginas principales o secundarias del libro. Si ha diseñado el diseño de la materia frontal, asígnelo al **Páginas principales de la materia** opción. Al seleccionar el diseño de la materia frontal en la lista desplegable, el diseño de la materia frontal se aplica a todos los temas presentes en la materia frontal.

  Si ha diseñado el diseño de la materia posterior, asígnelo al **Páginas de materia posterior** opción. Al seleccionar el diseño de la materia posterior en la lista desplegable, el diseño de la materia posterior se aplica a todos los temas presentes en la materia posterior.

  **Páginas principales de la materia** también se utiliza como diseño de reserva para **TDC**, **Lista de figuras** y Lista de tablas.  Del mismo modo, **Páginas de materia posterior** también se utiliza como diseño de reserva para **Índice** y **Glosario** diseños. Si no ha seleccionado el diseño para estas páginas, se aplica el diseño de páginas principales o secundarias seleccionado.  Si no ha seleccionado el diseño Páginas principales o páginas secundarias, se les aplica el diseño de página predeterminado.

* **Diseño de página para páginas vacías**: también puede especificar el diseño de página para las páginas vacías. El diseño seleccionado se aplicará a todas las páginas vacías. Por ejemplo, si ha diseñado un diseño de página en blanco para todas las páginas vacías, seleccione **Vacío** en la lista desplegable y todas las páginas vacías del documento tendrán el diseño Página en blanco.

* **Portada y contraportada**: si ha diseñado un diseño de portada, asígnelo al **Portada** opción. Del mismo modo, si tiene un diseño de página posterior, asígnelo al **Página posterior** opción. Si no se han creado diseños de portada o de página posterior, se aplica el diseño de página predeterminado.



Para obtener más información sobre los diseños de página, consulte [Diseño de una página](design-page-layout.md).

### Orden de diseño de página {#page-order}

Puede mostrar u ocultar las siguientes secciones en el PDF y también organizar el orden en que deben aparecer en la salida final del PDF:



* TDC
* Capítulos y temas
* Lista de figuras
* Lista de tablas
* Índice
* Glosario
* Cita

  <img src="assets/page-order-advance-settings.png" alt="Orden del diseño de página" width="550">

  Si no desea mostrar una sección en particular en la salida del PDF, puede ocultarla desactivando el conmutador.

  También puede definir el orden en que se generan estas diferentes secciones en el PDF. Para cambiar el orden predeterminado de estas secciones, seleccione las barras de puntos para arrastrar y soltar las secciones en la ubicación deseada.

  >[!NOTE]
  >
  > La configuración de orden e inclusión sólo se aplica a un mapa DITA. Para un mapa de libros, esta configuración no es aplicable. Las páginas de un mapa de libros se muestran según el orden de las secciones del mapa de libros.


.
**Capítulo y temas** el diseño siempre está habilitado de forma predeterminada. No puede cambiarlo.

**Combinar páginas**

De forma predeterminada, todas las secciones comienzan en una nueva página. Seleccione el **Página anterior** o **Página siguiente** de la opción **Combinar con** desplegable para combinar una sección con una página anterior o siguiente. Esto publicará la sección como continuación con la página seleccionada en la salida del PDF. Con esto, no habrá ningún salto de página entre medias.

>[!NOTE]
>
> Esta configuración solo se aplica a la sección y no a sus componentes.  Por ejemplo, si selecciona la variable **Página anterior** opción para **Capítulos y temas**, el **Capítulos y temas** se combina con la página anterior. Los diversos capítulos y temas se publican según el **General** settings.Por ejemplo, si en **Iniciar cualquier capítulo nuevo desde la configuración**, seleccione **Página impar**, se inserta una página en blanco después de un capítulo que termina en una página impar.

Al combinar una sección con su página anterior o siguiente, el contenido se combina y se aplica el estilo de la sección de destino en la que se combina el contenido.

Por ejemplo, si activa **TDC** y **Capítulo y temas** y seleccione la **Página siguiente** para **TDC**, el **TDC** se combina con la siguiente sección, que es la **Capítulo y temas**. El estilo de la **Capítulo y temas** se aplica al contenido combinado de ambas secciones.

La opción de combinación funciona sucesivamente, por lo que si ha seleccionado **Página siguiente** para varias secciones continuas, todas se combinan con la primera sección (en la siguiente dirección), que no tiene esta propiedad establecida. Por ejemplo, habilite **TDC**, **Capítulo y temas**, **Lista de figuras**, y **Índice**. A continuación, si establece **Página siguiente** para **TDC**, **Capítulo y temas**, **Lista de figuras**, y **Ninguno** para **Índice**, todos se combinan con  **Índice**.


**Páginas estáticas**

Los distintos diseños de página le ayudan a diseñar la salida de las distintas secciones. Estas secciones se generan a partir del mapa DITA mientras se publica la salida.
También puede crear diseños de página personalizados y publicarlos como páginas estáticas en la salida del PDF. Esto le ayuda a añadir contenido estático como notas o páginas en blanco.

Siga estos pasos para agregar un diseño de página personalizado:

1. Seleccionar **Añadir** ![](assets/add-icon.svg) para agregar un nuevo diseño de página. Se abre el panel Agregar diseño de página.
2. Seleccione el diseño de página de la lista y haga clic en Agregar. El nuevo diseño de página se agrega a la lista de diseños de página.


También puede realizar las siguientes acciones:

* Seleccione las barras de puntos para arrastrar y soltar el diseño de página en la ubicación deseada.

* Seleccionar **Quitar diseño** ![](assets/delete-icon.svg)  para quitar un diseño.

* También puede combinar una página estática con la página anterior o con la página siguiente.

* También puede agregar un diseño personalizado varias veces y ordenarlos. Esto le ayuda a publicar el contenido estático en consecuencia.

  Por ejemplo, puede utilizar un diseño personalizado para publicar una advertencia estática varias veces dentro de la salida del PDF.



### Organización de página

Las páginas de un documento de PDF suelen publicarse según el contenido organizado en el mapa DITA o en el fichero de mapa de libros. Sin embargo, también puede cambiar el orden de las páginas en el documento de PDF. Por ejemplo, puede imprimir un documento de varias páginas como un folleto. Al intercalar, plegar y grapar las hojas, el resultado es un solo libro con el orden de página correcto.  A continuación, puede leer el folleto publicado como un libro.

<img src="assets/template-page-organization.png" alt="Organización de página" width="550">


Las siguientes configuraciones están disponibles en la **Organización de página** sección:

#### Orden de páginas

Seleccione un orden de páginas que determine la secuencia de las páginas del documento de PDF. Puede elegir las siguientes opciones en la lista desplegable:

* **Predeterminado**: El orden predeterminado de las páginas según el archivo de origen.
* **Páginas impares primero**: todas las páginas impares se mueven antes que todas las páginas pares.
* **Páginas pares primero**: todas las páginas pares se mueven antes que todas las páginas impares.
* **Inverso**: el orden de las páginas se invierte.
* **Folleto**: todas las páginas se ordenan como en un folleto.
* **Folleto de derecha a izquierda**: todas las páginas están en orden de folleto de derecha a izquierda.
* **Personalizado**: defina un orden personalizado de páginas en lugar de un orden predefinido.
   * &quot;a..b&quot;: todas las páginas consecutivas de a a b.
   * &quot;a,b,c&quot; — Nuevo orden de páginas a, b, c.
   * &quot;a*b&quot; — La página a se repite por veces.
   * &quot;-a&quot;: los números de página negativos se cuentan hacia atrás a partir de la última página y se pueden combinar con otros pedidos personalizados.
   * &quot;X&quot; — todas las páginas del documento. Mismo resultado que &quot;1..-1&quot;.

Por ejemplo, puede dar un pedido personalizado como &quot;2, 3, 5*2, 7..10,-1,-2.
El orden de páginas dado hace que un PDF tenga los siguientes números de página del documento original, suponiendo que tenga 25 páginas en total: 2, 3, 5, 5, 7, 8, 9, 10, 25, 24.

#### Configurar más de una página por hoja

Elija esta opción para publicar varias páginas en una sola hoja de papel.  A continuación, seleccione el número de filas y columnas y publique las páginas como una cuadrícula en una sola hoja. Por ejemplo, puede publicar las páginas como una cuadrícula de 2 filas y 4 columnas.

Defina el tamaño de hoja de destino y la orientación en la que desea publicar la hoja. También puede especificar las propiedades de margen y relleno de la hoja.




### Impresa

Configure las opciones de producción de impresión para asignar marcas de impresora, seleccionar modelos de color y especificar propiedades relacionadas con la impresión de la salida del PDF.

* **Marcas de impresora**: cuando se prepara un documento para la producción de impresión, las marcas de impresora se agregan a los límites de la página para ayudar en la alineación, el recorte y la selección de color adecuados durante la impresión. Al seleccionar una marca de impresora, el límite de página se amplía para dar cabida a la marca, que se recorta durante la impresión. Puede elegir mostrar las siguientes marcas de impresora en la salida del PDF:
   * **Marcas de recorte**: seleccione la opción para colocar una marca en cada esquina del área de recorte para indicar dónde debe recortarse el papel después de la impresión.
   * **Marcas de sangrado**: seleccione esta opción para colocar una marca en cada esquina del cuadro de sangrado e indicar el área de recorte de la imagen ampliada.
   * **Marcas de registro**: seleccione esta opción para colocar una marca fuera del área de recorte y alinear las diferentes separaciones en un documento de color.
   * **Barras de color**: seleccione esta opción para agregar una franja de colores fuera del área de recorte para mantener la coherencia del color y ajustar la densidad de la tinta al imprimir.

  Definir dimensiones para las marcas de impresora seleccionadas utilizando **Anchura de línea**, **Color de línea**, y **Anchura del cuadro de sangrado** opciones.

* **Tamaño del cuadro multimedia**: Este es el tamaño total de la página, incluido el área extendida ocupada por las marcas de impresora. Utilice la opción desplegable para seleccionar el tamaño de página de la salida del PDF o crear su propio tamaño personalizado.

* **Espacio de color**: se le ofrece la opción de elegir entre espacios de color RGB o CMYK para imprimir el documento de PDF. Elija RGB para mostrar el PDF generado digitalmente y CMYK para la impresión física. Los colores definidos en el documento se convierten al espacio de color elegido.
  >[!NOTE]
  >
  >Es necesario un perfil de color ICC para la creación del PDF/A si se utiliza el espacio de color CMYK.

  <!--For more information on applying these print settings, see *Printing preferences*.-->

### Referencias cruzadas {#cross-references}

Utilice el **Referencia cruzada** para definir cómo se publican las referencias cruzadas en el PDF. Puede dar formato a las referencias cruzadas para el título del tema, tablas, ilustraciones, etc.

>[!NOTE]
>
> Si ha definido el texto del vínculo al insertar la referencia cruzada, tiene prioridad sobre el formato de referencia cruzada definido en la plantilla del PDF nativo.

También puede utilizar variables para definir una referencia cruzada.  Cuando se utiliza una variable, su valor se selecciona de las propiedades. Puede utilizar una sola variable o una combinación de ellas para definir una referencia cruzada. También puede utilizar una combinación de una cadena y una variable.

Por ejemplo, puede utilizar `View details on {chapter}`. Si el nombre del capítulo es &quot;Configuración general&quot;, la referencia cruzada en la salida es &quot;Ver detalles sobre la configuración general&quot;.

AEM Guías de proporciona las siguientes variables listas para usarse:

* {title}: crea una referencia cruzada al título del tema. Por ejemplo, consulte Vínculos útiles en la página 2.
* {page} Agrega una referencia cruzada a los números de página. Por ejemplo, consulte en la página 1.
* {description}: añade una referencia cruzada al texto de la descripción. AEM Por ejemplo, consulte los detalles de las Guías de.
* {chapter}: Añade una referencia cruzada a los números de capítulo. Por ejemplo, consulte en el capítulo 1.
* {bookmarkText}: crea una referencia cruzada al texto marcado. Por ejemplo, Consulte stop_words en la página 5.
* {captionText}: crea una referencia cruzada para el pie de ilustración de la figura o tabla del tema. Por ejemplo, consulte Flujo de aire en la página 2.
* {figure}: añade una referencia cruzada al número de la figura. Selecciona el número de figura de los estilos de numeración automática que ha definido para figcaption.  Por ejemplo, puede utilizar &quot;Consulte {figure} en la página {page}&quot;. La referencia cruzada en la salida contiene el número de figura generado automáticamente y su número de página, &quot;Ver Figura 1 en la página 5&quot;.
* {table}: añade una referencia cruzada al número de tabla. Selecciona el número de tabla de los estilos de numeración automática que ha definido para el pie de ilustración. Por ejemplo, puede utilizar &quot;Consulte {table} en la página {page}&quot;. La referencia cruzada de la salida contiene el número de tabla generado automáticamente y su número de página, &quot;Consulte la Tabla 1 de la página 5&quot;.



  >[!NOTE]
  >
  >Puede crear estilos de numeración automática para las etiquetas caption y figcaption.

#### Formato de referencia cruzada predeterminado

Si deja en blanco el campo de texto y no ha definido el texto del vínculo al insertar una referencia cruzada, Experience Manager Guides agrega las siguientes variables para las referencias cruzadas correspondientes:

* **Título**: `{title}`
* **Descripción**: `{description}`
* **Párrafo**: `{bookmarkText}`
* **Marcador**: `{bookmarkText}`
* **Figura**: `{captionText}`
* **Tabla**: `{captionText}`

El orden de prioridad de las referencias cruzadas es el siguiente:
* Texto del vínculo añadido en las referencias cruzadas
* Formato de referencia cruzada definido en la plantilla del PDF nativo
* Formato de referencia cruzada predeterminado


#### Variables de idioma en referencias cruzadas

También puede utilizar variables de idioma para definir referencias cruzadas localizadas. Según el idioma elegido, el valor localizado se selecciona automáticamente en la salida del PDF.

Por ejemplo, puede agregar una variable de idioma &quot;reference-label&quot; y definir los valores en inglés y alemán.

* Inglés - &quot;Ver en la página {page}&quot;
* Alemán - &quot;Einzelheiten finden Sie auf der Seite&quot; {page}&quot;


Al agregar `${lng:<variable name>}` en la sección Párrafo, las referencias cruzadas en los párrafos de la salida contienen el texto localizado y el número de página.\
Por ejemplo, las siguientes capturas de pantalla muestran las referencias cruzadas &quot;Ver en la página 1&quot; en inglés y &quot;Einzelheiten finden Sie auf der Seite 1&quot; en alemán.

<img src="./assets/english-output-corss-reference.png" alt="Resultado en inglés de una referencia cruzada en un párrafo" width ="800" border="2px">

*Una referencia cruzada dentro de un párrafo cuando se publica en inglés.*

<img src="./assets/german-output-corss-reference.png" alt="Resultado alemán de una referencia cruzada en un párrafo" width ="800" border="2px">


*Una referencia cruzada dentro de un párrafo cuando se publica en alemán.*

<!--For more information, see *Format cross-references*.-->
