---
title: Administrar tareas de publicación mediante el panel Publicar
description: AEM Administre las tareas de publicación mediante el Panel de publicación en las Guías de publicación de. Obtenga información sobre cómo acceder al panel de publicación y cancelar una tarea de publicación.
exl-id: d9e25e52-ba9d-4088-ac95-8df76b69f5d3
feature: Publishing
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 0%

---

# Administrar tareas de publicación mediante el panel Publicar {#id205CC08305Z}

Cuando se ejecuta un gran conjunto de tareas de publicación en el sistema, resulta prácticamente imposible comprobar cada mapa DITA de forma individual para controlar su tarea de publicación. AEM Guías de publicación proporciona a los administradores y editores una vista unificada de todas las tareas de publicación que se ejecutan en el sistema. En el tablero de publicación hay disponible una lista de todas las tareas de publicación activas.

El Tablero de publicación proporciona una visión general completa de todas las tareas de publicación que se ejecutan actualmente en el sistema.

![](images/publish-dashboard.png){width="800" align="left"}

El panel Publicar contiene los siguientes detalles:

- **Título del mapa** : título de un archivo de asignación que se está publicando actualmente o que está en la cola de publicación.

- **Nombre de archivo** : nombre de fichero del mapa DITA.

- **Ajuste preestablecido de salida** - Nombre del ajuste preestablecido de salida que se utiliza para generar la salida.

- **Iniciado por** : nombre de usuario del usuario que inició la tarea de publicación.

- **Se inició el** - Fecha y hora en que se inició la tarea de publicación.

- **Tiempo transcurrido** - Tiempo transcurrido desde que la tarea de publicación se está ejecutando en el sistema.

- **Icono Eliminar** - Cancelar o finalizar una tarea de publicación.

El panel izquierdo del panel Publicar proporciona las siguientes opciones de filtrado:

- **Ajuste preestablecido de salida** - Seleccione uno o varios ajustes preestablecidos de salida para los que desee ver las tareas de publicación activas actualmente. AEM En la siguiente captura de pantalla, las tareas de publicación se filtran para mostrar solo las tareas que utilizan el ajuste preestablecido de salida del sitio de la:

  ![](images/publish-dashboard-preset-filter.png){width="800" align="left"}

- **Iniciado por** - Seleccione un nombre de usuario de la lista para mostrar las tareas de publicación iniciadas por el usuario seleccionado.

- **Mapa** - Seleccione un fichero de mapa de la lista para mostrar las tareas de publicación que se están ejecutando para el mapa seleccionado.

## Acceso al panel de publicación {#id205CC100DY4}

Siga estos pasos para acceder al panel de publicación:

>[!NOTE]
>
> Solo un administrador o publicador puede acceder al panel de publicación.

1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.

1. Seleccionar **Guías** de la lista de herramientas.

1. Haga clic en **Publicar tablero** mosaico.

   El panel Publicar se abre con una lista de todas las tareas de publicación activas en el sistema.

   Si pulsa en el vínculo Nombre de fichero (File Name), se mostrará la consola de mapas DITA del mapa seleccionado.

   ![](images/publish-dashboard-click-filename-link.png){width="800" align="left"}


>[!NOTE]
>
> También puede acceder al panel Publicar desde la pestaña Salidas mientras genera resultados desde el panel de asignación. Para obtener más información, consulte [Ver el estado de la tarea de generación de resultados](generate-output-for-a-dita-map.md#viewing_output_history).

## Cancelar una tarea de publicación

Realice los siguientes pasos para cancelar una tarea de generación de resultados desde el panel de publicación:

1. [Acceso al panel de publicación](#id205CC100DY4).

1. En la lista de tareas de publicación activas, haga clic en el icono Eliminar de una tarea que desee cancelar.

   ![](images/publish-dashboard-cancel-task.png){width="800" align="left"}

1. Clic **Sí** en el mensaje Confirmar cancelación.

   Se acepta el comando Cancel y se intenta la cancelación mientras la tarea permanezca activa. Una vez finalizada correctamente la tarea, se quita de la lista de tareas activas actualmente. El estado de la tarea también se actualiza en la consola de mapas DITA como Cancelada. En la siguiente captura de pantalla, la variable *HTML 5* La tarea se cancela del tablero de publicación y su estado también se cambia en la consola de mapas DITA.

   ![](images/cancelled-output-task.png){width="800" align="left"}


**Tema principal:**[ Generación de salida](generate-output.md)
