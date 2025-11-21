---
title: Notas de versión | Versión de Adobe Experience Manager Guides 4.1
description: Última versión de Adobe Experience Manager Guides
exl-id: c70b3bbc-3332-4626-bc30-641034f8fd06
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '3644'
ht-degree: 1%

---

# Versión 4.1.x de Adobe Experience Manager Guides

En estas notas de la versión se explican las instrucciones de actualización, las nuevas funciones y las mejoras realizadas en la versión 4.1.x de Adobe Experience Manager Guides (más adelante denominada *AEM Guides*).

## Actualice a la última versión

Puede actualizar fácilmente su versión actual de AEM Guides a la versión 4.1.3. Antes de continuar actualizando a la versión 4.1.3 de AEM Guides, debe tener en cuenta los siguientes puntos:

* Si utiliza la versión 4.1 o 4.1.x, puede actualizar directamente a la versión 4.1.3.
* Si utiliza la versión 4.0.x, debe actualizar a la versión 4.1 o 4.1.x antes de actualizar a la 4.1.3.
* Si utiliza la versión 3.8.5, debe actualizar a la versión 4.0.x antes de actualizar a la 4.1.
* Si su versión es anterior a la 3.8.5, consulte la sección de actualización en la guía de instalación específica del producto.

Para obtener más información, consulte [Instrucciones de actualización](assets/Adobe-Experience-Manager-Guides-Upgrade-Instructions-EN.pdf).

## 4.1.3 | Notas de versión

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con la versión 4.1.3 de AEM Guides.

### ADOBE EXPERIENCE MANAGER

**No UUID**
Paquete de servicio 13, 12, 11 o 10 de la versión 6.5

**UUID**
Paquete de servicio 13, 12, 11 o 10 de la versión 6.5

Para obtener más información, consulte la sección Requisitos técnicos en la guía Instalar y configurar Adobe Experience Manager Guides.


### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión | FMPS 2020 | FMPS 2019 | Fm 2020 | Fm 2019 |
| --- | --- | --- | --- | --- |
| 4.1.3 (no UUID) | 2020.2 o superior* | 2019 | 2020.3 o superior | 2019.8 (última actualización) |
| 4.1.3 (UUID) | 2020.2 o superior* | No compatible | 2020.4 o superior | No compatible |
| | | | |  |

*Las condiciones y de línea de base creadas en AEM son compatibles con las versiones de FMPS a partir de 2020.2.

### Conector de oxígeno

| Versión | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.1.3 (no UUID) | 2.0 | 2.0 | 1,6 | 1,6 |
| 4.1.3 (UUID) | 2,7 | 2,7 | 2,3 | 2,3 |
|  |  |   |  |  |


## Problemas solucionados

El error corregido se enumera a continuación:

* El editor web carga la página en blanco de forma intermitente. (10678)


## 4.1.2 | Notas de versión

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con la versión 4.1.2 de AEM Guides.

### ADOBE EXPERIENCE MANAGER

**No UUID**
Paquete de servicio 13, 12, 11 o 10 de la versión 6.5

**UUID**
Paquete de servicio 13, 12, 11 o 10 de la versión 6.5

Para obtener más información, consulte la sección Requisitos técnicos en la guía Instalar y configurar Adobe Experience Manager Guides.


### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión | FMPS 2020 | FMPS 2019 | Fm 2020 | Fm 2019 |
| --- | --- | --- | --- | --- |
| 4.1.2 (no UUID) | 2020.2 o superior* | 2019 | 2020.3 o superior | 2019.8 (última actualización) |
| 4.1.2 (UUID) | 2020.2 o superior* | No compatible | 2020.4 o superior | No compatible |
| | | | |  |

*Las condiciones y de línea de base creadas en AEM son compatibles con las versiones de FMPS a partir de 2020.2.

### Conector de oxígeno

