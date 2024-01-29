---
title: Notas de versión | Instrucciones de actualización y problemas corregidos en la versión 4.4.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores y cómo actualizar a la versión 4.4.0 de las guías de Adobe Experience Manager
source-git-commit: 00ee1be73395d7d4266c6564b724b9794e03161a
workflow-type: tm+mt
source-wordcount: '1808'
ht-degree: 0%

---

# Versión 4.4.0 de Adobe Experience Manager Guides (febrero de 2024)

Esta nota de la versión cubre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en la versión 4.4.0 de Adobe Experience Manager Guides (más adelante denominada *Guías del Experience Manager*).

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 4.4.0 de las guías de Adobe Experience Manager](./whats-new-4.4.md).

## Actualización a la versión 4.4.0 de las guías del Experience Manager


Puede actualizar fácilmente su versión actual de Guides a la versión 4.4.0. Antes de continuar actualizando a la versión 4.4.0 de las Guías del Experience Manager, debe tener en cuenta los siguientes puntos:


- Si utiliza las versiones 4.3.1, 4.3.0 o 4.2.1 (revisión 4.2.1.3), puede actualizar directamente a la versión 4.4.0.
- Si utiliza las versiones 4.2, 4.1 o 4.1.x, debe actualizar a las versiones 4.3.1, 4.3.0 o 4.2.1 (revisión 4.2.1.3) antes de actualizar a la versión 4.4.0.
- Si utiliza la versión 4.0, debe actualizar a la versión 4.2 antes de actualizar a la versión 4.3.x.
- Si utiliza la versión 3.8.5, debe actualizar a la versión 4.0 antes de actualizar a la versión 4.2.
- Si su versión es anterior a la 3.8.5, consulte la sección Guías del Experience Manager de actualización en la guía de instalación específica del producto.



>[!NOTE]
>
>AEM Debe instalar el paquete de servicio de antes de actualizar la versión de las guías del Experience Manager.

Para obtener más información, consulte [Instrucciones de actualización](../install-guide/upgrade-xml-documentation.md).

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con la versión 4.4.0 de las Guías del Experience Manager.

### Adobe Experience Manager

**4.4.0 No UUID**
Paquete de servicio 19, 18 y 17 de la versión 6.5

**UUID 4.4.0**
Paquete de servicio 19, 18 y 17 de la versión 6.5

Para obtener más información, consulte la *Requisitos técnicos* de la guía Instalar y configurar guías de Adobe Experience Manager.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.4.0 (no UUID) | 2022 o superior | 2020.2 o superior* | 2022 o superior | 2020.3 o superior |
| 4.4.0 (UUID) | 2022 o superior | 2020.2 o superior* | 2022 o superior | 2020.4 o superior |
| | | | |

AEM *La línea de base y las condiciones creadas en la versión de FMPS a partir de 2020.2 son compatibles con las versiones de FMPS.

### Conector de oxígeno

| Versión | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.4.0 (no UUID) | 2.7-regular-1 | 2.7-regular-1 | 1,6 | 1,6 |
| 4.4.0 (UUID) | 3.4-uuid-1 | 3.4-uuid-1 | 2,3 | 2,3 |
|  |  |   |



### Versión de plantilla de base de conocimiento

| Nombre del paquete de componentes | Versión de componentes | Versión de plantilla |
|---|---|---|
| Paquete de contenido de componentes de guías del Experience Manager para Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

### Creación

