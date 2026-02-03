---
title: PDF nativo | Generación de salida de PDF
description: Obtenga información sobre cómo utilizar la publicación nativa de PDF, crear y generar un ajuste preestablecido de salida de PDF, descargar archivos temporales después de generar la salida nativa de PDF y utilizar variables de idioma en Adobe Experience Manager Guides.
exl-id: ec3d59b7-1dda-4fd1-848e-21d8a36ff5e4
feature: Publishing, Native PDF Output
role: User
source-git-commit: a6dafe6c634b872001a2b82d9d081b3e52a75b80
workflow-type: tm+mt
source-wordcount: '3293'
ht-degree: 0%

---

# Ajuste preestablecido de salida de PDF nativo

Al crear contenido, es esencial asegurarse de que el contenido esté optimizado para su visualización, edición e impresión. Mediante estándares como W3C CSS3 para el estilo de contenido y los estándares de medios paginados CSS para las propiedades de definición de página como tamaño, márgenes, orientación, saltos de página, encabezados, pies de página y numeración de páginas, puede establecer la vista y el diseño del documento de PDF, lo que garantiza la coherencia y la facilidad de uso. La función de publicación nativa de PDF utiliza estos estándares para generar un PDF.

Con la publicación nativa de PDF, puede utilizar plantillas predefinidas para garantizar la coherencia en el diseño y la estructura del contenido, aplicar hojas de estilo para alterar el aspecto de la salida, optimizar PDF, establecer marcas de impresora, permitir la compatibilidad con lectores de pantalla, establecer la conformidad con PDF, incrustar fuentes y mucho más.

La generación de un PDF mediante la publicación nativa de PDF tiene dos aspectos:

* Uso de plantillas para aplicar estilo al contenido, establecer diseños de página y varias configuraciones para ajustar el PDF. Los autores pueden elegir utilizar o modificar las plantillas de ejemplo proporcionadas o crear plantillas personalizadas y establecer las opciones de configuración avanzadas que utilizan los editores y desarrolladores.

* Cree o configure un ajuste preestablecido de salida de PDF para controlar la configuración de PDF. Una vez creado un ajuste preestablecido de salida de PDF, puede generar PDF.

## Crear un ajuste preestablecido de salida

Siga estos pasos para crear el ajuste preestablecido de PDF desde la consola Mapa:

