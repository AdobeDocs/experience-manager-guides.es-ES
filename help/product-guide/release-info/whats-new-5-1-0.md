---
title: Notas de versión | Novedades de la versión 5.1.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las funciones nuevas y mejoradas de la versión 5.1.0 de Adobe Experience Manager Guides
role: Leader
source-git-commit: f6617b727d385d31ba66d575ee48f29e77ac716f
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 0%

---

# Novedades de la versión 5.1.0 (septiembre de 2025)

Este artículo cubre las funciones nuevas y mejoradas introducidas con la versión 5.1.0 de Adobe Experience Manager Guides.

Para ver la lista de problemas que se han corregido en esta versión, consulte [Problemas corregidos en la versión 5.1.0](fixed-issues-5-1-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 5.1.0](../release-info/upgrade-instructions-5-1-0.md).


## Flujo de trabajo de revisión mejorado

Con esta versión, el flujo de trabajo de revisión se ha mejorado considerablemente para admitir mejor la comunicación fluida entre autores y revisores. Las actualizaciones clave incluyen:

- Flujos de trabajo de administración de tareas con notificaciones procesables
- Capacidad para etiquetar usuarios para buscar atención inmediata
- Acceso a los detalles de proyecto y tarea desde el panel de revisión para facilitar el uso

Con estas mejoras, los usuarios pueden esperar lo siguiente:

- Ciclos de revisión eficientes y oportunos
- Menor esfuerzo manual durante los intercambios de comentarios

Para obtener más información, vea [Introducción a la revisión](../user-guide/review.md)

## Experiencia mejorada para crear y utilizar archivos DITAVAL

Esta actualización introduce varias mejoras que simplifican la creación, administración y aplicación de archivos DITAVAL, lo que permite un mejor control sobre el contenido condicional y el estilo en todas las salidas.

Los aspectos destacados son los siguientes:

- **Compatibilidad mejorada con marcas en la creación de archivos DITAVAL:** Experience Manager Guides ofrece nuevas funciones para personalizar la publicación de contenido mediante la compatibilidad mejorada con marcas en archivos DITAVAL. Ahora puede aplicar marcas de inicio y finalización alrededor de contenido específico, incluidas imágenes, y enriquecer las secciones marcadas con opciones de formato como negrita, cursiva, etc. Para controlar las superposiciones de condiciones, se puede configurar el **conflicto de estilo**, que incluye la configuración de un fondo y un color de texto predeterminados, lo que garantiza la claridad y la coherencia en la salida. Estos indicadores son totalmente compatibles con la generación nativa de PDF y la salida resultante refleja de forma precisa y completa todos los elementos de estilo aplicados.
Para obtener más información, vea [Usar el editor DITAVAL](../user-guide/ditaval-editor.md).

  ![](assets/ditaval-flag-style-new.png){width="350" align="left"}

- **Compatibilidad con varios archivos DITAVAL para PDF nativo:** Para PDF nativo, ahora se pueden agregar varios archivos DITAVAL, cada uno de los cuales se muestra como una entrada etiquetada para facilitar la identificación y eliminación, lo que proporciona mayor flexibilidad y control sobre el contenido condicional en las salidas de PDF

  Además, esta actualización mejora la creación de ajustes preestablecidos de salida al habilitar campos DITAVAL editables entre formatos, lo que permite a los usuarios especificar manualmente las rutas DITAVAL.

  Para obtener más información, vea [Comprender los ajustes preestablecidos de salida](../user-guide/generate-output-understand-presets.md) en Experience Manager Guides.

## Mejoras de publicación

Se han realizado las siguientes mejoras de publicación como parte de la nueva versión:

### Filtrado mejorado del registro de generación de salida

Esta versión incorpora mejoras en la interfaz de usuario a la capacidad de filtrado de registros de generación de salida. Ahora puede filtrar mejor los registros de generación de salida para los cuatro niveles distintos; **Información**, **Advertir**, **Error** (incluidos errores y excepciones) y **Grave**; con indicadores de color mejorados e intuitivos que simplifican el análisis y agudizan la visibilidad en el flujo de registro. Esta mejora le permite navegar por los registros de forma más eficaz y localizar los problemas críticos con precisión.

