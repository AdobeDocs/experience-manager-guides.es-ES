---
title: Notas de versión | Novedades de la versión 5.2.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las funciones nuevas y mejoradas de la versión 5.2.0 de Adobe Experience Manager Guides
role: Leader
source-git-commit: 166dd4eec428d81bfe3db92ebc5a54f1760fe7dc
workflow-type: tm+mt
source-wordcount: '4052'
ht-degree: 0%

---

# Novedades de la versión 5.2.0 (mayo de 2026)

Este artículo cubre las nuevas y mejoradas funciones introducidas con la versión 5.2.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener la lista de problemas corregidos en esta versión, vea [Problemas corregidos en la versión 5.2.0](../release-info/fixed-issues-5-2-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 5.2.0](../release-info/upgrade-instructions-5-2-0.md).


## Introducción a Editor 2.0

Editor 2.0 (también conocido como Nuevo editor) proporciona una creación simplificada, lo que le permite crear contenido de forma más eficaz en los modos de etiqueta y sin etiqueta a través de una experiencia más intuitiva. La versión ofrece un rendimiento mejorado, con cargas de página más rápidas y una edición más suave incluso para temas grandes y complejos. También ofrece una mayor estabilidad al abordar las lagunas clave de creación, especialmente en torno a la navegación y el comportamiento del cursor. Además, una interfaz moderna ofrece una interfaz de usuario actualizada y fácil de usar que equilibra la funcionalidad con la facilidad de uso. Para obtener más información, vea [Introducción al editor](../user-guide/web-editor.md).

Este es un vídeo introductorio que resalta las capacidades de Editor 2.0.