| Versión | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.1.2 (no UUID) | 2.0 | 2.0 | 1,6 | 1,6 |
| 4.1.2 (UUID) | 2,7 | 2,7 | 2,3 | 2,3 |
|  |  |   |  |  |


## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

* Al seleccionar todos los perfiles de carpeta, aparece un perfil de carpeta invisible (que es incorrecto). (10393)
* La creación de la línea de base no elige la última versión, cuando la zona horaria del usuario es diferente de la del servidor. (10336)
* El método abreviado Control+F no abre el modal de búsqueda del explorador en la consola de Assets después de la instalación de AEM Guides 4.1. (10339)
* El error de creación de línea base se produce en el tema que tiene la referencia a una carpeta. (10383)
* La pestaña Ajustes preestablecidos de salida muestra una pantalla en blanco de forma intermitente y, en algunos casos, se muestran ajustes preestablecidos no editables. (10390)
* La administración del espacio de claves produce excepciones y errores. (10449)

### Problemas conocidos con la solución

* La línea de base exportada durante la traducción no se carga en la pestaña de línea de base del editor.

  **Solución alternativa**: utilice la ficha Línea base del tablero de mapas DITA.

## 4,1 | Notas de versión

En estas notas de la versión se explican las instrucciones de actualización, las nuevas funciones y las mejoras realizadas en la versión 4.1.x de Adobe Experience Manager Guides (más adelante denominada *AEM Guides*).

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con la versión 4.1 de AEM Guides.

### ADOBE EXPERIENCE MANAGER

**No UUID**
Paquete de servicio 13, 12, 10 o 11 de la versión 6.5

**UUID**
Paquete de servicio 13, 12, 10 o 11 de la versión 6.5

Para obtener más información, consulte la sección Requisitos técnicos en la guía Instalar y configurar Adobe Experience Manager Guides.




### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión | FMPS 2020 | FMPS 2019 | Fm 2020 | Fm 2019 |
| --- | --- | --- | --- | --- |
| 4.1 (no UUID) | 2020.2 o superior* | 2019 | 2020.3 o superior | 2019.8 (última actualización) |
| 4.1 (UUID) | 2020.2 o superior* | No compatible | 2020.4 o superior | No compatible |
| | | | | |

*Las condiciones y de línea de base creadas en AEM son compatibles con las versiones de FMPS a partir de 2020.2.

### Conector de oxígeno

| Versión | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.1 (no UUID) | 2.0 | 2.0 | 1,6 | 1,6 |
| 4.1 (UUID) | 2,7 | 2,7 | 2,3 | 2,3 |
|  |  |  | | |


## Nuevas funciones y mejoras

AEM Guides proporciona muchas mejoras y nuevas funciones en la versión 4.1:

### Publicación nativa de PDF

También se ha añadido compatibilidad con la creación de un PDF nativo en la versión 4.1 de AEM Guides. Se ha introducido un nuevo motor de publicación con las siguientes funciones:

* Creación de una plantilla CSS
* Crear diferentes plantillas de página
* Diseñar plantillas de PDF que incluyan plantillas CSS y de página
* Publicación de contenido de temas y mapas en formato PDF

### Compatibilidad con la ruta del sitio de la base de conocimiento en la publicación basada en artículos

AEM Guides proporciona la función de publicación basada en artículos para generar de forma incremental un resultado de uno o más temas o publicar el contenido en una plataforma de base de conocimiento. Con la versión 4.1, tiene una opción adicional para elegir la ruta del sitio de la Base de conocimiento en el que se debe publicar el tema o el mapa. Una vez seleccionada la ruta, la salida se genera en la ruta especificada.

### Editor web mejorado

* **Resolución de clave mejorada**

Una referencia de clave de contenido DITA inserta una parte del contenido de un tema en otro. Utiliza una clave para localizar el contenido. Deben resolverse las referencias clave asociadas a un tema DITA. El mapa raíz seleccionado tiene la prioridad más alta para resolver las referencias clave.

