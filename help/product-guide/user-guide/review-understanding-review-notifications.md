---
title: Explicación de las notificaciones de revisión
description: Obtenga información sobre los distintos tipos de notificaciones de revisión y cómo entran en déclencheur durante las distintas fases del flujo de trabajo de revisión en Experience Manager Guides.
feature: Reviewing
role: User
source-git-commit: b7648fe1d36de3c243ca5a55f42a41f7523056ce
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 0%

---

# Explicación de las notificaciones de revisión

>[!IMPORTANT]
>
> Las nuevas funciones descritas en este artículo se habilitan de forma predeterminada con la versión 2508 de Experience Manager Guides as a Cloud Services. Las revisiones creadas antes de la migración no se ven afectadas y seguirán utilizando el flujo de trabajo anterior. Si prefiere seguir utilizando las funciones existentes sin estas actualizaciones, póngase en contacto con el equipo de éxito del cliente para que se deshabiliten las nuevas funciones.

Experience Manager Guides optimiza la colaboración entre autores y revisores a través de un flujo de trabajo de revisión estructurado. Como parte de este flujo de trabajo, las notificaciones desempeñan un papel clave a la hora de mantener informados a todos los participantes de una tarea de revisión y responder a los cambios.

Cada vez que se realiza una acción relacionada con la revisión, como una asignación de tareas, una finalización o actualizaciones de comentarios, se envía una notificación automáticamente a los usuarios implicados en la tarea de revisión para llamar su atención inmediatamente. Estas notificaciones se entregan en dos formatos:

- **Notificaciones de AEM**: Se muestran en la interfaz de AEM.
- **Notificaciones por correo electrónico**: enviadas directamente a la bandeja de entrada del usuario.

La siguiente tabla proporciona información general sobre los diferentes tipos de notificaciones de revisión, qué acciones los almacenan en déclencheur y cómo aparecen en los diferentes formatos:


## Revisar formatos de notificación con valores de muestra

| **Acción de revisión** | **Título de notificación (AEM)** | **Texto de notificación (AEM)** | **Asunto del correo electrónico** | **Texto de notificación por correo electrónico** | **Destinatario** |
|-----------------------------|--------------------------------------------------|-------------------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------|-----------------------------|
| Revisar tarea creada | Tarea de revisión asignada: **Revisión de página principal** | Asignado por **autor** | Tarea de revisión asignada: **Revisión de página principal** | **El autor** ha creado una tarea de revisión **Revisión de página principal** en el proyecto **WebDocs Revamp** con fecha de vencimiento **15 de agosto de 2025**. Se le ha asignado como revisor. | **Revisor** |
| Comentarios enviados | Comentarios de revisión recibidos para **revisión de página principal** | Comentarios de **revisor** | Comentarios de revisión recibidos para **revisión de página principal** | El **revisor** ha enviado comentarios sobre la tarea **Revisión de la página principal** en el proyecto **Revisión de WebDocs**. Revise y realice las actualizaciones necesarias con mucha antelación al plazo de vencimiento **15 de agosto de 2025**. | **Autor** o **Iniciador de tarea** |
| Nueva revisión solicitada | Se ha solicitado una nueva revisión para **revisión de página principal** | Solicitado por **autor** | Se ha solicitado una nueva revisión para **revisión de la página principal** por parte del **autor** | **El autor** ha actualizado el documento de la tarea **Revisión de la página principal** basándose en sus comentarios y está solicitando una nueva revisión. Se debe revisar con mucha anticipación a la fecha de vencimiento **15 de agosto de 2025**. | **Revisor** |
| Revisión cerrada | Se ha cerrado la tarea de revisión: **Revisión de la página principal** | Cerrado por **autor** | Se ha cerrado la tarea de revisión: **Revisión de la página principal** | La tarea de revisión **Revisión de página principal** en el proyecto **WebDocs Revamp** ha sido cerrada por **Autor**. | **Autor** o **Iniciador de la tarea** , **Revisor** |
| Revisor sin asignar | Se quitó la asignación de la tarea de revisión **Revisión de página principal** | Desasignado por **Autor** | Se quitó la asignación de la tarea de revisión **Revisión de página principal** | El **autor** le ha desasignado de la tarea de revisión **Revisión de página principal** en el proyecto **Revisión de WebDocs**. | **Revisor** |
| Mención de etiqueta | Mencionado en el comentario de la tarea de revisión de **revisión de la página principal** | Mencionado por **autor** | Mencionado en el comentario de la tarea de revisión de **revisión de la página principal** | Se le ha mencionado en un comentario sobre la tarea **Revisión de página principal** en **Revisión de WebDocs** por parte de **Autor**. **Extracto del comentario:** *&quot;Actualice la estructura del encabezado para seguir las directrices de accesibilidad.&quot;* | **Usuario mencionado** |
| Contenido actualizado durante la revisión | Se actualizó el tema en la tarea de revisión **Revisión de la página principal** | Actualizado por **Autor** | Se actualizó el tema en la tarea de revisión **Revisión de la página principal** | **El autor** ha actualizado las versiones de los temas para la tarea de revisión **Revisión de la página principal**. Se debe revisar con mucha anticipación a la fecha de vencimiento **15 de agosto de 2025**. | **Revisor** |


En la tabla anterior, el **texto en negrita** representa valores de muestra y está controlado por variables predefinidas que se pueden usar en las notificaciones.


Por ejemplo:

- **Revisión de página principal** es un nombre de tarea de ejemplo.
- **Priya** (autor) y **John** (revisor) son nombres de usuario de ejemplo.
- **WebDocs Revamp** es un nombre de proyecto de ejemplo.
- **15 de agosto de 2025** es una fecha de vencimiento de ejemplo.

Además, si una tarea contiene comentarios, se incluye un extracto de comentario ( parte del comentario completo) en la notificación por correo electrónico. El extracto se muestra en los casos siguientes:

- Cuando se le etiqueta en un comentario, aparece un extracto del comentario etiquetado en la notificación por correo electrónico.
- Cuando se agrega un comentario de nivel de tarea a una tarea de revisión de la que forma parte, aparece un extracto de ese comentario en la notificación por correo electrónico.

Para obtener una lista completa de variables predefinidas y revisar la personalización de las notificaciones, vea [Configurar y personalizar flujos de trabajo](../cs-install-guide/customize-workflows.md#customize-email-and-aem-notification-templates).




**Tema principal:**[ Introducción a la revisión](review.md)
