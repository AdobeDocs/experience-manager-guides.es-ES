---
title: Notas de versión | Novedades de la versión 2026.01.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las funciones nuevas y mejoradas de la versión 2026.01.0 de Adobe Experience Manager Guides
role: Leader
exl-id: f24a6f4a-2754-48d9-b0ce-79229dc8dba9
source-git-commit: 2c20191ba998ad7da98587f1832e1fe8499d023c
workflow-type: tm+mt
source-wordcount: '1591'
ht-degree: 1%

---

# Novedades de la versión 2026.01.0 (febrero de 2026)

Este artículo cubre las funciones nuevas y mejoradas introducidas con la versión 2026.01.0 de Adobe Experience Manager Guides as a Cloud Service.

Para ver la lista de problemas corregidos en esta versión, consulte [Problemas solucionados en la versión 2026.01.0](fixed-issues-2026-01-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2026.01.0](../release-info/upgrade-instructions-2026-01-0.md).


## Introducción al modo de búsqueda de Source en Buscar y reemplazar

Experience Manager Guides ha introducido varias mejoras en la función Buscar y reemplazar disponible en el panel izquierdo de la interfaz del editor. Junto con una interfaz de usuario mejorada para mejorar la facilidad de uso, esta versión incluye una nueva opción **Usar modo de origen** en el panel **Buscar y reemplazar**.

Al habilitar este modo, puede realizar búsquedas globales no solo en el contenido visible, sino también en el contenido de origen subyacente (estructura XML, incluidos elementos, etiquetas y valores de atributo) para la cadena buscada. Este modo garantiza una búsqueda completa en todo el contenido.

![](assets/map-find-replace-with-source-mode.png){width="650" align="left"}

En este modo, puede aplicar filtros para restringir la búsqueda por tipo de archivo, estado del documento, fecha de la última modificación y más. También tiene la opción de descargar un informe CSV detallado después de realizar la operación Reemplazar todo, que proporciona una instantánea de todas las acciones de reemplazo realizadas junto con su estado de éxito y error.

