---
title: Notas de versión | Se han corregido problemas en la versión 2024.10.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2024.10.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 64c5318a064d28a42f3f11d2fe5b7d8548e341d8
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 2%

---

# Se han corregido problemas en la versión 2024.10.0

Este artículo describe los errores corregidos en varias áreas de la versión 2024.10.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 2024.10.0](whats-new-2024-10-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2024.10.0](upgrade-instructions-2024-10-0.md).


## Creación

- La opción **Buscar** no funciona en la vista de **Source**. (18610)
- El elemento `<title>` se agrega automáticamente cuando el elemento `<fig>` se inserta como un fragmento. (18562)
- La regeneración del tema falla debido al tema de regeneración OOTB o a un error incremental de la API de publicación. (18452)
- La instancia de Experience Manager Guides se vuelve inestable y los registros de errores aumentan de tamaño hasta 30-40 GB después de acceder a la interfaz de usuario de Assets. (18414)
- Los iconos **Desproteger** y **Proteger** aparecen juntos cuando `autocheckout` está configurado en xmleditor. (18088)
- La función de copiar y pegar imágenes de la vista Autor no funciona en la versión 2024.06.0 de Adobe Experience Manager Guides as a Cloud Service.(18062)
- `<conref>` para un tema al que se hace referencia en un mapa DITA no se refleja en la vista previa en el editor. (17794)
- Los mapas DITA grandes se cargan lentamente y tardan un tiempo en cambiar a la vista **Diseño**. (17590)
- La versión DITA muestra incorrectamente el nombre de usuario en la interfaz de usuario de Assets. (17580)
- Los errores de ID de imagen duplicados en los temas restringen al usuario de guardar o crear un tema. (17528)
- Se producen problemas al cargar un gran número de archivos con conjuntos de datos densos en Experience Manager Guides.(17008)
- Se producen errores intermitentes con la funcionalidad de renderización del PDF en Experience Manager Guides as a Cloud Service. (16966)
- Al crear un mapa DITA basado en una plantilla, el flujo de trabajo OOTB DXML causa interrupciones en el proceso y conduce a 503 errores no utilizables. (16529)
- **Los caracteres especiales** escritos con caracteres de escape se eliminan del tema después de ser cargados en Experience Manager Guides. (16495)
- El mensaje de error Archivo desprotegido por &quot;&quot; se muestra incorrectamente cuando los archivos de edición se mueven desde otra pestaña, cuando los tokens caducan o cuando el usuario ha cerrado la sesión. (15223)
- Los archivos grandes no se cargan en el Editor Web y hacen que el explorador se congele. (13227)
- `<Topicref>` agregado con `<keyref>` no se muestra en el PDF nativo. (11974)
- La ruta de acceso del componente `/libs/fmdita/components/versions` está codificada y los usuarios no pueden superponerla. (8779)
- Al abrir un tema o mapa DITA en una nueva pestaña para su edición, se bloquea la navegación de la selección en la IU de Assets. (4992)
- Déclencheur Al descargar un mapa DITA con archivos de vídeo de gran tamaño, se produce un error de memoria insuficiente en los registros y se produce un error en la interfaz de usuario. (18884)
- Al insertar una ecuación de MathML que contiene el símbolo &quot;&lt;&quot;, se genera un error **Carácter no válido**. (18742)
- La generación incorrecta de UUID durante el proceso de ingesta de contenido provoca referencias de submapa rotas en el mapa introducido. (18308)
- En algunos casos, se observan retrasos en el procesamiento de un nuevo tema DITA cuando se crea desde el editor web. (16836)
- La búsqueda de archivos en el **Repositorio** dentro del Editor web tarda demasiado y a veces no puede cargar los resultados. (16837)

## Publicación

