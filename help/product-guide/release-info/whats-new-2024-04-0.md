---
title: Notas de versión | Novedades de la versión 2024.4.0 de Adobe Experience Manager Guides
description: Conozca las funciones nuevas y mejoradas de la versión 2024.4.0 de Adobe Experience Manager Guides as a Cloud Service.
exl-id: e9db535a-5ad5-4ff0-94af-b4425594316a
source-git-commit: 5d99274da8fdacbd255d426fa4913b5773ca45f8
workflow-type: tm+mt
source-wordcount: '1806'
ht-degree: 28%

---

# Novedades de la versión 2024.4.0

Este artículo cubre las funciones nuevas y mejoradas de la versión 2024.4.0 de Adobe Experience Manager Guides.

Para ver la lista de problemas corregidos en esta versión, consulte [Problemas solucionados en la versión 2024.4.0](fixed-issues-2024-04-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2024.4.0](upgrade-instructions-2024-04-0.md).

## Capacidad para traducir contenido a varios idiomas utilizando grupos de idiomas preconfigurados

Ahora, Experience Manager Guides permiten crear grupos de idiomas y traducir fácilmente su contenido a varios idiomas. Esta función le ayuda a organizar y administrar las traducciones según las necesidades de su organización.

Por ejemplo, si tiene que traducir el contenido para algunos países de Europa, puede crear un grupo de idiomas para idiomas europeos como el inglés (EN), francés (FR), alemán (DE), español (ES) e italiano (IT).



![panel de traducción](assets/translation-languages-2404.png){width="300" align="left"}

*Seleccione los grupos de idiomas o idiomas a los que desee traducir los documentos.*

>[!NOTE]
>
>Si falta la carpeta de destino de un idioma o el idioma de destino es el mismo que el de origen, aparecerá atenuado y mostrará un signo de advertencia.

Como administrador, puede crear grupos de idiomas y configurarlos en varios perfiles de carpeta. Como autor, puede ver los grupos de idiomas configurados en el perfil de la carpeta.


En general, la creación de grupos de idiomas mejora la eficacia y la productividad de los proyectos de traducción y, en última instancia, mejora el proceso de localización en varios idiomas.


Aprenda a [traducir documentos desde el editor web](../user-guide/translate-documents-web-editor.md).



## Eliminar o deshabilitar el proyecto de traducción automáticamente después de la traducción

Ahora, como administrador, puede configurar los proyectos de traducción para que se deshabiliten o eliminen automáticamente después de completar la traducción. Esta función le ayuda a utilizar recursos de forma eficaz y a administrar archivos después de completar la traducción.

Al eliminar un proyecto, se quitan permanentemente todos los archivos y carpetas presentes en el proyecto. La eliminación de los proyectos de traducción también le permite liberar el espacio en disco ocupado.

Puede desactivar los proyectos de traducción si desea utilizarlos más adelante.

![](assets/editor-setting-translation.png){width="550" align="left"}


*Configurar grupos de idiomas y la configuración de limpieza para proyectos de traducción.*


