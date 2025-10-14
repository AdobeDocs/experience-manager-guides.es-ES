---
title: Notas de versión | Novedades de la versión 2025.08.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las funciones nuevas y mejoradas de la versión 2025.08.0 de Adobe Experience Manager Guides
role: Leader
exl-id: c3461d0a-6394-4275-9d54-b2b1545d7c18
source-git-commit: 1a44af3522060ebc531393d4d01b1cd00eb02c10
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 2%

---

# Novedades de la versión 2025.08.0 (agosto de 2025)

Este artículo cubre las funciones nuevas y mejoradas introducidas con la versión 2025.08.0 de Adobe Experience Manager Guides as a Cloud Service.

Para ver la lista de problemas corregidos en esta versión, consulte [Problemas solucionados en la versión 2025.08.0](fixed-issues-2025-08-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2025.08.0](../release-info/upgrade-instructions-2025-08-0.md).


## Flujo de trabajo de revisión mejorado

Con esta versión, el flujo de trabajo de revisión se ha mejorado considerablemente para admitir mejor la comunicación fluida entre autores y revisores. Las actualizaciones clave incluyen:

- Flujos de trabajo de administración de tareas con notificaciones procesables
- Capacidad para etiquetar usuarios para buscar atención inmediata
- Acceso a los detalles de proyecto y tarea desde el panel de revisión para facilitar el uso

Con estas mejoras, los usuarios pueden esperar lo siguiente:

- Ciclos de revisión eficientes y oportunos
- Menor esfuerzo manual durante los intercambios de comentarios

Para obtener más información, vea [Introducción a la revisión](../user-guide/review.md)

## Acciones configurables del Ayudante de IA en la configuración del Editor

La última actualización presenta una configuración mejorada para **Crear acciones rápidas** en el Asistente de IA, lo que permite a los administradores personalizar el entorno de creación según flujos de trabajo y preferencias específicos.

Una vez habilitada la opción **Asistente de IA**, los administradores pueden elegir selectivamente qué acciones rápidas están visibles en la pestaña **Creación**, lo que ayuda a optimizar las interacciones de autor. Esta configuración de visibilidad es específica para cada perfil de carpeta.