![cuadro de diálogo de preferencias de usuario](assets/user-preferences.png)

Ahora, las referencias clave se resuelven en función del mapa raíz establecido en el siguiente orden de prioridad:

1. Preferencias de usuario
1. Panel Vista de mapa
1. Perfil de carpeta

Para obtener más información, consulte la sección *Resolver referencias clave* en la guía Usar Adobe Experience Manager Guides.

* **Agregar un panel personalizado en el panel izquierdo**

Ahora puede agregar un panel personalizado en el panel izquierdo del editor web. Puede utilizar un panel personalizado para varios fines, como proporcionar ayuda o realizar pruebas en un proyecto. Si se ha configurado un panel personalizado, también aparecerá en la lista de paneles dentro de **Configuración del editor**. Puede alternar el conmutador para mostrar u ocultar el panel personalizado.

* **Posibilidad de cambiar el estado del documento de temas en un mapa DITA**

Ahora puede cambiar fácilmente el estado del documento de los temas seleccionados dentro de un mapa DITA. También puede abrir y editar las propiedades de los temas seleccionados en un mapa DITA desde el menú **Más opciones** en la parte inferior del panel Vista de mapa.

![propiedades del tema seleccionado](assets/map-view-properties.png)

* **Información de versión mostrada en el modo de vista previa**

El editor web le ayuda a administrar sus versiones. Ahora también puede ver la versión del tema activo o el mapa DITA en la esquina superior derecha de la ficha de archivo del tema en el modo Vista previa de un tema.

![versión de vista previa](assets/preview-version.png)


* **Comportamiento mejorado de actualización del Editor web**

Las siguientes mejoras están ahora disponibles con la operación de actualización del explorador en el Editor web:

* Ahora dispone de la asistencia para actualizar el explorador mientras edita su
contenido en el editor web. Si pulsa el icono de actualización del explorador mientras usa uno o más archivos con
los cambios no guardados se abren para su edición y se le pide que guarde los archivos o cancele la acción de actualización.

* Incluso al actualizar el explorador, se conservan las vistas de los paneles izquierdo y derecho.

* El tema activo o el mapa DITA se vuelve a abrir en el área de edición de contenido.

* **Crear asignaciones basadas en plantillas personalizadas**

Ahora dispone de la potente función para crear plantillas de mapas personalizadas. Se pueden utilizar para crear mapas DITA junto con las plantillas de temas y las plantillas de mapas a las que se hace referencia en la plantilla de mapas.

![plantillas dita](assets/dita-templates.png)

También puede hacer referencia a otras plantillas de mapas y plantillas de temas desde la plantilla de mapas personalizada. Las plantillas de mapas a las que se hace referencia pueden hacer referencia a varias plantillas de mapas, plantillas de temas, temas, mapas, imágenes, vídeos y otros recursos.

![crear plantillas de dita](assets/create-dita-template.png)

La plantilla de mapa personalizada puede ayudarle a replicar muy fácilmente las plantillas de mapa y toda la estructura de carpetas de referencia. Estas plantillas personalizadas son especialmente útiles para crear y recrear varios mapas con estructuras y referencias recursivas.

* **Compatibilidad con Schematron**
&quot;Schematron&quot; hace referencia a un lenguaje de validación basado en reglas que se utiliza para definir pruebas para un archivo XML. Con un fichero de Schematron se pueden definir determinadas reglas y, a continuación, validarlas para un tema DITA o un mapa. El editor web admite archivos Schematron. Puede importar los archivos de Schematron y también editarlos en el Editor Web. La compatibilidad con Schematron en el Editor Web le ayuda a validar los archivos con un conjunto de reglas y a mantener la coherencia y corrección en todos los temas.

![validar schematron](assets/schematron-validate.png)

* **Se mejoró el diálogo al cerrar el archivo**

