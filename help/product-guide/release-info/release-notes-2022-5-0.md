---
title: Notas de versión | Guías de Adobe Experience Manager as a Cloud Service, versión de mayo de 2022
description: Lanzamiento de mayo de las guías de Adobe Experience Manager as a Cloud Service
exl-id: 7928a300-5ec9-492c-b9be-02b6f87638c6
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1887'
ht-degree: 0%

---

# Lanzamiento de mayo de las guías de Adobe Experience Manager as a Cloud Service

## Actualización a la versión de mayo

Actualice las guías de Adobe Experience Manager actuales as a Cloud Service (más adelante denominadas *AEM Guías de as a Cloud Service*) realizando los siguientes pasos:
1. Consulte el código Git de los Cloud Service y cambie a la rama configurada en la canalización de Cloud Service correspondiente al entorno que desee actualizar.
1. Actualizar `<dox.version>` propiedad en `/dox/dox.installer/pom.xml` de su código Git de Cloud Service a 2022.5.144.
1. Confirme los cambios y ejecute la canalización de Cloud Service AEM para actualizar a la versión de mayo de las guías de los as a Cloud Service.

## Matriz de compatibilidad

AEM En esta sección se enumera la matriz de compatibilidad para las aplicaciones de software compatibles con las guías de la aplicación de la versión as a Cloud Service para mayo de 2022 de las Guías de.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| No compatible | Actualización 4 de 2020 y posterior |
| | |

AEM *La línea de base y las condiciones creadas en la versión de FMPS a partir de 2020.2 son compatibles con las versiones de FMPS.

### Conector de oxígeno

| AEM Versión de Guides as a Cloud de | Ventanas de conector de oxígeno | Conector de oxígeno Mac |
| --- | --- | --- |
| 2022.5.0 | 2.6.9 | 2.6.9 |
|  |  |  |


## Nuevas funciones y mejoras

AEM En la versión de mayo de, Guides as a Cloud Service proporciona muchas mejoras y nuevas funciones:

### Editor web mejorado

* **Creación de mapas basados en plantillas personalizadas**

Ahora dispone de la potente función para crear plantillas de mapas personalizadas. Se pueden utilizar para crear mapas DITA junto con las plantillas de temas y las plantillas de mapas a las que se hace referencia en la plantilla de mapas.

![plantillas dita](assets/dita-templates.png)

También puede hacer referencia a otras plantillas de mapas y plantillas de temas desde la plantilla de mapas personalizada. Las plantillas de mapas a las que se hace referencia pueden hacer referencia a varias plantillas de mapas, plantillas de temas, temas, mapas, imágenes, vídeos y otros recursos.

![crear plantillas de dita](assets/create-dita-template.png)

La plantilla de mapa personalizada puede ayudarle a replicar muy fácilmente las plantillas de mapa y toda la estructura de carpetas de referencia. Estas plantillas personalizadas son especialmente útiles para crear y recrear varios mapas con estructuras y referencias recursivas.

* El **Insertar palabra clave** se ha mejorado la función de. Ahora puede encontrar más fácilmente una palabra clave para insertarla, ya que las palabras clave se enumeran en orden alfabético. También puede buscar palabras clave escribiendo una cadena de búsqueda en el cuadro Buscar.

![insertar palabra clave](assets/insert-keyword.png)

* Ahora, en la Vista de repositorio, los archivos se cargan en lotes. Se cargan 75 archivos a la vez. Esta carga por lotes es eficiente y puede acceder a los archivos más rápido en comparación con cargar todos los archivos existentes en una carpeta.

![cargar más archivos](assets/load-more-files.png)

* Puede procesar imágenes de SVG que incluyan datos incrustados o vínculos en todas las pantallas del editor XML, incluidas, entre otras, la Vista previa y la Vista de autor.

* El XSD/DTD predeterminado se puede actualizar a la versión más reciente

### Proceso de traducción mejorado

* **Capacidad para crear un proyecto de traducción de ámbito**
Si necesita crear únicamente el ámbito para traducir un proyecto, puede seleccionar **Crear un nuevo proyecto de traducción de ámbito**. Esto no enviará las copias para su traducción y se mantendrá el estado de traducción original de los archivos.

![proyecto de traducción de ámbito](assets/scoping-translation-project.png)

* Si rechaza la traducción de uno o más temas de un trabajo de traducción, el estado de traducción En curso de todos los temas rechazados vuelve a su estado original.

* El **Idiomas** La lista muestra las carpetas de idioma junto con sus códigos de idioma. Por ejemplo, francés (fr) y alemán (de).

* La función de traducción ahora también admite el código de idioma, que incluye tanto el país como el idioma. Por ejemplo, `fr-fr`, `en-us`.

![idioma de traducción](assets/translation-languages.png)

* Al cargar un mapa DITA fuera de la carpeta de idioma, no se registra ninguna excepción en el servidor.

