---
title: Procesamiento y reprocesamiento de recursos
description: Obtenga información sobre cómo procesar recursos
feature: Migration
role: Admin
level: Experienced
exl-id: 27786098-119c-4b7a-8275-8a89d435294f
source-git-commit: 851dafc1f17864bf6a295de7be12ffe513c3af57
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 0%

---

# Procesamiento o reprocesamiento de recursos

En flujos de trabajo con gran cantidad de datos, como la publicación, la administración eficiente de recursos es crucial para mantener el rendimiento y la fiabilidad. El proceso de procesamiento o reprocesamiento de recursos está diseñado específicamente para gestionar recursos específicos del usuario que requieren operaciones de datos intensivas. Este método aborda dos situaciones principales: cuando el procesamiento inicial de los recursos encuentra errores o cuando los archivos no se procesaron debido a la falta de un déclencheur posterior al procesamiento. Al habilitar el procesamiento específico en el nivel de carpeta, los usuarios pueden aislar y procesar solo los recursos necesarios, lo que evita la sobrecarga de cálculos innecesarios. Este enfoque selectivo mejora significativamente el rendimiento, reduciendo el tiempo necesario para operaciones críticas como la publicación y la generación de informes. En general, contribuye a una mayor eficiencia y velocidad en la gestión de tareas de datos complejas.

>[!NOTE]
>
> Para conjuntos de datos grandes, es mejor ejecutar el procesamiento durante las horas de menor actividad para evitar afectar al rendimiento del sistema. Una vez finalizada la tarea de procesamiento, puede revisar los detalles para analizar los resultados.

## Procesamiento de recursos

Siga los pasos mencionados a continuación para procesar o reprocesar los recursos:

1. Seleccione el logotipo de Adobe Experience Manager en la parte superior y elija **Herramientas**.
1. En el panel **Herramientas**, seleccione **Guías**.
1. Seleccione el mosaico **Procesador de recursos**.

   ![procesador de recursos de flujo](images/flow-asset-processor.png){align="left"}

1. Se abrirá la ventana Procesador de recursos de guías con los detalles que se muestran a continuación. Además, solo se muestra en esta ventana la información perteneciente a las últimas cinco migraciones.

   - **ID de ejecución**: es el identificador único de cada tarea de reprocesamiento que realiza.

   - **Carpeta**: muestra la carpeta seleccionada para reprocesamiento.

   - **Carpetas excluidas**: señala a la carpeta que se excluye del reprocesamiento.

   - **Hora de inicio:** Muestra la fecha y la hora en que se inició el proceso de reprocesamiento.

   - **Hora de finalización**: muestra la fecha y la hora en que finaliza el proceso de reprocesamiento.

   - **Estado**: señala al estado de reprocesamiento como En curso, Completado o Cancelado.

   ![Guides-asset-processor](images/guides-asset-processor.png){align="left"}

1. Seleccione la pestaña **Nuevo proceso** en la esquina superior derecha de la ventana para iniciar una nueva tarea de procesamiento.

   ![Nuevo-procesador-recursos-procesos](images/new-process-asset-processor.png){width="550" align="left"}

1. Seleccione la carpeta que desea procesar o volver a procesar. También puede seleccionar las carpetas (dentro de la carpeta seleccionada principal) que desee excluir o ignorar.

   >[!NOTE]
   >
   >Solo se puede seleccionar una carpeta a la vez para su procesamiento. Para operaciones específicas, puede excluir varias carpetas.

1. Seleccione **Crear**. Aparece una ventana emergente que muestra **Éxito y el proceso se activó correctamente**, como se muestra en el fragmento. Lo mismo se refleja en la lista. Puede ver el estado de la tarea de reprocesamiento en la ventana.

   ![Procesador de recursos de mensajes](images/message-asset-processor.png){width="550" align="left"}


## Opciones adicionales para las tareas de procesamiento

Hay opciones adicionales disponibles para la tarea de procesamiento una vez iniciada. Puede acceder a estas opciones pasando el puntero sobre el ID de ejecución de la tarea. A continuación se ofrecen detalles sobre estas opciones:

- **Restart** : reinicia la tarea de procesamiento de recursos que se realizó correctamente anteriormente.

  ![restart-asset-processor](images/restart-asset-processor.png){align="left"}

- **Reanudar**: Reanuda la tarea de procesamiento de recursos que se canceló o produjo un error.

  ![resume-asset-processor](images/resume-asset-processor.png){align="left"}

- **Cancelar** : Cancela la tarea de procesamiento de recursos en curso.

  ![cancel-asset-processor](images/cancel-asset-processor.png){align="left"}

- **Ver registros**: muestra los registros de la tarea de procesamiento de recursos. Para las tareas en curso, el registro muestra información de procesamiento detallada, incluido el tiempo restante estimado y el estado del recurso. Esta lista de registros muestra hasta las últimas 500 entradas. Se puede descargar el registro completo.

  ![logs-asset-processor](images/logs-asset-processor.png){align="left"}