AEM Guides le pide que guarde los cambios y desbloquee los archivos bloqueados cuando intente cerrar un archivo abierto en el Editor Web. Las solicitudes se muestran según la configuración **Pedir protección al cerrar** y **Pedir nueva versión al cerrar** configurada por el administrador.

Según la configuración, tiene la opción de guardar los cambios y crear una nueva versión del documento. O bien, también puede proteger el archivo y guardar los cambios realizados en la versión actual.

![Cierre de archivo](assets/file-close-save-changes-unlock.png)

Para obtener más información, consulte la sección *Cerrar archivo y guardar escenarios* en la guía Usar Adobe Experience Manager Guides.* Se ha mejorado la característica **Insertar palabra clave**. Ahora puede encontrar más fácilmente una palabra clave para insertarla, ya que las palabras clave se enumeran en orden alfabético. También puede buscar palabras clave escribiendo una cadena de búsqueda en el cuadro Buscar.

![insertar palabra clave](assets/insert-keyword.png)

* **Compatibilidad con documentos de Markdown**
Markdown es un lenguaje de marcado ligero que puede ayudarle a agregar elementos de formato a documentos de texto sin formato. El editor web permite utilizar documentos Markdown (.md) junto con documentos DITA. Se puede crear y previsualizar fácilmente un documento Markdown en el Editor Web, así como añadirlo en el fichero de mapa a través del editor de mapas DITA.  Para obtener más información, consulte *Documentos de Markdown del autor desde el editor web* en la guía Uso de Adobe Experience Manager Guides.

![marcador de compatibilidad](assets/create-markdown-dita-topic.png)

* **Capacidad para configurar una vista de etiquetas predeterminada**
Si un usuario habilita la Vista de etiquetas desde el Editor web, permanecerá habilitada incluso en todas las sesiones.  Esto significa que no es necesario volver a habilitar la Vista de etiquetas para acceder a ella más adelante. El administrador puede configurar el estado predeterminado de la vista Etiquetas en el editor web. El valor predeterminado de Vista de etiquetas para la sesión de un nuevo usuario viene determinado por la propiedad tagsView del archivo ui_config.json.

* Ahora, en la Vista de repositorio, los archivos se cargan en lotes. Se enumerarán todos los archivos presentes en el principal o `/content/dam folder`. Sin embargo, desde el siguiente nivel o la carpeta secundaria, se cargan 75 archivos a la vez. Esta carga por lotes es eficiente y puede acceder a los archivos más rápido en comparación con cargar todos los archivos existentes en una carpeta.

![cargar más archivos](assets/load-more-files.png)

### Nuevo panel Línea base

La versión 4.1 de AEM Guides proporciona la función Línea de base integrada en el Editor web. Ahora puede crear líneas de base desde el Editor Web y utilizarlas para publicar o traducir temas de distintas versiones.

**Nota**: Para obtener un sistema actualizado, actualice el **ui_config.json** más reciente para el perfil de carpeta.

Utilice esta función para crear una línea base con una versión específica de los temas disponibles en una fecha y hora específicas. Además, se obtiene la compatibilidad con la API para crear o actualizar una línea de base con una etiqueta definida para una versión de temas.

![ficha de administración de línea base](assets/baseline-manage.png)

Puede buscar los archivos en función de sus nombres o ubicación. También puede filtrar los temas que se mostrarán en la ventana de edición de la línea de base y ordenarlos según columnas específicas.

![ficha de administración de línea base](assets/baseline-filter.png)

Se ha mejorado aún más el rendimiento del proceso de creación de la línea de base. El proceso de creación de líneas de base es asincrónico, por lo que puede seguir editando otros archivos en el Editor Web mientras se crea la línea de base. Para obtener más información, consulte *Crear y administrar líneas de base desde el editor web* en la guía Usar Adobe Experience Manager Guides.