Para obtener más información sobre la traducción, consulte *Traducir documentos desde el editor web* de Uso de las guías de Adobe Experience Manager as a Cloud Service.


### Publicación mejorada

* También puede acceder a las **Publicar tablero** en la pestaña Salidas mientras genera resultados desde el panel de asignación. En el tablero de publicación hay disponible una lista de todas las tareas de publicación activas.

![salidas en cola](assets/queued-output.png)

* Desde el panel de mapas puede seleccionar varios archivos DITAVAL para generar contenido condicionado. Puede mantener el orden de los archivos añadiendo o eliminando archivos. AEM También puede pasar el ratón sobre el nombre del archivo para ver la ruta en el repositorio de donde se almacena el archivo.

* **Función obsoleta**
AEM El formato as a Cloud Service ya no admite la generación de formato de salida DITA para documentos de FrameMaker. Esta opción DITA también se ha eliminado de los ajustes preestablecidos de salida del tablero de mandos Mapa.

### Publicación basada en artículos mejorada

El Editor XML proporciona la capacidad de asignar más de una categoría de producto a un artículo mientras se publica en un perfil de Salesforce.

### Otras mejoras de las funciones

* El modo de previsualización también admite `deliveryTarget` atributo de procesamiento condicional en DITA. Está disponible como opción en el filtro desplegable junto con **audiencia**, **plataforma**, **producto**, props, **otras props**.
* AEM Se ha proporcionado la opción de sincronizar a la fuerza entre el servidor de en Oxygen y el sistema local.

## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

