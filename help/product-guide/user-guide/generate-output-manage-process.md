---
title: Generación de salida
description: Administre el proceso de generación de resultados en AEM Sites, PDF, HTML5, EPUB, personalizado y JSON a través de complementos DITA-OT, publicación nativa de PDF y FMPS en AEM Guides.
feature: Publishing
role: User
source-git-commit: b061bcbcefba1700665bed33f017a962e84a0433
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 0%

---

# Administrar proceso de generación de resultados

Adobe Experience Manager Guides permite realizar las siguientes acciones en la salida generada:

- [Ver el estado de la tarea de generación de resultados](#view-the-status-of-the-output-generation-task)
- [Cancelar una tarea de generación de resultados](#cancel-an-output-generation-task)
- [Eliminar una tarea de salida](#delete-an-output-task)

## Ver el estado de la tarea de generación de resultados

Una vez iniciada la tarea de generación de resultados para una asignación o regenerada los temas seleccionados, Experience Manager Guides envía esta tarea a la cola de generación de resultados. Esta cola se actualiza en tiempo real y muestra el estado de cada tarea de generación de salida de la cola.

1. En la interfaz de usuario de Assets, vaya y abra el archivo de asignación para el que desea comprobar el estado de generación de salida.

1. Seleccione **RESULTADOS**.

   ![](images/output-queued.png){width="800" align="left"}

   La página Resultados se divide en dos partes:

   - **Salidas en cola:**

     Enumera las salidas que están a la espera de generarse o en proceso de generación. Las tareas en cola o en curso se muestran con un icono de color azul antes del nombre del ajuste preestablecido. También puede encontrar la configuración de generación de resultados o el ajuste preestablecido utilizado para la tarea en cola, el tipo, el usuario que inició la tarea, el tiempo desde que se puso en cola la tarea y el estado actual.

     Seleccione el enlace para acceder a **Tablero de publicación** y ver el estado de ejecución actual. En el tablero de publicación hay disponible una lista de todas las tareas de publicación activas. **Salidas en cola** y el vínculo **Panel de publicación** solo se muestran cuando hay salidas que están a la espera de ser generadas o en proceso de generación. No aparecen cuando se han completado las tareas de salida. Para obtener más información sobre el panel de publicación, vea [Administrar tareas de publicación mediante el panel de publicación](generate-output-publish-dashboard.md#).

   - **Salidas generadas**

     Enumera las tareas de salida que se han completado. De nuevo, la información que se muestra aquí es similar a la sección Salidas en cola con algunas diferencias. Tiene un nuevo conjunto de información en forma de icono de resultado de salida y el tiempo de generación de salida.

     En esta lista, puede tener tareas que se hayan ejecutado correctamente, tareas que se hayan ejecutado con un mensaje o tareas fallidas. Las tareas correctas se muestran con un icono de color verde, las tareas con un mensaje tienen un icono de color naranja y las tareas fallidas se muestran con un icono de color rojo.

     Para todas las tareas, el proceso de publicación crea un archivo de registro \(logs.txt\) al que se puede acceder seleccionando el vínculo en la columna Generated At. Para las tareas que han fallado o tienen mensajes, puede comprobar el archivo de registro, que se explica en la sección [Ver y comprobar el archivo de registro](generate-output-basic-troubleshooting.md#id1822G0P0CHS).

     >[!NOTE]
     >
     > Al seleccionar el vínculo de la salida de PDF generada, se le pide que descargue PDF.


## Cancelar una tarea de generación de resultados

Experience Manager Guides ofrece a los editores una forma sencilla y sencilla de cancelar cualquier tarea de publicación en curso. Como editor, puede cancelar una tarea de publicación en curso desde la consola de mapas DITA o el [Panel de publicación](generate-output-publish-dashboard.md#).

Realice los siguientes pasos para cancelar una tarea de generación de salida desde la consola de mapas DITA:

1. En la interfaz de usuario de Assets, vaya y abra el archivo de asignación para el que desea cancelar una tarea de generación de salida en curso.

1. Seleccione **RESULTADOS**.

1. En la lista **Salidas en cola**, pase el puntero sobre una tarea que desee cancelar.

1. Seleccione el icono **Cancelar este trabajo**.

   ![](images/cancel-publish-task-map-console.png){width="800" align="left"}

1. Seleccione **Sí** en el mensaje de **Confirmar cancelación**.

   ![](images/confirm-cancel-output-map-console.png){width="800" align="left"}

   Si la tarea aún no se ha iniciado, el comando cancel se ejecuta en la tarea. Para una tarea que se está cancelando, el estado se establece en Cancelando.

   Una vez cancelada correctamente la tarea, se mueve a la lista **Salidas generadas** con el estado **Cancelado**. Cuando pasa el ratón por encima de la tarea cancelada, se muestra el nombre del usuario que ha cancelado la tarea. En la siguiente captura de pantalla, se cancela la tarea *HTML5*.

   ![](images/cancelled-output-task.png){width="800" align="left"}


## Eliminar una tarea de salida

Cuando se generan varias salidas para un mapa DITA, durante un periodo de tiempo la lista de salidas generadas para dicho mapa se vuelve muy larga. Como editor, puede limpiar el historial de salida de cualquier archivo de asignación eliminando las tareas obsoletas de la lista *Salidas generadas*. Tenga en cuenta que la salida no se elimina del sistema, solo la entrada de la salida generada se elimina de la lista *Salidas generadas*.

Realice los siguientes pasos para quitar una tarea de salida de la lista Salida generada:

1. En la interfaz de usuario de Assets, vaya y abra el archivo de asignación desde el que desea eliminar las tareas.

1. Seleccione **RESULTADOS**.

1. En la lista **Salidas generadas**, pase el puntero sobre la tarea que desee eliminar.

1. Seleccione el icono Eliminar.

   ![](images/delete-output-task.png){width="800" align="left"}

1. Seleccione **Sí** en el mensaje de **Confirmar eliminación**.

   La tarea se elimina de la lista Resultados generados.

