---
title: Notas de la versión de Adobe Experience Manager Guides 3.8 y 3.8.5
description: Las principales nuevas funciones y mejoras de las versiones 3.8 y 3.8.5 de Adobe Experience Manager Guides (anteriormente conocida como solución XML Documentation).
source-git-commit: ff3d35832b80f6221f1261498934ab74261b282b
workflow-type: tm+mt
source-wordcount: '1589'
ht-degree: 0%

---


# Notas de versión | Adobe Experience Manager Guides 3.8

**Descargo de responsabilidad**:

*Adobe Experience Manager Guides* se había marcado anteriormente como *XML Documentation para Adobe Experience Manager*. Tenga en cuenta que algunas referencias de la documentación pueden seguir haciendo referencia a marcas anteriores, pero siguen siendo aplicables a la oferta actual.

En estas notas de la versión se enumeran las principales nuevas funciones y mejoras de la versión 3.8.x de XML Documentation para Adobe Experience Manager.

## Nuevas funciones y mejoras en la versión 3.8.5

### Correcciones de errores

Los errores corregidos en la versión 3.8.5 se enumeran a continuación:

- Falta la compatibilidad con la línea de base para la salida de PDF a través de FrameMaker Publishing Server.
- La API de cierre y registro de FrameMaker u Oxygen no funciona correctamente si se han configurado los permisos de nivel de carpeta para varios grupos en AEM.
- La vista previa del contenido no se muestra desde la página de IU de Assets.
- El botón &quot;Source&quot; no funciona en la página de la interfaz de usuario de Assets.
- Cuando se inserta una imagen a través de la función Insertar imagen del Editor Web, la ruta relativa de la imagen insertada cambia a su ruta absoluta.
- La lista desplegable de ajustes preestablecidos de FMPS no se muestra en la IU con la última versión 3.8.
- El panel Favoritos no se muestra cuando contiene un gran número de recursos en DAM y se agrega un nuevo elemento favorito desde el Editor Web XML.
- La redirección interna *sling:mapping* que redirige todos los vínculos no funciona y muestra direcciones URL largas (con rutas internas) en lugar de direcciones URL cortas para las páginas web.
- En la vista de lista, la columna Modificado muestra &quot;Usuario externo&quot; en lugar del nombre de usuario cuando los recursos se cargan o importan desde la página de la interfaz de usuario de Assets (excepto a través del Administrador de paquetes).
- El título no se muestra correctamente en la pestaña Temas del panel de mapas.
- Al habilitar la función de acoplamiento de nodos, algunos caracteres no deseados se almacenan en la salida de HTML.
- Los cambios en el perfil de carpeta de las preferencias de usuario no se vuelven a cargar automáticamente para un archivo ya abierto, pero es necesario actualizar el explorador.
- La salida generada mediante la opción Descargar mapa tiene algunos temas que faltan si hay algunos errores de validación.

## Nuevas funciones y mejoras en la versión 3.8

### Actualizaciones de configuración de nomenclatura de archivos

Al crear temas DITA en la solución XML Documentation, los usuarios pueden utilizar caracteres especiales como parte de los nombres de archivo. Esto resultaba en direcciones URL codificadas en la generación de páginas de sitios de AEM. Para evitar esta conversión en la dirección URL, la versión 3.8 de las soluciones de XML Documentation permite a un administrador definir una lista de caracteres especiales que no sean las configuraciones de nombre de archivo válidas predeterminadas (a-z A-Z 0-9 - _). Esto implica que, aunque puede configurar una lista de caracteres especiales en un nombre de archivo que incluya un espacio, se reemplazará con un guión (-).

### Cambios en la generación de nombres de páginas de AEM site

Durante la creación, es posible tener el mismo nombre de archivo para uno o varios archivos en carpetas diferentes. Durante el proceso de publicación del sitio de AEM, los nombres de página se anexaban con un sufijo cuando había al menos un nombre de archivo duplicado. Con la versión 3.8 de la solución XML Documentation, se ha corregido el proceso de generación de nombres de páginas de sitios de AEM. El sufijo se anexa al nombre de página generado solo si hay un nombre de archivo duplicado.

