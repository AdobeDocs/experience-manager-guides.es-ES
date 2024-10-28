---
title: Notas de versión | Se han corregido problemas en la versión 4.6.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 4.6.0 de Adobe Experience Manager Guides
role: Leader
source-git-commit: 9ffe068bbcdc0fe32e3dbf56a48171d241825e5a
workflow-type: tm+mt
source-wordcount: '1996'
ht-degree: 0%

---


# Se han corregido problemas en la versión 4.6.0 (septiembre de 2024)


Este artículo cubre los errores corregidos en varias áreas de la versión 4.6.0 de Adobe Experience Manager Guides.


Para obtener más información acerca de las nuevas características y mejoras, vea [Novedades de la versión 4.6.0](whats-new-4-6.md).

Obtenga información acerca de [instrucciones de actualización para la versión 4.6.0](../release-info/upgrade-instructions-4-6-0.md).

## Creación

- La opción **Buscar** no funciona en la vista de **Source**. (18610)
- Los iconos **Desproteger** y **Proteger** aparecen juntos cuando `autocheckout` está configurado en xmleditor. (18088)
- Los mapas DITA grandes se cargan lentamente y tardan un tiempo en cambiar a la vista **Diseño**.  (17590)
- Los errores de ID de imagen duplicados en los temas restringen al usuario de guardar o crear un tema. (17528)
- La operación de copiar y pegar de temas que superan los 15 KB falla con un error inesperado. (17171)
- La funcionalidad para cambiar el estado del documento desde el panel **Propiedades del archivo** no funciona correctamente y cambia al estado *Borrador*. (17088)
- Al cambiar la configuración del editor XML mediante un perfil de carpeta personalizado, `ui_config.json` se actualiza con un archivo incorrecto. (17011)
- Los paneles de contenido reutilizables no muestran elementos cuando las **preferencias de usuario** están configuradas para ver archivos por **Filename**. (16896)
- Los subelementos dentro del elemento de título de tabla no se pueden procesar en el modo **Preview** de Experience Manager Guides. (16691)
- **Los caracteres especiales** escritos con caracteres de escape se eliminan del tema después de ser cargados en Experience Manager Guides. (16495)
- Los vídeos de Vimeo no admiten la funcionalidad de pantalla completa en Experience Manager Guides. (15996)
- Al pegar secuencias de texto con formato previo largas en elementos `<pre>` o `<codeblock>`, se trunca el texto. (15859)
- La eliminación de contenido se produce debido a GUID duplicados cuando las plantillas se instalan mediante código pero no se procesan. (15858)
- Experience Manager Guides no puede adherirse al atributo **Rol de procesamiento** en el modo **Vista previa**. (15787)
- El editor elimina intermitentemente el texto adicional que hay más allá del área seleccionada. (15708)
- Imposibilidad de copiar y pegar tablas grandes de documentos o HTML de Word en el Editor Web. (15369)
- Falta de API o eventos para capturar la adición de atributos a un elemento o la inserción de un nuevo elemento. (15351)
- No se puede agregar la etiqueta `<data>` dentro de la etiqueta `<ol>` en el editor web. (15161)
- El componente de marcador de posición **Element** bloquea la interfaz de usuario. (14957)
- Web Editor no puede cargar archivos .pptx. (14837)
- Al buscar un texto en el Editor Web, el cursor vuelve a la primera aparición del texto buscado, al pulsar la tecla Intro. (14820)
- El guardado automático causa varios problemas, reposiciona el cursor y requiere clics manuales en el documento. (14253)
- Al presionar la tecla **Enter** en una celda de tabla dentro del texto, el párrafo no se divide como se esperaba. (14251)
- Los archivos grandes no se cargan en el Editor Web y hacen que el explorador se congele. (13227)
- Los resultados de la búsqueda se deshabilitaron después de abrir un archivo encontrado a través de **Buscar y reemplazar** global. (12142)
- En la vista de origen, `</conbody>` se inserta ocasionalmente en ubicaciones incorrectas. (11305)
- La ruta de acceso del componente `/libs/fmdita/components/versions` está codificada y los usuarios no pueden superponerla. (8779)
- `<conref>` para un tema al que se hace referencia en un mapa DITA no se refleja en la vista previa en el editor. (17794)
- La Guía DITA del Experience Manager no puede almacenar en déclencheur la función Guardar después de utilizar la función de sangría automática. (16482)
- La función de información de objeto no puede actualizar el campo Source en el Editor XML. (15847)
- La característica **Compartir vínculo UUID** no funciona para las imágenes de Adobe Experience Manager. (15598)
- En la vista **Autor**, se produce un problema de copiar y pegar al utilizar espacios sin saltos y provoca el desbordamiento del texto. (15541)
- Se producen problemas de superposición de texto en las etiquetas `<reltable>` y `<fig>`. (15238)
- Los problemas de parpadeo se producen en el panel **Atributos**. (15237)
- En el elemento `<othermeta>` dentro de `<topicmeta>`, al agregar `<conref>` a otro mapa DITA, el identificador de mapa también se anexa junto con el identificador del elemento. (15226)
- El cursor salta entre los elementos del bloque al eliminar un carácter o una palabra dentro del contenido. (15224)
- El mensaje de error Archivo desprotegido por &quot;&quot; se muestra incorrectamente cuando los archivos de edición se mueven desde otra pestaña, cuando los tokens caducan o cuando el usuario ha cerrado la sesión. (15223)
- `<conref>` no se puede actualizar desde el panel **Atributos** al realizar cambios. (15209)
- Se selecciona toda la celda al seleccionar una imagen dentro de una celda de tabla. (15188)
- El panel **Atributos** no se muestra en la vista Source del editor web. (14387)
- `<Topicref>` agregado con `<keyref>` no se muestra en el PDF nativo. (11974)
- Los espacios no deseados y de no separación se añaden al editar al final de una etiqueta en el editor web. (11786)
- El contenido se elimina al corregir los errores ortográficos en los archivos DITA. (11610)
- Al abrir un tema o mapa DITA en una nueva pestaña para su edición, se bloquea la navegación de la selección en la IU de Assets. (4992)
- Al eliminar los nodos de revisión, se interrumpe la capacidad de abrir y ver comentarios en Adobe Experience Manager Guides. (15366)
- La versión DITA muestra incorrectamente el nombre de usuario en la interfaz de usuario de Assets. (17580)
- El elemento `<title>` se agrega automáticamente cuando el elemento `<fig>` se inserta como un fragmento. (18562)
- Se producen problemas al cargar un gran número de archivos con conjuntos de datos densos en Experience Manager Guides.(17008)
- El editor web no muestra la palabra clave correcta de forma predeterminada, especialmente si la palabra clave se define de forma diferente en las asignaciones secundarias. (14748)
- El **estado del documento** no se muestra al editar las propiedades de más de 50 archivos de forma masiva desde la vista Mapa del Editor Web. (14574)
- El comportamiento del botón Cerrar no es coherente al utilizar la funcionalidad Guardar automáticamente. (10996)
- Los problemas de validación se producen en los elementos de MathML al insertar cualquier elemento nuevo o modificar ecuaciones. (10624)
- La funcionalidad Control de cambios no funciona con texto que comience con caracteres coreanos. (14538)
- Las imágenes vinculadas de los temas no aparecen en la línea de base después de la creación de la versión. (16931)