* En el panel de revisión del Editor Web, el usuario no puede responder a los comentarios de revisión. (9667)
* La aplicación se queda en blanco al hacer clic en una carpeta en blanco después de actualizarla mediante el menú Opciones. (9639)
* Se está creando una nueva versión cuando **Guardar y cerrar** el archivo protegido. (9638)
* El botón Cerrar no se muestra cuando **Guardar como nueva versión** La casilla de verificación está activada. (9637)
* El PDF correcto no se publica si primero se publica mediante un PDF independiente para cada capítulo y, a continuación, un solo archivo de PDF (la opción Crear archivos de PDF independientes está desactivada). (9632)
* El panel de mapas está generando un problema de metadatos para los usuarios no administradores. (9620)
* Una vez creada una línea de base, el estado se establece en failed en la interfaz de usuario (la llamada de obtener estado falla) si el servidor tiene más de 10000 archivos. (9608)
* El almacenamiento de datos grandes en propiedades provoca un error de publicación, ya que el flujo de trabajo de publicación dividido falla. (9586)
* El estado de los filtros de atributos condicionales no se conserva al cambiar entre Vista previa en origen y de nuevo en modo de Vista previa. (9553)
* El nombre de la asignación de libros aparece en blanco en la vista de repositorio en caso de que no se proporcione ningún nombre a través de la variable `mainbooktitle` etiqueta. (9538)
* El error HTTP 400 se produce al abrir un archivo cargado con Oxygen. (9535)
* Los ajustes preestablecidos de un mapa abierto anteriormente permanecen visibles en la pestaña Salida al abrir un mapa sin ajustes preestablecidos definidos. (9523)
* La funcionalidad de búsqueda para Etiquetas y atributos no funciona en el panel Esquema. (9506)
* La colección recién creada no será visible hasta que se actualice el explorador en el explorador. (9505)
* Las etiquetas de Atributos condicionales (no los valores) aparecen en el modo de origen al añadir todas las condiciones mediante la opción &quot;Añadir todas las props&quot;. (9501)
* Los archivos se desprotegen automáticamente al revertir a cualquier versión. (9482)
* Las diferencias de marca de tiempo incorrectas se muestran en la IU de Assets al revertir una versión de archivo. (9480)
* Se añaden varios elementos de los resultados de búsqueda al insertar elementos en el elemento topicref del mapa DITA. (9474)
* Si la configuración **Crear nueva versión para el archivo cargado** está activado, se crea una nueva versión al revertir y guardar en cualquier nodo inmovilizado. (9473)
* El texto de visualización de la referencia de clave y de la referencia de clave de contenido no se mantiene al cambiar la dirección URL del vínculo, si el texto de visualización no se añade al definir la referencia de clave. (9458)
* En el Historial de versiones, el número de versión y la etiqueta no se muestran para la versión actual. (9446)
* El editor se bloquea cuando se abren ciertos archivos de contenido en el editor. (9443)
* Buscar en el panel Repositorio y el cuadro de diálogo de exploración de referencias de tema congela la pantalla cuando el contenido es grande. (9432)
* AEM Los metadatos pasados a la salida del sitio de la no respetan la línea de base del contenido. (9416)
* AEM Oxygen comprueba una versión incorrecta de un tema después de que una versión vuelva a estar en la versión de la versión de la versión de la versión de la versión de la versión de la versión de la. (9411)
* La línea de base con error deshabilita la edición en la pestaña Ajuste preestablecido del panel de asignaciones. (9403)
* El error siempre se registra al crear contenido nuevo. (9388)
* Los recursos DITA recién creados siempre los extrae otro usuario. (9387)
* Rename element no funciona correctamente al convertir topicref en glossref. (9380)
* La etiqueta de versión no se presenta como lista desplegable en **Guardar como nueva versión** diálogo. (9379)
* Las condiciones no se aplican al cambiar entre distintas versiones de **Mostrar diferencia** desplegable. (9366)
* Se producen varios problemas al utilizar los filtros de vista previa. (9365)
* No se pueden insertar recursos no DITA y DITAVAL en topicref. (9363)
* La traducción aprobada no se integra al idioma de destino cuando el código de idioma de destino contiene cinco caracteres como `fr_ca`. (9357)
* No se pueden buscar archivos usando **Buscar archivos en la carpeta** desde el **Más opciones** y la aplicación deja de responder. (9337)
* El cuadro de diálogo Examinar se bloquea si hay un gran número de claves. (9332)
* Los archivos DITAVAL no funcionan mientras se realiza la publicación basada en artículos. (9330)
* AEM El orden de las notas al pie es incorrecto en la salida del sitio de la. (9327)
* La búsqueda no se realiza automáticamente cuando se cambia la ruta de selección. (9323)
* Cuando se realiza la traducción, se crea una versión adicional para el recurso traducido. (9310)
* No se pueden eliminar los usuarios administradores en el perfil de carpeta. (9306)
* El mapa raíz actualizado desde la Referencia de clave de contenido no se establece hasta que se actualiza la página. (9302)
* La autenticación web no funciona en Oxygen. (9296)
* Los vínculos web con caracteres codificados no funcionan correctamente. (9227)
* El archivo no está desprotegido cuando se abre en Oxygen. (9217)
* Actualizar archivos desprotegidos no funciona en el registro con autenticación Web en Oxygen. (9179)
* Las pestañas Traducción y Línea de base están visibles durante un tiempo en el panel Mapa. (9146)
* Los problemas de experiencia o funciones se producen al volver a cargar el perfil de carpeta. (9103)
* Al eliminar el editor de diseño de página, no se cierra desde el panel central de la vista Autor. (9087)
* El error de validación se produce en el Editor Web al quitar una imagen y guardar la nueva versión del documento. (8985)
* No se pueden ver todos los `glossrefs` en el panel Glosario (contenido específico). (8886)
* `xref` sin texto no se muestra en la salida de publicación basada en artículos. (8764)
* Las referencias se rompen al mover imágenes o archivos multimedia que tienen un espacio en los nombres de archivo. (8624)
* Las referencias se rompen al elegir `Select All` y mover los archivos multimedia o el contenido DITA a otra carpeta. (8622)
* Los trabajos de salida con un estado como &quot;Esperando&quot; o &quot;Ejecutando&quot; no se limpian en el panel de publicación.  (8569)
* La función de depuración de salida falla si hay un gran número de nodos de historial de salida restantes presentes. (8568)
* El paquete DITA Add on evita la detección de recursos duplicados DAM. (8417)
* Botón Crear tarea de revisión habilitado para archivos que no son DITA. (8401)
* El cuadro de diálogo Insertar referencias se abre al agregar subjectref a un mapa mediante la interfaz de usuario. (8212)
* Se ha encontrado espacio inesperado en cada espacio en blanco `entry` cuando se agrega el atributo outputclass a `tgroup` Elemento. (7532)
* El panel Repositorio no muestra los iconos de bloqueo de archivos protegidos o desprotegidos en cuanto se completa la acción. (5817)
* El icono de bloqueo se muestra en la vista del repositorio incluso cuando el archivo se registra desde el editor.  (5756)
* AEM Faltan sitios en los ajustes preestablecidos de la interfaz de usuario en la pestaña Salida. (9567)
* El Editor XML se bloquea al intentar editar algunos archivos DITA. (9537)
* Al realizar una búsqueda en el Editor XML, la página se bloquea. (9452)
* Descargar mapa con línea de base no funciona si el contenido se mueve a otra carpeta. (9331)
* AEM La recarga falla en Oxygen cuando el archivo o los archivos ya existen en la misma ubicación en la que se encuentran en la misma ubicación. (9328)
* La posición del resaltado es incorrecta en la vista en paralelo. (9305)
* AEM Después de registrar un documento de Oxygen en el que se ha realizado el registro, el contenido en japonés del documento se reemplaza por signos de interrogación (???). (9276)
* AEM La carga de archivos de Oxygen a la red de distribución de archivos falla. (9157)
* No se envía una notificación por correo electrónico cuando se reasigna una tarea de revisión en la bandeja de entrada. (8376)

## Problemas conocidos

La página en blanco se muestra intermitentemente al abrir el editor.
