---
title: Ver el estado de la tarea de generación de resultados
description: Vea la cola de generación de resultados de documentos de FrameMaker. Obtenga información sobre cómo ver el estado de una tarea de generación de resultados.
feature: Publishing FrameMaker Documents
role: User
hide: true
exl-id: bf5a4365-0183-43d5-a39a-b9eb8a34b27d
source-git-commit: 26fa1e52920c1f1abd5655b9ca7341600a9bca67
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---

# Ver el estado de la tarea de generación de resultados {#viewing_output_history}

Una vez iniciada la tarea de generación de resultados para un documento de FrameMaker, AEM Guides envía esta tarea a la cola de generación de resultados. Esta cola se actualiza en tiempo real y muestra el estado de cada tarea de generación de salida de la cola.

Realice los siguientes pasos para ver la cola de generación de resultados:

1. En la interfaz de usuario de Assets, vaya al documento de FrameMaker para el que desea comprobar el estado de generación de resultados y haga clic en él.

1. Haga clic en Salidas.

   ![](images/output-queued-fm.png){width="800" align="left"}

1. La página Resultados se divide en dos partes:

   - **Salidas en cola:**

     Enumera las salidas que están a la espera de generarse o en proceso de generación. También puede encontrar la configuración de generación de resultados o el ajuste preestablecido utilizado para la tarea en cola, el tipo, el usuario que inició la tarea, el tiempo desde que se puso en cola la tarea y el estado actual.

   - **Salidas generadas**

     Enumera las tareas de salida que se han completado. De nuevo, la información que se muestra en esta sección es similar a la de las salidas en cola, con la única diferencia del tiempo de generación de salida.

     En esta lista, puede tener tareas que se hayan ejecutado correctamente o tareas que hayan fallado. Para las tareas que se han completado correctamente, el proceso de publicación crea un archivo de registro \(logs.txt\) al que se puede acceder haciendo clic en el vínculo en la columna Generated At.


**Tema principal:**&#x200B;[&#x200B; Generar salida de documentos de FrameMaker](fm-output-generatation.md)
