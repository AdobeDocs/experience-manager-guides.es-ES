---
title: Generar salida para un mapa DITA desde la consola de mapas
description: Generar salida para un mapa DITA desde la consola de mapas de AEM Guides. Obtenga información sobre la generación de resultados incrementales y cómo ver el estado, cancelar y eliminar una tarea de salida.
feature: Publishing
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '1418'
ht-degree: 0%

---

# Generar salida para un mapa DITA desde la consola de mapas {#id1825FG00UHT}

Realice los siguientes pasos para generar la salida de un mapa DITA:

1. En la interfaz de usuario de Assets, vaya al archivo de mapa DITA que desee publicar y haga clic en él.

   Aparecerá la consola de mapas DITA con la lista de Ajustes preestablecidos de salida disponibles para generar la salida.

1. Seleccione uno o varios ajustes preestablecidos de salida que desee utilizar para generar la salida.

   ![](images/generate-multiple-outputs-uuid.png){width="800" align="left"}

   >[!NOTE]
   >
   > AEM AEM Si está generando la salida del sitio de la, el proceso de publicación utiliza la estructura definida en el archivo `.ditamap` para crear la estructura del sitio de la publicación de la página de destino de la página para crear la estructura del sitio de la publicación de la página de destino de la página de destino.

1. Haga clic en el icono Generate para iniciar el proceso de generación de resultados.