Para obtener más información, vea [Solución de problemas básica](../user-guide/generate-output-basic-troubleshooting.md).

![](./assets/log-file-new.png){align="left"}


### Los archivos temporales para la salida publicada ahora incluyen las direcciones URL de autor y publicación en un nuevo archivo de configuración

Las mejoras de publicación más recientes para Experience Manager Guides ahora agregan un nuevo archivo `system_config.xml` a los archivos temporales generados al publicar salidas de HTML, PDF y JSON mediante DITA-OT, así como salida nativa de PDF. Este archivo se incluye automáticamente en el trabajo de publicación y también se puede acceder a él mediante archivos temporales cuando se habilita la opción **Conservar archivos temporales** para los ajustes preestablecidos y se genera el resultado.

El archivo `system_config.xml` contiene detalles de la instancia de AEM, incluidas la URL del autor, la URL local y la URL de publicación, que proporcionan un contexto más claro y mejoran la trazabilidad de las URL descargadas.

Para obtener más información, vea [Comprender los ajustes preestablecidos de salida](../user-guide/generate-output-understand-presets.md).

### Nueva compatibilidad con variables de ruta de salida para la generación de resultados

Esta actualización presenta la configuración dinámica `output path` para ajustes preestablecidos de salida como Native PDF, DITA-OT PDF, JSON, HTML5 y Custom. En lugar de utilizar una ruta de acceso fija, los usuarios ahora pueden definir la ubicación de salida mediante la variable `${base_output_path}` durante la instalación, lo que ofrece una mayor flexibilidad. La ruta predeterminada anterior `/content/dam/fmdita-outputs` ya no es obligatoria.

Todas las rutas de salida asociadas con los ajustes preestablecidos de perfil de carpeta global se migrarán automáticamente para utilizar la nueva variable de ruta de salida base. Sin embargo, para los perfiles de carpeta personalizados, la migración no es automática; se recomienda ponerse en contacto con el equipo de éxito del cliente para obtener ayuda.

Para obtener más información, vea [Comprender los ajustes preestablecidos de salida](../user-guide/generate-output-understand-presets.md).

### La línea base exportada ahora incluye el estado del documento

La característica Exportar línea de base ahora incluye el **estado del documento** junto con detalles clave como el título, el nombre de archivo, el tipo de archivo y el número de versión en la instantánea de línea de base. Esta mejora mejora la gestión de la línea de base al proporcionar una visión general más completa de la línea de base.