## Publicación

- La referencia cruzada a la clave no se está resolviendo en la salida del PDF nativo. (18087)
- El error **duplicate_value** se produce de forma intermitente al volver a publicar un artículo existente en Salesforce. (17932)
- La validación de la conexión de Salesforce falla con la URL de Lightning. (17797)
- Al seleccionar la opción **Usar metadatos agregados en topicmeta**, las propiedades de los metadatos no se propagan en las propiedades del documento de la salida del PDF nativo.(17283)
- El filtrado de condiciones en la salida del PDF nativo no funciona como se esperaba en comparación con DITA-OT. (17095)
- La tabla de contenido no respeta las etiquetas `<sub>` o `<sup>` en la salida del PDF nativo. (17028)
- La vinculación entre mapas cruzados no puede mostrar todas las asignaciones principales en la configuración del contexto de publicación de un vínculo que tiene `scope="peer"` (16700)
- AEM La generación de sitios y la API de publicación incremental no funcionan según lo esperado. (16666)
- AEM La generación de salida del sitio falla cuando la opción **Eliminar sitio huérfano** está habilitada. (15896)
- Los atributos antiguos se conservan en los **ajustes preestablecidos de condición** al agregar o quitar atributos nuevos o existentes. (15890)
- En la salida JSON, los metadatos del tema o del mapa DITA no se pueden propagar a los archivos de salida JSON. (15713)
- El contenido de idioma RTL no se gestiona correctamente en la salida de publicación del PDF nativo. (15709)
- La publicación del PDF nativo falla cuando se cambia el nombre del ajuste preestablecido. (15662)
- AEM La propiedad **sourcePath** no es correcta en la salida publicada del sitio de la. (15502)
- La selección y personalización de las variables de idioma no funcionan correctamente en el ajuste preestablecido de salida del PDF nativo. (15399)
- La generación nativa de PDF falla al utilizar una hoja de estilo o una plantilla de diseño grandes. (15344)
- El contenido no se representa correctamente en la salida publicada si `<conref>` se utiliza con una ruta de acceso absoluta. (15222)
- El acortamiento de URL de AEM Sites no funciona debido a conflictos entre `fmdita rewriter` y `ResourceResolver`. (14793)
- La generación del PDF nativo falla con un error relacionado con la obtención de dependencias para Node.js. (14445)
- Los atributos **processing-role=&quot;resource-only&quot;**, **search=&quot;no&quot;** y **chunk=&quot;to-content&quot;** aparecen indistintamente en la salida de AEM Sites. (14442)
- `<Conref>` no se puede resolver en el modo `Preview` del editor web y en la salida del PDF nativo. (17827)
- En el PDF nativo, los temas DITA anidados se muestran incorrectamente en la tabla de contenido (TOC). (16742)
- Las miniaturas generadas a partir de **Dynamic Media** para archivos de vídeo no pueden persistir en la salida publicada. (15656)
- El PDF al que se hace referencia no se activa desde el **tablero de Publish en masa** durante la activación en lote del contenido publicado. (17793)
- Si una carpeta que contiene asignaciones 2k se establece en la ruta de carpeta dentro de cualquier perfil de carpeta, los cambios aplicados al ajuste preestablecido de salida fallan. (14852)
- La regeneración del tema falla debido al tema de regeneración OOTB o a un error incremental de la API de publicación. (18452)
- El ajuste preestablecido de condición no recupera atributos actualizados después de actualizar Experience Manager Guides. (18174)
- Las referencias de contenido no se resuelven correctamente para la salida del PDF nativo si el fichero que contiene las definiciones de claves no se encuentra en la misma carpeta que el mapa DITA. (15062)
- La activación masiva del contenido publicado no funciona para mapas localizados. (17638)