1. [Abra un archivo de mapa DITA en la consola de mapas](../user-guide/open-files-map-console.md).

   También puede obtener acceso al archivo de asignación desde el widget **Archivos recientes** en la [sección Información general](../user-guide/intro-home-page.md#overview). El archivo de mapa seleccionado se abriría en la consola de mapas.
1. En la pestaña **Ajustes preestablecidos de salida**, seleccione el icono + para crear un ajuste preestablecido de salida.
1. Seleccione **PDF** del menú desplegable Tipo en el cuadro de diálogo **Nuevo ajuste preestablecido de salida**.
1. En el campo **Nombre**, proporcione un nombre para este ajuste preestablecido.
1. En el campo **Generar PDF mediante**, seleccione **Native-PDF**.
1. Seleccione la opción **Agregar al perfil de carpeta actual** para crear un ajuste preestablecido de salida dentro del perfil de carpeta actual. El ![icono de perfil de carpeta](./assets/global-preset-icon.svg) indica un ajuste preestablecido de nivel de perfil de carpeta.

   Obtenga más información sobre [Administrar ajustes preestablecidos de salida de perfil global y de carpeta](../user-guide/web-editor-manage-output-presets.md).

1. Seleccione **Añadir**.

   Se crea el ajuste preestablecido de PDF.

## Configuración del ajuste preestablecido nativo de PDF

Una vez creado el ajuste preestablecido, configure el ajuste preestablecido nativo de PDF. Las opciones de configuración preestablecidas para DITA-OT se organizan en las fichas **General**, **Metadatos**, **Diseño**, **Seguridad**, **Imprimir** y **Avanzado**.

<img src="assets/preset-panel-new.png" alt="panel preestablecido" width="800">

**General**

Utilice para especificar la configuración básica de salida, como especificar la ruta de salida, el nombre del archivo PDF, etc.

| Configuración | Descripción |
| --- | --- |
| **Ruta de salida** | Ruta de acceso dentro del repositorio de AEM donde se almacena la salida de PDF. Asegúrese de que la ruta de acceso de salida no esté ubicada dentro de la carpeta del proyecto. La ruta de acceso de salida se establece a través de la variable `${base_output_path}`, que configura el administrador. Para configurar la ruta de salida, vea [Configurar la ubicación de salida base para Cloud Services](../native-pdf/configure-base-location-cs.md) o [Configurar la ubicación de salida base para On-Premise Services](../native-pdf/configure-base-output-location.md) según el servicio que esté usando. <br>También puede utilizar las siguientes variables integradas para definir la ruta de acceso de salida. Puede utilizar una sola variable o una combinación de ellas para definir esta opción. <br> `${map_filename}`: utiliza el nombre de fichero de mapa DITA para crear la ruta de destino. <br> `${map_title}`: utiliza el título de mapa DITA para crear la ruta de destino. <br>`${preset_name}`: utiliza el nombre del ajuste preestablecido de salida para crear la ruta de destino. <br> `${language_code}`: utiliza el código de idioma donde se encuentra el archivo de asignación para crear la ruta de acceso de destino. <br> `${map_parentpath}`: utiliza la ruta completa del archivo de asignación para crear la ruta de destino.  <br>`${path_after_langfolder}`: utiliza la ruta del archivo de asignación después de la carpeta de idioma para crear la ruta de destino. |
| **Archivo PDF** | Especifique un nombre de archivo para guardar PDF. De forma predeterminada, el nombre del fichero PDF añade el nombre del mapa DITA junto con el nombre del ajuste preestablecido. Por ejemplo, ditamap es &quot;TestMap&quot; y el nombre del ajuste preestablecido es &quot;preset1&quot;, el nombre predeterminado del pdf será &quot;TestMap_preet1.pdf&quot;. <br>También puede usar las siguientes variables predeterminadas para definir el archivo de PDF. Puede utilizar una sola variable o una combinación de ellas para definir esta opción. <br>`${map_filename}`<br>`${map_title}`<br>`${preset_name}` <br> `${language_code}`. |
| **Aplicar condiciones usando** | Para el contenido condicionado, elija entre las siguientes opciones para generar una salida de PDF basada en esas condiciones: <br><ul> <li> **Ninguno aplicado** Seleccione esta opción si no desea aplicar ninguna condición en el mapa y en el contenido de origen. <br><li> **Archivo DITAVAL** Seleccione un archivo DITAVAL para generar contenido condicional. Puede seleccionar varios archivos DITAVAL utilizando el cuadro de diálogo de exploración o introduciendo la ruta de archivo manualmente. Para quitar un archivo seleccionado, haga clic en el icono cruzado junto a su nombre. Si se selecciona un archivo no válido, aparece un mensaje de error indicando **Se ha seleccionado un archivo DITAVAL no válido**. <br> <br>Cada archivo DITAVAL puede contener una serie de propiedades, como condiciones de filtrado y estilos de indicación. El marcado le permite marcar visualmente el contenido mediante marcas de inicio y finalización, que pueden incluir imágenes o formato de texto como negrita o cursiva. En caso de que se superpongan condiciones o conflictos de estilo, puede definir un color de fondo mediante la configuración de conflictos de estilo. Para obtener más información, vea [Usar el editor DITAVAL](../user-guide/ditaval-editor.md).<br><li> **Ajuste preestablecido de condición** Seleccione un ajuste preestablecido de condición en la lista desplegable para aplicar una condición al publicar la salida. Esta opción está visible si se ha añadido una condición para el fichero de mapa DITA. La configuración condicional está disponible en la ficha Ajustes preestablecidos de condición de la consola de mapas DITA. Para obtener más información acerca del ajuste preestablecido de condición, vea [Usar ajustes preestablecidos de condición](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-condition-presets.html). <br> </ul> |
| **Usar línea de base** | Si ha creado una Línea base para el mapa DITA seleccionado, seleccione esta opción para especificar la versión que desea publicar. Ver [Trabajo con línea de base](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-baseline-for-publishing.html) para obtener más detalles. |
| **Crear PDF con barra de cambios entre versiones publicadas** | Utilice las siguientes opciones para crear un PDF que muestre las diferencias de contenido entre dos versiones con las barras de cambios:   <br><ul><li> **Línea de base de la versión anterior** Elija la versión de línea de base que desea comparar con la versión actual u otra línea de base. Aparecerá una barra de cambios en PDF para indicar el contenido modificado. Una barra de cambios es una línea vertical que identifica visualmente el contenido nuevo o revisado. La barra de cambios aparece a la izquierda del contenido que se ha insertado, modificado o eliminado. <br> **Nota**: Si selecciona **Usar línea de base** y elige una línea de base para publicar, la comparación se realizará entre las dos versiones de línea de base seleccionadas. Por ejemplo, si elige la línea de base Versión 1.3 en **Usar línea de base** y Versión 1.1 en **Línea de base de la versión anterior**, la comparación se realizará entre la línea de base Versión 1.1 y la línea de base Versión 1.3. <br><li> **Mostrar texto agregado** Seleccione esta opción para mostrar el texto insertado en color verde y subrayado. Esta opción está seleccionada de forma predeterminada. <br> <li> **Mostrar texto eliminado** Seleccione esta opción para mostrar el texto eliminado en color rojo y marcado con un tachado. Esta opción está seleccionada de forma predeterminada. <br>**Nota** También puede personalizar el estilo de la barra de cambios, el contenido insertado o el contenido eliminado mediante la hoja de estilo.<br></ul> |
| **Idioma** | Seleccione el idioma en el que desea traducir el resultado. <br> **Nota**: Los textos de referencia cruzada como &quot;Ver en el capítulo&quot; o &quot;Ver en la página&quot; están controlados por una variable de idioma. La variable utiliza el lenguaje definido en el tema a través del atributo `xml:lang`. Si no se especifica ningún idioma, se usa el idioma preestablecido. Si faltan ambos, el valor predeterminado es inglés (en_US). |

| **Flujo de trabajo de generación posterior** |Seleccione para mostrar una lista desplegable que contenga todos los flujos de trabajo configurados en AEM. Puede seleccionar el flujo de trabajo que desea ejecutar después de la finalización del flujo de trabajo de generación de PDF.|

**Metadatos**

Los metadatos son la descripción o definición del contenido. Los metadatos ayudan en la administración de contenido y en la búsqueda de archivos en Internet.

Utilice la pestaña Metadatos para establecer los campos de metadatos, como el nombre del autor, el título del documento, las palabras clave, la información de copyright y otros campos de datos para la salida de PDF. También puede agregar metadatos personalizados para la salida de PDF.

Estos metadatos se asignan a los metadatos de la ficha **Descripción** dentro de las **Propiedades del documento** de su PDF de salida.



<img src="assets/pdf-metadata.png" alt="ficha de metadatos" width="600">

En los ajustes preestablecidos de salida, seleccione **PDF** > **Native-PDF** > **Metadatos** para agregar y personalizar opciones de metadatos.
* **Usar metadatos agregados en topicmeta**

  Esta opción está seleccionada de forma predeterminada. Puede utilizar los metadatos que ha añadido en el elemento meta del tema del mapa DITA para rellenar los campos de metadatos de la salida de PDF.

* **Proporcionar archivo XMP**

  También puede rellenar directamente los campos de metadatos importando el archivo [XMP](https://www.adobe.com/products/xmp.html) (Extensible Metadata Platform). Puede descargar un archivo de XMP de ejemplo desde aquí.

[Descargar](assets/SampleXMP.xmp)

  También puede generar un archivo XMP con Adobe Acrobat.
   1. Seleccione **Archivo** > **Propiedades** en Acrobat.
   1. En **Descripción**, seleccione **Metadatos adicionales**.
   1. En el panel izquierdo, seleccione **Avanzado**.
   1. Seleccione **Guardar**.

  El archivo XMP se guardará en el dispositivo.

* **Proporcionar nombres y valores de metadatos**

   1. Añada un nombre seleccionándolo en la lista desplegable o agregue metadatos personalizados escribiendo directamente en el campo de nombre.
   1. Introduzca el valor de los metadatos y seleccione el icono &quot;+&quot;.
Los metadatos se añaden a la lista de metadatos de PDF.

También puede utilizar variables para definir los valores de los metadatos.  Se pueden utilizar los metadatos definidos para el mapa DITA o el fichero bookmap como variables. Los metadatos se encuentran en el nodo `/jcr:content/metadata` del mapa DITA o del archivo bookmap.
Cuando se utiliza una variable, su valor se selecciona de las propiedades de metadatos.

Para utilizar una variable, debe definirla en el formato `${<variable>}`.

Por ejemplo, una de las propiedades de metadatos definidas en el nodo /`jcr:content/metadata` es
`dc:title`. Puede especificar `${dc:title}`, y el valor del título se utilizará en el resultado final.

Puede utilizar una sola variable o una combinación de ellas para definir los metadatos. Por ejemplo, `${dc:title} ${dc:docstate}`. También puede utilizar la combinación de una variable y una cadena.  Por ejemplo, `View ${dc:title} in ${dc:language}`.

Utilice variables de idioma para definir el valor localizado de las propiedades de los metadatos. Según el idioma elegido, el valor localizado se selecciona automáticamente en la salida de PDF. Por ejemplo, puede imprimir &quot;Autor&quot; como el valor de los metadatos en inglés y &quot;Autor&quot; en alemán.

Formato: `${lng:<variable name>}`. Por ejemplo, `${lng:author-label}` donde `author-label` es una variable de idioma.

Pase el ratón sobre <img src="./assets/info-details.svg" alt= "icono de información" width="25"> cerca de la opción para ver más detalles al respecto.


**Diseño**

Utilice para definir los diseños de página y especificar las opciones de vista de página para la salida de PDF, como Visualización de página y definir los niveles de zoom.

| Configuración | Descripción |
| --- | --- |
| **Plantilla de PDF** | Las plantillas de PDF proporcionan una estructura clara para definir diseños de página, estilos de contenido y aplicar varias configuraciones a la salida de PDF. Seleccione en las opciones desplegables de PDF template para elegir la plantilla que prefiera. <br> También puede seleccionar **Examinar plantilla** <img src="./assets/browse-templates-icon.svg"  alt= "icono examinar plantillas" width="25"> para elegir una plantilla. En el cuadro de diálogo **Seleccionar plantilla de PDF** también puede obtener una vista previa de la miniatura y ver el título y la descripción de la plantilla seleccionada. |
| **Visualización de página** | Utilice la Visualización de página para la vista de página que muestra cómo se muestra PDF cuando se abre. Seleccione en las opciones desplegables de Visualización de página para elegir una vista preferida. <br><ul><li> **Predeterminado** se muestra según la configuración predeterminada del visor de PDF en el equipo de un usuario.  <br> <li> **Vista de página única** muestra una página cada vez.   <br> <li> **Desplazamiento de página única** Muestra una sola página en una columna vertical continua.  <br> <li> **Vista de dos páginas** muestra dos páginas en paralelo a la vez. .<br> <li> **Desplazamiento de dos páginas** Muestra un pliego de dos páginas en paralelo con desplazamiento continuo. </ul> |
| **Zoom** | Seleccione esta opción para cambiar el tamaño de la vista de página que muestra cómo se muestra PDF cuando se abre.  <br><ul><li> **Predeterminado** se muestra según la configuración predeterminada del visor de PDF en el equipo de un usuario    <br> <li> **100%** Hace que la página aparezca en su tamaño real.     <br> <li> **Ajustar página** Hace que el ancho y el alto de la página se ajusten al panel del documento.   .<br> <li> **Ajustar ancho de página** Hace que el ancho de la página llene el ancho del panel del documento.  <br> <li> **Ajustar alto de página** Hace que el alto de la página ocupe el alto del panel del documento. </ul> |

**Seguridad**

Proteja su PDF agregando restricciones para abrir y leer el archivo. Utilice las siguientes opciones para evitar el acceso no autorizado.

| Configuración | Descripción |
| --- | --- |
| **Establecer contraseña para abrir el documento** | Seleccione para añadir una contraseña segura para ver el archivo PDF. Especifique una contraseña en el campo **Contraseña de usuario**. Los usuarios solo pueden abrir PDF introduciendo la contraseña proporcionada en este campo. |
| **Establecer las restricciones del documento** | Seleccione esta opción para restringir la forma en que los usuarios pueden interactuar con su PDF. Especifique una contraseña en el campo **Contraseña de propietario** para que funcione la siguiente configuración de restricción.  <br><ul><li> **Impresión** Seleccione esta opción para permitir que un usuario imprima el PDF. <br> <li> **Impresión de calidad de borrador** Seleccione esta opción para permitir que un usuario imprima el PDF en una resolución inferior.  <br> <li> **Copia de contenido** Seleccione esta opción para permitir que un usuario copie contenido de PDF.   <br> <li> **Anotaciones** Seleccione esta opción para permitir que un usuario agregue una nota o comentario en PDF. <br> <li> **Modificaciones de contenido** Seleccione esta opción para permitir que un usuario modifique el contenido de PDF. <br> <li> **Copia de contenido para accesibilidad** Seleccione esta opción para permitir que los lectores de pantalla lean y naveguen por el contenido en PDF. <br>  **Ensamblado de documento** Seleccione esta opción para permitir que los usuarios inserten páginas en PDF. <br> **Nota**: los usuarios deben escribir la contraseña de propietario para cambiar las restricciones de Archivo > Propiedades en Adobe Acrobat. |

**Imprimir**

>[!NOTE]
>
> A partir de la versión 5.0/2025.02.0 de Experience Manager Guides, la sección Imprimir ahora forma parte del **ajuste preestablecido de salida nativa de PDF**. Para las plantillas existentes con la configuración de impresión guardada, los datos de impresión permanecerán intactos, pero ya no aparecerán en la interfaz de usuario ni se aplicarán durante la salida. Para seguir utilizando esta configuración, debe volver a configurarla en el ajuste preestablecido de salida nativa de PDF.

Configure las opciones de producción de impresión para asignar marcas de impresora, seleccionar modelos de color y especificar propiedades relacionadas con la impresión de la salida de PDF.

* **Marcas de impresora**: cuando se prepara un documento para la producción de impresión, las marcas de impresora se agregan a los límites de la página para ayudar en la alineación, el recorte y la selección de color adecuados durante la impresión. Al seleccionar una marca de impresora, el límite de página se amplía para dar cabida a la marca, que se recorta durante la impresión. Puede elegir mostrar las siguientes marcas de impresora en la salida de PDF:
   * **Marcas de recorte**: seleccione la opción para colocar una marca en cada esquina del área de recorte e indicar dónde debe recortarse el papel después de la impresión.
   * **Marcas de sangrado**: seleccione esta opción para colocar una marca en cada esquina del cuadro de sangrado e indicar el área de recorte de la imagen ampliada.
   * **Marcas de registro**: seleccione esta opción para colocar una marca fuera del área de recorte y alinear las diferentes separaciones de un documento de color.
   * **Barras de color**: seleccione esta opción para agregar una franja de colores fuera del área de recorte para mantener la coherencia del color y ajustar la densidad de la tinta al imprimir.

  Defina las dimensiones para las marcas de impresora seleccionadas utilizando las opciones **Anchura de línea**, **Color de línea** y **Anchura de cuadro de sangría**.

* **Tamaño de caja de medios**: Este es el tamaño total de la página, incluyendo el área extendida ocupada por las marcas de impresora. Utilice la opción desplegable para seleccionar el tamaño de página de la salida de PDF o crear su propio tamaño personalizado.

* **Espacio de color**: tiene la opción de elegir entre espacios de color RGB o CMYK para imprimir el documento de PDF. Elija RGB para mostrar el PDF generado digitalmente y CMYK para la impresión física. Los colores definidos en el documento se convierten al espacio de color elegido.

* **Perfil ICC**: aquí puede administrar la precisión de color entre dispositivos especificando un perfil ICC. Esto garantiza una representación uniforme del color en la salida impresa.

Para configurar esta opción, especifique la ruta del archivo de perfil ICC en el servidor y proporcione el nombre del perfil ICC para facilitar la identificación. Alternativamente, si el perfil ICC se almacena en línea, puede proporcionar su URL en lugar de la ruta del archivo.

>[!NOTE]
>
> Es necesario un perfil de color ICC para la creación de PDF/A si se utiliza el espacio de color CMYK.

<!--For more information on applying these print settings, see *Printing preferences*.-->

**Avanzado**

Utilice las siguientes opciones para especificar la configuración avanzada para combinar archivos PDF, utilizar compresión, seleccionar el estándar de conformidad y mucho más.

| Configuración | Descripción |
| --- | --- |
| **Crear PDF accesible (etiquetado)** | Seleccione esta opción para generar una PDF con etiquetas. Una PDF etiquetada facilita a los lectores de pantalla la lectura y la navegación por el contenido, los hipervínculos, los marcadores, etc. Por ejemplo, si se etiqueta una tabla, el lector de pantalla sabrá que está leyendo la tabla y no solo líneas y texto. |
| **Combinar PDF incluidos en el índice** | Seleccione esta opción para combinar los PDF existentes en la salida agregándolos al mapa DITA como un fichero de recursos. Los PDF se insertarán en la ubicación representada en el mapa y las páginas se incrementarán en consecuencia. |
| **Incrustar fuentes utilizadas** | Seleccione esta opción cuando utilice fuentes que no estén instaladas en el equipo del usuario final. Con esta opción seleccionada, las fuentes utilizadas se incrustan en el PDF, lo que garantiza que el usuario pueda ver el PDF como estaba previsto aunque las fuentes no estén instaladas en el equipo. <br> **Nota**: una fuente solo se puede incrustar si contiene una configuración del proveedor de fuentes que permita su incrustación. Asegúrese de tener la configuración o licencia necesarias antes de incrustar una fuente. |
| **Usar división automática de palabras** | Con la división automática de palabras habilitada, las palabras al final de las líneas se dividen en lugares gramaticalmente correctos con un guión. |
| **Habilitar JavaScript** | Active esta opción si tiene un código JavaScript que desee utilizar para transformar el contenido dinámicamente antes de generar un PDF. |
| **Incrustar archivos multimedia** | Seleccione esta opción para incluir cualquier audio, vídeo y contenido interactivo en PDF. |
| **Use compresión completa para optimizar el tamaño de PDF** | Seleccione esta opción si desea comprimir o reducir el tamaño de un PDF grande. Recuerde que la compresión de PDF puede reducir la calidad del archivo. |
| **Use la compresión de imágenes para optimizar el tamaño de PDF** | Seleccione esta opción si desea comprimir o reducir el tamaño de las imágenes utilizadas en el PDF. Recuerde que la compresión de una imagen puede reducir la calidad de la imagen. |
| **Usar resolución personalizada (píxeles por pulgada)** | Es la resolución de visualización de la página en píxeles por pulgada. Introduzca un valor preferido en el campo que aparece cuando se selecciona esta opción. El valor predeterminado es 96 píxeles por pulgada. Configure un valor más alto para que quepa más contenido en una pulgada y viceversa, si establece un valor más bajo. |
| **Mostrar filigrana** | Seleccione esta opción para superponer una marca de agua en la salida. Puede escribir una nueva cadena de texto en el cuadro de texto con la letra mayúscula tal y como desee. <br><br>Use texto estático o variables de idioma para publicar la versión localizada de la marca de agua.  Según el idioma elegido, el valor localizado se selecciona automáticamente en la salida de PDF. Por ejemplo, puede imprimir &#39;Publisher&#39; como marca de agua en inglés y &#39;Auteure&#39; en francés.  Formato <br>: `${lng:<variable name>}`. Por ejemplo, `$ {lng:publisher-label}` donde `publisher-label` es una variable de idioma. <br> pasar el ratón por encima <img src="./assets/info-details.svg" alt= "icono de información" width="25"> cerca de la opción para ver más detalles al respecto. |
| **Habilitar ecuaciones de MathML** | Seleccione esta opción para procesar las ecuaciones de MathML presentes en el contenido. Las ecuaciones se ignorarán de forma predeterminada. |
| **Crear formulario PDF interactivo** | Seleccione esta opción si desea incluir campos de formulario de PDF interactivos y personalizables para mejorar la entrada del usuario en las salidas de PDF generadas. |
| **Incluir cambios de seguimiento** | Seleccione esta opción si desea incluir las marcas de revisión en el PDF generado para facilitar la revisión y comparación. |
| **Conservar archivos temporales** | Seleccione esta opción si desea conservar los archivos HTML provisionales creados al generar la salida nativa de PDF. Posteriormente, puede descargar los archivos temporales después de generar la salida. Los archivos descargados también incluirían `system_config.xml` archivo que le brinda información sobre la URL del autor, la URL local y la URL de publicación. Estas direcciones URL se configuran en la configuración de externalización de AEM y se reflejan en el archivo `system_config.xml`. |
| **Conformidad de PDF** | Es el estándar con el que pretende guardar el PDF para asegurarse de que es compatible. Seleccione en el menú desplegable para elegir entre la lista de estándares de PDF disponibles. Para obtener más información acerca de los estándares admitidos, vea [Acerca de los estándares de PDF](https://helpx.adobe.com/es/acrobat/using/pdf-conversion-settings.html#about_pdf_x_pdf_e_and_pdf_a_standards). |
| **Propiedades de archivo** | Seleccione los metadatos que desea pasar a la publicación nativa de PDF. La lista desplegable enumera las propiedades personalizadas y predeterminadas. Por ejemplo, `dc:description`, `dc:language`, `dc:title` y `docstate` son las propiedades predeterminadas, mientras que puede tener `author` como propiedad personalizada. Las propiedades de metadatos seleccionadas se pasan al archivo de PDF generado mediante el PDF nativo. <br> Estas propiedades se seleccionaron del archivo `metadataList` disponible en:`/libs/fmdita/config/metadataList`. <br>Este archivo se puede superponer en: `/apps/fmdita/config/metadataList`. |



<!--------------


### Additional notes for PDF output

**Download temporary files after generating the Native PDF output**

If you select the **Download temporary files** option in the Advanced settings, you can also download the interim HTML files created while generating the Native PDF output. Once you've generated the output, you can download the temporary files using the **Download temporary files** ![download temporary files](assets/native-pdf-download-temporary-files-icon.svg)icon on the top bar. This feature helps you view your interim HTML styles and layouts and helps you correct or change your CSS styles according to your requirements.


>[!NOTE]
>
> The **Download temporary files**  ![download temporary files](assets/native-pdf-download-temporary-files-icon.svg) icon appears only if you have generated the last PDF output using the preset wherein you have selected the option in the **Advanced** tab. 


**Use language variables**

AEM Guides also provides the support for language variables. Select **Language Variables** <img src="assets/language-variables.svg" width="25">  in the left panel to define a localized version of the out-of-the-box labels like Note, Caution, and Warning or static text in the PDF output. For more details, view [Support for language variables](../native-pdf/native-pdf-language-variables.md).


**Support for Markdown documents**

Experience Manager Guides also provides support for your Markdown documents.  Markdown files are easy to author and also provide a variety of formatting options. Learn how to [author Markdown documents from the Editor](../user-guide/web-editor-markdown-topic.md). 

You can add the Markdown topics to your DITA map and generate the PDF output using the Native PDF output presets.  Learn how to configure or [create a PDF output preset](#create-a-pdf-output-preset-create-output-preset). 

--------------->