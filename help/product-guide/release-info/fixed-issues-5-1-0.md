---
title: Notas de versión | Se han corregido problemas en la versión 5.1.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 5.1.0 de Adobe Experience Manager Guides.
source-git-commit: 6c29d5540f48c850416db279b4392b6042c8ca2c
workflow-type: tm+mt
source-wordcount: '1789'
ht-degree: 1%

---

# Se han corregido problemas en la versión 5.1.0 (septiembre de 2025)

Este artículo trata sobre los errores corregidos en varias áreas de la versión 5.1.0 de Adobe Experience Manager Guides.


Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 5.1.0](whats-new-5-1-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 5.1.0](upgrade-instructions-5-1-0.md).


## Creación

- Los archivos **CSS** y **Page layout** de las plantillas nativas de PDF muestran un comportamiento inconsistente de bloqueo de archivos, lo que permite realizar modificaciones incluso cuando los archivos están bloqueados. (GUIDES-26688)
- Al actualizar la página después de agregar botones personalizados al panel izquierdo, se crean pestañas duplicadas. (GUIDES-30899)
- Cuando el contenido XML que contiene corchetes angulares (como &lt;/ o />) se agrega dentro de un elemento `code block` en un tema, el elemento de bloque de código aparece en blanco en el resultado final. (GUIDES-31007)
- Los valores de las variables globales `canCheckIn` y `canCheckOut` no se configuran correctamente cuando se desprotege y protege un archivo desde la barra de herramientas del Editor.(GUIDES-29890)
- Cuando se selecciona un mapa DITA en la vista Mapa, el recuento de selecciones no se muestra correctamente al principio porque los nodos secundarios del mapa no están seleccionados. El recuento de selección correcto y la inclusión de todos los nodos secundarios solo se reflejan en la selección posterior. (GUIDES-25663)
- Los archivos Markdown no se recuperan cuando se buscan en el panel Repositorio utilizando el filtro **DITA topic**. Además, **Buscar y reemplazar** no funciona con archivos Markdown ni con contenido relacionado. (GUIDES-27133)
- No se puede personalizar el menú desplegable **Menú** de la barra de herramientas del Editor usando el marco de trabajo de la extensión. Como resultado, no se puede ocultar ni mostrar ningún botón existente ni agregar botones nuevos en la lista desplegable Menú. (GUIDES-28748)
- Cuando se agrega un comentario XML dentro de un elemento en la vista de Source, los espacios iniciales y finales alrededor del comentario se pierden al cambiar de vista. (GUIDES-29781)
- Las opciones multimedia no funcionan cuando están presentes dentro del icono de puntos suspensivos (el menú **Más**) en la barra de herramientas. (GUIDES-29583)
- Al crear un nuevo tema a través de la interfaz de usuario o del editor de Assets, el tema no se abre automáticamente en el editor si la configuración de `xmleditor.uniquefilenames` está establecida en true en `XMLEditorConfig`. (GUIDES-28171)
- Los espacios añadidos dentro de una ecuación de MathML en la vista de Source no se conservan al cambiar a las vistas del editor. (GUIDES-26111)
- Si no se cierran las conexiones de sesión JCR al actualizar o crear temas, se producen pérdidas de memoria y tiempo de inactividad del servicio. (GUIDES-26282)
- Al arrastrar las columnas, su anchura cambia de valores de porcentaje a valores de píxel, lo que da como resultado tablas distorsionadas o mal alineadas.(GUIDES-23128)
- Cuando el contenido se pega en `code block` o cuando se agregan espacios en `code block` y se cambia la vista, se pierde el espaciado. (GUIDES-27478)
- Al agregar un mapa a `bookmap`, se almacena en `fmditatopicrefs` en lugar de en `fmditamaprefs`. (GUIDES-25480)
- El cuadro de diálogo **Insertar imagen** no se representa correctamente en una pantalla de alta resolución o con zoom ampliado, lo que hace que desaparezcan el título de la figura y los campos de texto alternativo. (GUIDES-26459)
- El cuadro de inserción de caracteres especiales del Editor no se carga para la configuración regional en alemán. (GUIDES-24537)
- Los comentarios y etiquetas añadidos al guardar una nueva versión de un archivo DITAVAL no se guardan en el Historial de versiones con la nueva versión. (GUIDES-24076)
- Las referencias salientes y entrantes bajo **Propiedades del archivo** en el panel derecho no se actualizan correctamente al cambiar entre archivos de asignación. Este problema se produce específicamente cuando los archivos de mapa contienen un gran número de referencias. (GUIDES-23344)
- El filtro Repositorio no conserva el orden de los filtros personalizados definidos en `ui_config.json`. (GUIDES-21193)
- Al eliminar varias líneas de texto en un elemento `codeblock`, se crea un espacio vacío que no se puede eliminar de la vista Autor. (GUIDES-20672)
- No se pueden generar nuevos identificadores para elementos cuando dichos elementos se agregan mediante fragmentos o se crean mediante plantillas, incluso cuando la opción **Generar automáticamente ID** está habilitada en `XMLEditorConfig`. (GUIDES-21734)
- Al crear un nuevo recurso DITA a partir de plantillas DITA, se copian las propiedades de replicación de las plantillas DITA correspondientes. (GUIDES-25145)
- No se puede acceder a las propiedades del archivo desde el panel del repositorio si el nombre de la carpeta principal incluye el carácter &quot;&amp;&quot;. (GUIDES-25762)
- El cierre de un archivo de tema permite guardarlo como una nueva versión, incluso cuando el tema está bloqueado. Este problema ocurre específicamente cuando la opción **Pedir nueva versión al cerrar** está habilitada en `XMLEditorConfig`. (GUIDES-23875)
- La anchura máxima actual del panel del repositorio oculta los títulos de temas y mapas cuando la jerarquía de contenido está profundamente anidada. (GUIDES-27751)

