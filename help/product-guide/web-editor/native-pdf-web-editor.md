---
title: PDF nativo | Generación de salida de PDF
description: Obtenga información sobre cómo utilizar la publicación de PDF nativos, crear y generar un ajuste preestablecido de salida de PDF, descargar archivos temporales después de generar la salida de PDF AEM nativo y utilizar variables de idioma en las guías de usuario de los idiomas.
exl-id: ec3d59b7-1dda-4fd1-848e-21d8a36ff5e4
source-git-commit: b8c90eb8d1acfe6777a615bd71367027cd8d1c3b
workflow-type: tm+mt
source-wordcount: '3196'
ht-degree: 0%

---

# Salida del PDF de publicación

AEM Con las guías de la aplicación, puede generar PDF de temas individuales o de un archivo de mapa completo. Puede publicar el contenido en formato de PDF mediante uno de los tres métodos siguientes:

* **DITA-OT**

Utilice este método para generar una salida de PDF para un mapa desde el panel de mapas. Puede establecer las propiedades de publicación antes de generar el PDF creando un ajuste preestablecido de salida para el mapa que está abierto en el panel de mapas. Para crear o editar un ajuste preestablecido de salida, la variable *Explicación de los ajustes preestablecidos de salida* de la sección [AEM Guía del usuario as a Cloud Service de Guías de](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-apr-22/XML-Documentation-for-Adobe-Experience-Manager_CS_User-Guide_EN.pdf).

Para obtener más información sobre la generación de un PDF mediante el método DITA-OT, consulte [Generación de PDF mediante DITA-OT](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-pdf.html).

* **FrameMaker Publishing Server (FMPS)**

Utilice este método para generar una salida de PDF no sólo a partir del contenido DITA, sino también de los documentos de FrameMaker AEM (.book y .fm) disponibles en el repositorio de la. El PDF se puede crear configurando un ajuste preestablecido de salida y publicarlo mediante FrameMaker Publishing Server (FMPS). Puede diseñar y configurar el aspecto de la salida para PDF y otros formatos, y almacenarla en un archivo de configuración (.sts). Este fichero de configuración lo utiliza FMPS para generar la salida de un fichero .book o de mapa DITA. Para crear o editar un ajuste preestablecido de salida, consulte la  *Explicación de los ajustes preestablecidos de salida* de la sección [AEM Guía del usuario as a Cloud Service de Guías de](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-apr-22/XML-Documentation-for-Adobe-Experience-Manager_CS_User-Guide_EN.pdf).

Para obtener más información sobre la configuración de FMPS, consulte [Generar resultados a partir de documentos de FrameMaker](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Ffm-output-generatation.html).

* **Publicación nativa de PDF**

Utilice este método para generar una salida de PDF con numerosas funciones basada en los estándares de medios paginados CSS3 y CSS del W3C. Con la publicación de PDF nativos, puede utilizar plantillas para establecer el diseño y el estilo del contenido y aplicar varias configuraciones para ajustar el PDF. Además, puede modificar y crear sus propias plantillas con el editor de plantillas.