Nota: La ficha Línea base del tablero de mandos de asignación está oculta por defecto. El administrador puede activar la pestaña Línea base en el panel de asignaciones.

* El parámetro de línea de base en las API para Descargar mapa ahora utiliza el título de la línea de base para recuperar el contenido versionado.

### Proceso de traducción mejorado

* **Capacidad para crear un proyecto de traducción de ámbito**
Si necesita crear solamente el ámbito para traducir un proyecto, puede seleccionar **Crear un nuevo proyecto de traducción de ámbito**. Esto no enviará las copias para su traducción y se mantendrá el estado de traducción original de los archivos.

![proyecto de traducción de ámbito](assets/scoping-translation-project.png)

* La lista **Idiomas** muestra las carpetas de idioma junto con sus códigos de idioma. Por ejemplo, francés (fr) y alemán (de).

![idioma de traducción](assets/translation-languages.png)

Para obtener más información sobre la traducción, consulte *Traducir documentos desde el editor web* en la guía Uso de Adobe Experience Manager Guides.


### Publicación mejorada

* También puede acceder a **Tablero de publicación** desde la pestaña Salidas mientras genera resultados desde el tablero de asignaciones. En el tablero de publicación hay disponible una lista de todas las tareas de publicación activas.

![salidas en cola](assets/queued-output.png)

* Desde el panel de mapas puede seleccionar varios archivos DITAVAL para generar contenido condicionado. Puede mantener el orden de los archivos añadiendo o eliminando archivos. También puede pasar el ratón sobre el nombre del archivo para ver la ruta en el repositorio de AEM donde está almacenado el archivo.

* Se han respetado las líneas de base para los metadatos de la salida del sitio de AEM. También puede procesar las propiedades de una versión de línea base como metadatos. Si no se define ninguna línea de base, las propiedades de la última versión se procesan como metadatos.

* Se han agregado las opciones **Nombre de archivo** y **Argumentos de línea de comandos DITA-OT** para los ajustes preestablecidos de salida personalizados, EPUB y HTML5. Ahora puede especificar el nombre del archivo con el que desea guardar la salida. También puede especificar los argumentos adicionales que desea que DITA-OT procese al generar resultados.

### Tablero de mapas

Cuando selecciona descargar el mapa DITA, la solicitud se pone en cola y recibe una notificación cuando el mapa está listo para descargarse. Puede elegir descargar el archivo de asignación inmediatamente o descargarlo más tarde desde el vínculo proporcionado en la bandeja de entrada de notificaciones de AEM.

![Descarga de mapa](assets/download-map-prompt.png)

### Otras mejoras de las funciones

* AEM Guides ahora es compatible con Oxygen XML Author versión 24.1.
* El parámetro de línea de base en las API para Descargar mapa ahora utiliza el título de la línea de base para recuperar el contenido versionado.

### Función obsoleta

AEM Guides ya no admite la generación del formato de salida DITA para documentos FrameMaker. Esta opción DITA también se ha eliminado de los ajustes preestablecidos de salida del tablero de mandos Mapa.

## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

