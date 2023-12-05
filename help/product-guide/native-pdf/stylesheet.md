---
title: Función de publicación nativa de PDF | Trabajar con los estilos de contenido comunes
description: Aprenda a crear hojas de estilo de uso y a crear estilos para el contenido.
exl-id: 42ba7347-d81d-45d9-9627-8d164e4f9539
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '3525'
ht-degree: 1%

---

# Trabajar con los estilos de contenido comunes {#work-with-common-styles}

Una hoja de estilo contiene las definiciones de estilos para los elementos que se utilizan en la salida del PDF. Puede elegir trabajar con las hojas de estilo de ejemplo o crear otras nuevas. En la mayoría de los casos, la creación de una copia de la hoja de estilo de muestra OOTB le ayudará a empezar rápidamente.

El editor de estilos es un editor WYSIWYG que oculta todas las complejidades de un código CSS detrás de la interfaz de usuario. Con el editor de estilos, puede personalizar de forma fácil y rápida los estilos de los elementos que elija. Los estilos se clasifican en los siguientes encabezados:

* Estilos de encabezado
* Estilos de párrafo
* Estilos de carácter
* Estilos de hipervínculo
* Estilos de imagen
* Estilos de lista
* Estilos de tabla
* Estilos Div
* Estilos de página
* Otros estilos