Obtenga más información sobre cómo [eliminar o deshabilitar automáticamente el proyecto de traducción](../user-guide/translate-documents-web-editor.md#automatically-delete-or-disable-a-completed-translation-project).


## Activar la salida para los mapas en la colección de activación masiva en la instancia de previsualización

Ahora, además de activar el resultado para la colección de activación masiva en la instancia de publicación, las guías del Experience Manager como Cloud Service proporcionan la función para activarla en la instancia **Preview**.


Esta característica le ayuda a activar el contenido en una instancia de vista previa, lo que le permite comprobar cómo se ve y funciona antes de activarlo en la instancia de **Publish**.


![&#x200B; creó la pestaña del historial de auditoría de la colección de activación masiva](assets/bulk-collection-audit-history.png){width="800" align="left"}

*Vea la información acerca de los resultados del mapa activado en la ficha **Historial de auditoría**.*


Más información sobre [activación en lotes](../user-guide/conf-bulk-activation-publish-map-collection.md).

## Mejoras en los conectores de fuentes de datos

Se han realizado las siguientes mejoras en los conectores de fuente de datos para la versión 2024.4.0:

### Conéctese a las fuentes de datos de los paneles de desarrollo de Salsify, Akeneo y Microsoft Azure (ADO)

Además de los conectores predeterminados existentes, las guías de Experience Manager también proporcionan conectores para fuentes de datos de Salsify, Akeneo y Microsoft Azure DevOps Boards (ADO). Como administrador, puede descargar e instalar estos conectores. A continuación, configure los conectores instalados.

### Copie y pegue la consulta de ejemplo para crear un fragmento de contenido o un tema

Puede copiar y pegar fácilmente una consulta de datos de muestra en el generador para crear un fragmento de código de contenido o un tema. Con esta función, no es necesario recordar la sintaxis ni crear una consulta manualmente. En lugar de escribir manualmente la consulta, puede copiar y pegar una consulta de muestra, editarla y utilizarla para recuperar los datos según sus necesidades.

![cuadro de diálogo para insertar fragmento de código de contenido](assets/insert-content-snippet.png){width="800" align="left"}

*Copie y edite una consulta de muestra para crear el fragmento de código de contenido.*

### Conexión a archivos de datos JSON mediante un conector de archivos


Ahora, como administrador, puede configurar un conector de archivo JSON para utilizar archivos de datos JSON como fuente de datos. Utilice el conector para importar los archivos JSON del equipo o de Adobe Experience Manager Assets. A continuación, como autor, puede crear fragmentos de código de contenido o temas mediante los generadores.

Esta función le ayuda a utilizar los datos almacenados en sus archivos JSON y a reutilizarlos en varios fragmentos de código. El contenido también se actualiza dinámicamente cada vez que se actualizan los archivos JSON.

### Configure varias URL de recursos para un conector para crear fragmentos de contenido o temas

Como administrador, puede configurar varias URL de recursos para algunos conectores, como Cliente REST genérico, Salsify, Akeneo y Tableros de DevOps de Microsoft Azure (ADO).

A continuación, como autor, conéctese con las fuentes de datos para crear fragmentos de código de contenido o temas mediante los generadores. Esta función es práctica, ya que no tiene que crear una fuente de datos para cada URL. Ayuda a recuperar rápidamente datos de cualquiera de los recursos de una fuente de datos concreta en un solo fragmento de contenido o tema.

Ver más detalles acerca de los conectores de origen de datos y cómo [configurar un conector de origen de datos desde la interfaz de usuario](../cs-install-guide/conf-data-source-connector-tools.md).

Obtenga información sobre cómo [utilizar datos de la fuente de datos](../user-guide/web-editor-content-snippet.md).

## Personalice la experiencia del editor web con la nueva interfaz de usuario de preferencias de usuario

El cuadro de diálogo **Preferencias de usuario** del Editor web ahora incluye una nueva pestaña **Aspecto**. Esta nueva pestaña le permite configurar cómodamente las preferencias de aspecto y funcionamiento más comunes en la interfaz del editor web.

Puede configurar para ver los archivos por título o nombre de archivo, y cambiar el tema de la aplicación y la vista de origen. También le ayuda a configurar los ajustes para localizar un archivo abierto en la vista del repositorio y gestionar los espacios de no separación.

![pestaña apariencia de preferencias de usuario](assets/user_preference_editor_appearance.png){width="550" align="left"}

*Personalice el aspecto según sus preferencias.*

Obtenga más información acerca de la descripción de la característica **Preferencias de usuario** en la sección [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Busque un archivo abierto en la vista del repositorio del Editor Web

Seleccione la opción **Buscar siempre archivos en el repositorio** en las **Preferencias de usuario** para buscar rápidamente su archivo en la vista del repositorio. No es necesario que lo busque manualmente.

Al editar, esta función también le ayuda a ver fácilmente la ubicación del archivo dentro de la jerarquía del repositorio.

Para obtener más información, vea [buscar un archivo abierto en la vista del repositorio](../user-guide/web-editor-edit-topics.md#locate-an-open-file-in-the-repository-view).


## Se ha mejorado el control de los espacios de no separación en el Editor web

Experience Manager Guides permite mostrar un indicador de espacio de no separación al editar documentos en el Editor web. También mejora el manejo de los espacios de no separación.
Convierte varios espacios en blanco consecutivos en un único espacio para conservar la vista WYSIWYG del documento en el Editor Web. Esta función también ayuda a mejorar el aspecto general y la profesionalidad del documento.


Para obtener más información, vea las [otras características del editor web](../user-guide/web-editor-other-features.md).




## Desactivar el posprocesamiento para carpetas selectivas en Adobe Experience Manager Assets


Como administrador, ahora puede deshabilitar el posprocesamiento y la generación de UUID para carpetas selectivas en Experience Manager Assets. Esta configuración puede resultar útil, especialmente cuando se tratan muchos recursos o estructuras de carpetas complejas. También permite a varios usuarios cargar rápidamente los recursos de forma simultánea sin interferir entre sí.  

La desactivación del posprocesamiento de una carpeta también afecta a todas sus carpetas secundarias. Sin embargo, Experience Manager Guides ahora ofrece la capacidad de habilitar selectivamente el posprocesamiento para carpetas secundarias individuales dentro de la carpeta ignorada.

Aprenda a [deshabilitar el posprocesamiento para una carpeta](../cs-install-guide/conf-folder-post-processing.md).

## Experiencia modificada para buscar y filtrar archivos en la vista del repositorio

Ahora tiene una mejor experiencia al filtrar archivos. La funcionalidad renovada para filtrar archivos ofrece una mejor forma de buscar y navegar por los archivos sin esfuerzo.


![búsqueda de archivos en la vista del repositorio](assets/repository-filter-search-2404.png){width="300" align="left"}

*Busque los archivos que contienen el texto`general purpose.`*

Disfrute de ventajas como un acceso más rápido a los archivos relevantes y una interfaz de usuario más intuitiva, lo que hace que su experiencia de búsqueda sea más fluida y eficiente.

![filtro de búsqueda rápida &#x200B;](assets/repository-filter-search-quick.png) {width="300" align="left"}

*Utilice los filtros rápidos para buscar archivos DITA y no DITA.*

Obtenga más información sobre la función **Filtrar búsqueda** en la sección [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Lista separada para ver e insertar elementos válidos según su posición

Al editar un documento en el Editor Web, ahora puede ver una lista separada de elementos que son válidos en la ubicación actual y fuera de la ubicación actual. Según sus necesidades, puede elegir un elemento de las siguientes opciones:

* **Elementos válidos en la ubicación actual** que puede insertar en la propia ubicación del cursor actual.
* **Elementos válidos fuera de la ubicación actual** que se pueden insertar después de cualquiera de los elementos primarios del elemento actual dentro de la jerarquía de elementos.

![Cuadro de diálogo Insertar elemento](assets/insert-element-dialog.png){width="300" align="left"}

*Ver las listas separadas de elementos válidos para insertar un elemento en la ubicación actual.*


Esta lista dividida de elementos válidos le ayuda a mantener la estructura de contenido y a seguir los estándares DITA.

Obtenga más información acerca de la característica **Insertar elemento** en la sección [Barra de herramientas secundaria](../user-guide/web-editor-features.md#2051ea0j0y4).


## El tipo de propiedades de contenido aparece como un menú desplegable

Ahora, las Propiedades de contenido **Type** aparecen como un menú desplegable. Puede ver y seleccionar las etiquetas de la jerarquía completa para la etiqueta actual en el menú desplegable.

Este menú desplegable le ayuda a acceder rápidamente a las etiquetas relevantes dentro de la estructura jerárquica.


![menú desplegable de tipo en las propiedades de contenido](assets/content-properties-type.png){width="300" align="left"}

*Seleccione una etiqueta de la jerarquía para la etiqueta actual.*

Obtenga más información acerca de la característica **Propiedades de contenido** en la sección [Panel derecho](../user-guide/web-editor-features.md#id2051eb003yk).



## Se ha mejorado el rendimiento al comprobar archivos de forma masiva desde el Editor de mapas

Experience Manager Guides mejora el rendimiento y la experiencia de la función de registro de archivos en lote desde el Editor de mapas. Esta mejora le ayuda a proteger los archivos de forma masiva con mayor rapidez.
También puede ver el progreso de la operación de protección de los archivos en el cuadro de diálogo **Guardar como nueva versión y desbloquear**. Por último, el mensaje de confirmación aparece una vez finalizada la operación y se registran todos los archivos desprotegidos seleccionados.

![Guardar como nueva versión y desbloquear cuadro de diálogo](./assets/save-version-lock.png){width="300" align="left"}

*Ver la lista y el estado de los archivos comprobados de forma masiva desde el Editor de mapas.*

Aprenda a [trabajar con el Editor de mapas avanzado](../user-guide/map-editor-advanced-map-editor.md)

## Descargar el archivo temporal mientras se genera la salida mediante DITA-OT

AEM También puede descargar los archivos temporales que se generan al publicar la salida del sitio, HTML, Personalizado, JSON o PDF mediante DITA-OT, y que se pueden publicar a través de DITA-OT. Esta función le ayuda a analizar cualquier problema que pueda producirse durante el proceso de generación de resultados y a solucionar problemas de forma eficaz.  
También puede descargar el archivo metadata.xml si ha seleccionado alguna propiedad de metadatos que se haya pasado a la salida generada mediante DITA-OT. 

Para obtener más información acerca de los ajustes preestablecidos, vea [Explicación de los ajustes preestablecidos de salida](../user-guide/generate-output-understand-presets.md).


## Reemplazar las credenciales de JWT de IMS por las credenciales de OAuth de IMS para la publicación basada en Microservice


Las credenciales de la cuenta de servicio (JWT) se han quedado obsoletas y ahora son **OAuth Server-to-Server**. Las aplicaciones que utilizan las credenciales de la cuenta de servicio (JWT) dejarán de funcionar a partir del 1 de enero de 2025. Debe migrar a la nueva credencial antes del 1 de enero de 2025 para garantizar que la aplicación siga funcionando.


El servicio de publicación en la nube para Experience Manager Guides ahora está protegido por la autenticación basada en OAuth de IMS de Adobe. Aprenda a [configurar la publicación basada en microservicios con autenticación OAuth](../knowledge-base/publishing/configure-microservices-imt-config.md).
