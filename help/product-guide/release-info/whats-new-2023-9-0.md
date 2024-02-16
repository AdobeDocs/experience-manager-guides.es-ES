---
title: Notas de versión | Novedades de las guías de Adobe Experience Manager, versión de septiembre de 2023
description: Conozca las funciones nuevas y mejoradas de la versión de septiembre de 2023 de las guías de Adobe Experience Manager as a Cloud Service
exl-id: d185d27f-0cbb-4ec6-ac65-cb69f7572c3f
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 0%

---

# Novedades de la versión de septiembre de 2023 de Adobe Experience Manager Guides as a Cloud Service

Este artículo cubre las funciones nuevas y mejoradas de la versión de septiembre de 2023 de las guías de Adobe Experience Manager (más adelante denominadas *AEM Guías de as a Cloud Service*).

Para obtener más información sobre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en esta versión, consulte [Notas de versión](release-notes-2023-9-0.md).

## Conectarse a un origen de datos e insertar los temas

AEM AEM Guías de proporciona conectores listos para usar que le ayudan a conectarse con sus fuentes de datos, lo que convierte a las guías en un auténtico centro de contenido. Esto le proporciona la ventaja de ahorrarle tiempo y esfuerzo que, de lo contrario, se invertirían en la adición o replicación manual de datos.

Junto con los conectores predeterminados existentes, como JIRA y SQL (MySQL, PostgreSQL, SQL Server, SQLite), el administrador también puede configurar conectores para bases de datos MariaDB, H2DB, AdobeCommerce y Elasticsearch. También pueden agregar otros conectores ampliando las interfaces predeterminadas.

Puede ver los conectores configurados en la **Fuentes de datos** Panel en el editor web.

<img src="assets/data-sources.png" alt="Lista de fuentes de datos en el panel" width="300">

*Vea las fuentes de datos conectadas.*

Ahora también puede crear un tema a partir de una fuente de datos conectada. Un tema puede contener datos en varios formatos, como tablas, listas y párrafos. También permite crear un mapa DITA para todos los temas. Puede asociar metadatos al tema al extraer de una fuente de datos.

Para obtener más información, consulte [Uso de datos de la fuente de datos](../user-guide/web-editor-content-snippet.md).

## Añadir citas al contenido

Las citas son referencias a la fuente de información agregada al contenido. Las citas le ayudan a establecer credibilidad y prevenir el plagio. Las citas ayudan a los lectores a localizar la fuente y verificar la información presentada en el texto.

AEM En las Guías de la, puede agregar citas o importarlas y aplicarlas al contenido. Puede añadir estas citas desde cualquier fuente de libros, sitios web y diarios.

Después de insertar las citas en los temas, puede obtener una vista previa de las mismas en el Editor Web. También puede publicar contenido con citas utilizando el PDF nativo.

![Citas enumeradas en un panel](assets/citation-panel.png){width="300" align="left"}

*Vea la lista de citas en el panel Citas.*

Para obtener más información, consulte [Añadir y administrar citas en el contenido](../user-guide/web-editor-apply-citations.md).


## Publicación en un fragmento de contenido

AEM Los fragmentos de contenido son fragmentos de contenido discretos en el espacio de trabajo de la. Son contenidos estructurados basados en un modelo de contenido. Los fragmentos de contenido son contenido puro sin información de diseño. AEM Se pueden crear y administrar de forma independiente de los canales que admite el usuario en la aplicación de la. La modularidad y reutilización de los fragmentos de contenido aumenta la flexibilidad, coherencia, eficacia y simplifica la administración.

AEM Ahora, las guías de la ofrecen una forma de publicar un tema o los elementos dentro de un tema en un fragmento de contenido. Puede crear una asignación basada en JSON entre un tema y un modelo de fragmento de contenido. Utilice esta asignación para publicar contenido presente en algunos o todos los elementos de un tema en un fragmento de contenido.

AEM AEM Ponga en mayúsculas el poder de las Guías de y los fragmentos de contenido, y utilice fragmentos de contenido en cualquier sitio de. También puede extraer los detalles a través de las API admitidas por los fragmentos de contenido.

![opción para publicar el fragmento de contenido](assets/content-fragment-publish.png){width="550" align="left"}

*Publicar un tema en un fragmento de contenido.*