Para obtener más información sobre la publicación de PDF nativos, consulte [Uso de la publicación nativa en PDF](#native-pdf-publishing).


## Uso de la publicación de PDF nativa {#native-pdf-publishing}

Al crear contenido, es esencial asegurarse de que el contenido esté optimizado para su visualización, edición e impresión. Mediante estándares como W3C CSS3 para el estilo de contenido y los estándares de medios paginados CSS para las propiedades de definición de página como tamaño, márgenes, orientación, saltos de página, encabezados, pies de página y numeración de páginas, puede establecer la vista y el diseño del documento de PDF, lo que garantiza la coherencia y la facilidad de uso. La función de publicación PDF nativo utiliza estos estándares para generar un PDF.

Con la publicación nativa de PDF, puede utilizar plantillas predefinidas para garantizar la coherencia en el diseño y la estructura del contenido, aplicar hojas de estilo para modificar el aspecto de la salida, optimizar el PDF, establecer marcas de impresora, permitir la compatibilidad con lectores de pantalla, establecer la conformidad del PDF, incrustar fuentes y mucho más.

La generación de un PDF mediante la publicación de un PDF nativo tiene dos aspectos:

* Uso de plantillas para aplicar estilo al contenido, establecer diseños de página y varias configuraciones para ajustar el PDF. Los autores pueden elegir utilizar o modificar las plantillas de ejemplo proporcionadas o crear plantillas personalizadas y establecer las opciones de configuración avanzadas que utilizan los editores y desarrolladores.

* Cree o configure un ajuste preestablecido de salida de PDF para controlar la configuración del PDF. Una vez creado un ajuste preestablecido de salida de PDF, puede generar el PDF.

Para obtener más información, consulte [Generar una salida de PDF](#generate-pdf-output).

## Crear un ajuste preestablecido de salida de PDF {#create-output-preset}

El primer paso para generar una salida de PDF es crear un ajuste preestablecido de salida de PDF, que es una colección de propiedades de publicación asignadas a un mapa. Puede crear un ajuste preestablecido de salida para cualquier mapa que esté abierto en el panel Vista de mapa o configurar un ajuste preestablecido existente para generar rápidamente un PDF para el mismo mapa.

En el ajuste preestablecido de salida del PDF puede seleccionar una plantilla, aplicar condiciones, establecer restricciones para controlar cómo interactúa un usuario con el PDF, configurar ajustes avanzados como compresión, conformidad y mucho más.

Para crear o configurar un ajuste preestablecido de salida de PDF:

1. En la pestaña Output, haga clic en **Ajustes preestablecidos** en la barra lateral izquierda.
Se abrirá el panel Ajuste preestablecido. <br>
<img src="assets/preset-panel.png" alt="panel preestablecido" width="600">

1. En la salida **Ajustes preestablecidos** , realice una de las siguientes acciones:
   * Haga doble clic en un ajuste preestablecido de salida de PDF predefinido para verlo.
   * Haga clic en el icono + de **Ajustes preestablecidos** para añadir un nuevo ajuste preestablecido de salida de **Tipo: PDF**

1. Para configurar los ajustes de un ajuste preestablecido de PDF existente:
   * Haga clic en  **Opciones** ![opciones](assets/options.svg) junto al ajuste preestablecido de salida deseado y seleccione **Editar**.
Puede utilizar la siguiente configuración en la **General**, **Metadatos**, **Diseño**, **Seguridad**, y **Avanzadas** pestañas para configurar un ajuste preestablecido de salida de PDF:

**General**

Utilice para especificar la configuración básica de salida, como la ruta de acceso de salida, el nombre del archivo del PDF, etc.

| Configuración | Descripción |
| --- | --- |
| **Ruta de salida** | AEM Ruta de acceso del repositorio de en la que se almacena la salida del PDF. Asegúrese de que la ruta de acceso de salida no esté ubicada dentro de la carpeta del proyecto. Si se deja en blanco, la salida se generará en la ubicación de salida del mapa DITA por defecto.<br>También puede utilizar las siguientes variables listas para usarse para definir la Ruta de salida. Puede utilizar una sola variable o una combinación de ellas para definir esta opción. <br> `${map_filename}`: utiliza el nombre de ficheros de mapa DITA para crear la ruta de destino. <br> `${map_title}`: utiliza el título del mapa DITA para crear la ruta de destino. <br>`${preset_name}`: utiliza el nombre del ajuste preestablecido de salida para crear la ruta de destino. <br> `${language_code}`: utiliza el código de idioma en el que se encuentra el archivo de asignación para crear la ruta de destino. <br> `${map_parentpath}`: Utiliza la ruta completa del archivo de asignación para crear la ruta de destino.  <br>`${path_after_langfolder}`: Utiliza la ruta del archivo de mapa después de la carpeta de idioma para crear la ruta de destino. |
| **Archivo de PDF** | Especifique un nombre de archivo para guardar el PDF. De forma predeterminada, el nombre del fichero de PDF añade el nombre del mapa DITA junto con el nombre del ajuste preestablecido. Por ejemplo, ditamap es &quot;TestMap&quot; y el nombre del ajuste preestablecido es &quot;preset1&quot;, el nombre predeterminado del pdf será &quot;TestMap_preet1.pdf&quot;. <br>También puede utilizar las siguientes variables listas para usarse para definir el archivo PDF. Puede utilizar una sola variable o una combinación de ellas para definir esta opción. <br>`${map_filename}`<br>`${map_title}`<br>`${preset_name}` <br> `${language_code}`. |
| **Aplicar condiciones usando** | Para el contenido condicionado, elija entre las siguientes opciones para generar una salida de PDF basada en esas condiciones: <br><ul> <li> **Ninguno aplicado** Seleccione esta opción si no desea aplicar ninguna condición al mapa y al contenido de origen. <br><li> **Archivo Ditaval** Seleccione un archivo DITAVAL para generar contenido condicionado. Para seleccionar, haga clic en Ajuste preestablecido de condición y busque el archivo. <br> <li> **Ajuste preestablecido de condición** Seleccione un ajuste preestablecido de condición en la lista desplegable para aplicar una condición al publicar la salida. Esta opción está visible si se ha añadido una condición para el fichero de mapa DITA. La configuración condicional está disponible en la ficha Ajustes preestablecidos de condición de la consola de mapas DITA. Para obtener más información sobre los ajustes preestablecidos de condición, consulte [Usar ajustes preestablecidos de condición](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-condition-presets.html). <br> </ul> |
| **Usar línea base** | Si ha creado una Línea base para el mapa DITA seleccionado, seleccione esta opción para especificar la versión que desea publicar. Consulte [Trabajar con línea base](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-baseline-for-publishing.html) para obtener más información. |
| **Crear PDF con barra de cambios entre versiones publicadas** | Utilice las siguientes opciones para crear un PDF que muestre las diferencias de contenido entre dos versiones con barras de cambios:   <br><ul><li> **Línea base de la versión anterior** Seleccione la versión de instantánea que desea comparar con la versión actual u otra instantánea. Aparecerá una barra de cambios en el PDF para indicar el contenido modificado. Una barra de cambios es una línea vertical que identifica visualmente el contenido nuevo o revisado. La barra de cambios aparece a la izquierda del contenido que se ha insertado, modificado o eliminado. <br> **Nota**: Si selecciona **Usar línea base** y elija una línea base para publicar, la comparación se realizará entre las dos versiones de línea base seleccionadas. Por ejemplo, si elige la línea base Versión 1.3 en **Usar línea base** y Versión 1.1 en **Línea base de la versión anterior**, la comparación se realizará entre la versión de línea base 1.1 y la versión de línea base 1.3. <br><li> **Mostrar texto añadido** Seleccione esta opción para mostrar el texto insertado en color verde y subrayado. Esta opción está seleccionada de forma predeterminada. <br> <li> **Mostrar texto eliminado** Seleccione para mostrar el texto eliminado en color rojo y marcado con un tachado. Esta opción está seleccionada de forma predeterminada. <br>**Nota** También puede personalizar el estilo de la barra de cambios, el contenido insertado o el contenido eliminado mediante la hoja de estilo.<br></ul> |
| **Flujo de trabajo de generación posterior** | AEM Seleccione esta opción para mostrar una lista desplegable que contenga todos los flujos de trabajo configurados en la aplicación de flujo de trabajo de la. Puede seleccionar el flujo de trabajo que desea ejecutar después de la finalización del flujo de trabajo de generación de PDF. |

**Metadatos**

Los metadatos son la descripción o definición del contenido. Los metadatos ayudan en la administración de contenido y en la búsqueda de archivos en Internet.

Utilice la pestaña Metadatos para establecer los campos de metadatos como el nombre del autor, el título del documento, las palabras clave, la información de copyright y otros campos de datos para la salida del PDF. También puede agregar metadatos personalizados para la salida del PDF.

Estos metadatos se asignan a los metadatos de la pestaña Descripción en las propiedades del documento del PDF de salida.

**Nota**: estos metadatos anulan los metadatos definidos en el nivel de libro.

<img src="assets/pdf-metadata.png" alt="ficha de metadatos" width="600">

Desde Ajustes preestablecidos de salida, **seleccionar PDF** > **Metadatos** para agregar y personalizar opciones de metadatos.
* **XMP Proporcionar archivo**

  Los campos de metadatos se pueden rellenar directamente importando [XMP](https://www.adobe.com/products/xmp.html) (Extensible Metadata Platform). XMP Puede descargar un archivo de muestra de la aplicación desde aquí.

[Descargar](assets/SampleXMP.xmp)

  XMP Como alternativa, puede generar un archivo de mediante Adobe Acrobat.
   1. Clic **Archivo** > **Propiedades** en Acrobat.
   1. En **Descripción**, haga clic en **Metadatos adicionales**.
   1. En el panel izquierdo, seleccione **Avanzadas**.
   1. Haga clic en **Guardar**.

  XMP Se ha guardado el archivo de en el dispositivo.

* **Proporcionar nombres y valores de metadatos**

   1. Añada un nombre seleccionándolo en la lista desplegable o agregue metadatos personalizados escribiendo directamente en el campo de nombre.
   1. Introduzca el valor de los metadatos y haga clic en el icono &quot;+&quot;.
Los metadatos se añaden a la lista de metadatos del PDF.

También puede utilizar variables para definir los valores de los metadatos.  Se pueden utilizar los metadatos definidos para el mapa DITA o el fichero bookmap como variables. Los metadatos se encuentran en `/jcr:content/metadata` nodo del mapa DITA o archivo bookmap.
Cuando se utiliza una variable, su valor se selecciona de las propiedades de metadatos.

Para utilizar una variable, debe definirla en la variable `${<variable>}` formato.

Por ejemplo, una de las propiedades de metadatos definidas en la variable /`jcr:content/metadata` el nodo es
`dc:title`. Puede especificar `${dc:title}`y el valor del título se utiliza en la salida final.

Puede utilizar una sola variable o una combinación de ellas para definir los metadatos. Por ejemplo, `${dc:title} ${dc:docstate}`. También puede utilizar la combinación de una variable y una cadena.  Por ejemplo, `View ${dc:title} in ${dc:language}`.

Utilice variables de idioma para definir el valor localizado de las propiedades de los metadatos. Según el idioma elegido, el valor localizado se selecciona automáticamente en la salida del PDF. Por ejemplo, puede imprimir &quot;Autor&quot; como el valor de los metadatos en inglés y &quot;Autor&quot; en alemán.

Formato: `${lng:<variable name>}`. Por ejemplo, `${lng:author-label}` donde `author-label` es una variable de idioma.

Pase el ratón sobre <img src="./assets/info-details.svg" alt= "icono de información" width="25"> cerca de la opción para ver más detalles al respecto.


**Diseño**

Utilice para definir los diseños de página y especificar las opciones de vista de página para la salida del PDF, como Visualización de página (Page Display) y definir los niveles de zoom.

| Configuración | Descripción |
| --- | --- |
| **Plantilla de PDF** | Las plantillas de PDF proporcionan una estructura clara para definir diseños de página, estilos de contenido y aplicar varios ajustes a la salida del PDF. Seleccione en las opciones desplegables de plantilla de PDF para elegir la plantilla que prefiera. <br> También puede seleccionar **Examinar plantilla** <img src="./assets/browse-templates-icon.svg"  alt= "icono examinar plantillas" width="25">  para elegir una plantilla. En el **Seleccionar plantilla de PDF** diálogo también puede previsualizar la miniatura y ver el título y la descripción de la plantilla seleccionada. |
| **Visualización de página** | Utilice la Visualización de página para la vista de página que muestra cómo se muestra el PDF cuando se abre. Seleccione en las opciones desplegables de Visualización de página para elegir una vista preferida. <br><ul><li> **Predeterminado**  Se muestra según la configuración predeterminada del visor de PDF en el equipo de un usuario.  <br> <li> **Vista de página única** Muestra las páginas de una en una.   <br> <li> **Desplazamiento de página única** Muestra una sola página en una columna vertical continua.  <br> <li> **Vista de dos páginas** Muestra dos pliegos de páginas uno al lado del otro. .<br> <li> **Desplazamiento de dos páginas** Muestra un pliego de dos páginas en paralelo con desplazamiento continuo. </ul> |
| **Zoom** | Seleccione para cambiar el tamaño de la vista de página que muestra cómo se muestra el PDF cuando se abre.  <br><ul><li> **Predeterminado** Se muestra según la configuración predeterminada del visor de PDF en el equipo de un usuario    <br> <li> **100 %** Hace que la página aparezca en su tamaño real.     <br> <li> **Ajustar página** Hace que el ancho y el alto de la página se ajusten al panel del documento. .<br> <li> **Ajustar ancho de página** Hace que el ancho de la página se rellene con el ancho del panel del documento.  <br> <li> **Ajustar altura de página** Hace que el alto de la página ocupe el alto del panel del documento. </ul> |

**Seguridad**

Protect el PDF agregando restricciones para abrir y leer el archivo. Utilice las siguientes opciones para evitar el acceso no autorizado.

| Configuración | Descripción |
| --- | --- |
| **Establecer contraseña para abrir el documento** | Seleccione para añadir una contraseña segura para ver el archivo de PDF. Especifique una contraseña en la **Contraseña de usuario** field. Los usuarios solo pueden abrir el PDF introduciendo la contraseña proporcionada en este campo. |
| **Establecer las restricciones del documento** | Seleccione esta opción para restringir la forma en que los usuarios pueden interactuar con el PDF. Especifique una contraseña en la **Contraseña de propietario** para que funcione la siguiente configuración de restricción.  <br><ul><li> **Impresión** Seleccione esta opción para permitir que un usuario imprima el PDF. <br> <li> **Impresión de calidad de borrador** Seleccione esta opción para permitir que un usuario imprima el PDF en una resolución inferior.  <br> <li> **Copia de contenido** Seleccione esta opción para permitir que un usuario copie contenido del PDF.   <br> <li> **Anotaciones** Seleccione esta opción para permitir que un usuario añada una nota o un comentario en el PDF.  <br> <li> **Modificaciones de contenido** Seleccione esta opción para permitir que un usuario modifique el contenido en el PDF.  <br> <li> **Copia de contenido para accesibilidad** Seleccione esta opción para permitir que los lectores de pantalla lean y naveguen por el contenido en PDF.  <br>  **Ensamblado de documento** Seleccione esta opción para permitir que los usuarios inserten páginas en el PDF.  <br> **Nota**: los usuarios deben introducir la contraseña de propietario para cambiar cualquier restricción de Archivo > Propiedades en Adobe Acrobat. |

**Avanzado**

Utilice las siguientes opciones para especificar la configuración avanzada para combinar PDF, utilizar compresión, seleccionar el estándar de conformidad y mucho más.

| Configuración | Descripción |
| --- | --- |
| **Crear PDF accesible (etiquetado)** | Seleccione esta opción para generar un PDF con etiquetas. Un PDF etiquetado facilita a los lectores de pantalla la lectura y la navegación por el contenido, los hipervínculos, los marcadores, etc. Por ejemplo, si se etiqueta una tabla, el lector de pantalla sabrá que está leyendo la tabla y no solo líneas y texto. |
| **Combinar PDF incluidos en el índice** | Seleccione esta opción para fusionar PDF existentes en la salida agregándolos al mapa DITA como un fichero de recursos. Los PDF se insertan en la ubicación representada en el mapa y las páginas se incrementan en consecuencia. |
| **Incrustar fuentes utilizadas** | Seleccione esta opción cuando utilice fuentes que no estén instaladas en el equipo del usuario final. Con esta opción seleccionada, las fuentes utilizadas se incrustan en el PDF, lo que garantiza que el usuario pueda ver el PDF como estaba previsto aunque las fuentes no estén instaladas en el equipo. <br> **Nota**: una fuente se puede incrustar solo si contiene una configuración del proveedor de fuentes que permita que se incruste. Asegúrese de tener la configuración o licencia necesarias antes de incrustar una fuente. |
| **Usar división automática de palabras** | Con la división automática de palabras habilitada, las palabras al final de las líneas se dividen en lugares gramaticalmente correctos con un guión. |
| **Habilitar JavaScript** | Active esta opción si tiene un código JavaScript que desee utilizar para transformar el contenido dinámicamente antes de generar un PDF. |
| **Incrustar archivos multimedia** | Seleccione esta opción para incluir audio, vídeo y contenido interactivo en el PDF. |
| **Utilice la compresión completa para optimizar el tamaño del PDF** | Seleccione esta opción si desea comprimir o reducir el tamaño de un PDF grande. Recuerde que la compresión del PDF puede reducir la calidad del archivo. |
| **Utilice la compresión de imágenes para optimizar el tamaño del PDF** | Seleccione esta opción si desea comprimir o reducir el tamaño de las imágenes utilizadas en el PDF. Recuerde que la compresión de una imagen puede reducir la calidad de la imagen. |
| **Utilizar resolución personalizada (píxeles por pulgada)** | Es la resolución de visualización de la página en píxeles por pulgada. Introduzca un valor preferido en el campo que aparece cuando se selecciona esta opción. El valor predeterminado es 96 píxeles por pulgada. Configure un valor más alto para que quepa más contenido en una pulgada y viceversa, si establece un valor más bajo. |
| **Mostrar filigrana** | Seleccione esta opción para superponer una marca de agua en la salida. Puede escribir una nueva cadena de texto en el cuadro de texto con la letra mayúscula tal y como desee. <br><br>Utilice texto estático o variables de idioma para publicar la versión localizada de la marca de agua.  Según el idioma elegido, el valor localizado se selecciona automáticamente en la salida del PDF. Por ejemplo, puede imprimir &quot;Publicador&quot; como marca de agua en inglés y &quot;Auteure&quot; en francés.  <br> Formato: `${lng:<variable name>}`. Por ejemplo, `$ {lng:publisher-label}` donde `publisher-label` es una variable de idioma. <br> Pase el ratón sobre <img src="./assets/info-details.svg" alt= "icono de información" width="25"> cerca de la opción para ver más detalles al respecto. |
| **Habilitar ecuaciones de MathML** | Seleccione esta opción para procesar las ecuaciones de MathML presentes en el contenido. Las ecuaciones se ignorarán de forma predeterminada. |
| **Descargar archivos temporales** | Seleccione esta opción si desea descargar los archivos de HTML provisionales creados al generar la salida del PDF nativo. Posteriormente, puede descargar los archivos temporales después de generar la salida. |
| **conformidad del PDF** | Es el estándar en el que desea guardar el PDF para asegurarse de que es compatible. Seleccione en el menú desplegable para elegir entre la lista de estándares de PDF disponibles. Para obtener más información sobre los estándares admitidos, consulte [Acerca de los estándares PDF](https://helpx.adobe.com/acrobat/using/pdf-conversion-settings.html#about_pdf_x_pdf_e_and_pdf_a_standards). |


## Generar una salida de PDF {#generate-pdf-output}

Una vez configurado el ajuste preestablecido de salida, puede generar resultados desde el panel Ajustes preestablecidos mediante el **Generar ajuste preestablecido** función.

1. En el **Autor** , seleccione la pestaña **Repositorio** Ver.\
   Se abrirá el panel Repositorio.

1. En el panel Repositorio, abra el fichero de mapa DITA en **Vista de mapa**.

1. En el **Output** pestaña, haga clic en **Ajustes preestablecidos** para ver el panel Ajuste preestablecido.
Para crear o configurar un ajuste preestablecido de salida, consulte [Crear un ajuste preestablecido de salida de PDF](#create-output-preset).
1. Para guardar la configuración, haga clic en **Guardar todo** ![guardar todo](assets/SaveFloppy_icon.svg) en la esquina superior izquierda de la barra de herramientas estándar en la vista Salida.
1. Haga clic en **Generar ajuste preestablecido** ![generar ajuste preestablecido](assets/generate-output.svg) en la barra superior.
Puede ver una barra de progreso junto al ajuste preestablecido de salida seleccionado en el panel Valores de salida.
1. Una vez finalizada la generación de resultados, haga clic en  **Ver salida** ![ver salida](assets/view-output.svg) en la barra superior para ver el resultado.\
   A **Correcto** El cuadro de diálogo se puede ver en la esquina inferior derecha de la pantalla.
Si una salida no se realiza correctamente, se muestra el siguiente mensaje de error.
<img src="assets/error-log.png" alt="registro de errores" width="250">

Para ver el registro de errores, haga clic en **Descartar**, pase el ratón sobre la pestaña de ajustes preestablecidos seleccionada y haga clic en ![opciones](assets/options.svg) **Opciones** > **Ver registro**.

### Descargar archivos temporales después de generar la salida del PDF nativo

Si selecciona la opción **Descargar archivos temporales** en la opción Advanced settings, también puede descargar los archivos de HTML provisionales creados al generar la salida del PDF nativo. Una vez que haya generado la salida, puede descargar los archivos temporales mediante el **Descargar archivos temporales** ![descargar archivos temporales](assets/native-pdf-download-temporary-files-icon.svg)en la barra superior. Esta función le ayuda a ver los estilos y diseños provisionales del HTML, y a corregir o cambiar los estilos CSS según sus necesidades.


>[!NOTE]
>
> El **Descargar archivos temporales**  ![descargar archivos temporales](assets/native-pdf-download-temporary-files-icon.svg) solo aparece si ha generado la última salida del PDF utilizando el ajuste preestablecido en el que ha seleccionado la opción en la **Avanzadas** pestaña.



### Usar variables de idioma

AEM Las guías de idioma también proporcionan compatibilidad con variables de idioma. Seleccionar **Variables de idioma** <img src="./assets/language-variables.svg" width="25">  en el panel izquierdo para definir una versión localizada de las etiquetas integradas, como Nota, Precaución y Advertencia o texto estático en la salida del PDF. Para obtener más información, consulte [Compatibilidad con variables de idioma](../native-pdf/native-pdf-language-variables.md).