## Administración de recursos

- Copiar una carpeta con un gran número de recursos desde la interfaz de usuario de Assets lleva a un tiempo de espera de API. La operación sigue ejecutándose en el servidor y se completa después de un tiempo, pero no se muestra ningún mensaje de éxito o error ni notificación en la interfaz de usuario. (GUIDES-30900)
- La operación de copiar y pegar realizada en una carpeta de la interfaz de usuario de Assets falla debido a errores posteriores al procesamiento. (GUIDES-30840)
- La operación de copiar y pegar falla en las carpetas que contienen recursos compuestos (recursos con subrecursos) en la interfaz de usuario de Assets. (GUIDES-28107)
- Las carpetas con un gran número de recursos no se cargan correctamente en el repositorio. (GUIDES-32500)
- Los nombres de los nodos de carpeta se muestran incorrectamente en lugar de los títulos de las carpetas en el Editor. (GUIDES-32402)
- Se produce un error al cargar recursos con caracteres no admitidos o prohibidos en los nombres de archivo. (GUIDES-28845)
- Al abrir un tema en la vista Autor después de actualizar el explorador, las etiquetas aplicadas anteriormente en el panel Propiedades del archivo no se conservan y la adición de nuevas etiquetas sobrescribe las existentes, especialmente cuando hay un gran número de etiquetas disponibles para su selección. (GUIDES-29078)
- Al generar un informe de metadatos para un mapa DITA que contiene un gran número de recursos, el botón **Administrar** deja de responder o muestra una respuesta retrasada. (GUIDES-28443)
- El estado del documento de la copia de trabajo de un tema se muestra con todas las versiones de ese tema en la IU Traducción y Línea de base. (GUIDES-20674)

## Revisión

- Los intentos de crear tareas de revisión a través del flujo de trabajo de AEM fallan de forma consistente porque no se crea el nodo de revisión. (GUIDES-28214)
- La vista de documento de la IU de revisión no ajusta el contenido para algunos tamaños de pantalla, lo que requiere que los usuarios se desplacen horizontalmente para ver el contenido completo. (GUIDES-25292)
- Al actualizar los detalles de una tarea de revisión en el panel Revisar, no se confirma si la actualización se ha realizado correctamente o no. (GUIDES-8051)

## Traducción

- Las traducciones enviadas a través de Experience Manager Guides no incluyen los recursos adjuntos, lo que provoca que el botón **Iniciar** del trabajo de traducción no esté disponible para los usuarios. (GUIDES-28237)

## Publicación