Para obtener más información, consulte [Publicación en un fragmento de contenido](../user-guide//publish-content-fragment.md).

## Revisar mejoras

AEM Las guías de la aplicación ahora proporcionan una capacidad de revisión mejorada con las siguientes funcionalidades:

### Buscar temas de revisión

AEM La realización de exámenes es una característica fundamental de las Guías de la. Ayuda a los revisores a revisar los documentos asignados a ellos
Ahora puede buscar un tema escribiendo parte del texto del título o ruta de archivo en la barra de búsqueda de la vista Temas del panel de revisión. También puede elegir ver todos los temas o ver los temas con comentarios. De forma predeterminada, puede ver todos los temas presentes en la tarea de revisión. Para obtener más información, consulte [Revisar temas](../user-guide/review-topics.md).

![Buscar en un panel de temas de revisión](assets/review-search-topic.png){width="800" align="left"}

*Busque un tema de revisión en el panel de revisión.*



## Marco de extensión de Guides

AEM AEM Cree paquetes personalizados sobre las Guías de para proporcionar extensibilidad mediante el marco de trabajo de extensión de las Guías de. Estos paquetes son útiles para desarrolladores y consultores y les proporcionan extensibilidad a los componentes del Editor. AEM Pueden segmentar botones, cuadros de diálogo y listas desplegables, y agregar JavaScript personalizado que pueda interoperar fácilmente con la interfaz de usuario de las guías de la interfaz de usuario de las guías de la aplicación.



## Mejoras del PDF nativo

En la versión de septiembre de 2023 de se realizaron las siguientes mejoras en el PDF AEM nativo para hacer que las guías de recursos sean un producto más robusto:



### Ordenar páginas en la salida del PDF

Puede mostrar u ocultar las siguientes secciones en el PDF y también organizar el orden en que deben aparecer en la salida final del PDF:

* TDC
* Capítulos y temas
* Lista de figuras
* Lista de tablas
* Índice
* Glosario
* Cita
* Diseños de página

Si no desea mostrar una sección en particular en la salida del PDF, puede ocultarla desactivando el conmutador.

Para obtener más información, consulte [Orden de páginas](../native-pdf/components-pdf-template.md#page-order).

### Combinar páginas

De forma predeterminada, en una salida de PDF nativo, todas las secciones comienzan en una nueva página. Ahora puede combinar una sección con su página anterior o con la página siguiente. Esto publica la sección como continuación con la página seleccionada en la salida del PDF y no hay ningún salto de página entre medias.

Para obtener más información, consulte **Combinar páginas** descripción de funciones en [Orden de páginas](../native-pdf/components-pdf-template.md#page-order) sección.

### Iniciar cualquier capítulo desde la página actual

Se pueden definir los valores de configuración básicos para iniciar un capítulo desde una página impar o par, la estructura del índice y definir el formato de línea directriz para las entradas del índice.

Ahora también puede iniciar un capítulo desde la página actual. Si decide hacerlo, todos los capítulos se publican a continuación sin saltos de página. Por ejemplo, si un capítulo termina en mitad de la página 15, el capítulo siguiente también comienza desde la propia página 15.

Para obtener más información, consulte **General** descripción de pestaña en  [Configuración avanzada del PDF](../native-pdf/components-pdf-template.md#advanced-pdf-settings-advanced-pdf-settings).

### Páginas estáticas

También puede crear diseños de página personalizados y publicarlos como páginas estáticas en la salida del PDF. Esto le ayuda a añadir contenido estático como notas o páginas en blanco.

Para obtener más información, consulte **Páginas estáticas** descripción de funciones en [Orden de páginas](../native-pdf/components-pdf-template.md#page-order) sección.


### Variables en referencias cruzadas

Puede utilizar variables para definir una referencia cruzada. Cuando se utiliza una variable, su valor se selecciona de las propiedades.

Ahora también puede utilizar {figure} y {table}.
Uso {figure}para añadir una referencia cruzada al número de la figura. Selecciona el número de figura de los estilos de numeración automática que ha definido para figcaption.

Uso {table} para añadir una referencia cruzada al número de tabla. Selecciona el número de tabla de los estilos de numeración automática que ha definido para el pie de ilustración.

Para obtener más información, consulte [Referencias cruzadas](../native-pdf/components-pdf-template.md##cross-references).



### Rediseño del editor CSS

Ahora el editor CSS se ha rediseñado para mejorar la experiencia del usuario con selectores y propiedades de estilo.

#### Mejora del cuadro de diálogo Agregar estilo

Ahora puede utilizar selectores personalizados para añadir estilos complejos. El nuevo campo Selector le ayuda a añadir selectores personalizados además de la combinación de Clase, Etiqueta y Pseudoclase. Por ejemplo, puede crear `table a.link` para todos los hipervínculos de una tabla.

![agregar estilos en las plantillas pdf nativas](assets/add-styles-native-pdf.png){width="300" align="left"}

*Agregue los detalles del nuevo estilo.*

#### Personalizar propiedades de estilo

AEM Ahora, Guías de le presenta un nuevo panel de propiedades en la sección de vista previa de los estilos. Puede editar las propiedades de los estilos de forma más eficaz y rápida desde el panel Propiedades.


## Compatibilidad con varias definiciones de asunto en una sola definición de enumeración

Ahora puede definir una o más definiciones de asunto en un mapa y las definiciones de enumeración en otro mapa y, a continuación, añadir la referencia de mapa. Las referencias de asunto y enumeración se resuelven en el mismo mapa o en el mapa al que se hace referencia.

Ahora también puede definir condiciones y aplicarlas a algunos elementos específicos de un tema.  Las condiciones solo son visibles para esos elementos específicos y no para todos los demás elementos.

Para obtener más información sobre la gestión de definiciones jerárquicas de definiciones de temas y enumeraciones, consulte la descripción de la función de esquema de temas en la [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS) sección.





## Seleccionar todos los ajustes preestablecidos de una colección de mapas

No solo puede activar un ajuste preestablecido individual y todos los ajustes preestablecidos de perfil de carpeta, sino también activar todos los ajustes preestablecidos para un mapa DITA de una sola vez.
![edición de una colección de mapas](assets/edit-map-collection-cs.png){width="800" align="left"}\
*Seleccione todos los ajustes preestablecidos de una colección de mapas.*

Para obtener más información, consulte [Usar la colección de mapas para generar resultados](../user-guide/generate-output-use-map-collection-output-generation.md).


## Compatibilidad con PDF nativos en el tablero de publicación masiva


AEM Con la función Activación masiva de guías de trabajo, puede activar de forma rápida y sencilla el contenido desde la creación a la publicación. En el mapa de activación masiva, puede incluir el ajuste preestablecido de salida del PDF AEM nativo, el sitio de la, el PDF, el HTML 5, el personalizado y la salida JSON.
Para obtener más información, consulte [Activación masiva de contenido publicado](../user-guide/conf-bulk-activation.md).

## Herramienta de movimiento masivo mejorada

Ahora, como administrador, puede utilizar la herramienta de movimiento masivo mejorada para mover carpetas con muchos archivos de una ubicación a otra.
Puede utilizar el cuadro de diálogo Examinar archivo para seleccionar las carpetas de origen que desea mover. También puede examinar y seleccionar la ubicación de destino para mover las carpetas de origen. Seleccionar ![icono de información](assets/info-icon.svg) {width="25" align="left"} cerca de un campo para ver más información al respecto.

Para obtener más información, consulte [Mover archivos por lotes](../user-guide/authoring-file-management.md#move-files-bulk).


## Experiencia de previsualización mejorada desde el menú contextual

Utilice el menú contextual para previsualizar rápidamente el archivo (.dita, .xml, audio, vídeo o imagen) sin abrirlo. Ahora puede cambiar el tamaño del panel de vista previa y, si el contenido contiene algún vínculo de referencia, puede seleccionarlo para abrirlo en una nueva pestaña.

![Panel Vista previa ](assets/quick-preview_cs.png){width="800" align="left"}

*Obtenga una vista previa del archivo en el panel.*

Para obtener más información sobre el menú contextual, consulte la **Opciones de un archivo** descripción de la función en [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS) sección.


## Utilice variables para la fecha y la hora actuales en las opciones Ruta de destino, Nombre del sitio o Nombre de archivo

AEM Al generar resultados en el sitio o en los PDF de, puede utilizar variables para configurar el **Ruta de destino**, **Nombre del sitio**, o **Nombre de archivo** opciones. Ahora también puede utilizar la variable `${system_date}`y `${system_time}` variables. Estas variables le ayudan a anexar la fecha y la hora actuales a estas opciones.

Obtenga información sobre cómo [usar variables para establecer las opciones Ruta de destino, Nombre del sitio o Nombre de archivo](../user-guide/generate-output-use-variables.md).