- La revisión ortográfica en el editor no permite la selección de sugerencias. (15045)
- El botón de navegación global no funciona y el panel no se puede cargar. (14968)
- En el editor web, la función de mapa de descarga no almacena en déclencheur una notificación emergente cuando está lista para descargarse. (14626)
- En el editor web, la función de mapa de descarga no puede descargar un mapa con una línea de base. (14622)
- Error de DTD no válido en las guías del Experience Manager. (14482)
- El título de la ficha Editor Web se trunca después de un punto (.) extra. (14372)
- No se ha actualizado la mensajería de error para nombres de asignaciones duplicados en la interfaz de usuario de Assets. (14320)
- Se produce un error en la lógica de creación de versiones al arrastrar y soltar recursos. (14291)
- El contenido reutilizable omite los ID de elemento. (14213)
- El control de configuración que se va a ocultar **Variables de idioma** panel debajo de **Output** falta la pestaña. (14194)
- El editor web genera errores de aplicación al agregar una nueva referencia o tema utilizando un esquema especializado en la variable **Diseño** vista. (14094)
- El espacio después de la conref `<ph>` desaparece al guardar el tema. (13642)
- Se produce un error de aplicación al intentar guardar archivos DITA antes de que finalice el posprocesamiento. (13571)
- Un vínculo de anclaje a `<dlentry>` o `<dt>` El elemento no muestra el texto del vínculo. (13543)
- El **Favoritos** La colección del Editor Web no se puede cargar. (13495)
- Si el título de un tema contiene una barra diagonal `/`, la pestaña del Editor web solo muestra las cartas que le siguen. (13455)
- La previsualización de la imagen no desaparece después de mostrar la previsualización en el editor web. (13454)
- Las citas muestran vínculos en los que no se puede hacer clic cuando se crean con un ID único con espacios. (13447)
- AEM Al cerrar un tema después de editarlo, se le redirige a la página de inicio de la página de inicio de la página de en lugar de volver a la vista de carpeta. (13306)
- La ventana emergente Insertar palabra clave no aparece al utilizar claves definidas por mapa raíz en otros temas. (12950)
- Los iconos de cierre no son visibles cuando se muestran gráficos muy altos en la vista previa de **Historial de versiones** panel. (12867)
- No se puede modificar la zona horaria de **Versión creada el** para las líneas de base. (12711)
- Los archivos Zip no se reconocen en el Editor Web y no se pueden arrastrar y soltar. (12709)
- El **Historial de versiones** en la IU de Assets muestra una marca de tiempo incorrecta para **Actual** field. (12624)
- En el **Diseño** vista de un mapa de libros, usando **Mover a la derecha** para convertir un capítulo seleccionado en un subelemento no funciona. (12567)
- La creación de un fichero DITA a partir de una plantilla con un nombre de fichero que empieza por caracteres numéricos da lugar a un error de espacio de nombres. (12188)
- La configuración de mapa de raíz persiste en el editor web aunque el usuario no la haya establecido explícitamente desde el **Preferencias de usuario**. (11551)
- El contenido con algunos atributos aplicados no se resalta en **Autor** o **Previsualizar** modo. (11063)
- En el Editor Web, la variable **Referencias clave** se abre al insertar el `varname` etiqueta. (10940)
- Arrastrar un tema del glosario desde el repositorio a un mapa del glosario crea `topicref`. (10767)
- La ventana de vista previa del Editor XML se trunca en los exploradores Google Chrome y Microsoft Edge. (10755)
- El editor web carece de la capacidad de envolver un elemento dentro de los posibles elementos principales. (8791)
- El editor web se desinstala después de volver a instalar la versión 4.3.1 de las guías de Adobe Experience Manager. (14519)
- El instalador de la versión 4.3.1 encuentra un conflicto de filtros, que provoca la anulación de `apps/cq/core/content/projects/properties`. (14517)
- Aparecerá un vínculo de referencia en la lista de **Vínculos rotos** en Informes. (13539)
- La pantalla de vista previa de los fragmentos de código está inmovilizada. (14840)
- Aparecen caracteres rotos al crear los fragmentos en coreano. (13489)

### Publicación

