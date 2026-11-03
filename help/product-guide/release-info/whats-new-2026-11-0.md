---
title: Notas de versión | Novedades de la versión 2026.11.0 de Adobe Experience Manager Guides
description: Explore las nuevas funciones de la versión 2026.11.0 de Adobe Experience Manager Guides, incluida la ramificación en el nivel de mapa y la creación de contenido del asistente de IA.
role: Leader
source-git-commit: ef5e433214f15b12102af7c9e38031536183ca72
workflow-type: tm+mt
source-wordcount: '1512'
ht-degree: 0%
---

# Novedades de la versión 2026.11.0 (noviembre de 2026)

Este artículo cubre las funciones nuevas y mejoradas introducidas con la versión 2026.11.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener la lista de problemas corregidos en esta versión, vea [Problemas corregidos en la versión 2026.11.0](fixed-issues-2026-11-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2026.11.0](../release-info/upgrade-instructions-2026-11-0.md).

## Introducción a la bifurcación y combinación a nivel de mapa

Adobe Experience Manager Guides introduce una capacidad de ramificación y combinación a nivel de mapa, que permite a los autores trabajar en varias versiones de documentación, actualizaciones de funciones y correcciones críticas en paralelo sin afectar al contenido principal. Los autores pueden crear ramas aisladas de un mapa DITA y sus dependencias, asegurándose de que las ediciones, los bloqueos y las vistas previas son específicos de cada rama.

Esta capacidad ayuda a los equipos de documentación a administrar flujos de trabajo paralelos, colaborar de forma eficaz y mantener la estabilidad de la versión de la documentación principal. Puede hacer lo siguiente:

- **Cree ramas** a partir de la versión principal de un mapa DITA para trabajar en funciones, mejoras o correcciones críticas de forma independiente.
- **Cambie entre ramas** en el editor para administrar varias versiones de la documentación.
- **Administrar versiones de contenido** para organizar los cambios mediante bifurcación y combinación.
- **Resolver conflictos de combinación** mediante un flujo de trabajo de comparación guiada con combinación tridireccional.
- **Combinar cambios** en la versión principal.
- **Publicar directamente desde una rama** usando publicación estándar sin modificar la versión principal.

Más información sobre [bifurcación y combinación](../user-guide/branching-overview.md).

![](./assets/branching.png){width="650"}


## Creación de contenido con tecnología de IA y habilidades de importación en el asistente de IA

>[!NOTE]
>
>Para utilizar el asistente de IA en modo automático, su organización debe estar integrada en Adobe CX Enterprise Coworker y tener los créditos necesarios.

Ahora, puede usar **Asistente de IA** para crear e importar contenido DITA con indicaciones en lenguaje natural. Con la tecnología **Adobe CX Enterprise Coworker**, las nuevas habilidades de **Create** e **Import** simplifican la creación de contenido estructurado y ayudan a los autores a trabajar con contenido DITA sin necesidad de tener mucha experiencia en DITA.

- **Crear:** Generar temas y asignaciones DITA a partir de peticiones de datos en lenguaje natural, documentos de referencia o contenido existente mediante plantillas de repositorio. Puede revisar el contenido generado antes de guardarlo y refinar de forma iterativa el contenido nuevo o existente para satisfacer sus necesidades.
- **Importar:** Convierta archivos PDF, DOCX o Markdown existentes en mapas y temas DITA estructurados. Puede obtener una vista previa del contenido convertido y revisarlo antes de guardarlo en el repositorio.
- **Etiquetado inteligente:** Obtenga recomendaciones de etiquetas relevantes para su contenido en función de la taxonomía de su organización. La experiencia mejorada permite a los administradores de perfiles de carpeta configurar áreas de nombres de taxonomía en la configuración de Workspace, lo que garantiza recomendaciones de etiquetas coherentes y controladas.

El panel **Asistente de IA** también presenta un modo de pantalla completa y una sección de **Conversaciones activas** para una experiencia de conversación mejorada.

