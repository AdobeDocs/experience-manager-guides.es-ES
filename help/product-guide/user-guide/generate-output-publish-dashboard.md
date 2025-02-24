---
title: Administrar tareas de publicación mediante el panel Publicar
description: Administre las tareas de publicación mediante el Panel de publicación en AEM Guides. Obtenga información sobre cómo acceder al panel de publicación y cancelar una tarea de publicación.
exl-id: d9e25e52-ba9d-4088-ac95-8df76b69f5d3
feature: Publishing
role: User
source-git-commit: ff75aca9ddd7b405501a62e055fb99bd5ea2291c
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 0%

---

# Administrar tareas de publicación mediante el panel Publicar {#id205CC08305Z}

Cuando se ejecuta un gran conjunto de tareas de publicación en el sistema, resulta prácticamente imposible comprobar cada mapa DITA de forma individual para controlar su tarea de publicación. Adobe Experience Manager Guides proporciona a los administradores y editores una vista unificada de todas las tareas de publicación que se ejecutan en el sistema. En el tablero de publicación hay disponible una lista de todas las tareas de publicación activas.

El Tablero de publicación proporciona una visión general completa de todas las tareas de publicación que se ejecutan actualmente en el sistema.

![](images/publish-dashboard.png){width="800" align="left"}

El panel Publicar contiene los siguientes detalles:

- **Título del mapa**: título de un archivo de mapa que se está publicando actualmente o que está en la cola de publicación.

- **Nombre de archivo**: nombre de archivo del mapa DITA.

- **Ajuste preestablecido de salida**: nombre del ajuste preestablecido de salida que se usa para generar la salida.

- **Iniciado por**: nombre de usuario del usuario que inició la tarea de publicación.

- **Comenzó el** - Fecha y hora en que se inició la tarea de publicación.

- **Tiempo transcurrido** - Tiempo transcurrido desde que la tarea de publicación se ejecutó en el sistema.

- **Icono Eliminar** - Cancelar o finalizar una tarea de publicación.

El panel izquierdo del panel Publicar proporciona las siguientes opciones de filtrado:

- **Ajuste preestablecido de salida**: seleccione uno o varios ajustes preestablecidos de salida para los que desee ver las tareas de publicación activas actualmente. En la siguiente captura de pantalla, las tareas de publicación se filtran para mostrar solo las tareas que utilizan el ajuste preestablecido de salida del sitio de AEM:

  ![](images/publish-dashboard-preset-filter.png){width="800" align="left"}

- **Iniciado por**: seleccione un nombre de usuario de la lista para mostrar las tareas de publicación iniciadas por el usuario seleccionado.

- **Mapa**: seleccione un archivo de asignación de la lista para mostrar las tareas de publicación que se ejecutan para el mapa seleccionado.

## Acceso al panel de publicación

Puede acceder a **Publicar panel** directamente desde la [página de inicio de Experience Manager Guides](./intro-home-page.md). Abra la página principal y seleccione la opción **Publicar cola** en el panel izquierdo.

>[!NOTE]
>
> Solo un administrador o publicador puede acceder al panel de publicación.

También puede obtener acceso a **Publicar panel** desde la página de **Herramientas** de Adobe Experience Manager. Para utilizar este método, realice los siguientes pasos:

1. Seleccione el logotipo de Adobe Experience Manager en la parte superior y luego seleccione **Herramientas**.

1. Seleccione **Guías** de la lista de herramientas.

1. Seleccione el mosaico **Publicar tablero**.

   El panel Publicar se abre con una lista de todas las tareas de publicación activas en el sistema.

   Si se selecciona el vínculo Nombre de fichero (File Name), se mostrará el tablero de mandos de mapa DITA del mapa seleccionado.

   ![](images/publish-dashboard-click-filename-link.png){width="800" align="left"}


>[!NOTE]
>
> También puede acceder al Panel de publicación desde la pestaña **Salidas** mientras genera resultados desde el panel de asignación. Para obtener más información, consulte [Ver el estado de la tarea de generación de resultados](generate-output-for-a-dita-map.md#viewing_output_history).

## Cancelar una tarea de publicación

Realice los siguientes pasos para cancelar una tarea de generación de resultados desde el panel de publicación:

1. [Acceder al panel de publicación](#access-the-publish-dashboard).

1. En la lista de tareas de publicación activas, seleccione el icono Eliminar de una tarea que desee cancelar.

   ![](images/publish-dashboard-cancel-task.png){width="800" align="left"}

1. Seleccione **Sí** en el mensaje de **Confirmar cancelación**.

   Se acepta el comando Cancel y se intenta la cancelación mientras la tarea permanezca activa. Una vez finalizada correctamente la tarea, se quita de la lista de tareas activas actualmente. El estado de la tarea también se actualiza en el tablero de mandos de asignación DITA como Cancelada. En la siguiente captura de pantalla, la tarea *HTML5* se cancela del panel de publicación y su estado también se cambia en el panel de asignación DITA.

   ![](images/cancelled-output-task.png){width="800" align="left"}


**Tema principal:**[ Generación de resultados](generate-output.md)