* La compatibilidad de creación no está disponible como alternativa para las referencias basadas en rutas de archivos para la publicación. (8076)
* El paquete DITA Add on evita la detección de recursos duplicados DAM. (8417)
* Después de registrar un documento de Oxygen a AEM, el contenido japonés del documento se reemplaza por signos de interrogación (???). (9124)
* Actualizar archivos desprotegidos no funciona en el registro con autenticación Web en Oxygen. (9179)
* El archivo no está desprotegido cuando se abre en Oxygen. (9192)
* Después de registrar un documento de Oxygen a AEM, el contenido japonés del documento se reemplaza por signos de interrogación (???). (9276)
* La autenticación web no funciona en Oxygen. (9296)
* La recarga falla en Oxygen cuando los archivos ya existen en AEM en la misma ubicación. (9328)
* Opción no disponible para sincronizar contenido a la fuerza entre AEM y el sistema local. (9439)
* La ID no se genera automáticamente para el elemento agregado mediante el cuadro de diálogo **Insertar contenido reutilizable** de la barra de herramientas secundaria. (5826)
* No se muestra ningún cuadro de diálogo de confirmación al cargar una imagen con el mismo nombre que un archivo existente, a través del editor. (6011)
* Un espacio de no separación no está disponible en el pallet de caracteres. (7523)
* La lista de elementos (Alt+Intro) aparece atenuada en el tema Oscuro/Más oscuro. (7913)
* La versión no se actualiza al guardar la revisión de un tema desde la barra de herramientas del panel de asignación. (8228)
* xref no se puede insertar ni siquiera en ubicaciones válidas. (8354)
* La operación &quot;getversionlabels&quot; tiene limitaciones y no proporciona el rendimiento esperado. (8513)
* Se producen problemas con el cuadro de diálogo de confirmación al cerrar un archivo bloqueado o editado que no está abierto actualmente en el editor. (8692)
* Se produce un error al añadir un usuario como administrador en el perfil de carpeta cuando el ID de usuario es numérico. (8908)
* El panel Traducción es visible incluso al abrir el mapa DITA en el Editor de mapas. (9053)
* El código de idioma no se muestra con el idioma en el panel Traducción. (9108)
* Las pestañas Traducción y Línea de base están visibles durante un tiempo en el panel Mapa. (9146)
* Cuando se realiza la traducción, se crea una versión adicional para el recurso traducido. (9310)
* La traducción aprobada no se integra al idioma de destino cuando el código de idioma de destino contiene cinco caracteres como `fr_ca`. (9357)
* El contenido traducido se interrumpe cuando el código de idioma de destino creado se menciona como `fr-fr, `, `en-us`. (9527)
* Al cargar un mapa DITA fuera de la carpeta de idioma, se registra una excepción en el servidor.(9543)
* No se puede crear un fichero DITA con la plantilla DITA personalizada desde el editor. (7262)
* El mapa DITA se pierde al publicar un mapa DITA UUID a través de FMPS. (7278)
* AEM Guides no copia las propiedades no únicas de un recurso cuando se copia y pega un recurso. (8241)
* El nombre de archivo de mapa DITA no se convierte a minúsculas en el momento de la creación. (8383)
* La descripción de la tarea de revisión no aparece en la notificación por correo electrónico que se envía cuando se asigna una nueva tarea de revisión. (8507)
* Descargar API de mapa | Las carpetas temporales no se limpian en caso de que se produzcan errores de proceso de descarga. (8523)
* `columnpreview.jsp` depende del SP.  (8543)
* Los trabajos de salida con un estado como &quot;Esperando&quot; o &quot;Ejecutando&quot; no se limpian en el panel de publicación.  (8569)
* Icono predeterminado seleccionado al generar un informe con el botón Generar, incluso cuando se define la propiedad del icono. (8573)
* Se han producido problemas en el proceso de revisión al actualizar de 3.8.X a 4.0. (8788)
* En el panel Revisar del editor web, si un nombre de usuario es largo, los iconos para aceptar/rechazar no se muestran claramente. (8793)
* Saltos del árbol de referencia después de quitar un tema y realizar una operación de movimiento. (8804)
* La DTD personalizada definida por el usuario no tiene prioridad sobre la DTD DITA estándar incrustada en DITA-OT. (9104)
* La posición del resaltado es incorrecta en la vista en paralelo. (9305)
* La nota al pie utilizada por referencia no se desplaza a la sección de notas al pie en la salida del sitio de AEM. (9061)
* El orden de las notas al pie es incorrecto en la salida del sitio de AEM. (9327)
* Los recursos DITA recién creados siempre los extrae otro usuario. (9387)
* El error siempre se registra al crear contenido nuevo. (9388)
* La tercera pantalla del proceso de creación de la tarea de revisión no muestra la lista de glosarios. (4558)
* Se han asignado referencias UUID incorrectas al cargar varios archivos desde el conector de FrameMaker/Oxygen. (8269)
* No se envía una notificación por correo electrónico cuando se reasigna una tarea de revisión en la bandeja de entrada. (8376)
* El segundo usuario administrador no se puede agregar como primer usuario administrador a una carpeta. (8430)
* El cuadro de diálogo **Aplicar etiquetas** de la pestaña Línea de base no muestra las etiquetas en la lista desplegable. (8455)
* Al utilizar la publicación de línea de base con imagen como referencia en el tema, la imagen no se publica en la salida. (8564)
* La función de depuración de salida falla si hay un gran número de nodos de historial de salida restantes presentes. (8568)
* En el panel Historial de versiones, la sección Versión actual muestra una marca de tiempo incorrecta y se ha modificado mediante información. (8765)
* La línea de base no se actualiza según la etiqueta definida. (8799)
* Se produce un error cuando los archivos cuya carpeta principal contiene caracteres especiales en el nombre de archivo se abren en Oxígeno (con el botón **Editar en Oxígeno**). (8918)
* La carga de archivos de Oxygen a AEM falla. (9157)
* Descargar mapa con línea de base no funciona si el contenido se mueve a otra carpeta. (9331)
* Oxygen comprueba una versión incorrecta de un tema después de revertir una versión en AEM. (9411)
* Buscar en el panel Repositorio y el cuadro de diálogo de exploración de referencias de tema congela la pantalla cuando el contenido es grande. (9432)
* Si la opción **Crear nueva versión para el archivo cargado** está activada, se crea una nueva versión al revertir y guardar en cualquier nodo inmovilizado. (9473)
* Las diferencias de marca de tiempo incorrectas se muestran en la IU de Assets al revertir una versión de archivo. (9480)
* Los archivos se desprotegen automáticamente al revertir a cualquier versión. (9482)
* El icono de bloqueo se muestra en la vista del repositorio incluso cuando el archivo se registra desde el editor.  (5756)
* No se pueden agregar elementos de contenido anterior y de contenido posterior en un mapa de libros mediante la vista Autor del Editor Web. (7652)
* El modo de vista previa no admite el atributo de procesamiento condicional `deliveryTarget` en DITA. (7685)
* Al abrir un tema del glosario en el editor XML, AEM obliga a guardarlo aunque no se haya modificado. (8105)
* El cuadro de diálogo Insertar referencias se abre al agregar subjectref a un mapa mediante la interfaz de usuario. (8212)
* El panel Reutilizar contenido se bloquea al buscar caracteres especiales `[` o `*`(8279)
* Durante la creación de Glossentry, el editor web muestra el contenido como una nota. (8384)
* El Editor XML elimina la nueva línea en el bloque de código. (8522)
* Cambiar entre el modo de origen y el de autor marca el tema como sucio y requiere que se vuelva a guardar el contenido.(8524)
* No se puede cerrar un tema desbloqueado. (8545)
* No existe ninguna opción para elegir la ruta de la base de conocimiento en los ajustes preestablecidos de publicación basados en artículos. (8636)
* Faltan atributos al agregar un capítulo al mapa de libros mediante arrastrar y soltar desde la vista Favoritos. (8746)
* El cuadro de diálogo Insertar palabra clave no tiene la capacidad de búsqueda y las palabras clave no se muestran en orden. (9094)
* Al realizar una búsqueda en el Editor XML, la página se bloquea. (9452)
* Faltan sitios en los ajustes preestablecidos de AEM en la pestaña Salida. (9567)
* Imágenes de SVG que no se representan correctamente en los modos de autor del Editor XML. (9426)
* La línea de base no se cumple al publicar mediante Salesforce. (8953)
* No está presente la capacidad de borrar el mapa de raíz de la configuración de preferencias de usuario. (8534)
