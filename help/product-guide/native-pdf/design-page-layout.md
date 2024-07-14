---
title: Función nativa de PDF Publish | Diseño de una página
description: Aprenda a diseñar el diseño de página para presentar la información en diferentes secciones de la salida del PDF.
exl-id: b4d3bdc4-0d01-46eb-b182-540380220485
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: aad652509c54b516fca49b7ca28d7dd5547f9a1b
workflow-type: tm+mt
source-wordcount: '4972'
ht-degree: 0%

---


# Diseño de una página {#design-page-layout}

Al crear un documento de PDF, tendría diferentes secciones para presentar diferentes tipos de información. Por ejemplo, un documento de PDF comenzaría desde una portada o portada, que tendría el logotipo de su compañía, el título del libro o la información de la versión. Luego habría capítulos, apéndices o páginas de glosarios. Cada sección de un documento de PDF tiene un aspecto diferente y se logra creando y personalizando el diseño de página.

Al diseñar el diseño de página, puede definir los distintos elementos que componen una página. Por ejemplo, puede definir el tamaño de página, los márgenes, el encabezado y pie de página, la orientación y otras especificaciones de página de una página. La característica Publicación de PDF nativo le permite diseñar su página según los [estándares de medios de página](https://www.w3.org/TR/css-page-3/). La mayoría de las opciones de configuración incluidas en los estándares de medios paginados se pueden personalizar fácilmente con la interfaz de usuario de la función de publicación nativa de PDF. Para aplicar otro formato de nivel avanzado, puede utilizar la vista de Source para escribir su propio código CSS.

Una vez diseñados los diseños de página, debe asociarlos con sus secciones respectivas en la configuración de Diseño de página del PDF. Consulte la sección [Crear y personalizar diseños de página](components-pdf-template.md#create-customize-page-layout) para obtener más información sobre cómo crear y abrir un diseño de página para personalizar.

## Tipos de diseños de página {#types-of-page-layout}

Un documento de PDF suele contener las siguientes secciones:

* Portada
* Tabla de contenido
* Alza de cifras
* Alza de tablas
* Páginas de capítulo o tema
* Glosario
* Índice
* Página posterior

Estas secciones necesitarían un diseño de página correspondiente para presentar la información en un formato específico. Además, también puede tener una página en blanco que se utiliza como relleno para iniciar un nuevo capítulo desde una página par o impar. En ese caso, puede utilizar el diseño de página predeterminado o crear un diseño de página para una página en blanco. Consulte [Crear un nuevo diseño de página](components-pdf-template.md#create-page-layout) para obtener más información.

La configuración de Diseños de página en la sección **Plantilla>Configuración** permite definir qué diseño de página se utilizará para las diferentes secciones del PDF. Además, cada diseño de página puede tener diferentes variantes de página inicial, derecha o izquierda.

### Crear las primeras variantes de diseño de página a la derecha o a la izquierda {#page-layout-variants}

Los distintos diseños de página de la plantilla de PDF se pueden personalizar aún más teniendo diferentes variantes de diseño de página en primer lugar, a la derecha o a la izquierda. Puede diseñar estas páginas de forma diferente con el diseñador de diseños de página.

>[!NOTE]
>
>Si desea tener un diseño de página único para una sección del libro, no necesita crear los diseños de página Primero, Derecha o Izquierda.

Tenga en cuenta los siguientes puntos al crear los diseños de página:

>[!NOTE]
>
>Los puntos siguientes han tomado como ejemplo el diseño de página Capítulo. Sin embargo, estos puntos también son válidos para otros diseños de página.

* Si desea utilizar un diseño de página único para todas las páginas de un capítulo, cree un único diseño de página de capítulo sin ninguna variante.

* Si desea tener un aspecto diferente para la primera página de los capítulos del libro, debe crear una variante de diseño de Primera página para los capítulos.

* Si desea tener un aspecto diferente para cada página del lado izquierdo y derecho del libro, debe crear las variantes del lado izquierdo y derecho para el diseño de la página del capítulo.

* Si desea que los capítulos comiencen desde una página impar o par, puede elegir crear un diseño de página para la página en blanco. Este diseño de página se utiliza para rellenar el espacio entre dos capítulos para asegurarse de que el capítulo comienza en la página par o impar deseada.

  >[!NOTE]
  >
  >Si no crea un diseño de página en blanco independiente, se utilizará el diseño de página predeterminado. Para crear un diseño de página, vea [Crear un nuevo diseño de página](components-pdf-template.md#create-page-layout).

El siguiente ejemplo lo guiará por el proceso de creación de variantes de un diseño de página:

1. Cree un diseño de página de &quot;Capítulo&quot; siguiendo los pasos que se indican en el procedimiento &quot;Crear un nuevo diseño de página&quot;.

   Se crea un diseño de página de capítulo en blanco y se agrega en Diseños de página.

   De forma predeterminada, al crear un diseño de página, también se abre para editarlo. La siguiente captura de pantalla muestra un diseño de página en blanco (predeterminado):

   <img src="./assets/default-blank-page-layout.png" width="300">

   El encabezado, el pie de página y el área de contenido de una plantilla se crean de forma predeterminada. Puede personalizar fácilmente estas áreas mediante las propiedades de página, las propiedades de contenido y varias herramientas (como insertar imágenes, campos, etc.) de la interfaz de usuario.

   >[!NOTE]
   >
   >Para obtener una configuración avanzada, puede utilizar la vista de Source y agregar su HTML personalizado y código CSS.

1. Pase el ratón sobre el diseño de **Chapter** y haga clic en **Options** para mostrar el menú contextual.

1. Pase el ratón o haga clic sobre **Agregar variante de diseño** y elija el diseño de página que desee (Primero, Izquierdo o Derecho) que desee crear.

El diseño de página seleccionado se crea con una copia del diseño de capítulo base. Esto significa que si ha realizado cambios en el diseño de página de capítulo predeterminado, los mismos cambios se replicarán en el diseño de página de variante en el momento de la creación del diseño de página.

## Trabajar con las propiedades de página de un diseño de página {#page-props-page-layout}

Al diseñar un diseño de página, es esencial tener control sobre las distintas propiedades de la página. La función Publicación nativa de PDF encapsula todas las propiedades de página principales en el panel Propiedades de página. El panel Propiedades de página proporciona acceso a varias propiedades en las siguientes secciones:

>[!NOTE]
>
>El panel Propiedades de página encapsula las propiedades y sigue las reglas definidas en [Estándares de medios de página](https://www.w3.org/TR/css-page-3/).

* **Tamaño de página** : especifique el tamaño de página que desea utilizar para el diseño de página. La lista desplegable Tamaño de página le permite elegir entre más de 15 tamaños de página. También puede crear un diseño de página usando un tamaño de página personalizado. Vea [Establecer el tamaño de página](#set-page-size) para obtener más detalles.

* **Orientación** : especifique la orientación de página que se utilizará en el diseño de página. Puede elegir entre las orientaciones de página Vertical u Horizontal. Tenga en cuenta que puede elegir que se apliquen diferentes orientaciones a diferentes variantes de página en un diseño de página. Por ejemplo, si el contenido contiene una tabla ancha o una imagen grande, puede crear un diseño de página horizontal y aplicar ese diseño a la tabla o imagen más ancha.

* **Rotación de vista** : especifique el lado o la dirección en que se representa el lado superior original después de la rotación. Puede elegir entre 90 en sentido horario, 90 en sentido antihorario o 180 en sentido antihorario. Esto resulta muy útil en una situación en la que desea utilizar una combinación de diseños Vertical y Horizontal en la salida. Por ejemplo, puede utilizar vertical como diseño de página genérico y establecer un diseño de página horizontal para representar tablas anchas. En ese caso, puede configurar para que muestre el contenido de la tabla en el sentido de las agujas del reloj 90 grados. De esta forma, la página estará orientada en horizontal y el contenido rotará 90 grados para mantener la continuidad a la vista. Veremos cómo se logra esto como ejemplo más adelante en esta sección.

* **Numeración de páginas**: La numeración de páginas, de forma predeterminada, es continua en un PDF. Por ejemplo, un PDF de 100 páginas podría tener números de página continuos de 1 a 100. También puede reiniciar la numeración desde un número específico en todas las secciones diferentes o desde la primera aparición de una sección.
   * **Reiniciar desde** : especifique el número de página desde el que se iniciará la numeración para este diseño de página. Por ejemplo, puede establecer el número de página para que se reinicie cada capítulo. En ese caso, debe establecer la propiedad restart from en 1 en la variante First page layout del diseño de página del capítulo. De forma predeterminada, la numeración de páginas continúa desde la página anterior.

   * **Aplicar solo a la primera incidencia**: También puede comenzar desde un número específico solo para la primera incidencia de una sección. Por ejemplo, puede comenzar solamente el primer capítulo desde 1 y continuar con los números de página de otros capítulos.

* **Diseño** : especifique los márgenes de página junto con el relleno para los lados superior, inferior, izquierdo y derecho. La siguiente ilustración explica cómo se representan los márgenes, el relleno y los bordes alrededor del contenido. Tenga en cuenta que el margen superior e inferior de una página contiene el encabezado y el pie de página.

  <img src="./assets/margins-padding-illustration.png" width="300">

* **Fondo**: incluye una imagen o un color como fondo del diseño de página. Para una imagen, puede especificar la altura y anchura de la imagen junto con las propiedades de repetición y posición.

* **Nota al pie** : especifique las propiedades para mostrar las notas al pie en la salida. Puede elegir especificar las propiedades de márgenes y relleno junto con un estilo de borde.

### Establecer el tamaño de página {#set-page-size}

Lo primero que debe definir en un diseño de página es el tamaño de la página. En Propiedades de página, hay más de 15 tamaños de página que puede elegir para un diseño de página. También puede crear un tamaño de página personalizado realizando los siguientes pasos:

1. Abra el diseño de página necesario para editarlo.

   >[!NOTE]
   >
   >Consulte la sección [Personalizar un diseño de página](components-pdf-template.md#customize-page-layout) para abrir un diseño de página y personalizarlo o editarlo.

1. En el panel derecho, haga clic en **Propiedades de página**.
1. En la lista desplegable **Tamaño de página**, seleccione **Personalizado**.

   Se muestran los campos Anchura de página y Altura de página.

1. Introduzca las dimensiones de página que desee en los campos **Anchura de página** y **Altura de página**.

   >[!NOTE]
   >
   >Algunas de las unidades más utilizadas son píxeles, puntos, rem, em, porcentaje y pulgadas.

### Utilizar la orientación de página y la rotación de vistas {#page-orientation-rotation}

Veamos un ejemplo en el que se utiliza una combinación de orientación de página vertical y horizontal y propiedades de rotación de vista. En este ejemplo, crearemos un PDF con orientación vertical predeterminada, pero se procesará una tabla en orientación horizontal con contenido en la vista de 90 grados en el sentido de las agujas del reloj. El resultado final tendrá un aspecto similar al siguiente:

<img src="./assets/portrait-landscape-page-layouts.png" width="400">

En la salida anterior, la información de la Lista de contactos se presenta en modo horizontal con el contenido también girado en 90 grados. El contenido restante se muestra en el modo vertical normal.

Para lograr este tipo de resultados, debemos realizar las siguientes tareas principales:

1. Cree un diseño de página con orientación horizontal.

1. Cambie la propiedad **View Rotation** para representar el contenido en 90°.

1. Cree un estilo personalizado para utilizar el nuevo diseño de página.

1. Añada el estilo en la definición de clase de salida de la tabla que queremos procesar en el diseño de página horizontal.

Siga estos pasos para realizar las tareas anteriores:

1. Cree un diseño de página con orientación horizontal.
   1. Cree un diseño de página &quot;Horizontal&quot; siguiendo los pasos indicados en el procedimiento &quot;Crear un nuevo diseño de página&quot;.

   1. En el panel derecho, haga clic en **Propiedades de página**.

      <img src="./assets/page-properties-panel.png" width="300">
   1. Cambie **Orientación** a **Horizontal**.

1. Cambie la propiedad Ver rotación para representar el contenido en 90° en el sentido de las agujas del reloj.

   1. Seleccione **90°** a la derecha del reloj en la lista desplegable Ver rotación.
   <img src="./assets/view-rotation-page-props.png" width="300">

   1. Haga clic en **Guardar todo** para guardar las propiedades actualizadas del diseño de página.

1. Cree un estilo personalizado para utilizar el nuevo diseño de página.
   1. Expanda la barra lateral izquierda y haga doble clic en la plantilla en la que desea crear el estilo.

   1. Expanda la sección Hojas de estilo.

   1. Pase el ratón sobre la hoja de estilo Diseño, haga clic en el icono (_Opciones_)... y seleccione Editar.

      La hoja de estilos Diseño se abre para editarla.

   1. Haz clic con el botón derecho en **Otros estilos** y elige **Nuevo estilo**.
      <img src="./assets/stylesheet-other-new-style.png" width="300">

   1. En la ventana emergente Agregar estilo, escriba **landscape-style** en **classname**.
      <img src="./assets/stylesheet-new-landscape-style.png" width="400">

   1. Haga clic en **Listo**.

      Se crea un nuevo estilo denominado `.landscape-style` que se agrega al final de la lista Otros estilos.

   1. Haga doble clic en el estilo `.landscape-style` para abrirlo y editarlo.

   1. Expanda la propiedad **Paginación**.

   1. Escriba `Landscape` en la propiedad **Diseño de página**.

      <img src="./assets/new-style-with-landscape-layout.png" width="500">

   1. Haga clic en **Guardar todo** para guardar las propiedades de estilo actualizadas.

1. Agregue el estilo en la definición de `outputclass` de la tabla que queremos procesar en el diseño de página horizontal.
   1. En un editor de archivos DITA, abra el archivo en el que desee aplicar el nuevo diseño de página.

   1. Busque el elemento `<table>`, que se procesará en modo horizontal.

   1. En la ruta de exploración, haga clic en el elemento de tabla para seleccionar la tabla.

      <img src="./assets/new-style-table-element.png" width="400">

   1. En el panel derecho, haga clic en y abra el panel Propiedades del contenido.

   1. En el panel Propiedades de contenido, agregue una nueva propiedad **outputclass** con **landscape-style** como valor de propiedad.

      <img src="./assets/new-style-table-outputclass.png" width="300">

1. Haga clic en **Guardar todo** para guardar el archivo actualizado.
1. Genere la salida del PDF.

El PDF final procesará el contenido de la tabla en modo horizontal como se muestra al principio del ejemplo.

### Agregar una imagen de fondo {#add-bg-image}

En función de sus necesidades, es posible que desee añadir una imagen de fondo que aparezca en cada primera página de salida de capítulo (PDF). Las propiedades Fondo en Propiedades de página permiten agregar fácilmente una imagen de fondo. Puede elegir replicar esta imagen en una página y colocarla en cualquier lugar del área superior, inferior o central de la página.

Por ejemplo, para insertar una imagen de fondo en la parte central del área de contenido, realice los siguientes pasos:

1. Abra el diseño de página necesario para editarlo.

   >[!NOTE]
   >
   >Consulte la sección [Personalizar un diseño de página](components-pdf-template.md#customize-page-layout) para abrir un diseño de página y personalizarlo o editarlo.

1. Haga clic en cualquier lugar del área de contenido.

1. En el panel derecho, haga clic en **Propiedades de página**.

1. Expanda la sección **Fondo**.

1. Haga clic en el botón Examinar en el campo de ubicación **Ruta de la imagen**.

1. Busque y seleccione la imagen que desea utilizar como imagen de fondo.

   La imagen se inserta y se replica para cubrir toda la página.

1. Cambie el tamaño de la imagen ajustando las propiedades de altura y anchura.

   >[!NOTE]
   >
   >Puede introducir cualquiera de las propiedades height o width, ya que la imagen se escala automáticamente para mantener la proporción de aspecto.

1. Establezca las demás propiedades para ajustar la forma en que desea que aparezca la imagen de fondo.

   * **Repetición en segundo plano** : especifique si desea que el fondo se repita o no.

   * **Posición de fondo** : especifique una posición para la imagen de fondo de la página.

La siguiente captura de pantalla muestra la imagen de fondo con la propiedad Repetición de fondo establecida en _no repetir_ y la propiedad Posición de fondo establecida en _centro_.

<img src="./assets/background-image.png" width="500">

## Trabajar con encabezado y pie de página {#work-header-footer}

Cuando se incluye información en un encabezado o pie de página de un diseño de página, esa información se repite en todas las páginas que utilizan ese diseño de página. Normalmente, el área de encabezado se utiliza para el título del capítulo o tema y el área de pie de página se utiliza para mostrar los números de página.

Al crear un nuevo diseño de página, el área de encabezado y pie de página se crea de forma predeterminada. Puede realizar muchas personalizaciones en el área de encabezado y pie de página de un diseño de página. Por ejemplo, puede insertar una imagen (como un logotipo), variables (que contengan información dinámica) o contenido estático.

### Cambiar los márgenes y líneas del encabezado y pie de página {#header-footer-margins}

De forma predeterminada, los márgenes del encabezado y del pie de página se establecen en 1 pulgada. Puede cambiar este valor predeterminado cambiando la configuración Margen en el panel Propiedades de página. Realice los siguientes pasos para cambiar el tamaño del encabezado y el pie de página:

1. Abra el diseño de página necesario para editarlo.

   >[!NOTE]
   >
   >Consulte la sección [Personalizar un diseño de página](components-pdf-template.md#customize-page-layout) para abrir un diseño de página y personalizarlo o editarlo.

1. En el panel derecho, haga clic en **Propiedades de página**.
1. Expanda la sección **Diseño**.
1. Haga clic en el icono de candado junto a la propiedad **Margin**.
1. Para cambiar el tamaño del encabezado, introduzca el valor deseado en el campo Margen superior.

   >[!NOTE]
   >
   >Algunas de las unidades más utilizadas son píxeles, puntos, rem, em, porcentaje y pulgadas.

1. Para cambiar el tamaño del pie de página, introduzca el valor deseado en el campo Bottom margin.

Puede diseñar el área de encabezado y pie de página para que contenga varias líneas. Para ello, añada una etiqueta \&lt;p\> utilizando Insertar elementos de HTML (<img src="./assets/insert-html-element-2.svg" width="25">) en el área del encabezado o pie de página.

| _Rincón del desarrollador_: <img src="./assets/developer-corner-icon.svg" width="25"> |
|---|

Si desea trabajar directamente con el código CSS y el código de HTML, puede cambiar los valores de los márgenes como se muestra en el siguiente fragmento de código:

```css
…

<meta name="page-style" content="size:A4 portrait;margin-top:3cm;margin-right:30pt;margin-bottom:1in;margin-left:90px;" />

…
```

>[!NOTE]
>
>En el ejemplo anterior, se utilizan distintas unidades para especificar los valores de los márgenes.

### Quitar el encabezado y el pie de página {#remove-header-footer}

El encabezado y el pie de página se superponen en los márgenes superior e inferior. Técnicamente, esto significa que si desea incluir un encabezado y un pie de página en el diseño de página, debe reservar el espacio necesario en los márgenes superior e inferior.

Si no desea que un diseño de página tenga un encabezado y un pie de página, existen dos formas de hacerlo:

* Si desea conservar los márgenes superior e inferior, deje en blanco el área de encabezado y pie de página.
* Si no desea conservar los márgenes superior e inferior (como diseñar la portada y la contraportada de una revista), puede quitar los márgenes estableciendo las propiedades de los márgenes superior e inferior en 0. Esto no deja espacio para el encabezado y el pie de página.

### Añadir una imagen o un logotipo en el encabezado {#add-image-header}

En función de sus necesidades, es posible que desee agregar una imagen que aparezca en el área de encabezado (o en cualquier otra parte) del diseño de página. Existen dos maneras de agregar una imagen al diseño de página:

* Utilice una imagen de los recursos de plantilla.
* Utilice la herramienta \&lt;Agregar imagen\> en el editor de diseño de página.

>[!NOTE]
>
>Se recomienda utilizar la carpeta Recursos para administrar todos los recursos de plantilla, como imágenes o fuentes.

Para insertar una imagen como el logotipo de su empresa en el área del encabezado, realice los siguientes pasos:

1. Abra el diseño de página necesario para editarlo.

>[!NOTE]
>
>Consulte la sección [Personalizar un diseño de página](components-pdf-template.md#customize-page-layout) para abrir un diseño de página y personalizarlo o editarlo.

1. Haga clic en el encabezado Editar (<img src="./assets/header-icon.svg" width="25">) para llevar el cursor al área de encabezado.

   O bien, haga clic dentro del área de encabezado.

1. Para añadir una imagen, elija cualquiera de los siguientes métodos:
1. Haga clic en **Insertar imagen** (<img src="./assets/insert-image-icon.svg" width="25">) en la barra de herramientas; en el elemento emergente **Seleccionar ruta**, busque la ubicación de la imagen y haga clic en **Seleccionar** para insertarla en el área de encabezado.
1. Arrastre y suelte una imagen de la carpeta Recursos en el área de encabezado.

La siguiente captura de pantalla muestra una imagen de muestra agregada en el área del encabezado.

<img src="./assets/image-in-header-area.png" width="500">

Una vez insertada una imagen, puede modificar sus atributos para darle la apariencia que desee. La forma más sencilla de cambiar el aspecto de una imagen o de cualquier otro elemento del diseño de página es mediante el panel Propiedades del contenido. Consulte [Trabajar con el panel Propiedades de contenido](#work-with-content-props) para ver las distintas propiedades disponibles a través de la interfaz de usuario que se van a personalizar.

### Añadir campos y metadatos {#add-fields-metadata}

Los campos son muy útiles cuando desea insertar un fragmento de información predefinido. Por ejemplo, puede incluir un campo Título de capítulo en el área de encabezado del capítulo que se sustituya por el título real del capítulo cuando se publique.

Existen las siguientes categorías para los campos que puede insertar en el diseño de página:

* Metadatos
* Título del tema
* Título del capítulo
* Título del mapa
* Número de página
* Número de capítulo
* Total de páginas
* Fecha
* Hora


Cada una de estas categorías de campos contiene diferentes variaciones en las que se puede insertar la información del campo. Por ejemplo, un campo Fecha puede tener diferentes variaciones como `YYYY-MM-DD`, `MM/DD/YY`, `MM/DD/YYYY`, etc. Del mismo modo, Número de página puede tener variaciones en la forma de formatos romanos, decimales o incluso específicos de la configuración regional, como _Árabe_, _Devanagari_, _Hebreo_ y más.


Además de los campos predefinidos, también puede agregar información de metadatos como variables o campos en el diseño de página. Estos metadatos se almacenan en el contenido de origen DITA **Map**, o bien se pueden seleccionar de las propiedades de archivo DITA **Map** o de las propiedades de archivo **Topic** y se pueden insertar fácilmente en el diseño de página.

Puede seleccionar los metadatos de las siguientes opciones:

* **Contenido de mapa** incluye los metadatos que ha definido en el elemento `<topicmeta>` del mapa DITA.
* **Propiedades del archivo de mapa** incluye los metadatos, a los que puede tener acceso desde la página **Propiedades** de un mapa DITA.
* **Propiedades del archivo de tema** incluye los metadatos, a los cuales puede tener acceso desde la página **Propiedades** de un tema.


Puede combinar metadatos de **Asignar propiedades de archivo** y **Propiedades de archivo de tema** en un solo documento. Por ejemplo, puede publicar un PDF con el título del mapa en la portada y el título del tema en el encabezado de otras páginas. Para ello, puede agregar los metadatos del título de asignación desde **Propiedades del archivo de asignación** al diseño de la portada. A continuación, agregue los metadatos del título del tema de **Propiedades del archivo de tema** al encabezado en Diseño de página de capítulos y temas.

Si un tema termina en una página y el otro empieza en la misma página, se seleccionan los metadatos del primer tema. También puede agregar propiedades personalizadas e insertarlas como campos en el diseño de página.


>[!NOTE]
>
> Los campos de metadatos se muestran de acuerdo con la selección del recurso o el mapa en la lista desplegable **De**.




<!--For more information, see [Add fields and metadata](design-page-layout.md#add-fields-and-metadata).-->

En el siguiente ejemplo, insertaremos un número de página y un título de capítulo en el área de pie de página de un diseño de página.

1. Abra el diseño de página necesario para editarlo.

   >[!NOTE]
   >
   >Consulte la sección [Personalizar un diseño de página](components-pdf-template.md#customize-page-layout) para abrir un diseño de página y personalizarlo o editarlo.

1. Haga clic en el icono **Editar pie de página** (![](./assets/footer-icon.svg)) para colocar el cursor en el área del pie de página.

   O bien, haga clic dentro del área de pie de página.

1. Inserte un elemento de párrafo haciendo clic en **Insertar elementos de HTML** (<img src="./assets/insert-html-element-2.svg" width="25">) y seleccionar Párrafo de la lista de elementos.

1. Haga clic en el icono **Insertar campos** (![](./assets/insert-fields-icon.svg)).

   Aparecerá la ventana emergente Campos.

1. Seleccione la categoría **Número de página** de la lista Campo, el formato de número de página **default(1)** de la lista Formato y haga clic en **Insertar**.

   <img src="./assets/insert-page-number-field.png" width="400">

   >[!NOTE]
   >
   >También puede editar el formato de todos los campos, excepto el formato predeterminado. Para ello, haga clic en el icono Edit junto al formato que desee editar, realice cambios y haga clic en OK. Para obtener más información, consulte [Agregar campos y metadatos](#add-fields-metadata).

   El campo de número de página predeterminado se inserta en el área de pie de página del diseño de página.

   <img src="./assets/page-number-field-in-footer.png" width="400">

   La ruta de exploración superior enumera los elementos en los que se almacena la información.

1. Escriba un espacio en blanco después del campo de número de página y haga clic en el icono **Insertar campos**.

1. Seleccione la categoría **Chapter Title** de la lista Field, el formato **Chapter Title** de la lista Format y haga clic en **Insertar**.

   El campo _Título de capítulo_, que se rellena con el título del capítulo en el momento de la publicación, se inserta en el área de pie de página. En este momento, los campos número de página y título de capítulo están separados por un espacio.

   <img src="./assets/page-number-topic-title-near-footer.png" width="400">

1. Para alinear a la derecha el título del capítulo, realice los siguientes pasos:

   1. Haga clic en el elemento Campo de la ruta de exploración para seleccionar el campo Título del capítulo.

   1. En el panel derecho, haga clic en **Propiedades del contenido** (<img src="./assets/content-properties-icon.png" width="25">).

   1. Expanda la sección de propiedades **Diseño** y establezca el valor de la propiedad **Flotante** en **derecho**.
      <img src="./assets/float-prop-html-content.png" width="400">

      El campo Título del capítulo se alinea a la derecha del pie de página.
      <img src="./assets/topic-title-moved-right-footer.png" width="500">


| _Rincón del desarrollador_: <img src="./assets/developer-corner-icon.svg" width="25"> |
|---|

Si desea trabajar directamente con el código CSS y de HTML, también puede hacerlo en la vista Source del diseño de página y realizando cambios en el código. El siguiente fragmento de código muestra la misma configuración de pie de página realizada a través del código:

```css
…
<p>

<span data-field="page-number" data-format="default">1</span>

<span data-field="chapter-title" data-format="default" style="float: right">Chapter Title</span>

</p>
…
```

## Trabajo con el área de contenido {#content-area}

El área de contenido es el área más grande en términos de espacio de contenido. El área de contenido se rellena con el contenido del tema. En algunos casos especiales, puede agregar contenido de plantillas en el área de contenido. Este contenido se publica en la ubicación especificada del diseño de página. Por ejemplo, el encabezado de la tabla de contenido, el glosario y el índice se pueden agregar como contenido de plantillas, que se publica &quot;tal cual&quot; en la salida final. Otro ejemplo es la tabla de contenido del capítulo, que suele añadirse en la primera página de cada capítulo.

Una de las personalizaciones más utilizadas en el área de contenido es el diseño de varias columnas. Con el potente diseñador de diseños de página, puede personalizar páginas específicas para que se representen en varias columnas, al tiempo que mantiene el contenido de otras páginas en una sola columna.

En las secciones siguientes, se describen varios escenarios para personalizar el área de contenido.

### Añadir un índice de capítulo {#add-chapter-toc}

Una tabla de contenido de capítulo sirve como referencia rápida para que los lectores sepan qué hay en el capítulo. Normalmente, se añade una tabla de contenido de capítulo al principio de un capítulo. Por lo tanto, si desea utilizar una tabla de contenido de capítulo, puede agregarla al área de contenido del diseño de página del capítulo principal o a la primera variante de diseño de página de un capítulo.

En el siguiente ejemplo, insertaremos una tabla de contenido de capítulo en el primer diseño de página de un capítulo:

>[!NOTE]
>
>Para este procedimiento, se da por hecho que ha creado la variante Primera página para un diseño de página de capítulo. Para obtener instrucciones sobre cómo crear una variante de página, vea [Crear las primeras variantes de diseño de página a la derecha o a la izquierda](#page-layout-variants).

1. Abra el diseño de página necesario para editarlo.

   >[!NOTE]
   >
   >Consulte la sección [Personalizar un diseño de página](components-pdf-template.md#customize-a-page-layout) para abrir un diseño de página y personalizarlo o editarlo.

1. Coloque el cursor en el área de contenido del diseño de página.

1. Haga clic en el índice del capítulo (<img src="./assets/chapter-toc-icon.svg">).

   El índice de capítulo predeterminado se inserta en el área de contenido.

   <img src="./assets/chapter-toc-default.png" width="400">

   >[!NOTE]
   >
   >El índice del capítulo predeterminado contiene los encabezados 1 a 4. En este caso, el Encabezado 1 es el propio Título del capítulo. Por lo tanto, es posible que no desee volver a colocar el título del capítulo en la TDC o que desee aumentar el nivel de encabezados que desea incluir en la TDC. Puede personalizar la tabla de contenido cambiando las propiedades.

1. Abra el panel Propiedades del contenido para personalizar los niveles de encabezado de la TDC.

   Por ejemplo, si desea comenzar desde Encabezado 2, cambie la primera lista desplegable para que empiece desde 2.

   <img src="./assets/customize-chapter-toc.png" width="400">

   Del mismo modo, si desea tener encabezados hasta el nivel 5, cambie la segunda lista desplegable a 5. El índice actualizado tendrá el siguiente aspecto:

   <img src="./assets/chapter-toc-updated.png" width="400">

   >[!NOTE]
   >
   >El PDF final publicado solo mostrará las entradas del índice en función del contenido de los capítulos. Si no tiene encabezados de nivel 5 en un capítulo, no se mostrará en la salida final.

El aspecto del índice predeterminado se puede personalizar mediante las hojas de estilo. El estilo que comienza por `chaptoc-level-#` (como `chaptoc-level-1`, `chaptoc-level-2`, etc.) se usa para personalizar los estilos del índice del capítulo. <!--For more details on the stylesheet elements used in the TOC and how to customize them, see _Customize default chapter TOC_-->.

>[!IMPORTANT]
>
>Actualmente, si realiza cualquier actualización de estilo en una hoja de estilo, es posible que no se refleje en la previsualización de contenido. Sin embargo, el resultado se procesa con los estilos actualizados.

### Trabajar con diseño de página de varias columnas {#multi-column-layout}

Los diseños de página de varias columnas son muy comunes en las revistas de publicación o en los índices de un libro. La función Publicación nativa de PDF permite dividir fácilmente el documento en varias columnas. Con diferentes diseños de página, puede elegir mantener solo una sección específica dividida en varias columnas, mientras que las demás secciones se mantienen en un diseño de una sola columna (o normal).

Para crear un diseño de página con varias columnas, realice los siguientes pasos:

1. Abra el diseño de página necesario para editarlo.

   >[!NOTE]
   >
   >Consulte la sección [Personalizar un diseño de página](components-pdf-template.md#customize-a-page-layout) para abrir un diseño de página y personalizarlo o editarlo.

1. Dado que el diseño de varias columnas se aplica al contenido, excluyendo el área de encabezado y pie de página, debe seleccionar el elemento de contenido en la ruta de exploración.

   Una vez seleccionada la ruta de exploración de contenido, el panel Propiedades del contenido mostrará las propiedades de Varias columnas.

   <img src="./assets/multiple-columns-properties.png" width="400">

1. Utilice las propiedades de varias columnas para personalizar el diseño de página de varias columnas:

   * **Recuento de columnas:** Especifique el número de columnas para dividir la página. Utilice los iconos de flecha arriba y abajo o introduzca un número para definir el número de columnas.

   * **Anchura de columna:** Especifique el ancho de una columna en un diseño de varias columnas. De forma predeterminada, el tamaño se establece en píxeles (px); también puede especificarlo en pt, rem, em, % o en unidades.

     >[!NOTE]
     >
     >Si no especifica un tamaño, las columnas se dividen uniformemente para ajustarse a la página dada. En la mayoría de los casos, no es necesario especificar este valor.

   * **Espacio entre columnas** : especifique el espacio entre columnas individuales.

   * **Intervalo de columna** : Si desea que cualquier elemento del diseño de página se extienda entre columnas, debe utilizar esta propiedad. Esto se logra modificando el estilo del elemento deseado mediante las hojas de estilo. <!--for more information see _Section explaining style customization_-->.

   En el diseño de página, si desea que un texto determinado aparezca en la primera página de todos los diseños de página de capítulo, puede agregarlo a la variante Primera página del diseño de página de capítulo.

   Como se muestra en el ejemplo siguiente, la propiedad Span Column del texto del encabezado se establece en all. Esto garantiza que, aunque el documento tenga varias columnas, el encabezado se extienda por las columnas.

   <img src="./assets/element-span-across-columns.png" width="400">

   >[!IMPORTANT]
   >
   >La propiedad Span Column se puede aplicar a cualquier elemento DITA mediante el atributo outputclass.

   * **Relleno de columna** : especifica cómo rellena el contenido las columnas. De forma predeterminada, se establece en Balance, que rellena cada columna con la misma cantidad de contenido.

   * **Regla de columna**: Si desea que haya una línea entre las columnas, utilice esta propiedad para definir la línea o los estilos de regla. Especifique los valores para las reglas Estilo, Color y Anchura para agregar una línea entre las columnas.

## Trabajo con el panel Propiedades de contenido {#work-with-content-props}

El panel Propiedades del contenido permite actualizar fácilmente el aspecto de los elementos en el diseño de página. Las propiedades del panel Propiedades del contenido se dividen en las siguientes secciones:

* **Fuente**: contiene propiedades relacionadas con texto. Puede establecer la familia de fuentes, el grosor, el tamaño, la decoración del texto (como subrayado, superposición, línea de separación), el estilo del texto (como negrita, cursiva y mucho más), la alineación del texto (como izquierda, derecha, centro o justificado), los espacios en blanco (como formato predefinido, sin ajuste, espacio de interrupción y más), el alto de la línea, el espaciado entre letras y la sangría del texto.

* **Borde**: contiene propiedades para agregar y dar formato a un borde de un elemento en el diseño de página. Puede definir Borde lateral (como todo, superior, inferior, derecho o izquierdo), Estilo de borde (como Sólido, Discontinuo, Líneas de puntos o más), Color de borde, Anchura y Radio para tener un borde curvo. En el ejemplo siguiente, se ha agregado un borde curvo en el área de encabezado de la página.

  <img src="./assets/border-properties.png" width="500">

* **Diseño** : contiene propiedades para configurar el diseño de un elemento en el diseño de página. Puede establecer Altura, Anchura, Márgenes y relleno (para arriba, abajo, izquierda o derecha), Alineación horizontal o vertical, Flotante (como izquierda, derecha o ninguno), Borrar (como izquierda, derecha, ambos o ninguno), Posición del elemento (como absoluto, fijo, relativo o más), Mostrar (como bloque, contenido, fijo o más), Índice Z, Transparencia, Transformar (rotando o escalando) y Transformar origen (por X y desplazamiento Y).

* **Fondo**: contiene propiedades para incluir una imagen de fondo o una sombra de color. Puede establecer el tamaño de la imagen (mediante la definición de Altura o Anchura), la repetición del fondo (como repetición, sin repetición, redondeada o más) y la posición del fondo (como parte superior izquierda, centro derecha, centro inferior central o más).
* **Varias columnas** : Contiene propiedades para configurar propiedades de varias columnas para la página o cualquier elemento específico, como la TDC del capítulo. Para obtener más información sobre las propiedades y cómo utilizarlas, consulte [Trabajar con diseño de página de varias columnas](#multi-column-layout).