## Administración


- La conversión de InDesign a DITA tiene una ruta de configuración codificada para que no se seleccionen los archivos de configuración personalizados. (16891)
- Las **soluciones de recursos** sin cerrar causan un aumento en el recuento de sesiones y `PathNotFoundException` errores tras la versión 4.3.1 de Experience Manager Guides. (15604)
- Error al instalar los paquetes de guías en repositorios grandes. (15160)
- La creación de una línea base mediante la API de Java no funciona con Experience Manager Guides. (14787)
- La API `/bin/fmdita/import` permanece atascada en una solicitud pendiente indefinidamente cuando los recursos que se cargan superan los 500 MB. (14743)
- La edición de una instantánea existente y la selección de una versión específica déclencheur errores de aplicación. (14451)
- La ejecución del script posterior al proceso falla debido a la excepción **FileNotFoundException**. (16517)
- Los títulos dinámicos con `<conkeyref>` no aparecen en la lista de temas de informes. (16967)
- Los recuentos inexactos de la **lista de temas** se producen en la interfaz de usuario de informes de Experience Manager Guides debido a las propiedades sin aplicar parches al copiar recursos DITA. (15529)
- Los temas que contienen referencias externas con %20 en la dirección URL muestran referencias a archivos rotos. (15347)
- Las propiedades fmditaMaprefs y fmditakeydefrefs muestran rutas relativas, a pesar de que establecen rutas absolutas para el mapa y los temas DITA. (18353)
- La ruta para la funcionalidad Superposición está codificada para el archivo en coreano y no está seleccionada correctamente. (17089)
- La hora predeterminada en la creación de Línea base en el Editor Web se muestra como 00:00 en lugar de la hora actual. (15215)