Para obtener más información, vea [Usar el Asistente de IA en el modo Agente](../user-guide/ai-assistant.md#agentic-mode).

![](./assets/preview-import.png){width="650"}


## Nuevo panel Asistente de ayuda en Experience Manager Guides

La capacidad generativa **Ayuda inteligente** con tecnología de IA está disponible a través del panel **Asistente de ayuda**, al que se puede acceder desde las interfaces de la página principal, el editor y la consola de mapas. El panel proporciona una experiencia de búsqueda conversacional que le permite hacer preguntas en lenguaje natural y encontrar rápidamente información relevante en la documentación de Experience Manager Guides. Esto le ayuda a acceder a la guía contextual y a resolver consultas sin salir del Editor, lo que optimiza el flujo de trabajo de creación.

Los administradores pueden administrar la disponibilidad del panel Asistente de ayuda a través de la configuración de Workspace. La sección **Asistente de ayuda de IA** incluye un conmutador para habilitar o deshabilitar el panel para los usuarios.

Para obtener más información, vea [Asistente de ayuda](../user-guide/ai-based-smart-help.md).

![](./assets/help-assistant.png){width="650"}

## Mejoras de creación

### Panel Seguimiento de cambios en el nuevo editor

El panel **Rastrear cambios** está ahora disponible en el nuevo editor, lo que le permite ver todas las inserciones y eliminaciones dentro de un tema. Puede hacer un seguimiento de las ediciones realizadas por varios usuarios y aceptar o rechazar cambios directamente desde el panel.

También puede controlar cómo aparece el contenido eliminado en el Editor mediante la opción **Mostrar eliminaciones de seguimiento en línea** que permite mostrar el contenido eliminado como texto tachado o reemplazarlo con un icono de lápiz vinculado al cambio correspondiente. Más información sobre [Rastrear cambios](../user-guide/config-editor-settings.md#track-changes).

![Configuración del editor](./assets/track-changes-all.png){width="650"}

### Ordenar archivos y carpetas en el panel Explorador

El panel **Explorador** del Editor le permite ordenar archivos y carpetas en orden ascendente o descendente mediante el botón **Ordenar**. De forma predeterminada, los elementos se ordenan en orden ascendente por título o nombre de archivo, según la configuración de **Visualización de archivos del editor** en **Preferencias de usuario**. Esto facilita la navegación y la localización de contenido en el editor.

Para obtener más información, vea la sección [Explorer](../user-guide/paginated-loading-assets.md#explorer) en Carga paginada de archivos y carpetas.

### Administrar versiones y etiquetas para archivos no DITA desde el Editor

Experience Manager Guides permite ver el historial de versiones y administrar las etiquetas de versión de los archivos que no son DITA, como imágenes, multimedia, ZIP, PDF y DOCX, directamente desde el Editor. Puede obtener una vista previa de estos archivos, revisar su historial de versiones, comparar versiones y revertir a una versión anterior sin navegar a la interfaz de usuario de Assets. También puede aplicar o actualizar etiquetas de versión para las versiones de archivos existentes a fin de simplificar la identificación y administración de las versiones.

Para obtener más información, vea [Trabajar con medios y otros archivos que no son DITA](../user-guide/authoring-file-management.md#work-with-media-and-other-non-dita-files).


![Configuración del editor](./assets/version-management-non-dita-files.png){width="650"}


## Revisar mejoras

### Colaboración de revisión mejorada con comentarios del iniciador

Los iniciadores de la revisión pueden agregar comentarios en línea y anotaciones a temas dentro de una tarea de revisión mediante la IU Revisar. Esto les permite proporcionar un contexto adicional, resaltar contenido específico y llamar la atención de los revisores sobre las áreas que requieren comentarios.

Estos comentarios aparecen en el panel **Comentarios** junto con los comentarios de otros revisores, lo que proporciona una vista consolidada de las discusiones de revisión. Los revisores también reciben una notificación de AEM cuando el iniciador agrega un comentario, lo que ayuda a optimizar la colaboración y la comunicación a lo largo del proceso de revisión. Para obtener más información, vea [Agregar comentarios para revisores](../user-guide/review-send-topics-for-review.md#add-comments-for-reviewers).

## Mejoras de publicación

### Ver y administrar el historial de salida desde la consola Mapa

La consola Mapa de Experience Manager Guides ahora incluye una ficha **Historial de resultados**, que le permite ver y administrar las tareas de generación de resultados directamente desde el Editor sin ir al Tablero de mapas.

La pestaña proporciona una vista consolidada de las tareas de generación de resultados, incluido su estado, los detalles preestablecidos, la fecha de generación y la duración. Puede buscar y filtrar tareas, cancelar generaciones en curso, acceder a resultados y registros generados y quitar entradas completadas del historial. También puede exportar el historial de salida como archivo CSV para un análisis más detallado. Los estados de generación de salida utilizan indicadores de color coherentes con el panel Mapa.

Para obtener más información, vea [Administrar el proceso de generación de resultados](../user-guide/generate-output-manage-process.md#view-and-manage-output-generation-tasks-from-the-editor).

![Configuración del editor](./assets/output-history-editor-view.png){width="650"}


### Opciones de purga del historial de salida mejorado

Puede purgar el historial de salida **Por edad** (eliminando las entradas anteriores a un número de días especificado) o **Por recuento** (conservando solamente un número especificado de entradas recientes).

También puede optar por depurar únicamente los registros de salida preservando al mismo tiempo las entradas del historial para fines de auditoría o eliminar tanto los registros como sus entradas asociadas. Estas opciones ayudan a optimizar el almacenamiento del repositorio y, al mismo tiempo, proporcionan un mayor control sobre la depuración del historial de salida.

Para obtener más información, vea [Configurar el período de depuración automática para el historial de resultados](../install-conf-guide/conf-output-generation.md#configure-auto-purging-period-for-output-history-id19aai070v8q).

### Compatibilidad de GitLab con perfiles de publicación de Edge Delivery Services

La publicación en Edge Delivery Services admite repositorios alojados en GitLab junto con GitHub, lo que proporciona una mayor flexibilidad para administrar y publicar contenido DITA. Para publicar en un sitio alojado en GitLab, seleccione GitLab como tipo de servidor al crear un perfil de publicación de Edge Delivery Services y proporcione el token de acceso al proyecto del repositorio en el campo Token de acceso.

Los ajustes preestablecidos de publicación también incluyen un campo para una subcarpeta, de modo que puede publicar contenido en una subcarpeta dentro de la carpeta raíz especificada en el perfil.

Para obtener más información, vea [Configurar un Edge Delivery Services](../knowledge-base/publishing/configure-eds.md).

### Mejoras en la publicación de Salesforce

Experience Manager Guides mejora la publicación de Salesforce con una seguridad, un rendimiento y una eficacia de publicación mejorados. Estas mejoras incluyen compatibilidad con Clave de prueba para intercambio de código (PKCE), autenticación basada en tokens de actualización, estado de publicación en el nivel de artículo, registros de publicación detallados, historial de salida y publicación de recursos optimizada para reducir las cargas redundantes.

Para obtener más información, vea [Publicación mejorada de Salesforce mediante procesamiento back-end](../user-guide/web-editor-article-publishing.md#enhanced-salesforce-publishing-using-backend-processing).


### Compatibilidad con imágenes de metadatos de mapas en PDF nativo

La publicación nativa de PDF admite la visualización dinámica de imágenes definidas en los metadatos de mapas DITA, mapas de libro y mapas personalizados. Puede utilizar una sola plantilla de PDF en varios mapas y mostrar imágenes específicas del mapa, como imágenes de portada de productos, en la salida generada.

Al agregar un marcador de posición de imagen al diseño de página, puede rellenarlo automáticamente con la imagen a la que se hace referencia en los metadatos del mapa durante la publicación. Esto elimina la necesidad de mantener plantillas independientes para distintas imágenes y simplifica la administración de plantillas.

Para obtener más información, vea [Agregar una imagen a partir de los metadatos del mapa](../native-pdf/design-page-layout.md#add-an-image-from-map-metadata-add-image-map-metadata).

### Validar la calidad del contenido con la comprobación de estado del contenido en el antiguo editor

La comprobación del estado del contenido está disponible en el antiguo editor (ya es compatible con el nuevo editor), lo que ayuda a validar la calidad del contenido en los mapas DITA antes de la publicación. Los administradores pueden crear ajustes preestablecidos de comprobación de estado reutilizables combinando comprobaciones de vínculos rotos, ID duplicados y validación de Schematron.

Los autores pueden ejecutar una comprobación de estado en un mapa DITA o una línea de base seleccionada en el antiguo editor para generar un informe consolidado de problemas en los temas y mapas asociados. Para obtener más información, vea [Ejecutar comprobación de estado en un mapa](../user-guide/map-editor-other-features.md#run-health-check-on-a-map).

## Actualización de la API para la migración de contenido heredado

Esta API le permite crear o actualizar contenido y sus metadatos a través de una sola API. Admite la especificación del contenido del tema, los metadatos y un GUID en la solicitud. La API está disponible en la documentación de la API Swagger en `/bin/guides/v1/asset/upsert/`.