Puede ver el estado actual de la solicitud de generación de resultados haciendo clic en Salidas. Para obtener más información, vea [Ver el estado de la tarea de generación de resultados](#viewing_output_history)

>[!IMPORTANT]
>
> Si un proceso de generación de resultados de un ajuste preestablecido está en cola o en curso, no se puede iniciar otra tarea de generación de resultados para el mismo ajuste preestablecido.

Se puede generar la salida del PDF para uno o más ajustes preestablecidos de salida creados para un mapa DITA desde el Editor Web. Para obtener más información, consulte [Usar el panel Generación rápida para generar y ver los resultados de los ajustes preestablecidos](web-editor-quick-generate-panel.md#).

AEM También se puede generar la salida del sitio de para uno o más temas, o todo el mapa DITA desde el Editor Web. Para obtener más información, consulte [Publicación basada en artículos desde el editor web](web-editor-article-publishing.md#id218CK0U019I).

## Generación incremental de resultados {#generating_standalone_topic}

>[!NOTE]
>
> AEM La generación de resultados incrementales solo se aplica a la salida del sitio de la. Además, sólo se pueden regenerar temas DITA \(.dita/.xml\) desde un mapa o submapas DITA. Si selecciona un mapa DITA, submapa, grupo de temas o un tema con `@processing-role="resource-only"`, la opción de regeneración no estará disponible.

Podría haber varias instancias en las que se actualizaran sólo unos pocos temas del mapa DITA y sólo se insertaran en directo esos temas actualizados. Para gestionar estos escenarios, AEM Guides le permite crear salidas incrementales. Si se han actualizado algunos temas, no es necesario volver a generar todo el mapa DITA. Solo puede seleccionar los temas actualizados y volver a generarlos.

Si el mapa está fragmentado y ha actualizado un solo tema en ese mapa, debe volver a generar todo el mapa para que el tema o el contenido actualizado se refleje en la salida. No obtendrá la opción de regeneración de salida en un nivel de tema, solo está disponible en el nivel de asignación \(fragmentado\). Esto se aplica al mapa principal y a todos los submapas.

Realice los siguientes pasos para volver a generar los resultados de un tema específico o un grupo de temas:

>[!IMPORTANT]
>
> AEM Cuando se regenera la salida del sitio del sitio de la, la salida se crea utilizando la versión actual de los archivos y no la línea de base adjunta.

1. En la interfaz de usuario de Assets, vaya al fichero de mapa DITA y haga clic en él.

   Aparecerá la consola de mapas DITA con la lista de Ajustes preestablecidos de salida disponibles para generar la salida.

1. Seleccione la ficha **Temas**.

   Se mostrará una lista de los temas disponibles en el mapa DITA.

1. Seleccione los temas que desee volver a generar.

   >[!NOTE]
   >
   > Si ha añadido nuevos temas al mapa DITA, no podrá generar esos nuevos temas desde aquí. En primer lugar, debe publicar los temas recién añadidos mediante la función de publicación de mapa DITA.

   ![](images/regenerate-topics.png){width="800" align="left"}

1. Haga clic en **Regenerar**.

   Aparecerá la página Regenerar Temas Seleccionados.

1. Seleccione el ajuste preestablecido de salida que desee utilizar para regenerar los temas seleccionados.

1. Haga clic en **Regenerar** para iniciar el proceso de generación de resultados.


>[!IMPORTANT]
>
> Si se cambia el nombre de un título de tema y se vuelve a generar el tema, el título actualizado no se refleja en la tabla de contenido del mapa DITA. Para actualizar el título del tema en el índice, se debe generar todo el mapa DITA.

Puede ver el estado actual de la solicitud de generación de resultados haciendo clic en Salidas. Para obtener más información, vea [Ver el estado de la tarea de generación de resultados](#viewing_output_history).

## Ver el estado de la tarea de generación de resultados {#viewing_output_history}

Una vez iniciada la tarea de generación de resultados para una asignación o regenerada los temas seleccionados, AEM Guides envía esta tarea a la cola de generación de resultados. Esta cola se actualiza en tiempo real y muestra el estado de cada tarea de generación de salida de la cola.

Realice los siguientes pasos para ver la cola de generación de resultados:

1. En la interfaz de usuario de Assets, vaya al archivo de asignación para el que desea comprobar el estado de generación de resultados y haga clic en él.

1. Haga clic en **Resultados**.

   ![](images/output-queued.png){width="800" align="left"}

   La página Resultados se divide en dos partes:

   - **Salidas en cola:**

     Enumera las salidas que están a la espera de generarse o en proceso de generación. Las tareas en cola o en curso se muestran con un icono de color azul antes del nombre del ajuste preestablecido. También puede encontrar la configuración de generación de resultados o el ajuste preestablecido utilizado para la tarea en cola, el tipo, el usuario que inició la tarea, el tiempo desde que se puso en cola la tarea y el estado actual.

     Haga clic en el vínculo para acceder a **Publish Dashboard** y ver el estado de ejecución actual. Hay disponible una lista de todas las tareas de publicación activas en el panel de Publish. **Salidas en cola** y el vínculo **Tablero de Publish** solo se muestran cuando hay salidas que están a la espera de generarse o en proceso de generación. No aparecen cuando se han completado las tareas de salida. Para obtener más información sobre el panel de Publish, consulte [Administrar tareas de publicación mediante el panel de Publish](generate-output-publish-dashboard.md#).

   - **Salidas generadas**

     Enumera las tareas de salida que se han completado. De nuevo, la información que se muestra aquí es similar a la sección Salidas en cola con algunas diferencias. Tiene un nuevo conjunto de información en forma de icono de resultado de salida y el tiempo de generación de salida.

     En esta lista, puede tener tareas que se hayan ejecutado correctamente, tareas que se hayan ejecutado con un mensaje o tareas fallidas. Las tareas correctas se muestran con un icono de color verde, las tareas con un mensaje tienen un icono de color naranja y las tareas fallidas se muestran con un icono de color rojo.

     Para todas las tareas, el proceso de publicación crea un archivo de registro \(logs.txt\) al que se puede acceder haciendo clic en el vínculo de la columna Generated At. Para las tareas que han fallado o tienen mensajes, puede comprobar el archivo de registro, que se explica en la sección [Ver y comprobar el archivo de registro](generate-output-basic-troubleshooting.md#id1822G0P0CHS).

     >[!NOTE]
     >
     > Al hacer clic en un vínculo de la salida del PDF generado, se le pide que descargue el PDF. AEM Este es el comportamiento predeterminado en las versiones 6.5 y 6.4 de.


## Cancelar una tarea de generación de resultados {#id2061H100T5Z}

AEM Guides ofrece a los editores una forma sencilla y sencilla de cancelar cualquier tarea de publicación en curso. Como editor, puede cancelar una tarea de publicación en curso desde la consola de mapas DITA o el [Tablero de Publish](generate-output-publish-dashboard.md#).

Realice los siguientes pasos para cancelar una tarea de generación de salida desde la consola de mapas DITA:

1. En la interfaz de usuario de Assets, vaya al archivo de asignación para el que desea cancelar una tarea de generación de salida en curso y haga clic en él.

1. Haga clic en **Resultados**.

1. En la lista Salidas en cola, pase el puntero sobre una tarea que desee cancelar.

1. Haga clic en el icono *Cancelar este trabajo*.

   ![](images/cancel-publish-task-map-console.png){width="800" align="left"}

1. Haga clic en **Sí** en el mensaje Confirmar cancelación.

   ![](images/confirm-cancel-output-map-condole.png){width="800" align="left"}

   Si la tarea aún no se ha iniciado, el comando cancel se ejecuta en la tarea. Para una tarea que se está cancelando, el estado se establece en Cancelando.

   Una vez cancelada correctamente la tarea, se mueve a la lista **Salidas generadas** con el estado **Cancelado**. Cuando pasa el ratón por encima de la tarea cancelada, se muestra el nombre del usuario que ha cancelado la tarea. En la siguiente captura de pantalla, se cancela la tarea *HTML 5*.

   ![](images/cancelled-output-task.png){width="800" align="left"}


## Eliminar una tarea de salida de la consola de mapas DITA

Cuando se generan varias salidas para un mapa DITA, durante un periodo de tiempo la lista de salidas generadas para dicho mapa se vuelve muy larga. Como editor, puede limpiar el historial de salida de cualquier archivo de asignación eliminando las tareas obsoletas de la lista *Salidas generadas*. Tenga en cuenta que la salida no se elimina del sistema, solo la entrada de la salida generada se elimina de la lista *Salidas generadas*.

Realice los siguientes pasos para quitar una tarea de salida de la lista Salida generada:

1. En la interfaz de usuario de Assets, vaya al archivo de asignación desde el que desea eliminar las tareas y haga clic en él.

1. Haga clic en **Resultados**.

1. En la lista Resultados generados, pase el puntero sobre una tarea que desee eliminar.

1. Haga clic en el icono Eliminar.

   ![](images/delete-output-task.png){width="800" align="left"}

1. Haga clic en **Sí** en el mensaje Confirmar eliminación.

   La tarea se elimina de la lista Resultados generados.


**Tema principal:**[ Generación de resultados](generate-output.md)
