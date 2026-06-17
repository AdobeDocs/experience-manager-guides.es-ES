---
title: Completar la tarea de revisión como revisor
description: Obtenga información sobre cómo marcar una tarea como completada como revisor en AEM Guides.
feature: Reviewing
role: User
exl-id: 99b64fb5-c509-41cf-b091-ba78b90db481
TQID: https://experienceleague.adobe.com/Ttty7SNmwHvrs-Ma5SN0JqjQRR3Y6yM-W-ozgQ3Vcyg
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 0763896c75767d8a4bffc019d42c129e2e34f4be
workflow-type: tm+mt
source-wordcount: 691
ht-degree: 0%

---

# Completar la tarea de revisión como revisor

>[!IMPORTANT]
>
> Las nuevas funciones descritas en este artículo se habilitan de forma predeterminada con la versión 2508 de Experience Manager Guides as a Cloud Service. Las revisiones creadas antes de la migración no se ven afectadas y seguirán utilizando el flujo de trabajo anterior. Si prefiere seguir utilizando las funciones existentes sin estas actualizaciones, póngase en contacto con el equipo de éxito del cliente para que se deshabiliten las nuevas funciones.

Como revisor, puede marcar una tarea de revisión como completada una vez que haya revisado todo el contenido y desee notificarlo al autor. También puede dejar cualquier comentario final en este momento.

Siga estos pasos para completar una tarea de revisión:

1. Abra la tarea de revisión asignada.
2. Seleccione **Marcar como listo** en la parte superior como se muestra a continuación:

   ![](images/review-task-mark-as-done.png){width="350"}

   Se muestra el cuadro de diálogo **Completar tarea**.
3. En el cuadro de diálogo **Completar tarea**, agregue los comentarios finales para el autor y seleccione **Completar**.

   >[!NOTE]
   >
   > Los comentarios de nivel de tarea sirven como resumen o comentarios finales y son distintos de los comentarios de nivel de texto agregados durante la revisión del tema. En este cuadro de diálogo, puede esbozar acciones de seguimiento como solicitar al autor que dirija comentarios específicos y reenvíe la tarea para su revisión o indicar que la revisión ha finalizado.

   Por ejemplo, como revisor, puede agregar un comentario como acción de seguimiento para el autor:

   ![](images/complete-task-dialog-followup.png){width="350"}

   O bien, agregue un comentario para indicar la finalización de la tarea, como se muestra a continuación:

   ![](images/complete-task-dialog.png){width="350"}


Ha marcado correctamente la tarea como completada y su estado ahora se establece en **Completada**. No se permiten más acciones una vez que la tarea se marca como completada. Se envía una notificación al autor o al iniciador de la tarea de revisión para llamar su atención inmediatamente. Para obtener más información sobre el déclencheur de las notificaciones de revisión, consulte [Explicación de las notificaciones de revisión](./review-understanding-review-notifications.md).

![](images/task-completed-status.png){width="350"}

En función de los comentarios, si el autor o el iniciador de la tarea decide [cerrar la tarea de revisión](./review-close-review-task.md), el estado de la tarea en la interfaz de usuario de revisión cambia a **Cerrada**.

![](images/review-status-closed-review-ui.png){width="350"}

>[!NOTE]
>
>De manera predeterminada, cuando un revisor marca una tarea de revisión como **Completada**, la tarea permanece en la Bandeja de entrada de AEM del revisor hasta que el autor o el iniciador de la tarea revise los comentarios y cierre la tarea de revisión.
>
>Sin embargo, puede optar por habilitar la sincronización de tareas entre la interfaz de usuario de revisión y la bandeja de entrada de AEM. Cuando esta característica está habilitada, al marcar una tarea de revisión como **Completada** en la interfaz de usuario de revisión, se completa automáticamente la tarea correspondiente y se quita de la Bandeja de entrada de AEM del revisor. Del mismo modo, al completar una tarea desde la bandeja de entrada AEM, se marca automáticamente como completada en la interfaz de usuario de revisión.
>
>El autor o el iniciador de la tarea pueden seguir revisando los comentarios y reasignando la tarea si se requiere una revisión adicional. Cuando se reasigna una tarea, se genera una nueva notificación en la bandeja de entrada AEM para el revisor, que permite volver a revisar la tarea.
>
>Para habilitar esta función en su entorno, póngase en contacto con el equipo de éxito del cliente.


## Ver comentarios de nivel de tarea

Todos los comentarios de nivel de tarea se muestran en el cuadro de diálogo **Comentarios sobre tareas**, que está disponible en el modo de solo lectura. Cuando complete una tarea de revisión con un comentario final, la entrada se registra en este cuadro de diálogo para referencia futura.

Para acceder a los comentarios de nivel de tarea desde la interfaz de usuario de revisión, vaya al panel izquierdo y seleccione el icono **Comentarios de tarea**.

![](images/task-comments-icon.png){width="350"}

El cuadro de diálogo **Comentarios de la tarea** se muestra a la derecha.

![](images/task-comments-reviewer.png){width="350"}

Los comentarios del cuadro de diálogo se muestran en orden cronológico, con los comentarios recientes apareciendo primero y los más antiguos apareciendo últimos. Este orden le ayuda a seguir la conversación a medida que progresa con el tiempo.

El cuadro de diálogo **Comentarios de la tarea** es accesible para todos los usuarios involucrados en la tarea de revisión, incluidos el autor o iniciador de la tarea de revisión y otros revisores. Por lo tanto, los comentarios de otros revisores (si están implicados) también pueden aparecer en el cuadro de diálogo Comentarios sobre la tarea. Esto ayuda a garantizar una comunicación clara y rastreable a lo largo del proceso de revisión.

Después de revisar los comentarios de nivel de tarea, el autor puede solicitar una nueva revisión o cerrar la tarea de revisión. En ambos casos, todos los comentarios capturados durante el proceso de revisión permanecen disponibles en el cuadro de diálogo **Comentarios de la tarea** como referencia.