- La referencia cruzada a la clave no se está resolviendo en la salida del PDF nativo. (18087)
- El error **duplicate_value** se produce de forma intermitente al volver a publicar un artículo existente en Salesforce. (17932)
- El estilo y el formato de contenido de las plantillas de cliente cambian automáticamente cuando el diseño incluye campos de metadatos, lo que provoca un formato incorrecto en los PDF publicados. (17900)
- La validación de la conexión de Salesforce falla con la URL de Lightning. (17797)
- El PDF al que se hace referencia no se activa desde el **tablero de Publish en masa** durante la activación en lote del contenido publicado. (17793)
- La activación masiva del contenido publicado no funciona para mapas localizados. (17638)
- Al seleccionar la opción **Usar metadatos agregados en topicmeta**, las propiedades de los metadatos no se propagan en las propiedades del documento de la salida del PDF nativo. (17283)
- El filtrado de condiciones en la salida del PDF nativo no funciona como se esperaba en comparación con DITA-OT. (17095)
- La tabla de contenido no respeta las etiquetas `<sub>` o `<sup>` en la salida del PDF nativo. (17028)
- AEM La generación de sitios y la API de publicación incremental no funcionan según lo esperado. (16666)
- La generación del PDF nativo falla con un error relacionado con la obtención de dependencias para Node.js. (14445)
- `<Conref>` no se puede resolver en el modo `Preview` del editor web y en la salida del PDF nativo. (17827)
- Las referencias de contenido no se resuelven correctamente para la salida del PDF nativo si el fichero que contiene las definiciones de claves no se encuentra en la misma carpeta que el mapa DITA. (15062)
- Cuando un mapa DITA contiene niveles de encabezado de hasta 7 o más, el encabezado de nivel 7 se trata incorrectamente como un encabezado de nivel 1 en la salida del PDF nativo. (19698)
- Cuando se ajusta un fragmento de contenido (texto) dentro de un elemento, los espacios antes y después del texto no se muestran en los formatos de previsualización o salida. (19308)
- Los flujos de trabajo de generación de publicaciones activados manualmente fallan debido a una EXCEPCIÓN DE PUNTERO NULO en el flujo de trabajo, lo que provoca que el contenido se cargue 11 veces. (18880)
- **El panel de Publish en lotes** se muestra en blanco para las asignaciones que aún se encuentran en proceso de traducción. (19352)


## Administración

- La ruta para la funcionalidad Superposición está codificada para el archivo en coreano y no está seleccionada correctamente. (17089)
- Los cambios/personalizaciones realizados en el cuadro de diálogo **Guardar versión** no se reflejan al usar el marco de trabajo de extensión de guías. (17828)
- La conversión de InDesign a DITA tiene una ruta de configuración codificada para que no se seleccionen los archivos de configuración personalizados. (16891)
- Las referencias/recursos completos no se descargan cuando se descarga un mapa DITA que contiene dependencias/referencias grandes mediante Línea base. (19099)


### Revisión

- La obtención de la lista de usuarios al crear una tarea de revisión falla si el recuento de usuarios supera los 25. (17329)
- Si un tema de tarea contiene la etiqueta `<cmd>` en uno o más pasos, el panel de revisión muestra el atributo `importance` como prefijo en todos los pasos que contienen la etiqueta. (19699)

## Traducción

- Las referencias de los recursos traducidos no se actualizan. (18086)
- Las referencias no se filtran correctamente como Directas o Indirectas al traducirlas a varios idiomas. (17891)
- No se pueden crear proyectos XLIFF con traducción humana. (16964)
- Añadir un tema actualizado en un proyecto de traducción activo resulta en un tema duplicado y el proceso falla. (7688)
- Los proyectos de traducción creados al seleccionar la opción **Crear estructura solamente** no tienen UUID asignados. (18980)
- Al seleccionar un proyecto de traducción con el **estado de traducción** como **En curso**, se abre una página incorrecta. (13248)
- El título de `<conref>` no se resuelve en los paneles Línea de base y Traducción del Editor web. (16961)

## Problemas conocidos

- Al abrir un ajuste preestablecido de AEM Sites (no heredado), se marca el tema como sucio.
- El panel seleccionado no se retiene al actualizar el explorador desde la pestaña Salida.
- No se puede arrastrar y soltar el tema entre dos referencias de tema en la vista **Autor**.
- El filtrado de condición aplicado en el ajuste preestablecido no se está aplicando mediante **Descargar como PDF**.
- La generación de un solo tema desde el panel Asignación genera todos los temas seleccionados en el ajuste preestablecido de AEM Sites (no heredado).
- La referencia del tema aparece rota en la interfaz de usuario cuando se inserta desde la barra de herramientas superior del mapa DITA.
- La generación del PDF nativo falla para un mapa DITA si faltan referencias.
- AEM La publicación de un solo tema de un sitio de con condiciones falla en un entorno con microservicios habilitados.
- Una vez que el estado del documento de un tema se haya actualizado a **Listo**, el icono **Iniciar una nueva versión** solo está disponible en el modo **Vista previa** del tema.
