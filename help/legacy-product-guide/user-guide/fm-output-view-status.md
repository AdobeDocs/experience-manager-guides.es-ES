---
title: Ver el estado de la tarea de generación de resultados
description: Vea la cola de generación de resultados de documentos de FrameMaker. Obtenga información sobre cómo ver el estado de una tarea de generación de resultados.
feature: Publishing FrameMaker Documents
role: User
hide: true
exl-id: bf5a4365-0183-43d5-a39a-b9eb8a34b27d
TQID: https://experienceleague.adobe.com/FP5RxNtyWcdS-xpw2Atttt3x6DHx73Ljv-Ym91IxY5s
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: bf79f6d3-0ad0-4d82-99e4-42ce98324d60id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 245
ht-degree: 0%

---

# Ver el estado de la tarea de generación de resultados {#viewing_output_history}

Una vez iniciada la tarea de generación de resultados para un documento de FrameMaker, AEM Guides envía esta tarea a la cola de generación de resultados. Esta cola se actualiza en tiempo real y muestra el estado de cada tarea de generación de salida de la cola.

Realice los siguientes pasos para ver la cola de generación de resultados:

1. En la interfaz de usuario de Assets, vaya al documento de FrameMaker para el que desea comprobar el estado de generación de resultados y haga clic en él.

1. Haga clic en Salidas.

   ![](images/output-queued-fm.png){width="800"}

1. La página Resultados se divide en dos partes:

   - **Salidas en cola:**

     Enumera las salidas que están a la espera de generarse o en proceso de generación. También puede encontrar la configuración de generación de resultados o el ajuste preestablecido utilizado para la tarea en cola, el tipo, el usuario que inició la tarea, el tiempo desde que se puso en cola la tarea y el estado actual.

   - **Salidas generadas**

     Enumera las tareas de salida que se han completado. De nuevo, la información que se muestra en esta sección es similar a la de las salidas en cola, con la única diferencia del tiempo de generación de salida.

     En esta lista, puede tener tareas que se hayan ejecutado correctamente o tareas que hayan fallado. Para las tareas que se han completado correctamente, el proceso de publicación crea un archivo de registro \(logs.txt\) al que se puede acceder haciendo clic en el vínculo en la columna Generated At.


**Tema principal:**[ Generar salida de documentos de FrameMaker](fm-output-generatation.md)
