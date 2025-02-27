---
title: Administrar tareas de revisión mediante el panel Revisar
description: Administre las tareas de revisión desde el Panel de revisión en AEM Guides. Conozca las acciones que se realizan en la pestaña tarea, contenido y revisores, y compruebe el estado de una tarea de revisión.
feature: Reviewing
role: User
hide: true
exl-id: f3ed7e82-8bb8-400f-9406-367da9e0052c
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 0%

---

# Administrar tareas de revisión mediante el panel Revisar {#id2056B0Y70X4}

El flujo de trabajo de administración de revisiones puede incluir diversas tareas. Por ejemplo, puede que desee agregar revisores para un tema concreto o ampliar la fecha límite para una revisión. También es posible que desee marcar la tarea de revisión como completada si cree que todas las partes interesadas han proporcionado sus comentarios. Estas tareas se pueden administrar mediante el panel de revisión.

Siga estos pasos para acceder y utilizar el panel de revisión:

>[!NOTE]
>
> Solo puede administrar las tareas de revisión de los proyectos de los que sea autor \(o iniciador\). Aunque sea revisor o publicador \(usuario\), no tendrá acceso a ninguna de las tareas del proyecto.

1. En la consola **Proyectos**, haga clic en el proyecto de revisión que desee administrar.

   Se muestra un panel Proyecto con mosaicos de tareas.

   ![](images/review-management.png){width="800" align="left"}

1. Haga clic en los tres puntos del mosaico **Críticas**.

   Se muestra el panel Revisar. En el panel se muestran todas las tareas de revisión que ha creado.

   ![](images/review-dashboard.png){width="800" align="left"}

   El panel de revisión muestra los detalles sobre la tarea de revisión, como el nombre de la tarea, quién inició la revisión, la fecha en la que se inició, la fecha de vencimiento, el estado, el número de nuevos comentarios que el autor no ha aceptado o rechazado, y el nombre de los revisores. Las tareas se enumeran en el orden de las tareas recién creadas a las tareas más antiguas.

   >[!NOTE]
   >
   > Si hace clic en el vínculo Revisar tarea, se abre el tema o el archivo de asignación enviado para su revisión.