### Nuevas funciones y mejoras

Se han introducido una serie de nuevas funciones y mejoras en las siguientes áreas del producto.

#### Editor web

- Ahora puede elegir una etiqueta de una lista desplegable mientras crea una versión de un tema desde el Editor Web.

  ![Etiquetas en una lista desplegable](assets/labels-drop-down-saving-topic-res.avif)

- El panel Revisar del Editor Web ahora es más eficaz, lo que le permite revertir un tema a una versión compartida para revisión. Puede incorporar fácilmente comentarios de revisión en la versión revisada sin tener que recordar qué versión del tema se compartió para revisión.

  ![Revertir tema a la versión de revisión](assets/revert-review-topic.avif)

- Se ha introducido una nueva pista visual para indicar si está trabajando en la última versión de un tema o en una versión anterior.

  ![Señal de versión](assets/old-version-icon.avif)

- En esta versión se ha introducido una nueva función Historial de versiones. Utilice la función Historial de versiones para:
   - Ver una lista de todas las versiones del tema activo junto con las etiquetas agregadas para cada versión.
   - Volver a una versión anterior del tema.

  ![Historial de versiones](assets/version-history.avif)

- Se ha agregado una nueva característica de Administración de etiquetas de versión que permite aplicar etiquetas a las versiones actuales o anteriores de un tema.

  ![Administración de etiquetas de versión](assets/version-label-management.avif)

- Se ha añadido una nueva función, &quot;Aprobar para publicación&quot;, con la que un autor puede marcar un recurso como aprobado y bloquearlo para editarlo.
- Al iniciar un proceso de revisión, ahora puede filtrar los temas según su estado.

  ![Seleccionar temas de revisión según su estado](assets/review-select-topic-on-state.avif)

- `<navtitle>` en un mapa se rellena automáticamente con el título de un tema agregado al archivo de asignación. También puede actualizar `<navtitle>` fácilmente desde el Editor Web.
- La vista previa de una tabla con un gran número de columnas ahora se muestra dentro del área de página.
- Puede aplicar varias clases de salida a la vez desde el panel Propiedades (multiselect).
- Al obtener una vista previa de un tema, también puede generar (un resultado incondicional) de PDF de un solo tema directamente desde el editor web.

  ![Salida de PDF de la vista previa](assets/pdf-output-from-preview.avif)

- Bloquee una solicitud de publicación si la generación de salida del mismo ajuste preestablecido está en curso.
- Se ha agregado la capacidad de eliminar recursos que tienen referencias secundarias activas únicamente a un conjunto de usuarios privilegiados.
- Se ha añadido una función para ver o copiar el código XML de la vista de Source desde la interfaz de usuario de Assets aunque el archivo esté desprotegido por otro usuario.

  ![Vista de XML Source](assets/xml-source-view-from-assets-ui.avif)

- Ahora, el nombre de archivo se reemplaza por el título del archivo en el cuadro de diálogo Guardar, el panel Contenido reutilizable y el panel Buscar y reemplazar.

#### Publicación

- **Permitir la configuración de reglas de saneamiento para páginas generadas del sitio**: como administrador, puede definir las reglas de saneamiento para los nombres de archivo del sitio AEM generado o la salida DITA-OT. Siempre que genere una salida o salida de sitio de AEM mediante DITA-OT, puede configurar las siguientes reglas para sanear las direcciones URL o los nombres de archivo generados por salida:
   - Convierta todos los caracteres a minúsculas.
   - Reemplace los caracteres especiales por un separador.
   - Restrinja un nombre de archivo largo a un número predefinido de caracteres.