- En la salida nativa de PDF, la lista de índices (LOI) aparece en un orden no alfabético y los términos de índice anidados no se agrupan correctamente, lo que dificulta la navegación por el índice. (GUIDES-29090)
- La lista desplegable **Plantilla de página de mapa** y **Plantilla de página de tema** de la página de salida de la asignación de componentes de AEM Sites aparece en blanco cuando la ruta de destino contiene una variable con dos puntos. (GUIDES-28119)
- Cuando un mapa DITA contiene diferentes tipos de referencias temáticas, como Concepto, Referencia o Tarea, y se combina con el atributo `chunk=to-content` para generar una salida de página única en AEM Sites con asignación de componentes, el contenido no se publica correctamente debido a errores de publicación. (GUIDES-28118)
- Al publicar un mapa DITA con el atributo `chunk=to-content`, se crean nodos JCR duplicados en la nueva salida de AEM Sites, lo que da como resultado una estructura de contenido redundante en AEM Sites. (GUIDES-28104)
- Al publicar un mapa DITA con la nueva salida de AEM Sites, si un tema tiene el atributo `chunk =to-content` y la salida está configurada para utilizar títulos de temas como nombres de página, el nombre de página generado muestra incorrectamente la palabra **fragmento** en lugar de conservar el nombre de tema original. (GUIDES-28102)
- La propiedad `cq:template` establecida en la plantilla de tema de AEM Guides para la nueva publicación de AEM Sites muestra un valor incorrecto, que afecta a la estructura de la plantilla y a la representación de contenido. (GUIDES-27789)
- La publicación nativa de PDF continúa indefinidamente si el contenido DITA tiene un vínculo web sin tener el ámbito `external`. (GUIDES-26434)
- La publicación de PDF nativos y sitios de AEM se detiene y se pone en cola cuando hay errores en el contenido. (GUIDES-26516)
- Al generar páginas de sitio de AEM con títulos que incluyen varias palabras separadas por espacios, el título del mapa muestra guiones en lugar de espacios. (GUIDES-27903)
- Para PDF nativo, no se está resolviendo un nombre de propiedad de metadatos no válido y se muestra como `unresolved property name` en **propiedades de documento**. (GUIDES-25680)
- El texto multilínea dentro de `codeblock` causa problemas de desbordamiento de texto durante la generación de PDF. (GUIDES-15541)
- Al añadir mapas a la colección de mapas, se muestran recursos que no sean mapas (le gustan los temas, etc.) y los idiomas de mapa traducidos tampoco se ordenan correctamente.(GUIDES-25085)
- En la salida heredada de AEM Sites, los vínculos de sección dentro de los temas anidados de un mapa no se resuelven correctamente cuando se establecen manualmente en el modo Source o el contenido se importa desde un origen externo. En lugar de ir a la sección deseada, se redirige al tema principal que contiene el tema anidado. (GUIDES-26103)
- Si falta el atributo `scope=external` en los vínculos externos de un tema DITA, la publicación de HTML5 falla sin indicar los archivos en los que falta este atributo en los registros de errores. (GUIDES-25969)
- No se pueden incrustar vínculos de vídeo en el PDF nativo aunque la opción **Incrustar archivos multimedia** esté habilitada en el ajuste preestablecido de PDF. (GUIDES-9989)
- No se pueden pasar las propiedades de metadatos para asignar las páginas de aterrizaje generadas mediante la nueva publicación de AEM Sites. (GUIDES-27288)

## Línea de base

- Al copiar un mapa DITA desde la interfaz de usuario de Assets, también se copia la línea de base adjunta al nuevo mapa. (GUIDES-11227)
- Al crear una nueva línea base con un gran número de etiquetas, se evita que se recuperen todas las etiquetas. (GUIDES-16232)

## Página de inicio

- La página de inicio queda en blanco cuando uno de los archivos enumerados en el widget **Archivos recientes** se basa en una plantilla cuya plantilla de origen no incluye una miniatura. (GUIDES-31506)

## Plataforma

- Los problemas de rendimiento como tiempos de carga más largos y tiempos de espera intermitentes se observan al trabajar con colecciones grandes. (GUIDES-29065, GUIDES-28793)
- Vulnerabilidades asociadas con la biblioteca de Guava en desuso que se utiliza en los componentes de AEM Guides cargados en Experience Manager Guides.(GUIDES-27402)

## Problemas conocidos

Adobe ha identificado los siguientes problemas conocidos para la versión 5.1.0:


- El comentario más reciente en el nivel de tarea se muestra en la notificación por correo electrónico al iniciador de la tarea si el revisor la completa sin agregar ningún comentario. (GUIDES-33590)
- En el cuadro de diálogo Combinar, la lista desplegable muestra incorrectamente el contenido principal en lugar de mostrar las versiones disponibles del tema seleccionado. (GUIDES-30820)
- Al cambiar entre ajustes preestablecidos que utilizan la misma Línea base, se desactiva el botón Guardar para el ajuste preestablecido actual. (GUIDES-28025)
- Se inserta automáticamente una línea vacía al pegar el nuevo contenido en una nueva línea dentro de un elemento de bloque de código.(GUIDES-27842)
- Un tema de un mapa DITA no se puede publicar en la salida de AEM Sites cuando se utiliza como keydef y topicref dentro de sus submapas. (GUIDES-22269)
- En el panel Propiedades de contenido, el campo Atributos se cierra automáticamente cuando intenta actualizar una referencia desde el cuadro de diálogo Actualizar vínculo, lo que impide que se actualice el vínculo. (GUIDES-17767)