## Revisión

- La obtención de la lista de usuarios al crear una tarea de revisión falla si el recuento de usuarios supera los 25. (17329)
- Los temas de la revisión no aparecen en el orden correcto. (16319)
- En el Editor web, el panel Revisar se carga lentamente. (14680)
- Los revisores no pueden agregar, resaltar ni tachar espacios al realizar una revisión de documento en Experience Manager Guides. (14752)
- Cuando un usuario actualiza una tarea de revisión, no todos los revisores asignados reciben una notificación sobre la actualización. (9496)

## Traducción

- Las referencias de los recursos traducidos no se actualizan. (18086)
- No se pueden crear proyectos XLIFF con traducción humana. (16964)
- El título con `<conref>` o `<conkeyref>` no se resuelve en los paneles Línea de base y Traducción del Editor web. (16961, 16879)
- Los proyectos de traducción no agregan nuevos trabajos de idioma a Adobe Experience Manager 6.5 SP18 con la versión 4.3.1 de Experience Manager Guides. (15398)
- **Aceptar traducción** no puede completar la traducción de los archivos temporales. (14665)
- Añadir un tema actualizado en un proyecto de traducción activo resulta en un tema duplicado y el proceso falla. (7688)
- Las referencias no se filtran correctamente como Directas o Indirectas al traducirlas a varios idiomas. (17891)
- La traducción basada en XLIFF falla con un error para usuarios &quot;no administradores&quot;.(17296)
- El título de los archivos traducidos vuelve al inglés después de la segunda traducción, aunque el contenido se haya traducido. (15200)
- Al seleccionar un proyecto de traducción con el **estado de traducción** como **En curso**, se abre una página incorrecta. (13248)
- Los proyectos de traducción creados al seleccionar la opción **Crear estructura solamente** no tienen UUID asignados. (18980)


## Problemas conocidos

El Adobe ha identificado los siguientes problemas conocidos para la versión 4.6.0:
- Al abrir un ajuste preestablecido de **AEM Sites** (no heredado), se marca el tema como sucio.
- El panel seleccionado no se retiene al actualizar el explorador desde la ficha **Salida**.
- No se pueden arrastrar y soltar temas entre dos `topicrefs` en la vista **Autor**.
- El filtrado de condición aplicado en el ajuste preestablecido no se está aplicando mediante **Descargar como PDF**.
- La generación de un solo tema desde el panel de asignación genera todos los temas seleccionados en el ajuste preestablecido **AEM Sites** (no heredado).
- La referencia del tema aparece rota en la interfaz de usuario cuando se inserta desde la barra de herramientas superior del mapa DITA.
- La generación del PDF nativo falla para un mapa DITA si faltan referencias.
- Una vez que el estado del documento de un tema se haya actualizado a **Listo**, el icono **Iniciar una nueva versión** solo está disponible en el modo **Vista previa** del tema.
- Al seleccionar un archivo DITA en la interfaz de usuario de recursos, aparece la opción **Abrir en el FrameMaker**, aunque esté deshabilitada en la configuración.