1. Seleccione una tarea de revisión.

   Se le mostrarán las opciones Editar propiedades y [Estado](#check-review-status-id199RF0A0UHS) en la barra de herramientas.

1. Si hace clic en **Editar propiedades**, se muestra la página Detalles de la tarea.

   Existen tres pestañas en la página Detalles de la tarea: Tarea, Contenido y Revisores. En las siguientes secciones se explican las distintas funciones disponibles en cada pestaña.


## Pestaña Tarea

![](images/review-task-page.png){width="800" align="left"}

Puede realizar las siguientes acciones en la ficha **Tarea**:

- Modifique el título de la tarea en el campo **Título**.
- Agregar usuarios asignados predeterminados en la lista desplegable **Asignar a**. Los revisores que agregue desde aquí tendrán acceso para revisar todos los temas que formen parte de esta tarea de revisión. Puede elegir entre quitar o agregar selectivamente más revisores a temas específicos en la [pestaña Revisores](#reviewer-tab-id199RF0N0MUI).
- Actualice la descripción de la tarea en el campo **Descripción**.
- Modificar **fecha de vencimiento**. Puede adelantar o posponer la fecha límite para la finalización de la tarea.
- Seleccione la opción para restringir a los usuarios la revisión sólo de los temas asignados a ellos.
- Haga clic en **Actualizar** para actualizar los detalles modificados.
- Haga clic en **Completar** para marcar la tarea de revisión como completada antes de la fecha de vencimiento. Cuando la tarea de un tema individual se marca como Completada, se cierra la revisión del tema seleccionado. Sin embargo, en el caso de los temas compartidos para revisión a través de un mapa DITA, al marcar la tarea de mapa DITA como Completada se cerrará la revisión de todos los temas del mapa que se compartieron para revisión.
- Haga clic en **Duplicar** para crear una copia de la tarea de revisión. El proceso de crear una tarea de revisión duplicada es similar a crear una nueva tarea de revisión. Una vez iniciado el flujo de trabajo de tareas duplicadas, se muestra la página Crear tarea de revisión. Debe proporcionar los detalles de la nueva tarea como se explica en [Enviar temas para revisión](review-send-topics-for-review.md#).

  Si ha seleccionado una tarea de revisión creada a partir de un mapa DITA, se mostrarán los temas que son un pert del mapa. A continuación, puede elegir los temas que desea incluir en la nueva tarea de revisión.

  Si la tarea de revisión está duplicada a partir de uno o varios temas revisados, sólo se mostrarán esos temas en la lista de tareas de revisión. Puede optar por compartir estos temas para su revisión con otro conjunto de revisores.

- Haga clic en **Cerrar** para ir a la página Bandeja de entrada.

## Pestaña Contenido

![](images/review-content-page.png){width="800" align="left"}

Puede realizar las siguientes acciones en la ficha **Contenido**:

- Cambie la versión del tema enviado para su revisión. Puede elegir la última versión del tema, la versión como fecha, la versión con una etiqueta específica o la versión con una línea de base \(para un mapa DITA\) específica.

- Haga clic en **Actualizar** para compartir la versión actualizada del tema con los revisores. Los revisores reciben una notificación por correo electrónico que indica que se ha enviado la versión más reciente del tema para su revisión. La próxima vez que un revisor abra el tema, verá la versión actualizada.

  >[!NOTE]
  >
  > En el caso de una versión actualizada de un tema, los comentarios antiguos también se conservan en la versión más reciente. Los revisores también pueden ver las diferencias entre las dos versiones.

- Haga clic en **Completar** para marcar la tarea de revisión como completada antes de la fecha de vencimiento. Cuando la tarea de un tema individual se marca como Completada, se cierra la revisión del tema seleccionado. Sin embargo, en el caso de los temas compartidos para revisión a través de un mapa DITA, al marcar la tarea de mapa DITA como Completada se cerrará la revisión de todos los temas del mapa que se compartieron para revisión.

- Haga clic en **Duplicar** para crear una nueva tarea de revisión usando la tarea actual como base.


## Pestaña Revisores {#reviewer-tab-id199RF0N0MUI}

![](images/reviewers-tab.png){width="800" align="left"}

Puede realizar las siguientes acciones en la ficha **Revisores**:

- **Seleccionar todo**: selecciona todos los temas de la lista de temas. Puede realizar fácilmente una operación por lotes después de seleccionar todos los temas.
- **Borrar selección**: Anula la selección de los temas seleccionados en la lista de temas.

  >[!NOTE]
  >
  > También puede seleccionar o deseleccionar un tema individualmente si hace clic en la casilla de verificación situada junto al tema.

- **Agregar**: Muestra el cuadro de diálogo Agregar revisores. Puede escribir el nombre de un revisor o la función de usuario \(o grupo\) que desee agregar como revisor a los temas seleccionados.
- **Quitar**: muestra el cuadro de diálogo Quitar revisores. Puede escribir el nombre de un revisor o la función de usuario \(o grupo\) que desee quitar como revisor de los temas seleccionados.
- **Volver a asignar**: muestra el cuadro de diálogo Volver a asignar revisores. Puede escribir el nombre del revisor o la función de usuario \(o grupo\) al que desee asignar la tarea de revisión. De este modo, se quitarán todos los revisores existentes de los temas seleccionados y se asignarán a ellos los revisores recién seleccionados.
- **Exportar**: permite exportar los detalles de la tarea de revisión en un archivo CSV. El archivo contiene detalles como la ruta y el título del tema, el nombre del revisor y la versión de los temas enviados para su revisión.
- **Editar revisores**: al hacer clic en el icono ![](images/edit_pencil_icon.svg)de la lista de temas, se muestra el cuadro de diálogo Editar revisores. Puede agregar o quitar revisores para el tema seleccionado desde este cuadro de diálogo.

## Comprobar el estado de una tarea de revisión {#check-review-status-id199RF0A0UHS}

En la página principal del panel de revisión, si selecciona una tarea de revisión y hace clic en **Estado**, se muestra el informe de estado de la tarea de revisión:

![](images/review-status-report.png){width="800" align="left"}

El informe de estado de la tarea de revisión contiene los siguientes detalles:

- Nombre del revisor al que se ha asignado la tarea de revisión.
- La columna Estado indica el estado de la revisión. El estado puede ser uno de los siguientes:
   - **No iniciado**: el revisor aún no ha abierto el vínculo de revisión.
   - **En curso**: el revisor ha abierto el vínculo de revisión y está revisando el tema.
   - **Completar**: el revisor ha completado la revisión al completar la tarea de revisión asignada. La tarea de revisión se encuentra en la bandeja de entrada de notificaciones de AEM de cada revisor.
- Cuando un revisor abre un vínculo de revisión y navega a un tema concreto, ese tema se agrega a la lista Temas revisados. Esto ayuda a los autores a determinar si los revisores han abierto sus secciones respectivas o no. Si se presentan comentarios, se muestran entre corchetes.
- Número total de observaciones formuladas sobre todos los temas. En el caso de varios temas en revisión, el número de comentarios de cada tema se menciona \(entre corchetes\) con el nombre del tema.
- La fecha en la que el revisor accedió por última vez a cualquier tema.

**Tema principal:**[ Revisar temas o asignaciones](review.md)