Obtenga más información acerca del [asistente de IA en la configuración del editor](../cs-install-guide/workspace-settings.md#general) en Experience Manager Guides.

![](assets/authoring-quick-actions.png){width="350" align="left"}


## Experiencia mejorada para crear y utilizar archivos DITAVAL

Esta actualización introduce varias mejoras que simplifican la creación, administración y aplicación de archivos DITAVAL, lo que permite un mejor control sobre el contenido condicional y el estilo en todas las salidas.

Los aspectos destacados son los siguientes:

- **Compatibilidad mejorada con marcas en la creación de archivos DITAVAL:** Experience Manager Guides ofrece nuevas funciones para personalizar la publicación de contenido mediante la compatibilidad mejorada con marcas en archivos DITAVAL. Ahora puede aplicar marcas de inicio y finalización alrededor de contenido específico, incluidas imágenes, y enriquecer las secciones marcadas con opciones de formato como negrita, cursiva, etc. Para controlar las superposiciones de condiciones, se puede configurar el **conflicto de estilo**, que incluye la configuración de un fondo y un color de texto predeterminados, lo que garantiza la claridad y la coherencia en la salida. Estos indicadores son totalmente compatibles con la generación nativa de PDF y la salida resultante refleja de forma precisa y completa todos los elementos de estilo aplicados.
Para obtener más información, vea [Usar el editor DITAVAL](../user-guide/ditaval-editor.md).

  ![](assets/ditaval-flag-style-new.png){width="350" align="left"}

- **Compatibilidad con varios archivos DITAVAL para PDF nativo:** Para PDF nativo, ahora se pueden agregar varios archivos DITAVAL, cada uno de los cuales se muestra como una entrada etiquetada para facilitar la identificación y eliminación, lo que proporciona mayor flexibilidad y control sobre el contenido condicional en las salidas de PDF

  Además, esta actualización mejora la creación de ajustes preestablecidos de salida al habilitar campos DITAVAL editables entre formatos, lo que permite a los usuarios especificar manualmente las rutas DITAVAL.

  Para obtener más información, vea [Comprender los ajustes preestablecidos de salida](../user-guide/generate-output-understand-presets.md) en Experience Manager Guides.

## Filtrado mejorado del registro de generación de salida

Esta versión incorpora mejoras en la interfaz de usuario a la capacidad de filtrado de registros de generación de salida. Ahora puede filtrar mejor los registros de generación de salida para los cuatro niveles distintos; **Información**, **Advertir**, **Error** (incluidos errores y excepciones) y **Grave**; con indicadores de color mejorados e intuitivos que simplifican el análisis y agudizan la visibilidad en el flujo de registro. Esta mejora le permite navegar por los registros de forma más eficaz y localizar los problemas críticos con precisión.

Para obtener más información, vea [Solución de problemas básica](../user-guide/generate-output-basic-troubleshooting.md).

![](./assets/log-file-new.png){align="left"}


## Los archivos temporales para la salida publicada ahora incluyen las direcciones URL de autor y publicación en un nuevo archivo de configuración

Las mejoras de publicación más recientes para Experience Manager Guides ahora agregan un nuevo archivo `system_config.xml` a los archivos temporales generados al publicar salidas de HTML, PDF y JSON mediante DITA-OT, así como salida nativa de PDF. Este archivo se incluye automáticamente en el trabajo de publicación y también se puede acceder a él mediante archivos temporales cuando se habilita la opción **Conservar archivos temporales** para los ajustes preestablecidos y se genera el resultado.

El archivo `system_config.xml` contiene detalles de la instancia de AEM, incluidas la URL del autor, la URL local y la URL de publicación, que proporcionan un contexto más claro y mejoran la trazabilidad de las URL descargadas.

Para obtener más información, vea [Comprender los ajustes preestablecidos de salida](../user-guide/generate-output-understand-presets.md).

## Nueva compatibilidad con variables de ruta de salida para la generación de resultados

Esta actualización presenta la configuración dinámica `output path` para ajustes preestablecidos de salida como Native PDF, DITA-OT PDF, JSON, HTML5 y Custom. En lugar de utilizar una ruta de acceso fija, los usuarios ahora pueden definir la ubicación de salida mediante la variable `${base_output_path}` durante la instalación, lo que ofrece una mayor flexibilidad. La ruta predeterminada anterior `/content/dam/fmdita-outputs` ya no es obligatoria.

Todas las rutas de salida asociadas con los ajustes preestablecidos de perfil de carpeta global se migrarán automáticamente para utilizar la nueva variable de ruta de salida base. Sin embargo, para los perfiles de carpeta personalizados, la migración no es automática; se recomienda ponerse en contacto con el equipo de éxito del cliente para obtener ayuda.

Para obtener más información, vea [Comprender los ajustes preestablecidos de salida](../user-guide/generate-output-understand-presets.md).

## Mejoras en la IU en la barra de herramientas del Editor y Preferencias de usuario

Con esta versión, se ha reestructurado la configuración de las **preferencias de usuario** en la página de inicio para las fichas General y Apariencia. Incluye cambiar el nombre de la etiqueta **Abrir las preferencias de los mapas** y mover el conmutador Espacios de no separación a la barra de herramientas del Editor.

Además, en la barra de herramientas del Editor, algunos toggles de acceso rápido para habilitar o deshabilitar los cambios de seguimiento, las etiquetas y los espacios de no separación ahora se agrupan en la opción **Mostrar** en el menú desplegable de Menú para mejorar el uso.

Para obtener más información, vea [Barra de herramientas en el editor](../user-guide/web-editor-toolbar.md#menu-dropdown).