Para obtener más información, vea la sección [Buscar y reemplazar](../user-guide/web-editor-left-panel.md#find-and-replace) en el _panel izquierdo del editor_.

>[!NOTE]
>
> Para la característica **Usar modo de origen** en el panel Buscar y reemplazar, primero debe completarse una implementación de índice personalizada. Una vez implementada la indexación, póngase en contacto con el equipo de éxito del cliente para habilitar esta función.

## Experiencia mejorada de exploración de archivos y carpetas

Esta versión presenta una interfaz más limpia e intuitiva para explorar archivos y rutas de carpetas en Experience Manager Guides.

Al examinar los archivos, el cuadro de diálogo **Seleccionar archivo** modificado ahora incluye un diseño con pestañas con dos vistas: **Repositorio** para navegar por todo el repositorio de contenido en formato tabular y **Colecciones** para acceder rápidamente a los temas, mapas e imágenes utilizados con frecuencia.

![](assets/select-file.png){width="650" align="left"}

Las mejoras clave incluyen:

- Vista tabular de archivos y carpetas para una navegación organizada.
- Rutas de exploración y panel de navegación de carpetas para desplazarse fácilmente por las carpetas.
- Compatibilidad con la selección de varios archivos para contenido reutilizable, referencias de temas, Schematron, ajustes preestablecidos de salida (mediante DITAVAL) y Workfront.
- Obtenga una vista previa de los archivos seleccionados para facilitar su revisión; para varias selecciones, obtenga una vista previa de todos los archivos y elimine los que sean necesarios del panel Vista previa.
- Opciones de búsqueda y filtrado para reducir los resultados por nombre, título, tipo de archivo, estado del documento y etiquetas.

El cuadro de diálogo **Seleccionar ruta** también incluye una vista estructurada en árbol mejorada para la navegación por carpetas, lo que garantiza una forma más organizada y eficaz de seleccionar rutas en el repositorio de contenido.

![](assets/select-path-dialog-new.png){width="350" align="left"}

Para obtener más información, vea la sección [Exploración de archivos y carpetas en Experience Manager Guides](../user-guide/web-editor-other-features.md#browse-files-and-folders-in-experience-manager-guides) en _Otras características del Editor_.

## Mejoras en la búsqueda y filtrado de repositorios

### Compatibilidad con el filtro de estado del documento

Ahora, filtre los resultados de búsqueda del Repositorio en función del estado actual del documento de los archivos. Con el nuevo filtro **Estado del documento**, puede limitar la búsqueda mediante los valores de filtro disponibles definidos en el archivo `ui_config.json` dentro del perfil de carpeta.

![](assets/document-state-filter-repository.png){align="left"}

Los valores de filtro predeterminados disponibles para el estado del documento son: Borrador, Editar, En revisión, Aprobado, Revisado y Listo. Para obtener detalles sobre cómo personalizar los valores predeterminados de los filtros de estado del documento, vea [Configurar filtros de estado del documento](../cs-install-guide/config-doc-state-filters.md).

>[!NOTE]
>
> Si usa la configuración personalizada de `ui_config.json`, asegúrese de realizar una copia de seguridad de los mismos antes de actualizar. Después de la actualización, revise y ajuste la configuración para que se ajuste a los cambios introducidos en la versión más reciente.

### Icono de miniatura para multimedia

Todos los archivos multimedia ahora se muestran con iconos de miniaturas, lo que facilita la identificación y localización visual de imágenes dentro del **Repositorio**. Esta mejora también se aplica al buscar archivos en el **panel Buscar**, lo que le ayuda a distinguir rápidamente los recursos multimedia de otros tipos de archivos.

![](assets/thumbnail-repository.png){align="left"}

## Mejoras del editor

Se han realizado las siguientes mejoras de Editor como parte de esta versión:

### Actualizar temas o asignar en el modo Vista previa

Presentamos la nueva funcionalidad **Refresh** para asignaciones que ya están abiertas en el modo de vista previa. Con esta nueva función, puede actualizar fácilmente el contenido de todo el mapa o de los temas individuales presentes dentro de él.

- Para actualizar todo el mapa (incluidos todos los temas), se ha introducido un nuevo botón **Actualizar** en la esquina superior izquierda del Editor.

  ![](assets/refresh-map.png){width="600" align="left"}

- Para actualizar el contenido de temas individuales, se ha introducido una nueva opción **Actualizar tema** en el menú contextual.

  ![](assets/refresh-topic.png){width="600" align="left"}

Para obtener más información, vea [Funciones del editor de mapas](../user-guide/map-editor-advanced-map-editor.md).

### Indicador de copia de trabajo para cambios de metadatos

Cualquier cambio en los campos de metadatos disponibles en **Propiedades del archivo** almacenará en déclencheur el indicador de copia de trabajo. La versión de un documento se marca como _sucio (*)_ siempre que agregue, elimine o modifique cualquier campo de metadatos predeterminado o personalizado. Esta mejora garantiza que todos los cambios en los metadatos se rastreen con precisión, lo que proporciona una mayor visibilidad y control sobre las versiones de los documentos.

### Recuento de palabras para temas y mapas

Ahora puede realizar un seguimiento del recuento de palabras presentes en un mapa o archivo de tema. El nuevo campo **Recuento de palabras** del panel derecho mostraría el número total de palabras presentes en un tema (o mapa), donde las palabras separadas por espacios se cuentan como palabras individuales. Se actualiza automáticamente cada vez que se guardan los cambios. En el caso de las referencias cruzadas, solo se incluye el texto para mostrar, mientras que las claves se excluyen.

![](assets/file-properties-new.png){width="350" align="left"}

Para obtener más información, vea [Panel derecho en Editor](../user-guide/web-editor-right-panel.md#file-properties).

### Las propiedades de metadatos ya no se pueden editar para archivos de solo lectura

Con esta versión, cuando la configuración `Disable Edit Without Checkout` está habilitada, las propiedades del archivo ya no se pueden editar si el archivo está en modo **Solo lectura**.

Esta restricción se aplica a todos los puntos de entrada en los que se pueden modificar propiedades, incluidos los siguientes:

- El **panel derecho** de la interfaz del editor
- La opción **Propiedades** del menú contextual del archivo
- El informe de metadatos de un mapa
- La IU de Assets

Si un archivo es de sólo lectura, primero debe desprotegerlo antes de realizar cambios en sus propiedades. Este cambio exige controles de permisos más estrictos y garantiza que las actualizaciones de propiedades sigan las mismas reglas de cierre y cierre que las ediciones de contenido.

## Revisar mejoras

### Agregar o quitar temas de una tarea de revisión en curso

Ahora puede agregar nuevos temas a una tarea de revisión en curso (si no se han enviado anteriormente para su revisión) o quitar temas de una tarea de revisión en curso sin afectar al flujo de trabajo de revisión.

En la página **Detalles de la tarea**, simplemente puede seleccionar o deseleccionar temas para modificar la lista de temas. Los revisores reciben notificaciones (a través de AEM y por correo electrónico) sobre cualquier cambio en los temas asignados mediante notificaciones de AEM y por correo electrónico. Para obtener más información, vea [Enviar temas para revisión](../user-guide/review-send-topics-for-review.md).

![](assets/modify-review-topics.png){width="650" align="left"}

## Mejoras de traducción

### Indicador de recursos sin versiones enviados para su traducción

Al administrar las traducciones, es importante asegurarse de que todo el contenido tenga versiones antes de enviarlo para su procesamiento. Para ayudarle con esto, Experience Manager Guides ahora proporciona un indicador claro para los temas que han guardado cambios pero aún no tienen versiones.

Si un archivo contiene cambios sin versiones (no guardados como una nueva versión en el mapa), aparece un icono de _información_ junto al archivo, que indica que existen actualizaciones. Para centrarse rápidamente en estos archivos, habilite la opción **Mostrar recursos solo con cambios sin versiones** en el panel Filtros.

Para obtener más información, vea [Traducir documentos desde la consola de mapas](../user-guide/translate-documents-web-editor.md).

![](assets/unversioned-changes-translation.png){width="650" align="left"}

## Mejoras de publicación

### Representaciones de imágenes personalizadas para ajustes preestablecidos de salida específicos

Ahora puede configurar diferentes representaciones de imagen para ajustes preestablecidos de salida individuales bajo el mismo tipo de salida utilizando el atributo `outputName` en `renditionmapping.xml`. Esta mejora le proporciona una mayor flexibilidad a la hora de publicar contenido que requiera distintas resoluciones de imagen para diferentes escenarios. Por ejemplo, es posible que desee una imagen de alta resolución para la salida principal de HTML5 mientras utiliza una miniatura más pequeña para un ajuste preestablecido ligero.

Para obtener más información, vea [Controlar la representación de imágenes en la generación de salida](../cs-install-guide/conf-output-generation.md#handle-image-rendition-during-output-generation).


### Descargar registros para la salida generada

Al generar resultados a través de la interfaz de usuario de Assets, ahora hay disponible un nuevo botón **Descargar registros** que le permite descargar registros en su dispositivo local para facilitar el acceso y la revisión.


### Variables de idioma para referencias cruzadas en la salida nativa de PDF

Al publicar la salida nativa de PDF, puede usar [variables de idioma](../native-pdf/native-pdf-language-variables.md) para traducir texto de referencia cruzada estático como _Ver en el capítulo_ o _Ver en la página_. La variable utiliza el lenguaje definido en el tema a través del atributo `xml:lang`.

Para obtener más información sobre la configuración del ajuste preestablecido de salida de PDF nativo y las opciones de referencia cruzada, vea [Ajuste preestablecido de salida de PDF nativo](../web-editor/native-pdf-web-editor.md).


### Compatibilidad con la asignación de componentes de nivel de elemento en la publicación de New AEM Sites (con asignación de componentes compuestos)

Experience Manager Guides ahora admite la asignación de componentes a nivel de elemento en la salida de AEM Sites (mediante asignación de componentes compuestos), lo que proporciona a los equipos un control preciso sobre cómo se representan los elementos DITA mediante `componentmapping.json`. Al asignar `topicref`, títulos, imágenes, tablas y mucho más a los componentes principales de AEM adecuados, se obtiene una estructura más limpia en lugar de todo lo que se establece como predeterminado en el componente Texto. Esto mejora el rendimiento y desbloquea experiencias de Sites más ricas y modernas.

Para obtener más información, vea [Asignación de componentes en AEM Sites](../cs-install-guide/component-mapping.md).

## Mejoras en el procesamiento de recursos

Esta versión introduce las siguientes mejoras en el procesamiento de recursos:

- Ejecutar el procesamiento de recursos en los niveles de carpeta y archivo individual
- Filtre los recursos eligiendo tipos específicos, como temas, mapas, Markdown, HTML/CSS, DITAVAL u otros archivos compatibles, para procesar solo los archivos que necesite.
- Aplique filtros basados en fechas para limitar el ámbito de procesamiento para un periodo de tiempo especificado.
- Volver a procesar recursos directamente mediante la nueva opción (**Volver a procesar recursos**) disponible en el menú contextual de archivos y carpetas en la vista Repositorio y el panel Explorador.

Para obtener más información sobre el procesamiento de recursos, vea [Procesar recursos](../user-guide/asset-processor.md).

## Mejoras de API

Se han realizado las siguientes mejoras de API como parte de esta versión:

- Se introducen nuevas API para crear un nuevo proyecto de traducción y rastrear su estado. Estas API ayudan a automatizar el proceso de traducción, reduciendo el esfuerzo manual y mejorando la eficacia. Para obtener más información, vea [Crear proyecto de traducción](../api-reference/translation-project.md)
- API de procesamiento de recursos mejoradas con capacidad de filtrado mejorada para archivos y carpetas. Para obtener más información, vea [Procesar recursos](../api-reference/bulk-assets-processing.md).