- La publicación de AEM Sites falla y provoca errores de ámbito en los archivos que tienen `xref` al fichero DITA que empieza por &quot;HTTP&quot;. (15154)
- En la publicación de PDF nativo, las propiedades de metadatos de mapa DITA no se pueden utilizar para rellenar los metadatos de salida de archivo de PDF. (15159)
- En la publicación de PDF nativos, los atributos personalizados dentro de ajustes preestablecidos de condición no funcionan para la publicación de PDF nativos. (14943)
- No se puede añadir una plantilla personalizada desde el **Salidas** en el Editor. (14846)
- **AEM Sitio web de** el ajuste preestablecido no funciona debido a una ruta de plantilla vacía. (14804)
- AEM La regeneración de sitios falla en los mapas DITA con temas que contienen ecuaciones MathML. (14790)
- En la publicación de PDF nativos, la generación de PDF genera errores al obtener dependencias para `Node.js` publicación. (14445)
- **AEM Sitio web de** no permite la selección de una plantilla fuera del `/content` jerarquía en el editor web. (14260)
- La funcionalidad para publicar como fragmento de contenido no funciona para los archivos enumerados en los resultados de búsqueda. (14090)
- Los componentes de Famidia tienen una ruta codificada de `delegator.jsp`, evitando la superposición de componentes de AEM Sites. (13993)
- La vista etiquetada del reactor de PDF en la salida de publicación del PDF nativo no funciona como se esperaba. (13622)
- En la publicación en PDF nativo, la selección del color de fondo en la **Plantilla** El diseño requiere volver a cargar la página al volver a `None`. (13621)
- AEM La publicación de sitios encuentra un problema al comprometerse con el almacén de datos para mapas grandes con vínculos de igual a igual de ámbito. (13531)
- AEM Se produce un problema al comprometerse con el almacén de datos para un mapa DITA grande con vínculos de igual a igual de ámbito en la publicación de sitios de. (13530)
- Se muestran iconos e información de objeto incorrectos para  **Editar contenido** en la opción **Diseños de página** de las plantillas utilizadas en la publicación nativa del PDF. (13492)
- No se puede activar un sitio mediante las guías del Experience Manager **Tablero de publicación masiva**. (13439)
- En la publicación nativa en PDF, la accesibilidad se ve comprometida, ya que las imágenes del encabezado y del pie de página no muestran texto alternativo. (12829)
- En la salida de AEM Sites, el estilo o los saltos de línea se perdieron para la variable `<lines>` elemento con subelementos.(12542)
- La duplicación del diseño de página en el PDF nativo no funciona sin que se agregue ninguna extensión automáticamente. (12534)
- La localización de las etiquetas de elementos no funciona correctamente en la salida de AEM Sites. (12144)
- Los metadatos personalizados no están disponibles en la salida final. (12116)
- `fmdita rewriter` entra en conflicto con la configuración de reescritura del usuario y provoca la visualización de direcciones URL largas en lugar de los vínculos. (12076)
- Falta **ditaval** en los ajustes preestablecidos de salida del nivel de perfil de carpeta creados mediante la interfaz de usuario del editor web. (11903)
- En el **AEM Sitio web de**  ajuste preestablecido, la opción para **Generar un PDF independiente para cada tema** no funciona. (11555)
- La publicación en PDF nativo no es compatible con la conversión del espacio de color CMYK. (10754)
- Al actualizar a la versión 4.3.1, se producen algunas excepciones en el nodo PDF nativo. (14492)
- Al generar la salida del PDF con la publicación del PDF nativo, el nombre del archivo se trunca después de un punto. (13620)


### Administración

- La referencia de contenido se interrumpe al copiar y pegar los archivos DITA con vínculos de referencia automática sin GUID. (13540)
- **Filtro de línea base** Los archivos no funcionan con Nombre de archivo en el Editor web. (13486)
- En el Editor Web, la instantánea muestra el título de la versión anterior en lugar de la versión seleccionada del fichero DITA. (13444)
- Desactivar la indexación del mapa DITA principal para obtener un mejor rendimiento puede afectar a la funcionalidad de determinadas funciones.(12213)
- No se crean ajustes preestablecidos de condición para mapas DITA grandes. (10936)
- No se pueden editar los ajustes preestablecidos de las primeras asignaciones de la colección mientras se edita una colección de asignaciones. (10649)
- Etiquetas de la `labels.json` Los archivos aparecen en orden aleatorio en el Editor Web. (10508)
- Las llamadas de línea de base dinámicas utilizan el nombre en lugar del título, lo que provoca el fallo de la API Exportar mapa DITA. (14268)

### Revisión

- El menú contextual del botón secundario no funciona para **Aceptar** o **Rechazar** haga un seguimiento de cambios. (14607)
- Cambiar para cerrar los temas de DITA en la pantalla de revisión no funciona en la versión 4.3.1 de Adobe Experience Manager Guides. (14537)
- Los problemas de simetría se producen en los paneles de revisión en paralelo de las versiones anterior y actual en el Editor Web. (14156)
- La personalización de las plantillas de correo electrónico para el flujo de trabajo de revisión no funciona con la superposición. (13954)
- Los archivos adjuntos coreanos de la pantalla Revisión de las guías del Experience Manager no se pueden seleccionar. (13436)
- El título del mapa se corta en la pantalla de revisión y colaboración, sin opción de ver el título completo. (13012)

### Traducción

- El **Aceptar/Rechazar** aparecen erróneamente botones para la traducción humana aprobada automáticamente. (14318)
- AEM Los problemas de internacionalización (i18n) se producen durante la transformación de archivos DITA que no están en inglés a páginas de. (14286)
- La aprobación automática no funciona a veces y se producen excepciones si se establece un valor incorrecto en **Estado de traducción**. (13607)
- La línea de base exportada desde el panel de traducción produce un error y no se abre en el idioma de destino. (12993)
- El contenido traducido no se puede sincronizar desde proyectos de traducción temporales y el asistente de traducción del editor XML DITA muestra incorrectamente **En curso** estado de los trabajos aprobados. (9938)

## Problema conocido

El Adobe ha identificado el siguiente problema conocido para la versión 4.4.0:

- La versión 1.0 no se muestra en la interfaz de usuario del archivo DITA duplicado.