- Inserte fácilmente la salida de la instancia de autor en la instancia de publicación mediante el panel de activación masiva. Puede trabajar con un solo mapa o una colección de mapas y elegir el ajuste preestablecido de salida que desee utilizar para la publicación.

  ![Tablero de publicación en lotes](assets/bulk-publish-dashboard.avif)

#### Mejoras de rendimiento

- Acoplamiento de nodos para la salida de AEM Sites: anteriormente, la estructura de nodos del sitio de la salida de AEM Sites era demasiado profunda. Ahora, tiene el control para acoplar la estructura del nodo para obtener un mejor rendimiento.
- Compatibilidad con la última versión de la versión de verano de 2020 de FrameMaker Publishing Server.
- Los archivos temporales generados durante la traducción ahora se eliminan, lo que mejora el proceso de traducción.

#### Otras mejoras

- Se ha eliminado la dependencia del flujo de trabajo del recurso de actualización DAM mientras se posprocesaba el contenido DITA. Si hay algún paso del proceso personalizado definido en el flujo de trabajo de recursos de actualización de DAM, debe actualizarlos para que se ejecuten una vez completado el procesamiento posterior.
- El iniciador del proceso de traducción ahora recibe una notificación en su Bandeja de entrada cuando el trabajo de traducción se crea correctamente.

### Correcciones de errores

Los errores corregidos en la versión 3.8 se enumeran a continuación:

- Los objetos de audio no se muestran en la salida de HTML.
- La ventana Forzar eliminación que se muestra al borrar un tema DITA muestra varios botones &quot;Forzar eliminación&quot;.
- La transferencia de línea base a copias de idioma no funciona para la línea base creada con la vista del lado del servidor.
- A veces, la versión 3.0 de un tema aparece como 3 en la vista en paralelo, lo que no permite que se importen los comentarios de revisión.
- Carga lenta de los detalles de contenido referenciado en la ficha Líneas bases para el mapa DITA movido.
- La reversión a una versión anterior no funciona para los recursos que no son dita.
- Se están creando muchos nodos de _texto vacíos con la generación de resultados de AEM Sites.
- Editor XML: la resolución de vínculos en mapas de imágenes después de la generación de páginas no funciona.
- Aplicar etiquetas de la pestaña Líneas bases no agrega etiquetas al contenido al que se hace referencia, como las imágenes.
- Los archivos SVG se descargan en un formato incorrecto a través de la opción Descargar mapa.
- No se puede editar el fragmento de contenido en una vista de lista.
- No se pueden desproteger y abrir los archivos en Oxygen XML Author mediante el conector.
- El texto del elemento `<alt>` no está visible en la vista Creación.
- El recurso de imagen siempre se muestra como Obsoleto incluso cuando existe una copia traducida.
- El título personalizado de la plantilla de mapa es incorrecto y no se muestra la miniatura.
- Elementos de marca aplicados que no se muestran en la vista Creación del editor web.
- Las notas al pie vinculadas no son visibles en el contenido.
- La codificación de color en el Editor Web no funciona con atributos condicionales especializados.
- La lista desplegable de @keyref no es fácil de usar, ya que considera que casi no se puede utilizar para clientes con un gran número de @keyref.
- No se representa el texto de variable al que hace referencia @keyref.
- Conector de oxígeno El botón || &quot;Editar en oxígeno&quot; ahora abre el archivo en modo de edición aunque el archivo no esté desprotegido.
- Los ajustes preestablecidos de salida personalizados no se crean con una plantilla de mapa personalizada.
- La conversión de Microsoft Word (.docx) a DITA no crea el nodo jcr:content y permite caracteres especiales para los nombres de carpeta.
- Una vez que se mueve un MAPA (que tiene más de 150 referencias), las referencias se rompen y se observan errores al abrir los temas.
- La resolución de una imagen se calcula incorrectamente cuando se cambia la anchura de la imagen.
- Cuando se agrega una imagen en `<codeblock>`, se encuentran espacios en blanco no deseados en la salida del sitio de AEM.