Al trabajar con contenido DITA estructurado, la asignación de estilos para la mayoría de los elementos DITA se establece en la hoja de estilos predeterminada. Si está trabajando con elementos DITA estándar, puede cambiar su aspecto realizando directamente cambios en la definición del estilo. Estas definiciones de estilo están disponibles en la categoría Otro estilo. Para obtener más información, consulte [Trabajar con otros estilos](#other-styles) más adelante en este tema.

En las secciones siguientes se describen los ajustes de estilo más utilizados en forma de ejemplos.

>[!NOTE]
>
>En los ejemplos siguientes, se da por hecho que está trabajando con la hoja de estilo de muestra enviada con el producto.

## Trabajar con estilos de encabezado {#heading-styles}

Los estilos de encabezado encapsulan todos los estilos base para los encabezados utilizados en el contenido. OOTB obtendrá 6 estilos de encabezado base y un estilo de encabezado para el título del tema/capítulo y el título del apéndice. En un documento estructurado, H1 representa el título del tema o capítulo y H2 a H6 se utilizan para subtemas o secciones dentro de un tema o capítulo. Esta jerarquía de encabezados se aplica automáticamente al contenido siempre que se encuentra el encabezado correspondiente.

>[!NOTE]
>
>Puede crear sus propios estilos de encabezado personalizados y utilizarlos en el contenido mediante la clase output. Para obtener más información, consulte el paso 4 de [Utilizar la orientación de página y la rotación de vistas](design-page-layout.md#page-orientation-rotation) ejemplo.

### Creación de encabezados de nivel de capítulo personalizados {#create-chapter-level-heading}

En un libro (o un mapa de libros), se trabaja con Capítulos. Los estilos de título base están diseñados de tal manera que se aplican a los títulos de nivel de capítulo sin ninguna personalización. Sin embargo, si desea crear encabezados especializados para el contenido, deberá crear dichos encabezados. Por ejemplo, la opción predeterminada `h1.chapter` El encabezado de se aplica al título del capítulo. Si desea que el título del capítulo aparezca en un estilo diferente, debe personalizar la variable `h1.chapter` estilo. Del mismo modo, puede crear estilos personalizados para los subtítulos del capítulo. Por ejemplo, si desea crear un estilo personalizado para los 2<sup>nd</sup> y 3<sup>rd</sup> nivele los encabezados en el capítulo y, a continuación, debe crear un nuevo estilo como `h2.chatper` y `h3.chatper`.

Como la característica Publicación nativa de PDF contiene las definiciones de estilos base para los estilos más comunes, incluso si elimina accidentalmente un estilo, el estilo predeterminado se aplica al contenido. Por ejemplo, si no hay una definición de estilo para el estilo h2 en la hoja de estilo, la función Publicación nativa de PDF aplicará algún estilo base en el contenido h2.

En este ejemplo, crearemos un estilo de encabezado de capítulo de segundo nivel:

1. Abra la hoja de estilo necesaria para editarla.
   >[!NOTE]
   >
   >Consulte [Personalizar un estilo predefinido o nuevo](components-pdf-template.md#customize-style) para abrir una hoja de estilo para personalizarla o editarla.

1. En el **Estilos** , expanda la **Estilos de encabezado**.
1. Clic con el botón derecho en **Estilos de encabezado** estilo y elegir **Nuevo estilo**.
1. En el *Añadir estilo* diálogo, mantenga el **Etiqueta** nombrar como `h2` y escriba `chapter` en el **Clase** campo de nombre.
1. Haga clic en **Listo**.

Un nuevo estilo de encabezado denominado `h2.chapter` se crea y se agrega en la lista Estilos de encabezado.

Una vez creado un estilo, puede personalizar sus propiedades mediante el editor de estilos.

### Crear encabezados de número automático {#auto-number-heading}

Uno de los estilos de salida más utilizados son los encabezados numerados automáticamente. Estos encabezados representan el número de capítulo, los números de tema y de subtema. Los encabezados de numeración automática son diferentes de los estilos de lista en los que se asigna un número automático a una lista de elementos dentro de un tema.

En este ejemplo, personalizaremos los encabezados de nivel 1 a nivel 3 para utilizar números automáticos en diferentes formatos.

1. Abra la hoja de estilo necesaria para editarla.

   >[!NOTE]
   >
   >Consulte [Personalizar un estilo predefinido o nuevo](components-pdf-template.md#customize-style) para abrir una hoja de estilo para personalizarla o editarla.

1. En el **Estilos** , expanda la **Estilos de encabezado**.

1. Seleccione el **h1** estilo de la lista.
Las propiedades del estilo h1 se muestran en el panel Propiedades junto con su Vista previa.

   >[!NOTE]
   >
   >El panel Previsualización le ofrece una vista en tiempo real de cualquier actualización de estilo que aplique en cualquier elemento.

1. Seleccione el **Autonumerar** propiedad.

   Los estilos que puede aplicar en la lista de numeración automática se muestran debajo de la propiedad Autonumérico.

1. Establezca las siguientes propiedades:
   * **Estilo**: seleccione entre una amplia gama de estilos de numeración específicos de la configuración regional o genéricos. Puede elegir estilos como Árabe-Índico, Devanagari, Georgiano, Decimal, Alpha inferior y más. Para el ejemplo actual, seleccione `upper-alpha`.

   * **Formato**: el formato predeterminado está establecido en `<x>`, donde la variable `x` El valor se reemplaza por el estilo de numeración seleccionado en la propiedad Style. Por ejemplo, si ha seleccionado `decimal` (1) estilo, luego el valor de `x` se incrementa automáticamente en cada instancia de `h1` estilo y va como 2, 3, etc. También puede agregar texto personalizado en el campo para dar formato al estilo de encabezado. Por ejemplo, si desea que todos los encabezados h1 tengan un prefijo de `Chapter`, entonces debe configurar este campo como `Chapter <x>`.

   * **Insertar carácter**: Si desea agregar cualquier carácter especial en el formato, haga clic en el botón Insertar carácter (<img src="./assets/insert-chars.png" width="25">) icono. Seleccione el carácter que desee añadir en el formato de estilo y haga clic en Insert. Existen diferentes tipos de caracteres especiales que puede elegir en la lista desplegable Seleccionar categoría. Para nuestro ejemplo, seleccione el signo de comillas dobles de ángulo recto de la categoría Puntuación.

     <img src="./assets/insert-special-chars.png" width="400">


   * **Iniciar numeración desde**: Si desea que la numeración comience desde un número específico, proporcione ese valor. Para nuestro ejemplo, mantenga el valor predeterminado de 1.

   * **Sangría**: Si desea aplicar sangría al encabezado, debe establecer el valor Sangría. Para nuestro ejemplo, establézcalo en 0 px.

     >[!NOTE]
     >
     >Puede introducir el valor en píxeles, puntos, rem, em, porcentaje o en unidades (pulgadas).

   * **Anchura del prefijo**: Esta es el área ocupada por el formato de número automático. Se establece automáticamente en un tamaño que puede ajustarse fácilmente al formato de estilo seleccionado. Si desea aumentar el tamaño, puede reemplazar el valor predeterminado.

     Al configurar este valor manualmente, intente cambiar las demás propiedades que puedan afectar al ancho. Por ejemplo, para cambiar el tamaño de fuente, el formato con prefijo (Capítulo) o un sufijo (:), defina el valor máximo en la variable *Iniciar numeración desde* y las distintas propiedades de fuente para obtener el tamaño óptimo.

     Para nuestro ejemplo, mantenga el valor predeterminado.

   * **Espaciado**: especifique el espaciado horizontal y vertical. Para nuestro ejemplo, mantenga los valores predeterminados.

     Con las personalizaciones anteriores, el estilo se personaliza como se muestra a continuación:

     <img src="./assets/h1-style-custmization.png" width="500">

   * **Aplicar formato a**: las propiedades de la categoría Autonumérico le ayudarán a definir el estilo de numeración. Para aplicar más personalizaciones al estilo de numeración o al contenido del formato de encabezado, puede elegir Numeración o Párrafo en este campo. Si elige Numeración, cualquier cambio realizado en Fuente, Borde, Diseño y otras categorías se aplicará únicamente al estilo de numeración del encabezado. Sin embargo, si elige Párrafo, los cambios se aplicarán al contenido del encabezado y no al estilo de numeración.

   Utilice la siguiente configuración para generar un resultado como se muestra en la siguiente captura de pantalla:

   | **Estilo de encabezado** | **Propiedad** | **Valor** | **Comentarios adicionales** |
   | :- | :- | :- | :- |
   | h1 | Estilo | Decimal | Estas propiedades se encuentran en la categoría Autonumérico |
   |  | Formato | `Capter <x>:` |  |
   |  | Anchura del prefijo | 160 px |  |
   |  | Fuente > Alineación del texto | Izquierda | Asegúrese de que Aplicar formato a está establecido en Numeración |
   | h2 | Estilo | Decimal | Estas propiedades se encuentran en la categoría Autonumérico |
   |  | Formato | `Section <x>:` |  |
   |  | Anchura del prefijo | 125 px |  |
   |  | Fuente > Alineación del texto | Izquierda | Asegúrese de que Aplicar formato a está establecido en Numeración |
   | h3 | Estilo | Decimal | Estas propiedades se encuentran en la categoría Autonumérico |
   |  | Insertar nivel | 2 |  |
   |  | Formato | `Section <2>.<x>:` |  |
   |  | Anchura del prefijo | 125 px |  |
   |  | Fuente > Alineación del texto | Izquierda | Asegúrese de que Aplicar formato a está establecido en Numeración |
   |  |

   <img src="./assets/auto-number-output.png" width="500">

## Trabajo con estilos de párrafo {#paragraph-style}

Se puede crear un estilo de párrafo para aplicar un formato especial a todo un párrafo. Sin embargo, con la pseudoclase, puede aplicar un estilo solo a una parte específica del texto. En el siguiente ejemplo, se crea un estilo de párrafo para utilizar el estilo de letra capital.

### Creación del estilo de la letra capital {#drop-cap-style}

Se utiliza un estilo de capitular (o capital caído) en revistas y documentos literarios en los que se da un estilo especial al primer carácter de un párrafo o sección. Puede lograr el mismo efecto utilizando la función Publicación nativa de PDF.

En el siguiente ejemplo, creamos un estilo de letra capital:

1. Abra la hoja de estilo necesaria para editarla.

   >[!NOTE]
   >
   Consulte [Personalizar un estilo predefinido o nuevo](components-pdf-template.md#customize-style) para abrir una hoja de estilo para personalizarla o editarla.

1. En el **Estilos** , expanda la **Estilos de párrafo**.

1. Haga clic con el botón derecho en **Estilo de párrafo** y elija **Nuevo estilo**.

1. En el *Añadir estilo* diálogo, mantenga el **Etiqueta** nombre como p y en el **Pseudo** **Clase** , seleccione `::first-letter`.

1. Haga clic en **Listo**.

   Un nuevo estilo de párrafo llamado `::first-letter`  se crea y se añade en **Estilos de párrafo** lista.

1. Seleccionar `::first-letter` en el estilo p y defina las siguientes propiedades:

   * **Fuente**: establezca la fuente deseada para la primera letra del párrafo. Para nuestro ejemplo, defina la Familia de fuentes en cursiva, el peso de fuente en 500, el tamaño de fuente en 30 pt y elija un color de fuente.

   * **Diseño**: establezca la alineación vertical del texto alrededor del estilo de la letra capital. Para nuestro ejemplo, estableceremos la Alineación vertical en Inferior.

Como el `p` se asigna con la etiqueta `<p>` en DITA, no es necesario añadir explícitamente este estilo utilizando el atributo outputclass. Dondequiera que se encuentre el contenido `<p>` , se le aplica automáticamente el estilo de la letra capital. En la siguiente captura de pantalla, los elementos del título del capítulo, la descripción breve y la lista de definición no tienen el formato del estilo de la letra capital. Solo el estilo de párrafo tiene formato con el estilo de la letra capital:

<img src="./assets/char-style-drop-cap.png" width="500">

## Trabajar con estilos de carácter {#char-style}

Con los estilos de carácter, puede crear estilos para dar formato a caracteres o palabras dentro del contenido. Por ejemplo, puede crear un estilo de caracteres para código en línea o nombre de archivo, o bien puede crear un estilo que utilice varios formatos de estilo en el contenido seleccionado.

### Creación de un estilo de caracteres en línea {#inline-char-style}

El formato de caracteres en línea o palabras en un párrafo es un estilo muy común. El proceso de creación de un estilo en línea implica dos tareas: primero, crear un nuevo estilo en la hoja de estilo y, segundo, aplicar el estilo en el contenido mediante `outputclass` atributo.

En el siguiente ejemplo, crearemos un estilo de caracteres en línea:

1. Abra la hoja de estilo necesaria para editarla.

   >[!NOTE]
   >
   Consulte [Personalizar un estilo predefinido o nuevo](components-pdf-template.md#customize-style) para abrir una hoja de estilo para personalizarla o editarla.

1. En el **Estilos** , expanda la **Estilos de carácter**.

1. Haga clic con el botón derecho en **Estilo de carácter** y elija **Nuevo estilo**.

1. En el cuadro de diálogo Agregar estilo, mantenga **Etiqueta** nombre como span e enter `BoldItalic` en el **Clase** campo de nombre.

   <img src="./assets/create-char-style.png" width="400">

1. Haga clic en **Listo**.

   Se crea un nuevo estilo de carácter denominado código y se agrega en la lista Estilos de carácter.

1. Seleccionar `span.BoldItalic` desde el **Estilo de carácter** y establezca las siguientes propiedades:

   * **Fuente**: todas las propiedades relacionadas con la fuente se pueden personalizar desde esta sección. De forma predeterminada, hay algunas fuentes incluidas en el producto. Puede elegir la fuente que desee para el estilo de carácter. Para nuestro ejemplo, establezca la Familia de fuentes en *Serif,* y seleccione *Negrita* y *Cursiva* en la propiedad Estilo de fuente. También puede personalizar otras propiedades de fuente, como Grosor de fuente (como negrita y más claro), Decoración del texto (como subrayado, superposición), Tamaño de fuente, Color de fuente, Alineación del texto, etc.

     >[!NOTE]
     >
     También puede agregar fuentes a la plantilla, que se almacenan en la sección Recursos de la plantilla. Para obtener más información sobre cómo agregar fuentes y trabajar con recursos, consulte [Trabajo con recursos](components-pdf-template.md#work-with-resources).

   * **Diseño**: puede establecer las propiedades relacionadas con el diseño, como Altura y anchura, Margen, Relleno, Alineación, etc.

   * **Fondo**: las propiedades Background permiten dar formato al color de fondo de un estilo concreto. Puede definir el color de fondo o la imagen para cualquier estilo.

Una vez creado el estilo de caracteres en línea, debe aplicarlo al contenido. Para aplicar el estilo de código en línea, vaya a la vista de código fuente y añada la variable `outputclass` en el contenido deseado:

`outputclass="BoldItalic"`

El ejemplo siguiente muestra el formato de negrita cursiva aplicado en diferentes lugares del texto en ejecución:

<img src="./assets/char-format-applied.png" width="500">

## Personalizar estilo de lista {#custom-list-style}

Los estilos de lista contienen la configuración de estilo predeterminada para las listas ordenadas y desordenadas. Puede personalizar fácilmente estos estilos de lista para satisfacer sus requisitos de documentación.

En el siguiente ejemplo, personalizamos el estilo de lista numerada u ordenada:

1. Abra la hoja de estilo necesaria para editarla.

   >[!NOTE]
   >
   Consulte [Personalizar un estilo predefinido o nuevo](components-pdf-template.md#customize-style) para abrir una hoja de estilo para personalizarla o editarla.

1. En el **Estilos** , expanda la **Estilos de lista**.

1. Seleccione el **ol** estilo de la lista.

   Las propiedades del estilo antiguo se muestran en el panel Propiedades junto con su Vista previa.

   <img src="./assets/list-style-default.png" width="500">

1. Seleccione el **Formato avanzado** opción.

   Se muestra un mensaje de confirmación.

1. Clic **Sí** en el *Confirmación* para abrir el **Formato avanzado** propiedades.

   Las siguientes propiedades están disponibles de forma predeterminada:

   * **Nivel**: De forma predeterminada, hay 6 niveles de listas numeradas. El nivel que seleccione en esta lista desplegable controla los cambios de estilo en el nivel seleccionado y en todos los niveles subsiguientes. Por ejemplo, si selecciona el nivel 4, todos los cambios de estilo que aplique se establecerán en los niveles 4, 5 y 6.

   * **Tipo de estilo de lista**: puede elegir entre varios estilos de numeración de listas. La lista contiene estilos de numeración genéricos y específicos de la configuración regional que se utilizan para crear una lista numerada. Algunos de los tipos de estilo de la lista son árabe, camboyano, devanagari, etíope, hangul, hebreo, japonés, coreano, chino simple, urdu y más.

   Además, puede trabajar con las siguientes propiedades de formato avanzado:

   * **Formato de número**: el formato predeterminado está establecido en `<x>`, donde la variable `x` El valor se reemplaza por el estilo de numeración seleccionado en la propiedad Tipo de estilo de lista. Por ejemplo, si ha seleccionado `decimal` (1) estilo, luego el valor de `x` se incrementa automáticamente por cada instancia del elemento de lista y se va como 2, 3, etc. También puede agregar texto personalizado en el campo para dar formato al estilo de la lista. Por ejemplo, si desea que todos los estilos de lista de primer nivel tengan un sufijo &quot;`)`&quot;, entonces debe establecer este campo para el estilo de lista de primer nivel como &quot;`<x>)`&quot;.

   * **Insertar carácter**: Si desea agregar cualquier carácter especial en el formato de número, haga clic en el botón Insertar carácter (<img src="./assets/insert-chars.png" width="25">) icono. Seleccione el carácter que desee añadir en el formato de estilo y haga clic en Insert. Existen diferentes tipos de caracteres especiales que puede elegir en la lista desplegable Seleccionar categoría.

   * **Insertar nivel**: Puede incluir el número de cualquiera de los niveles anteriores en el formato de número. Por ejemplo, si desea incluir el formato de número del quinto nivel en el formato de número del sexto nivel, elija 5 en la lista desplegable Insertar nivel. Tenga en cuenta que la lista desplegable Insertar nivel muestra los números solo de los niveles anteriores y no del siguiente nivel. Por ejemplo, mientras se encuentra en el Nivel 3, la lista Insertar nivel sólo mostrará los niveles 1 y 2.

     <img src="./assets/list-insert-level.png" width="400">

     También puede cambiar el formato de número para presentar los valores de la lista según sea necesario. Por ejemplo, cuando utiliza un estilo de numeración anidado para el nivel 3, puede darle el formato &quot;`<2>.<x>))`&quot;. Se mostrará la lista número 2, seguida de un punto, seguida de la lista número 3 y, a continuación, dos paréntesis, como `2.3))`.

   * **Sangría**: Si desea aplicar sangría a la lista, debe establecer el valor Sangría. Cualquier cambio en la sangría se puede revisar en el panel Previsualización y ajustar.

     >[!NOTE]
     >
     Puede introducir el valor en píxeles, puntos, rem, em, porcentaje o en unidades (pulgadas).

   * **Anchura del prefijo**: Esta es el área ocupada por el Formato de número. Se establece automáticamente en un tamaño que puede ajustarse fácilmente al formato seleccionado. Si desea aumentar el tamaño, puede reemplazar el valor predeterminado.

     Al configurar este valor manualmente, intente cambiar las demás propiedades que puedan afectar al ancho. Por ejemplo, cambie el tamaño de fuente, el formato con prefijo o un sufijo y las distintas propiedades de fuente para obtener el tamaño óptimo.

   * **Espaciado**: especifique el espaciado horizontal entre el formato de número de lista y el contenido. El espaciado vertical controla el espacio entre los dos elementos de la lista.

     La siguiente captura de pantalla muestra la lista ordenada personalizada para cada nivel:

     <img src="./assets/list-number-format-final.png" width="500">

## Trabajar con estilo de tabla {#table-styles}

Con las hojas de estilo, puede diseñar *n* número de estilos de tabla. Con los estilos de tabla, puede diseñar cómo se muestra toda la tabla, una fila o una columna en particular. Con el control al nivel de celda, puede crear estilos de tabla muy presentables.

En el siguiente ejemplo, vemos cómo crear un estilo de tabla y las distintas opciones de estilo de tabla que puede personalizar:

1. Abra la hoja de estilo necesaria para editarla.

   >[!NOTE]
   >
   Consulte [Personalizar un estilo predefinido o nuevo](components-pdf-template.md#customize-style) para abrir una hoja de estilo para personalizarla o editarla.

1. En el **Estilos** Haga clic con el botón derecho en la lista **Estilo de tabla** y elija **Nuevo estilo**.

1. En el *Añadir estilo* diálogo, mantenga el **Etiqueta** nombrar como `table` y escriba `double-border` en el **Clase** campo de nombre.

1. Haga clic en **Listo**.

   Un nuevo estilo de tabla denominado `table.double-border` se crea y se agrega en la lista Estilos de tabla.

1. Seleccionar `table.double-border` desde el **Estilos de tabla** y establezca las siguientes propiedades:

   * **Aplicar formato a**: puede elegir aplicar el formato de estilo a toda la tabla, a las filas o columnas impares/pares o a la primera/última fila o columna.

     >[!NOTE]
     >
     Las siguientes configuraciones están disponibles en la **General** sección cuando **Aplicar formato a** se establece en **Toda la tabla**.

   * **Ajuste de texto**: seleccione cómo ajustar el texto alrededor de la tabla. Esto resulta útil cuando la tabla está dentro de otro elemento de nivel de bloque y la tabla debe representarse junto con otro contenido del elemento de bloque. Las opciones de ajuste son *left* o *derecha* alineado, o *ninguno*.

   * **Contraer borde**: seleccione el aspecto del borde de la tabla. Si selecciona contraer, sólo se dibujará una única línea de borde entre las celdas de la tabla. Sin embargo, para estilos independientes, el borde es visible alrededor de cada celda con relleno adicional.

     <img src="./assets/table-style-collapse-separate.png" width="500">

   * **Espaciado del borde**: esta configuración solo está disponible cuando Contraer borde está establecido en Separar. Con esta configuración, puede especificar el espaciado vertical y horizontal entre los bordes de las celdas.

     <img src="./assets/table-border-spacing.png" width="500">

     >[!NOTE]
     >
     Las siguientes configuraciones están disponibles en la **Celda** sección cuando **Aplicar formato a** se establece en **Toda la tabla**.

   * **Relleno**: especifique el relleno entre las celdas de la tabla. Puede especificar diferentes valores de relleno para los lados superior, inferior, izquierdo y derecho.

   * **Alineación vertical**: especifique la alineación vertical para el contenido de la celda. Las opciones disponibles son: Superior, Medio e Inferior.

   * **Borde, estilo, color, anchura y radio:** Especifique las propiedades relacionadas con los bordes. Puede elegir que los bordes estén sólo en lados específicos, como Izquierda o Derecha. El estilo de borde muestra los estilos de borde disponibles, como Sólido, Discontinuo, Doble línea, etc. Especifique el color del borde con la paleta de colores. Puede especificar el ancho del borde en píxeles, puntos, rem, em, % y en unidades. El Radio define la curva para crear esquinas circulares.

   Las demás propiedades de Fuente, Borde, Diseño, Paginación y Fondo se explican en otros ejemplos de este tema. Según la selección en la **Aplicar formato a** , puede aplicar estos valores a toda la tabla o a las filas o columnas seleccionadas.

   A continuación, se muestra una vista previa de una tabla de ejemplo con diferentes filas formateadas de una manera diferente:

   <img src="./assets/table-final-design.png" width="500">

## Trabajar con otros estilos {#other-styles}

Si está trabajando con contenido estructurado (DITA), observará que casi todos los elementos DITA tienen una asignación de estilo en la hoja de estilo por defecto. Por ejemplo, una `<shortdesc>` el estilo del elemento se define en **Otro estilo** > **.shortdesc** definición de estilo. Puede personalizar fácilmente cualquiera de estos estilos y se aplicarán automáticamente en la salida del PDF generada a partir del contenido estructurado. Esto significa que, a diferencia de otros estilos personalizados, no es necesario agregar un `outputclass` en el contenido de estos estilos.

Si desea crear una definición de estilo para cualquier elemento que no esté disponible de forma predeterminada o si tiene un elemento personalizado, puede crearlo fácilmente en la hoja de estilo. El único punto que debe tener en cuenta es crear el estilo con el mismo nombre que el nombre del elemento estructurado.

En el ejemplo siguiente, crearemos un título de ventana nueva (`wintitle`) estilo:

1. Abra la hoja de estilo necesaria para editarla.

   >[!NOTE]
   >
   Consulte [Personalizar un estilo predefinido o nuevo](components-pdf-template.md#customize-style) para abrir una hoja de estilo para personalizarla o editarla.

1. En el **Estilos** lista, expandir **Otros estilos**.

1. Haga clic con el botón derecho en **Otro estilo** y elija **Nuevo estilo**.

1. En el *Añadir estilo* diálogo, mantenga el **Etiqueta** nombrar como *blank* y escriba `wintitle` en el **Clase** campo de nombre.

   Como `wintitle` es un nombre de elemento DITA reconocido, su definición de estilo se asigna automáticamente al `<wintitle>` en el origen.

1. Haga clic en **Listo**.

   Un nuevo estilo denominado `.wintitle` se crea y se añade en **Otros estilos** lista.

1. Seleccione .wintitle en **Otros estilos** y establezca las propiedades según sea necesario.

La siguiente captura de pantalla muestra el estilo wintitle que se está aplicando al texto &quot;Control principal&quot;.

<img src="./assets/other-style-wintitle.png" width="500">