>[!VIDEO](https://video.tv.adobe.com/v/3484007)

A continuación se indican las mejoras que facilitan y hacen que la creación de contenido sea más eficaz.

### Interfaz de usuario y experiencia rediseñadas

Una interfaz actualizada mejora la facilidad de uso general, lo que hace que la navegación y la creación de contenido sean más intuitivas y coherentes.

- **CSS más enriquecido para los elementos en los modos de creación y vista previa**: La CSS predeterminada mejorada para los elementos proporciona un estilo mejorado y una mejor coherencia visual en los modos de creación y vista previa.

  ![](assets/rich-css.png){width="650"}

- **Compatibilidad con temas oscuros**: La compatibilidad con un tema oscuro en el área de edición de contenido mejora la experiencia de creación para los usuarios que prefieren trabajar con una interfaz oscura.

  ![](assets/dark-theme.png){width="650"}

- **Configuración del editor consolidada en el nivel de usuario**: Un nuevo panel de configuración centralizado que proporciona a los autores un mejor control sobre el comportamiento del editor, lo que permite a los usuarios administrar las preferencias con mayor facilidad desde una sola ubicación. Las opciones de configuración incluyen la capacidad de habilitar/deshabilitar:

   - Espacios de no separación en el modo Autor
   - Configuración de visibilidad de etiquetas con atributos o sin atributos
   - Comentarios XML en el modo Autor
   - Menú de inserción rápida para insertar elementos en el editor

  ![](assets/editor-settings-dialog.png){width="350"}


  Para obtener más información acerca de cómo configurar las opciones del Editor, vea [Opciones del editor](../user-guide/config-editor-settings.md).

- **Mejor representación del contenido condicional en el modo Autor**: el contenido condicional se muestra más claramente en el modo Autor, lo que ayuda a los autores a identificar y administrar las variaciones de forma más eficaz. Para obtener más información, vea [Condiciones](../user-guide/web-editor-left-panel.md#conditions) en el panel izquierdo del editor.

  ![](assets/multiple-conditions-applied_cs-editor-2-0.png){width="650"}

### Funciones de creación mejoradas

Proporciona herramientas mejoradas y flexibilidad para optimizar los flujos de trabajo de creación y edición de contenido.

- **Ver atributos junto con elementos en el modo de etiqueta**: Los autores ahora pueden ver atributos de elementos con el modo de etiqueta, lo que ofrece una mejor visibilidad y control sobre el contenido estructurado. Para configurar esta característica, vea [Configuración del editor](../user-guide/config-editor-settings.md).

  ![](assets/config-tags-attributes.png){width="650"}

- **Menú de inserción rápida**: permite agregar elementos directamente mientras se edita en el modo Autor en la posición del cursor sin desplazarse a la barra de herramientas. Los elementos utilizados con frecuencia también se pueden configurar en la sección Favoritos mediante Configuración del editor para acceder más rápidamente. Para obtener detalles, vea [Editar temas](../user-guide/web-editor-edit-topics.md).

  ![](assets/quick-insert-menu.png){width="650"}

- **Capacidad para ver, editar e insertar comentarios XML en el modo Autor**: permite a los autores ver, editar e insertar comentarios XML directamente en el modo Autor para obtener una mejor visibilidad del contenido. Para configurar esta característica, vea [Configuración del editor](../user-guide/config-editor-settings.md).

  ![](assets/config-xml-comments.png){width="650"}

- **Modo paralelo**: permite la visualización simultánea de los modos Autor y Source, con ambas vistas en perfecta sincronización para facilitar la comparación, edición y validación de los cambios de contenido. Para obtener más información, vea [Vistas del editor](../user-guide/web-editor-views.md).

  ![](assets/side-by-side-editor-2-0.png){width="650"}

- **Creación de tablas mejorada**: Mejora la experiencia general de creación de tablas con interacciones más intuitivas y eficientes para crear y administrar tablas.

   - Interacciones fluidas e intuitivas: inserte filas y columnas fácilmente, junto con la compatibilidad de arrastrar y soltar para reordenar filas y columnas.
   - Barra de herramientas contextual: Acceda a acciones específicas de la tabla, como formato, alineación, combinación y otras acciones adicionales directamente dentro de la tabla.
   - Configuración de tablas: Añada varias filas o columnas en una sola acción, reduciendo los pasos repetitivos y mejorando la eficacia.

  ![](assets/config-table.png){width="650"}

  Para obtener información detallada, vea [Trabajar con tablas](../user-guide/web-editor-other-features.md#work-with-tables-in-the-new-editor).

### Rendimiento mejorado para temas grandes

El nuevo editor mejora la experiencia de trabajar con temas grandes y complejos al ofrecer una representación de contenido más rápida, una funcionalidad más fiable de deshacer y rehacer y un marcador sucio para indicar claramente los cambios no guardados.

## Introducción de un nuevo repositorio en la página de inicio y una experiencia de búsqueda mejorada

El repositorio, ahora accesible directamente desde la página de inicio, sirve como espacio centralizado para mejorar la capacidad de detección de carpetas y archivos. Incluye **panel de navegación de carpetas** dedicado y una **vista tabular personalizable del repositorio**. La experiencia renovada de búsqueda y filtrado facilita considerablemente la búsqueda y localización de archivos. Para obtener más información, vea [Conocer la interfaz del repositorio](../user-guide/home-page-repository-view.md).

![](assets/repository-view-home.png)

En el Editor, la experiencia de búsqueda y filtrado de archivos es ahora coherente con la página de inicio. Se ha introducido un nuevo [panel de búsqueda](../user-guide/search-panel-explorer.md) ubicado en la parte inferior de la interfaz del editor para mostrar los resultados de búsqueda. Además, ahora se cambia el nombre del repositorio a **Explorador** en el Editor, lo que le permite examinar carpetas y archivos como antes.

![](assets/search-panel-explorer.png)

### Compatibilidad con el filtro de estado del documento

También puede filtrar los resultados de búsqueda del Repositorio en función del estado actual del documento de los archivos. Con el filtro Estado del documento, puede limitar la búsqueda mediante los valores de filtro disponibles definidos en el archivo `ui_config.json` dentro del perfil de carpeta.

![](assets/document-state-filter-repository.png)

Los valores de filtro predeterminados disponibles para el estado del documento son: Borrador, Editar, En revisión, Aprobado, Revisado y Listo.

<!-- For details on customizing the default document state filters values, view [Configure document state filters](../install-conf-guide/conf-doc-state-filters.md).  -->

>[!NOTE]
>
> Si usa la configuración personalizada de `ui_config.json`, asegúrese de realizar una copia de seguridad de los mismos antes de actualizar. Después de la actualización, revise y ajuste la configuración para que se ajuste a los cambios introducidos en la versión más reciente.

### Icono de miniatura para multimedia

Todos los archivos multimedia se muestran con iconos de miniaturas, lo que facilita la identificación y localización visual de las imágenes del **repositorio**. Esta mejora también se aplica al buscar archivos en el **panel Buscar**, lo que le ayuda a distinguir rápidamente los recursos multimedia de otros tipos de archivos.

![](assets/thumbnail-repository.png)

## Introducción al modo de búsqueda de Source en Buscar y reemplazar

Experience Manager Guides ha introducido varias mejoras en la función Buscar y reemplazar disponible en el panel izquierdo de la interfaz del editor. Junto con una interfaz de usuario mejorada para mejorar la facilidad de uso, esta versión incluye una nueva opción **Usar modo de origen** en el panel **Buscar y reemplazar**.

Al habilitar este modo, puede realizar búsquedas globales no solo en el contenido visible, sino también en el contenido de origen subyacente (estructura XML, incluidos elementos, etiquetas y valores de atributo) para la cadena buscada. Este modo garantiza una búsqueda completa en todo el contenido.

![](assets/map-find-replace-with-source-mode.png){width="650"}

En este modo, puede aplicar filtros para restringir la búsqueda por tipo de archivo, estado del documento, fecha de la última modificación y más. También tiene la opción de descargar un informe CSV detallado después de realizar la operación Reemplazar todo, que proporciona una instantánea de todas las acciones de reemplazo realizadas junto con su estado de éxito y error.

Para obtener más información, vea la sección [Buscar y reemplazar](../user-guide/web-editor-left-panel.md#find-and-replace) en el _panel izquierdo del editor_.

>[!NOTE]
>
> Para la característica **Usar modo de origen** en el panel Buscar y reemplazar, primero debe completarse la reindexación.

## Experiencia mejorada de exploración de archivos y carpetas

Esta versión presenta una interfaz más limpia e intuitiva para explorar archivos y rutas de carpetas en Experience Manager Guides.

Al examinar los archivos, el cuadro de diálogo **Seleccionar archivo** modificado ahora incluye un diseño con pestañas con dos vistas: **Repositorio** para navegar por todo el repositorio de contenido en formato tabular y **Colecciones** para acceder rápidamente a los temas, mapas e imágenes utilizados con frecuencia.

![](assets/select-file.png){width="650"}

Las mejoras clave incluyen:

- Vista tabular de archivos y carpetas para una navegación organizada.
- Rutas de exploración y panel de navegación de carpetas para desplazarse fácilmente por las carpetas.
- Compatibilidad con la selección de varios archivos para contenido reutilizable, referencias de temas, Schematron, ajustes preestablecidos de salida (mediante DITAVAL) y Workfront.
- Obtenga una vista previa de los archivos seleccionados para facilitar su revisión; para varias selecciones, obtenga una vista previa de todos los archivos y elimine los que sean necesarios del panel Vista previa.
- Opciones de búsqueda y filtrado para reducir los resultados por nombre, título, tipo de archivo, estado del documento y etiquetas.

El cuadro de diálogo **Seleccionar ruta** también incluye una vista estructurada en árbol mejorada para la navegación por carpetas, lo que garantiza una forma más organizada y eficaz de seleccionar rutas en el repositorio de contenido.

![](assets/select-path-dialog-new.png){width="350"}

Para obtener más información, vea la sección [Exploración de archivos y carpetas en Experience Manager Guides](../user-guide/web-editor-other-features.md#browse-files-and-folders-in-experience-manager-guides) en _Otras características del Editor_.

## Mejoras de creación

Se han realizado las siguientes mejoras de creación como parte de esta versión:

### Acceda a la ruta y el UUID de referencias en archivos desde el panel Propiedades de contenido

Ahora, puede usar **Ruta del vínculo** para ver la ruta relativa de la referencia seleccionada y **UUID del vínculo** para ver su identificador único desde el panel de propiedades de contenido. También puede copiar la ruta absoluta completa y el UUID asociado directamente desde la interfaz mediante los iconos junto a Ruta de vínculo y UUID de vínculo, lo que facilita el seguimiento y la reutilización de los recursos vinculados.

Para obtener más información, vea [Propiedades del contenido](../user-guide/web-editor-right-panel.md#content-properties).

### Indicador de copia de trabajo para cambios de metadatos

Cualquier cambio en los campos de metadatos disponibles en **Propiedades del archivo** o aplicado en el backend también almacenará en déclencheur el asterisco (*) en la versión del documento. Una versión de documento se marca como _dirty (*)_ siempre que se agregan, eliminan o modifican campos de metadatos predeterminados o personalizados. Para evitar que las actualizaciones de metadatos generadas por el sistema afecten a este indicador, los administradores pueden configurar una lista de omisión para las propiedades de los metadatos. Para obtener detalles sobre cómo configurar las propiedades de metadatos, vea [Configurar la lista de omisión de propiedades de metadatos](../install-conf-guide/conf-metadata-prop.md).

### Mejoras en el panel de validación de Schematron

Se han realizado las siguientes mejoras en la interfaz de usuario de Schematron para mejorar la claridad, la facilidad de uso y los resultados de validación:

- En el panel Validación, se muestra un mensaje de estado vacío cuando no se agrega ningún archivo de Schematron, lo que proporciona una mejor claridad y dirección para los pasos siguientes.

  ![](assets/schematron-panel.png){width="350"}

- Cuando se agregan varios archivos de Schematron, se organizan en un acordeón consolidado, lo que proporciona una mejor visibilidad de los archivos de Schematron configurados.

  ![](assets/schematron-panel-error.png){width="350"}

- Según el atributo de rol definido en el archivo Schematron, los resultados de validación ahora se clasifican en: `Fatal`, `Error`, `Warn` o `Info`. Cada categoría incluye un recuento visible junto con información sobre herramientas contextuales para una interpretación más clara.

  ![](assets/schematron-validation-errors.png){width="350"}

Para obtener más información sobre el uso de archivos Schematron en Experience Manager Guides, vea [Compatibilidad con archivos Schematron](../user-guide/support-schematron-file.md).

### Las copias de idioma de traducción ya están disponibles en el panel derecho de la interfaz del editor

Ahora hay disponible una nueva sección **Traducciones** en el panel derecho bajo *Propiedades del archivo* en el editor. Esta sección proporciona acceso directo a todas las copias de idioma disponibles para el recurso abierto actualmente (mapa, tema, imagen, etc.). Ya no es necesario navegar a la interfaz de usuario de Assets para ver o acceder a estas copias de idioma.

![](assets/translations-right-panel.png){width="350"}

Para cada copia de idioma, puede pasar el ratón sobre el archivo para localizar su ruta en el repositorio o simplemente seleccionarlo para abrirlo en el Editor. Además de abrir archivos, también puede realizar muchas acciones utilizando el menú **Opciones**. Algunas de las acciones que puede realizar son Editar, Vista previa, Copiar UUID, Copiar ruta, Agregar a colecciones y Propiedades.

Para obtener más información, vea [Panel derecho en el editor](../user-guide/web-editor-right-panel.md#file-properties).

### Actualizar temas o asignar en el modo Vista previa

>[!NOTE]
>
>Este comportamiento solo se aplica al Editor antiguo. En el nuevo editor, la vista previa del contenido se actualiza automáticamente.

Presentamos la nueva funcionalidad **Refresh** para asignaciones que ya están abiertas en el modo de vista previa. Con esta nueva función, puede actualizar fácilmente el contenido de todo el mapa o de los temas individuales presentes dentro de él.

- Para actualizar todo el mapa (incluidos todos los temas), se ha introducido un nuevo botón **Actualizar** en la esquina superior izquierda del Editor.

  ![](assets/refresh-map.png){width="600"}

- Para actualizar el contenido de temas individuales, se ha introducido una nueva opción **Actualizar tema** en el menú contextual.

  ![](assets/refresh-topic.png){width="600"}

Para obtener más información, vea [Funciones del editor de mapas](../user-guide/map-editor-advanced-map-editor.md).

### Recuento de palabras para temas y mapas

Ahora puede realizar un seguimiento del recuento de palabras presentes en un mapa o archivo de tema. El nuevo campo **Recuento de palabras** del panel derecho mostraría el número total de palabras presentes en un tema (o mapa), donde las palabras separadas por espacios se cuentan como palabras individuales. Se actualiza automáticamente cada vez que se guardan los cambios. En el caso de las referencias cruzadas, solo se incluye el texto para mostrar, mientras que las claves se excluyen.

![](assets/file-properties-new.png){width="350"}

Para obtener más información, vea [Panel derecho en Editor](../user-guide/web-editor-right-panel.md#file-properties).

### Identifique y corrija fácilmente los ID duplicados en los temas y asignaciones de la vista Autor

Experience Manager Guides ahora incluye un botón **ID duplicados** en el editor para ayudarle a identificar y corregir rápidamente los ID duplicados presentes en un solo tema o asignación. Cuando se detectan ID duplicados, este botón aparece en la esquina inferior izquierda de la interfaz del editor en la vista **Autor**. Al seleccionar el botón, se muestra en una ventana emergente una lista de todas las instancias con ID duplicados. Al seleccionar una instancia, se resalta el contenido correspondiente del tema o asignación, lo que permite localizar y corregir los ID duplicados desde el panel derecho.

Para obtener más información, vea [Características adicionales en el editor](../user-guide/web-editor-other-features.md).

![](assets/duplicate-element-IDs.png){width="350"}

### Mejoras en los filtros Repositorio e Informes

El filtro **Bloqueado por** en Filtros avanzados en el repositorio y el filtro **Autor** en los informes de mapas DITA ahora cargan listas de usuarios gradualmente a medida que se desplaza, en lugar de todos a la vez. Esta carga paginada mejora la velocidad y hace que trabajar con conjuntos de datos de usuario grandes sea más eficiente y fluido.

### Buscar citas en todos los campos del diario

Ahora puede buscar citas en todos los campos de diario, como *Título*, *Título del diario*, *Autor*, *Año*, *Volumen*, *Número* y *Páginas*, usando la opción **Cualquier campo** en el cuadro de diálogo **Agregar cita**. La búsqueda devuelve la cita coincidente más cercana en función del texto introducido.

Para obtener más información sobre cómo agregar citas en Experience Manager Guides, vea [Agregar y administrar citas en el contenido](../user-guide/web-editor-apply-citations.md).

![](assets/add-citations.png){width="350"}

### Ahora se cambia el nombre de Configuración a Configuración de Workspace y se puede acceder a ella desde la página principal

Para mejorar la navegación y la facilidad de uso, se han introducido las siguientes mejoras:

- Se cambió el nombre de **Configuración** en el menú **Más acciones** del Editor a **Configuración de Workspace**.
- Ahora se puede acceder al menú **Más acciones** (el menú de tres puntos), que antes solo estaba disponible en la interfaz de la consola Editor y Mapa, desde la [Página principal](../user-guide/intro-home-page.md).

  ![](assets/workspace-settings.png)

### Indexación mejorada para sugerencias inteligentes en el asistente de IA

Ahora puede rastrear fácilmente el estado de cada intento de indexación de sugerencias inteligentes en el Asistente de IA con nuevos indicadores de estado: Indexación completada, No sincronizado, En curso y Error de indexación. La última marca de tiempo de indexación ahora se registra en el nivel de perfil de carpeta para mejorar la trazabilidad. Además, se aplican restricciones de carpeta principal-secundaria al especificar una carpeta o ruta de archivo para la indexación.

Para obtener más información, vea [Configurar el Asistente de IA para obtener ayuda y crear experiencias inteligentes](../install-conf-guide/conf-profiles.md#configure-ai-assistant-for-smart-help-and-authoring-only-for-cloud-service).

## Revisar mejoras

Se han realizado las siguientes mejoras de revisión como parte de esta versión:

### Recordatorios automatizados para tareas de revisión

Ahora puede habilitar **Recordatorios automatizados** para programar notificaciones de AEM y recordatorios de correo electrónico para los revisores, tanto antes de la fecha de vencimiento de una tarea de revisión como después de que haya vencido. Puede configurar varios recordatorios en cada caso, con recordatorios de vencimiento anticipado enviados en una secuencia definida y recordatorios de vencimiento activados después de que la tarea se marque como vencida, según la programación de recordatorios configurada. Para obtener información detallada, vea [Enviar temas para revisión](../user-guide/review-send-topics-for-review.md).

### Historial de versiones

Los revisores ahora pueden acceder al Historial de versiones para los temas que se están revisando, lo que les permite ver y comparar versiones previamente revisadas y actualizadas del mismo tema en tareas de revisión anteriores. Esto ayuda a los revisores a validar los cambios realizados desde ciclos de revisión anteriores y a mantener la continuidad mediante la revisión de comentarios, etiquetas y otros detalles relacionados dentro del contexto de revisión actual. Para obtener más información, vea [Historial de versiones del revisor](../user-guide/review-topics.md#version-history-for-the-reviewer).

### Acceder al estado de las tareas de revisión directamente desde el panel Revisar

Como iniciador de una tarea de revisión, ahora puede comprobar el estado de la tarea de revisión directamente desde el panel Revisar. Con las mejoras más recientes, el cuadro de diálogo **Actualizar tarea** del panel Revisar incluye una nueva opción **Comprobar estado de revisión**. Al seleccionar esta opción, accederá directamente al panel de revisión, donde podrá ver el estado de las tareas de cada revisor, lo que permitirá acceder más rápidamente al progreso de las tareas sin necesidad de cambiar de contexto.

Para obtener más información, vea [Solicitar una nueva revisión o cerrar una tarea de revisión como autor](../user-guide/review-close-review-task.md).

![](assets/check-review-status-icon.png){width="350"}

### Asignación del revisor basada en la selección activa del proyecto

- La asignación de un revisor a una tarea de revisión ahora depende de la selección de un proyecto activo. El campo **Asignar a** de la página *Crear tarea de revisión* permanece deshabilitado hasta que se seleccione un proyecto activo. Después de seleccionar un proyecto, el campo **Asignar a** se habilita y muestra solamente los usuarios y grupos de usuarios asociados con ese proyecto. Esto garantiza que las tareas de revisión se asignen únicamente a miembros de proyecto válidos y evita que se seleccione un revisor de forma involuntaria.

  ![](assets/create-review-task-023.png)


- El campo **Asignar a** ahora admite la búsqueda de escritura anticipada, lo que le permite localizar rápidamente usuarios o grupos de usuarios escribiendo texto.

En conjunto, estas mejoras hacen que la selección de Revisor sea más precisa, eficiente y esté alineada con los flujos de trabajo de revisión específicos del proyecto.

Para obtener más información, vea [Enviar temas para revisión](../user-guide/review-send-topics-for-review.md).

### Modificar las tareas de revisión en curso

Puede agregar temas nuevos a una tarea de revisión en curso (si no se han enviado anteriormente para su revisión) o quitar temas de una tarea de revisión en curso sin que ello afecte al flujo de trabajo de revisión. En la página **Detalles de la tarea**, simplemente puede seleccionar o deseleccionar temas para modificar la lista de temas. Los revisores reciben notificaciones (a través de AEM y por correo electrónico) sobre cualquier cambio en los temas asignados mediante notificaciones de AEM y por correo electrónico. Para obtener más información, vea [Enviar temas para revisión](../user-guide/review-send-topics-for-review.md).

![](assets/modify-review-topics.png){width="650"}

## Mejoras de traducción

Se han realizado las siguientes mejoras de traducción como parte de esta versión:

### Indicador de recursos sin versiones enviados para su traducción

Al administrar las traducciones, es importante asegurarse de que todo el contenido tenga versiones antes de enviarlo para su procesamiento. Para ayudarle con esto, Experience Manager Guides ahora proporciona un indicador claro para los temas que han guardado cambios pero aún no tienen versiones.

Si un archivo contiene cambios sin versiones (no guardados como una nueva versión en el mapa), aparece un icono de _información_ junto al archivo, que indica que existen actualizaciones. Para centrarse rápidamente en estos archivos, habilite la opción **Mostrar recursos solo con cambios sin versiones** en el panel Filtros.

Para obtener más información, vea [Traducir documentos desde la consola de mapas](../user-guide/translate-documents-web-editor.md).

![](assets/unversioned-changes-translation.png){width="650"}


## Mejoras en la administración de recursos

Esta versión introduce las siguientes mejoras en la administración de recursos:

### Utilice Acoplar jerarquía de archivos para descargar asignaciones con nombres de archivo originales y metadatos asociados

Ahora puede utilizar la opción Acoplar jerarquía de archivos para descargar un mapa con su nombre de archivo original. Además, el paquete descargado incluye un archivo de `metadata.json`, lo que facilita el acceso y la reutilización de los metadatos asociados fuera de Experience Manager Guides.

Para obtener más información sobre cómo descargar archivos en Experience Manager Guides, vea [Descargar archivos](../user-guide/authoring-download-assets.md).

### Las propiedades de metadatos ya no se pueden editar para archivos de solo lectura

Con esta versión, cuando la configuración `Disable edit without locking the file` está habilitada, las propiedades del archivo ya no se pueden editar si el archivo está en modo **Solo lectura**.

Esta limitación se aplica a todos los puntos de entrada en los que las propiedades se pueden modificar para archivos DITA y Markdown, incluidos:

- El **panel derecho** de la interfaz del editor
- La opción **Propiedades** del menú contextual del archivo
- El informe de metadatos de un mapa
- La IU de Assets

Para los recursos que no son DITA (como imágenes y multimedia), las propiedades de metadatos siguen siendo editables, incluso en modo de solo lectura.

Si un archivo es de sólo lectura, primero debe desprotegerlo antes de realizar cambios en sus propiedades. Este cambio exige controles de permisos más estrictos y garantiza que las actualizaciones de propiedades sigan las mismas reglas de cierre y cierre que las ediciones de contenido.

### Usar regex para habilitar o deshabilitar el procesamiento posterior

Ahora puede utilizar regex para habilitar o deshabilitar el posprocesamiento para carpetas. Esta mejora permite a los administradores definir reglas de procesamiento posterior que se aplican a varias carpetas o jerarquías de carpetas completas mediante una sola configuración, en lugar de especificar rutas de carpeta individuales.

Para obtener más información, vea [Use regex para habilitar o deshabilitar el procesamiento posterior](../install-conf-guide/conf-folder-post-processing.md).

### Limpieza automatizada del árbol B para un rendimiento óptimo

Para mantener la eficiencia del sistema y evitar la congestión de recursos, un nuevo proceso de fondo limpia regularmente los árboles B del nivel del sistema. Esto garantiza que los recursos que ya no existen o que se agregaron temporalmente no ocupen un espacio innecesario.

El sistema identifica de forma inteligente a los candidatos para la limpieza y realiza la eliminación automatizada. Además, esta función es configurable, lo que proporciona a los administradores control sobre su comportamiento en función de las necesidades operativas.

Para obtener más información, vea [Configurar la limpieza del árbol B](../install-conf-guide/conf-btree-cleanup.md).

### Se ha mejorado el manejo de los mapas DITA con un gran número de claves

Ahora puede trabajar sin problemas con mapas DITA que contienen un gran número de claves. Esta mejora garantiza una carga más rápida y un rendimiento mejorado, lo que facilita la administración de mapas complejos sin interrupciones.

Después de la actualización de la compilación, el sistema puede experimentar un aumento temporal de la carga, lo que provoca un retraso en el posprocesamiento de los datos recién cargados. Esto se debe a un script de un solo uso automatizado (OTS) que se ejecuta en segundo plano. Una vez que el script se complete, el rendimiento del sistema volverá a la normalidad.

### Procesamiento de recursos mejorado

- Se ha introducido un proceso automatizado para mantener los recursos de `/content/dam` actualizados. El sistema déclencheur el reprocesamiento de recursos cada 15 minutos. Durante cada ciclo, los recursos que se agregaron recientemente o que permanecieron sin procesar en el intervalo de 15 minutos más reciente se recogen y se vuelven a procesar, lo que mejora la eficacia y la coherencia en todo el repositorio de contenido.
- Ejecutar el procesamiento de recursos en los niveles de carpeta y archivo individual
- Filtre los recursos eligiendo tipos específicos, como temas, mapas, Markdown, HTML/CSS, DITAVAL u otros archivos compatibles, para procesar solo los archivos que necesite.
- Aplique filtros basados en fechas para limitar el ámbito de procesamiento para un periodo de tiempo especificado.
- Volver a procesar recursos directamente mediante la nueva opción (**Volver a procesar recursos**) disponible en el menú contextual de archivos y carpetas en la vista Repositorio y el panel Explorador.

Para obtener detalles sobre el procesamiento de recursos, vea [Procesar recursos](../user-guide/asset-processor.md).


## Mejoras de publicación

Se han realizado las siguientes mejoras de publicación como parte de esta versión:

### Configurar representaciones de imágenes personalizadas para ajustes preestablecidos de salida específicos

Ahora puede configurar diferentes representaciones de imagen para ajustes preestablecidos de salida individuales bajo el mismo tipo de salida utilizando el atributo `outputName` en `renditionmapping.xml`. Esta mejora le proporciona una mayor flexibilidad a la hora de publicar contenido que requiera distintas resoluciones de imagen para diferentes escenarios. Por ejemplo, es posible que desee una imagen de alta resolución para la salida principal de HTML5 mientras utiliza una miniatura más pequeña para un ajuste preestablecido ligero.

Para obtener más información, vea [Controlar la representación de imágenes en la generación de salida](../install-conf-guide/conf-output-generation.md#handle-image-rendition-during-output-generation).


### Descargar registros para la salida generada

Al generar los registros de salida y visualización, ahora está disponible un nuevo botón **Descargar registros** que le permite descargar el registro en su dispositivo local para facilitar el acceso y la revisión.

### Variables de idioma para referencias cruzadas en la salida nativa de PDF

Al publicar la salida nativa de PDF, puede usar [variables de idioma](../native-pdf/native-pdf-language-variables.md) para traducir texto de referencia cruzada estático como _Ver en el capítulo_ o _Ver en la página_. La variable utiliza el lenguaje definido en el tema a través del atributo `xml:lang`.

Para obtener más información sobre la configuración del ajuste preestablecido de salida de PDF nativo y las opciones de referencia cruzada, vea [Ajuste preestablecido de salida de PDF nativo](../web-editor/native-pdf-web-editor.md).


### Compatibilidad con la asignación de componentes de nivel de elemento en la publicación de AEM Sites (mediante asignación de componentes compuestos)

Experience Manager Guides ahora admite la asignación de componentes a nivel de elemento en la salida de AEM Sites (mediante asignación de componentes compuestos), lo que proporciona a los equipos un control preciso sobre cómo se representan los elementos DITA mediante `componentmapping.json`. Al asignar `topicref`, títulos, imágenes, tablas y mucho más a los componentes principales de AEM adecuados, se obtiene una estructura más limpia en lugar de todo lo que se establece como predeterminado en el componente Texto. Esto mejora el rendimiento y desbloquea experiencias de Sites más ricas y modernas.

Para obtener más información, vea [Asignación de componentes para AEM Sites](../install-conf-guide/component-mapping.md).

## Nueva experiencia de línea de base introducida en Experience Manager Guides

La administración de líneas de base grandes y complejas es ahora más rápida, estable y fácil de escalar con la **nueva experiencia de línea de base**, basada en una arquitectura de línea de base rediseñada. Esta actualización aborda los desafíos de rendimiento y fiabilidad de larga data, al tiempo que preserva los flujos de trabajo existentes.

Disponible como mejora beta, esta actualización proporciona una solución a los problemas comunes, como la carga lenta, los estados de línea de base incoherentes y la capacidad de administración limitada, al ofrecer una experiencia de línea de base más rápida, estable y predecible, con compatibilidad añadida para la automatización y las operaciones de línea de base a gran escala. Las principales mejoras son las siguientes:

- Rendimiento y escalabilidad mejorados
- Consistencia del back-end y IU más sólida
- Mayor visibilidad de filtrado, navegación y dependencias

Para obtener más información, vea [Nueva experiencia de línea de base (Beta) en Experience Manager Guides](../user-guide/web-editor-baseline-v2.md).

## Mejoras de API

Se han realizado las siguientes mejoras de API como parte de esta versión:

- Se introducen nuevas API para crear un nuevo proyecto de traducción y rastrear su estado. Estas API ayudan a automatizar el proceso de traducción, reduciendo el esfuerzo manual y mejorando la eficacia. Para obtener más información, vea [Crear proyecto de traducción](../api-reference/translation-project.md)
- API de procesamiento de recursos mejoradas con capacidad de filtrado mejorada para archivos y carpetas. Para obtener más información, vea [Procesar recursos](../api-reference/bulk-assets-processing.md).
- Hay una nueva API disponible para rastrear el estado posterior al procesamiento de recursos y carpetas individuales. Esto resulta especialmente útil en equipos que utilizan flujos de trabajo automatizados, donde la publicación solo debe producirse después de que el contenido se haya procesado por completo. La API ofrece una forma fiable de confirmar la preparación, lo que reduce el riesgo de errores de publicación causados por un procesamiento incompleto. Además, con la introducción de esta API, los eventos de procesamiento posterior de recursos no se activan automáticamente. Ahora los administradores pueden habilitar este evento mediante una configuración en `fmdita config manager`.
Para obtener más información, vea la [API para rastrear el estado posterior al procesamiento de recursos y carpetas individuales](../api-reference/track-post-processing-status.md) y la configuración del controlador de eventos posterior al procesamiento en el administrador de configuración de fmdita](../api-reference/post-process-event.md)[

## Introducción de formación sobre productos y contenido de aprendizaje en Experience Manager Guides

La función de contenido **Aprendizaje y formación sobre productos** de Experience Manager Guides permite a los equipos de formación y a los diseñadores de instrucciones crear cursos interactivos de aprendizaje electrónico directamente desde la interfaz de Experience Manager Guides.

![](assets/lc-overview.png)

Con la creación basada en plantillas, los componentes interactivos de los cursos y el soporte para las evaluaciones, los equipos pueden desarrollar contenido de formación de alta calidad alineado con sus objetivos organizativos.

>[!NOTE]
> 
> La función Aprendizaje y contenido del producto permanece deshabilitada de forma predeterminada para todas las instancias de Experience Manager Guides as a Cloud Service. Los administradores pueden habilitar esta característica en el nivel de perfil de carpeta desde **Configuración de Workspace** > **General**.

Las funciones clave son las siguientes:

- Administración centralizada de contenido de aprendizaje
- Creación basada en plantillas
- Compatibilidad con la reutilización de contenido
- Creación y administración de evaluaciones
- Flujos de trabajo de revisión basados en web
- Administración de traducción líder del sector
- Publicación multicanal mediante los formatos de salida SCORM y PDF predeterminados.

Para obtener más información, consulte [Guía de introducción](../learning-content/course-overview.md) y [Guía de configuración](../lc-config-guide/introduction.md).