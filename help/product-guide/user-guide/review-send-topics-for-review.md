---
title: Enviar temas para revisión
description: Obtenga información sobre cómo crear una tarea de revisión y enviar temas para su revisión en AEM Guides. Envíe uno o varios temas en un mapa DITA para su revisión.
exl-id: c486eb6a-7e1f-4faa-973d-b47252d3e7c5
feature: Reviewing
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '2793'
ht-degree: 0%

---

# Enviar temas para revisión {#id199RD0S035Z}

El flujo de trabajo de revisión crea un entorno de varios revisores en el que el iniciador especifica una lista de temas para revisión, agrega varios revisores y asigna una cronología para la tarea de revisión. Adobe Experience Manager Guides permite a los usuarios pertenecientes a los grupos Autores y Publicadores iniciar una revisión.

Como el flujo de trabajo de revisión es específico del proyecto, el iniciador de la revisión debe ser parte del equipo del proyecto o tener derechos para crear un proyecto. En el momento de crear un proyecto, se definen los integrantes del equipo y se les asignan diversas funciones o grupos. Para obtener más información acerca de los proyectos, vea [Crear un proyecto DITA](authoring-create-dita-project.md#).

Puede crear una tarea de revisión desde:

- **Editor**: permite enviar un tema individual o un mapa DITA para su revisión. Tenga en cuenta que el flujo de trabajo para crear una tarea de revisión es común en el Editor y en la IU de Assets. Solo difiere el método para iniciar el flujo de trabajo de revisión. Para obtener información sobre cómo iniciar el flujo de trabajo de revisión desde el Editor, vea la característica [Crear tarea de revisión](web-editor-features.md#id215OCJ00JXA) en el Editor.

- **IU de Assets**: permite enviar uno o varios temas y un mapa DITA para su revisión. El uso compartido de documentos para su revisión desde el flujo de trabajo de la IU de Assets se trata en este tema.


Desde la interfaz de usuario de Assets, hay dos formas en las que un autor o editor puede crear una tarea de revisión:

- Enviar uno o varios temas para su revisión
- Enviar varios temas desde un mapa DITA para su revisión

## Enviar uno o varios temas para su revisión {#id1721E600FY4}

>[!IMPORTANT]
>
> Antes de crear una tarea de revisión, asegúrese de haber creado un proyecto y de haber agregado revisores a ese proyecto.

Para crear una tarea de revisión y enviar temas para su revisión, realice los siguientes pasos:

>[!NOTE]
>
> Sólo puede crear una tarea de revisión si es autor o editor de un proyecto DITA.

1. Vaya a la carpeta requerida en la interfaz de usuario de Assets.

1. Elija el icono **Seleccionar** en la acción rápida y seleccione los temas que desee enviar para su revisión.

   ![](images/select-asset-62.png){width="300" align="left"}

1. En la barra de herramientas, seleccione **Crear tarea de revisión**. Se muestra la página de creación de la tarea de revisión.

   >[!NOTE]
   >
   > Puede crear una tarea de revisión sólo para los temas que tengan una revisión. Si el tema seleccionado no tiene una revisión, se le mostrará un mensaje.

   ![](images/create-review-task-023.png){width="650" align="left"}

1. Escriba un **Título** para la tarea y seleccione un proyecto DITA.

1. En el campo desplegable **Proyecto**, seleccione un proyecto DITA para esta tarea de revisión. También puede escribir el nombre del proyecto para localizarlo rápidamente en la lista desplegable.

1. En el campo desplegable **Asignar a**, seleccione los revisores a los que desee enviar los temas para su revisión.

   Puede asignar una tarea de revisión a usuarios individuales del proyecto o a grupos de usuarios. Tenga en cuenta que sólo puede asignar una tarea de revisión a usuarios individuales cuando forme parte del grupo de administradores del proyecto; de lo contrario, sólo verá los grupos de usuarios en el campo Asignar a.

   >[!NOTE]
   >
   > El flujo de trabajo de revisión es específico del proyecto. Cuando crea proyectos, agrega los integrantes del equipo al proyecto y los asigna a grupos. Así que cuando seleccionas el proyecto aquí, puedes elegir a los miembros que son parte de ese proyecto. Para obtener más información acerca de los proyectos, vea [Crear un proyecto DITA](authoring-create-dita-project.md#).

1. Escriba una **descripción** para la tarea.

   Esta descripción se utiliza como cuerpo del correo electrónico de notificación enviado a los revisores.

1. Seleccione la **fecha de vencimiento** y la hora para marcar la fecha límite para la revisión.

   >[!NOTE]
   >
   > Al llegar a la fecha límite, se envía un correo electrónico al iniciador para notificarle que la tarea de revisión se ha completado. El iniciador puede extender la fecha límite de la tarea de revisión desde el [Panel de revisión](review-manage-tasks-review-dashboard.md#).

1. Seleccione el mapa raíz de la ruta de acceso **Rootmap**. Este mapa de raíz se utiliza para resolver todas las referencias clave y los términos del glosario utilizados en el contenido de la revisión. Si no selecciona el mapa de raíz, las referencias clave o los términos del glosario asociados con el tema DITA no se resuelven antes de enviar el tema para su revisión.

   Si está creando la revisión para un mapa DITA, la ruta **Rootmap** se establece de forma predeterminada en la ruta de ese mapa. Si está creando la revisión para uno o varios temas, la ruta de acceso **Rootmap** se establece de manera predeterminada en el mapa definido en Preferencias del usuario.

   >[!NOTE]
   >
   > El mapa raíz seleccionado tiene la prioridad más alta para resolver las referencias clave. Para obtener más información, vea [Resolver referencias clave](map-editor-other-features.md#id176GD01H05Z).

1. Dado que puede asignar distintos revisores a diferentes temas, la opción **Permitir que los usuarios asignados revisen cualquier tema** controla si los revisores pueden revisar todos los temas de una tarea de revisión o sólo aquellos temas para los que están asignados a la revisión.

   Si desea permitir que todos los revisores revisen cualquier tema de la tarea de revisión, seleccione **Permitir que los usuarios asignados revisen cualquier tema**.

   Si no selecciona esta opción, los revisores agregados en el campo **Asignar a** tendrán acceso para revisar solamente los temas que estén asignados a ellos.

1. Seleccione **Siguiente**.

   Se muestra la página Contenido.

   ![](images/content_page_review.png){align="left"}

1. En la página Contenido, seleccione una versión del tema que desee compartir para su revisión.

   Puede utilizar uno de los siguientes métodos para seleccionar una versión:

   - *\(Predeterminado\)* Elija la opción **Su última versión** para seleccionar la última revisión guardada de los temas.
   - Elija la opción **Versión el** y especifique la fecha y la hora para seleccionar una versión en la fecha y la hora especificadas. Si no hay ninguna versión del tema disponible en la fecha especificada, se selecciona una versión disponible inmediatamente después de la fecha y la hora especificadas.
   - Elija la opción **Seleccionar una etiqueta** y seleccione una etiqueta de la lista desplegable.
1. Después de hacer la selección para elegir una versión, selecciona **Aplicar**.

   La versión basada en la opción seleccionada se elige para los temas.

   >[!NOTE]
   >
   > También puede seleccionar manualmente la versión que desee en la lista desplegable **Versión** de cada tema.

1. Seleccione **Siguiente**.

   Se muestra la página Revisores, donde puede agregar o quitar revisores. De forma predeterminada, los revisores agregados en el campo Asignar a se agregan automáticamente a cada tema seleccionado para la revisión.

   ![](images/add-reviewers-topics.png){width="650" align="left"}

1. En la página Revisores, puede agregar o quitar revisores. Las siguientes operaciones están disponibles en la página Revisores:

   - **Seleccionar todo**: selecciona todos los temas de la lista de temas. Puede realizar fácilmente una operación por lotes después de seleccionar todos los temas.
   - **Borrar selección**: Anula la selección de los temas seleccionados en la lista de temas.

     >[!NOTE]
     >
     > También puede seleccionar o deseleccionar un tema individualmente seleccionando en la casilla de verificación situada junto al tema.

   - **Agregar**: Muestra el cuadro de diálogo Agregar revisores. Puede escribir el nombre de un revisor o la función de usuario \(o grupo\) que desee agregar como revisor a los temas seleccionados.
   - **Quitar**: muestra el cuadro de diálogo Quitar revisores. Puede escribir el nombre de un revisor o la función de usuario \(o grupo\) que desee quitar como revisor de los temas seleccionados.

     >[!NOTE]
     >
     > También puede quitar una revisión de un tema seleccionando el signo cruzado en el cuadro del revisor.

   - **Volver a asignar**: muestra el cuadro de diálogo Volver a asignar revisores. Puede escribir el nombre del revisor o la función de usuario \(o grupo\) al que desee asignar la tarea de revisión. De este modo, se quitarán todos los revisores existentes de los temas seleccionados y se asignarán a ellos los revisores recién seleccionados.
   - **Exportar**: permite exportar los detalles de la tarea de revisión en un archivo CSV. El archivo contiene detalles como la ruta y el título del tema, el nombre del revisor y la versión de los temas enviados para su revisión.
   - **Editar revisores**: al seleccionar el icono ![](images/edit_pencil_icon.svg)de la lista de temas, se muestra el cuadro de diálogo Editar revisores. Puede agregar o quitar revisores para el tema seleccionado desde este cuadro de diálogo.
1. Seleccione **Crear** para crear la tarea de revisión.

   Se muestra un mensaje de confirmación cuando la tarea de revisión se crea correctamente. El [estado del documento](web-editor-document-states.md#) para los temas enviados a revisión está establecido en En revisión.

   >[!NOTE]
   >
   > También puede seleccionar la campana Notificaciones en la parte superior derecha de la pantalla y confirmar que la tarea de revisión se ha creado correctamente. En el panel Notificaciones, encontrará una notificación para cada uno de los revisores que formaban parte de la tarea de revisión y una notificación para el iniciador de la revisión.


Se envía un mensaje de correo electrónico a todos los revisores para notificarles que se les ha asignado uno o varios temas para su revisión. El correo electrónico contiene un vínculo directo que puede utilizar para acceder al tema en una ventana del explorador.

Si se asignan varios temas, los revisores pueden verlos y seleccionarlos en una lista desplegable de temas del explorador web.

## Enviar varios temas para su revisión desde un mapa DITA

Un mapa DITA es una organización lógica de temas dentro de un libro. Cuando envía un tema individual para su revisión, el revisor no obtiene ninguna información sobre la ubicación de ese tema en el libro. Si un revisor tiene información sobre la ubicación exacta del tema que se está revisando, obtiene un mejor contexto del tema que se está revisando.

Experience Manager Guides permite enviar uno o varios temas en un mapa DITA para su revisión al mismo tiempo. El revisor puede ver el archivo de asignación completo junto con los temas compartidos para su revisión. Esto facilita al revisor obtener un contexto del tema en el archivo de mapa o libro.

Puede compartir el mismo mapa DITA en para revisarlo en varias tareas de revisión. Por ejemplo, si en un mapa DITA hay temas A, B, C, D y E. En una tarea de revisión puede compartir A, B y C para su revisión y en otra tarea de revisión puede enviar los temas C, D y E para su revisión. El proceso de revisión permite compartir el mismo tema y asignar archivos en varias tareas de revisión. Para el tema común en varias tareas de revisión, los comentarios proporcionados en una tarea de revisión no se sobrescriben ni se combinan con los comentarios de las demás tareas de revisión.

>[!IMPORTANT]
>
> Si un tema de un archivo de asignación se ha compartido en varias tareas de revisión, su estado sería En revisión hasta que todas las tareas de revisión se hayan completado.

Para enviar uno o varios temas junto con el archivo de asignación para su revisión, realice los siguientes pasos:

>[!IMPORTANT]
>
> Una vez iniciada una revisión a través de un archivo de asignación, no debe cambiar la estructura del archivo de asignación agregando nuevos temas o quitando temas existentes.

1. Vaya a la carpeta requerida en la interfaz de usuario de Assets.

   >[!NOTE]
   >
   > Asegúrese de que la vista de la consola está configurada en vista de tarjeta o vista de lista.

1. Seleccione el mapa desde el que desea enviar los temas para su revisión.

1. En la barra de herramientas, seleccione **Crear tarea de revisión**. Se muestra la página de creación de la tarea de revisión.

1. Escriba un **Título** para la tarea.

1. En el campo desplegable **Proyecto**, seleccione un proyecto DITA para esta tarea de revisión. También puede escribir el nombre del proyecto para localizarlo rápidamente en la lista desplegable.

   >[!NOTE]
   >
   > Puede crear una tarea de revisión sólo para los temas que tengan una revisión. Si la asignación contiene temas que no tienen una revisión, se mostrará un mensaje con una lista de dichos ficheros. Los archivos sin revisión se excluyen de la tarea de revisión.

1. En el campo desplegable **Asignar a**, seleccione los revisores a los que desee enviar los temas para su revisión.

   Puede asignar una tarea de revisión a usuarios individuales del proyecto o a grupos de usuarios. Tenga en cuenta que sólo puede asignar una tarea de revisión a usuarios individuales cuando forme parte del grupo de administradores del proyecto; de lo contrario, sólo verá los grupos de usuarios en el campo Asignar a.

   >[!NOTE]
   >
   > El flujo de trabajo de revisión es específico del proyecto. Cuando crea proyectos, agrega los integrantes del equipo al proyecto y los asigna a grupos. Así que cuando seleccionas el proyecto aquí, puedes elegir a los miembros que son parte de ese proyecto. Para obtener más información acerca de los proyectos, vea [Crear un proyecto DITA](authoring-create-dita-project.md#).

1. Escriba una **descripción** para la tarea.

   Esta descripción se utiliza como cuerpo del correo electrónico de notificación enviado a los revisores.

1. Seleccione la **fecha de vencimiento** y la hora para marcar la fecha límite para la revisión.

   >[!NOTE]
   >
   > Al llegar a la fecha límite, se envía un correo electrónico al iniciador para notificarle que la tarea de revisión se ha completado. El iniciador puede extender la fecha límite de la tarea de revisión desde el [Panel de revisión](review-manage-tasks-review-dashboard.md#).

1. Dado que puede asignar distintos revisores a diferentes temas, la opción **Permitir que los usuarios asignados revisen cualquier tema** controla si los revisores pueden revisar todos los temas de una tarea de revisión o sólo aquellos temas para los que están asignados a la revisión.

   Si desea permitir que todos los revisores revisen cualquier tema de la tarea de revisión, seleccione **Permitir que los usuarios asignados revisen cualquier tema**.

   Si no selecciona esta opción, los revisores agregados en el campo **Asignar a** tendrán acceso para revisar solamente los temas que estén asignados a ellos.

1. Seleccione **Siguiente**.

   La página Contenido se muestra con todos los temas a los que se hace referencia desde el archivo de asignación. Si el mapa DITA contiene mapas anidados, también se enumerarán aquí los temas de los mapas anidados.

   ![](images/content-page-map-review.png){align="left"}

1. En la página Contenido, seleccione una versión del tema que desee compartir para su revisión.

   Puede utilizar uno de los siguientes métodos para seleccionar una versión:

   - *\(Predeterminado\)* Elija la opción **Su última versión** para seleccionar la última revisión guardada de los temas.
   - Elija la opción **Versión el** y especifique la fecha y la hora para seleccionar una versión según la fecha y la hora. Si no hay ninguna versión del tema disponible en la fecha especificada, se selecciona una versión disponible inmediatamente después de la fecha y la hora especificadas.
   - Elija la opción **Seleccionar una etiqueta** y seleccione una etiqueta de la lista desplegable. Todos los temas que contengan la etiqueta seleccionada se seleccionarán en la lista desplegable **Versión**.
   - Elija la opción **Seleccionar una línea de base** y seleccione una línea de base en la lista desplegable. Todas las versiones de temas que forman parte de la línea de base seleccionada se seleccionan en la lista desplegable **Versión**.
1. Después de hacer la selección para elegir una versión, selecciona **Aplicar**.

   La versión basada en la opción seleccionada se elige para los temas.

   >[!NOTE]
   >
   > También puede seleccionar manualmente la versión que desee en la lista desplegable **Versión** de cada tema.

1. Seleccione **Siguiente**.

   Se muestra la página Revisores, donde puede agregar o quitar revisores. De forma predeterminada, los revisores agregados en el campo Asignar a se agregan automáticamente a cada tema seleccionado para la revisión.

1. En la página Revisores, puede agregar o quitar revisores. Las siguientes operaciones están disponibles en la página Revisores:

   - **Seleccionar todo**: selecciona todos los temas de la lista de temas. Puede realizar fácilmente una operación por lotes después de seleccionar todos los temas.
   - **Borrar selección**: Anula la selección de los temas seleccionados en la lista de temas.

     >[!NOTE]
     >
     > También puede seleccionar o deseleccionar un tema individualmente seleccionando en la casilla de verificación situada junto al tema.

   - **Agregar**: Muestra el cuadro de diálogo Agregar revisores. Puede escribir el nombre de un revisor o la función de usuario \(o grupo\) que desee agregar como revisor a los temas seleccionados.
   - **Quitar**: muestra el cuadro de diálogo Quitar revisores. Puede escribir el nombre de un revisor o la función de usuario \(o grupo\) que desee quitar como revisor de los temas seleccionados.
   - **Volver a asignar**: muestra el cuadro de diálogo Volver a asignar revisores. Puede escribir el nombre del revisor o la función de usuario \(o grupo\) al que desee asignar la tarea de revisión. De este modo, se quitarán todos los revisores existentes de los temas seleccionados y se asignarán a ellos los revisores recién seleccionados.
   - **Exportar**: permite exportar los detalles de la tarea de revisión en un archivo CSV. El archivo contiene detalles como la ruta y el título del tema, el nombre del revisor y la versión de los temas enviados para su revisión.
   - **Editar revisores**: al seleccionar el icono ![](images/edit_pencil_icon.svg)de la lista de temas, se muestra el cuadro de diálogo Editar revisores. Puede agregar o quitar revisores para el tema seleccionado desde este cuadro de diálogo.

   >[!IMPORTANT]
   >
   > Debe asignar al menos un revisor para crear la tarea de revisión.

1. Seleccione **Crear** para crear la tarea de revisión.

   Se muestra un mensaje de confirmación cuando la tarea de revisión se crea correctamente. El [estado del documento](web-editor-document-states.md#) para los temas enviados a revisión está establecido en En revisión.

   >[!NOTE]
   >
   > También puede seleccionar el panel Notificaciones en la parte superior derecha de la interfaz y confirmar que la tarea se ha creado correctamente. En el panel Notificaciones, encontrará una notificación para cada revisión que formaba parte de la tarea de revisión y una notificación para el iniciador de la revisión.

   >[!IMPORTANT]
   >
   > Una vez iniciada una revisión, no se debe mover ni eliminar el mapa o los temas DITA a otra ubicación. De hacerlo, se interrumpirá el proceso de revisión.


Se envía un mensaje de correo electrónico a todos los revisores para notificarles que se les han asignado temas para su revisión. El correo electrónico contiene un vínculo directo que puede utilizar para acceder al tema en una ventana del explorador. Los temas junto con el mapa DITA se abren en el modo de revisión.

**Tema principal:**&#x200B;[&#x200B; Introducción a la revisión](review.md)