Para obtener más información, vea [Crear y administrar líneas de base desde la consola de mapas](../user-guide/web-editor-baseline.md#manage-baselines).

### Compatibilidad con la publicación incremental impulsada por línea de base mediante el panel de asignación para la salida de AEM Sites mediante la asignación de componentes heredados

El proceso de generación de resultados incrementales se ha mejorado para admitir la publicación de versiones específicas de temas definidos en la línea de base seleccionada para sitios de AEM mediante la asignación de componentes heredados, lo que garantiza la propagación precisa del contenido en la salida.

Para obtener más información, vea [Generación incremental de resultados](../user-guide/generate-output-aem-site.md).

## Mejoras del editor

Se han realizado las siguientes mejoras de editor como parte de la nueva versión:

### Experiencia de búsqueda mejorada para el panel de contenido reutilizable

Experience Manager Guides presenta una experiencia de búsqueda mejorada en el panel Contenido reutilizable. Con esta actualización, la búsqueda de cualquier palabra clave ahora analiza todos los archivos añadidos como contenido reutilizable, y no solo los abiertos, lo que garantiza que encuentre la posición exacta de la palabra clave en todas las ocurrencias, ya sean contenedores abiertos o contraídos. Además, cuando borra la barra de búsqueda, se conserva el estado original de todos los contenedores, lo que proporciona una funcionalidad de búsqueda más eficiente y fácil de usar.

Para obtener más información, vea [Contenido reutilizable](../user-guide/web-editor-features.md#reusable-content).

### Atributo &quot;Format&quot; añadido para vínculos de referencia

Adobe Experience Manager Guides ahora agrega un atributo **format** para los vínculos de referencia dentro del Editor. Este atributo se muestra en la **vista de Source** e indica claramente el tipo de archivo, como:

- Para los archivos con una extensión **.pdf**, el formato se establecerá en **pdf**
- Para los archivos con una extensión **.html**, el formato se establecerá en **html**
- Para los archivos con **.dita** o **.ditamap**, el formato se establecerá en **dita**

Además, los archivos con una extensión **.xml** también tendrán el formato establecido en **dita**. Para los archivos sin extensión, el formato se deja en blanco. Además, para cualquier vínculo de referencia con un ámbito establecido en **external**, el formato se establecerá en **html** independientemente de la extensión de archivo de los vínculos de referencia.

### Opciones mejoradas de descarga de mapas en el editor

Experience Manager Guides presenta una nueva opción **Usar nombres de archivo reales** en el cuadro de diálogo **Descargar mapa**. Ahora, al descargar archivos de asignación, puede elegir mantener sus nombres de archivo originales en lugar de los UUID predeterminados, lo que facilita en gran medida el reconocimiento y la administración de sus archivos. Esta opción solo está disponible si selecciona **Conservar jerarquía de archivos** y se deshabilita al elegir **Acoplar jerarquía de archivos**, lo que le proporciona más flexibilidad para organizar las asignaciones descargadas.

Para obtener más información, vea [Descargar archivos](../user-guide/authoring-download-assets.md#download-a-dita-map-file-from-the-editor).

![](assets/download-map-dialog-new.png){width="300" align="left"}

### Tiempo de espera de sesión para evitar la pérdida accidental de contenido

Ahora, un mensaje emergente le notifica cuando caduca la sesión de Adobe Experience Manager y cuando ha cerrado la sesión debido a la inactividad. Este mensaje se activa cuando intenta editar contenido en Experience Manager Guides después de que finalice la sesión. La función ayuda a reducir el riesgo de perder trabajo no guardado y mejora la fiabilidad y fluidez generales de la experiencia, incluso durante períodos de inactividad.

![](assets/sign-out-prompt.png)

Obtenga más información acerca de [solicitud de tiempo de espera de sesión](../user-guide/session-timeout-prompt.md) en Experience Manager Guides.

### Tratamiento mejorado de `navref` en el editor

Las mejoras más recientes realizadas en el Editor mejoran el control de `navref` elementos en un mapa DITA. Ahora, cuando agregue un elemento `navref` a un mapa, se abrirá el cuadro de diálogo **Seleccionar ruta**, que le permitirá elegir fácilmente las referencias de mapa que se incluirán como vínculos de navegación en el mapa. Una vez añadido, el título del mapa añadido se muestra en las vistas Autor y Presentación, lo que proporciona una mejor visibilidad de la navegación incluida durante la creación.  Además, el elemento `navref` agregado se resuelve automáticamente para mostrar el mapa referido en el Editor.

Para obtener más información, vea [Agregar referencias de navegación](../user-guide/map-editor-other-features.md#add-navigation-references).


### Mejoras en la IU en la barra de herramientas del Editor y Preferencias de usuario

Con esta versión, se ha reestructurado la configuración de las **preferencias de usuario** en la página de inicio para las fichas General y Apariencia. Incluye cambiar el nombre de la etiqueta **Abrir las preferencias de los mapas** y mover el conmutador Espacios de no separación a la barra de herramientas del Editor.

Además, en la barra de herramientas del Editor, algunos toggles de acceso rápido para habilitar o deshabilitar los cambios de seguimiento, las etiquetas y los espacios de no separación ahora se agrupan en la opción **Mostrar** en el menú desplegable de Menú para mejorar el uso.

Para obtener más información, vea [Barra de herramientas en el editor](../user-guide/web-editor-toolbar.md#menu-dropdown).







