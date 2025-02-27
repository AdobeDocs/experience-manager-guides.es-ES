---
title: Revisar temas
description: Obtenga información sobre cómo revisar temas y utilizar las funciones como revisor, vista de documento, vista de tema, barra de herramientas contextual, modo de vista previa, agregar archivos adjuntos a comentarios y panel de condiciones en AEM Guides.
feature: Reviewing
role: User
hide: true
exl-id: 371d89b8-fe05-4477-9bf8-cc47c0899108
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '2351'
ht-degree: 0%

---

# Revisar temas {#id2056B0W0FBI}

Si es revisor, recibirá un correo electrónico de solicitud de revisión con el vínculo a los temas de la revisión. Al hacer clic en el vínculo, accederá a la página de revisión, donde podrá añadir sus comentarios sobre los temas compartidos.

Siga estos pasos para revisar un tema:

1. Haga clic en el vínculo directo que aparece en el correo electrónico de solicitud de revisión.

   El vínculo del tema o del mapa se abre en un explorador.

   >[!NOTE]
   >
   > También puede acceder al vínculo de revisión del tema desde el área de notificaciones de la bandeja de entrada en la interfaz de usuario de AEM.

1. Según la forma en que se inicie la revisión del tema, podrá ver cualquiera de las dos pantallas siguientes:

   >[!NOTE]
   >
   > La interfaz de usuario puede ser diferente si ha creado la revisión en:
   >
   > - Versión de noviembre de 2022 o anterior de AEM Guides as a Cloud Service
   > - AEM Guides versión 4.1 o anterior



   La siguiente pantalla aparece cuando se utiliza un mapa DITA para iniciar el flujo de trabajo de revisión:

   ![](images/multiple-topics-review.png){width="800" align="left"}

   Las siguientes opciones están disponibles en esta pantalla:

   - **A**: Nombre de la tarea de revisión.
   - **B**: haga clic en el icono Vista de temas para mostrar u ocultar el panel de temas.

   - **C**: puede buscar el tema requerido al escribir parte del texto del título o ruta de archivo en la barra de búsqueda.

     Seleccione ![](images/view-options.svg) cerca de la barra de búsqueda para elegir ver todos los temas o ver los temas con comentarios. De forma predeterminada, puede ver todos los temas presentes en la tarea de revisión.


   - **D**: Los números resaltados por ***F*** se pueden filtrar eligiendo la opción de filtro deseada desde aquí. Puede filtrar los comentarios por tipo, estado, revisor o versión. Por ejemplo, si desea ver cuántos comentarios de tachado se han realizado en cada uno de los temas de revisión, haga clic en el icono de filtro y, a continuación, elija **Tipo de revisión** \> **Eliminación**.

     >[!NOTE]
     >
     > Al aplicar los filtros, solo se muestran en el panel de comentarios los comentarios que coinciden con los filtros seleccionados. El número de comentarios filtrados se muestra a la izquierda en el panel Temas.

   - **E**: un tema asignado para revisión al revisor actual se muestra en negro y se puede hacer clic en él. Cuando el revisor haga clic en un vínculo de un tema, ese tema se coloca en la parte superior de la pantalla.
   - **F**: Un tema que no está disponible para revisión está atenuado. El tema se muestra en modo de sólo lectura y no se le permite agregar comentarios de revisión sobre dichos temas.

   - **G**: Número de comentarios recibidos sobre un tema. Este número cambia según el filtro que aplique.

   Todos los temas del mapa se muestran como un solo documento compuesto. Los temas que el revisor puede revisar se muestran normalmente. No se muestran los temas que la revisión no puede revisar.

   ![](images/review-read-only.png){width="800" align="left"}

   En la captura de pantalla anterior, el tema Descripción general se comparte para que el revisor actual lo revise, lo que se muestra normalmente. Sin embargo, el tema siguiente, Historial del contenido del vuelo no se comparte para su revisión y se muestra en modo de solo lectura. El tema que está actualmente en el punto de mira también se resalta en el índice.

   La siguiente pantalla aparece cuando se selecciona uno o varios temas y se comparten para su revisión:

   ![](images/review-composite-view.png){width="800" align="left"}

   >[!NOTE]
   >
   > Si hay varios temas, se muestran como un documento compuesto en la vista de documento. La captura de pantalla anterior resalta dos temas diferentes presentados uno tras otro en una sola vista.

1. Abra el panel Comentarios haciendo clic en el icono **Comentarios** en la esquina superior derecha de la barra de herramientas.

   Proporcione comentarios de revisión seleccionando un tipo de comentario adecuado en la barra de herramientas y pulse Intro para enviar el comentario.

   >[!NOTE]
   >
   > El panel Comentarios muestra únicamente los comentarios proporcionados sobre los temas actuales. Cuando se desplaza el enfoque a otro tema, se muestran los comentarios proporcionados sobre el otro tema.

1. Haga clic en el botón **Cerrar** cuando termine de revisar el tema. Al hacer clic en el botón **Cerrar**, se le redirigirá a la página desde la que obtuvo acceso al tema de revisión.

## Funciones adicionales disponibles en la pantalla de revisión

**Vista de documento y vista de tema**: de forma predeterminada, si se comparten varios temas para su revisión, se muestra a los revisores una vista de documento compuesta de los temas. En el caso de una revisión de mapa DITA, todos los temas del mapa se presentan en forma de un único documento, similar a una vista de libro. Si lo desea, también puede hacer clic en un tema en particular y solo ese tema se muestra en la pantalla de revisión.

Cuando vea un solo tema, obtendrá una opción adicional para volver a la vista de documento. En la siguiente captura de pantalla, se abre un tema concreto de un archivo de mapa para su revisión. La opción resaltada: **Mostrar vista de documento** permite al usuario volver a la vista de documento del archivo de asignación.

![](images/switch-document-view.png){width="800" align="left"}

**Uso de diferentes tipos de herramientas de comentarios**: puede agregar comentarios entre líneas resaltando texto, tachando texto, insertando texto o agregando una nota de comentario. A continuación se describen los distintos tipos de herramientas de comentarios que se proporcionan en la barra de herramientas Comentarios:

![](images/comments-toolbar.png){width="350" align="left"}

- **Resaltar** \(![](images/review-highlight-icon.svg)\): para agregar un comentario resaltado, seleccione el texto y haga clic en el icono Resaltar. O bien, haga clic en el icono Resaltar y seleccione el texto deseado:

  ![](images/highlight-comment.png){width="650" align="left"}

  Aparece una ventana emergente en el panel Comentarios, donde puede agregar el comentario para el contenido resaltado.

- **Tachado** \(![](images/review-text-strike-through-icon.svg)\): Si desea sugerir la eliminación de contenido, puede seleccionarlo y hacer clic en el icono Tachado. O bien, seleccione el texto deseado y haga clic en la tecla Supr:

  Aparece una ventana emergente en el panel Comentarios, donde puede agregar el comentario para el contenido eliminado.

- **Insertar texto** \(![](images/review-insert-text-icon.svg)\): Si desea insertar texto, haga clic en el icono Insertar texto y coloque el cursor donde desee insertar el texto y escriba la información. O bien, coloque el cursor donde desee insertar texto y empiece a escribir. La información añadida aparece en una fuente de color verde:

- **Agregar comentario**\(![](images/review-comment-icon.svg)\): si desea agregar un tipo de comentario de nota adhesiva, haga clic en el icono Agregar comentario e introduzca el comentario en la ventana emergente.


**Barra de herramientas contextual**

También puede resaltar o tachar texto rápidamente con la barra de herramientas contextual. Siga estos pasos para comentar mediante la barra de herramientas contextual:

1. Seleccione el texto que desee resaltar o tachar. Aparecerá la barra de herramientas contextual.

   ![](images/review-quick-launch-toolbar.png){width="550" align="left"}

1. Haz clic en el icono **Resaltar** o **Tachar**.
1. Puede agregar comentarios en el panel de comentarios para la acción de resaltado o tachado.

**Revisar con el panel Comentarios**: el panel Comentarios muestra una lista de comentarios proporcionados sobre el tema actual. En este panel también se muestran los comentarios de otros revisores si el tema se envía a varios revisores. Cada comentario del panel de comentarios está vinculado al texto correspondiente del tema actual. Ayuda a identificar el texto comentado. Cada comentario muestra el nombre del revisor que lo ha agregado junto con la marca de tiempo.

Los comentarios se muestran en el orden del texto comentado en el documento. Por ejemplo, hay un comentario resaltado en la primera frase y un comentario de texto insertado en la segunda frase del primer párrafo, y el comentario de texto resaltado se muestra antes del comentario de texto insertado.

A continuación, se describen las tareas que puede realizar mediante el panel Comentarios:

- Al hacer clic en un comentario, se resalta y se muestra la ubicación del comentario correspondiente en el documento.
- Puede agregar respuestas a los comentarios.
- Puede editar su propio comentario haciendo clic en el texto comentado en el panel Comentarios y, a continuación, seleccionando **Editar** en el menú Opciones.
- Para eliminar sus propios comentarios, haga clic en el comentario en el panel Comentarios y, a continuación, seleccione la opción **Eliminar** en el menú Opciones.

  ![](images/review-comment-options-menu.png){width="300" align="left"}

  >[!NOTE]
  >
  > El menú Opciones sólo aparece cuando pasa el ratón por encima de sus propios comentarios. No se muestra para los comentarios de otros revisores.

- Todos los usuarios participantes pueden responder a los comentarios enviados por otros usuarios. En un comentario, haga clic en **Responder** y presione Entrar para enviar una respuesta.

**Modo de previsualización**

- Al abrir un tema en el modo Vista previa, se muestra cómo se mostrará cuando un autor lo vea después de aplicar todos los cambios. Por ejemplo, todo el texto insertado se muestra como texto normal y todo el texto tachado \(eliminado\) se elimina del contenido.

- La siguiente captura de pantalla muestra el contenido en el modo *Revisar*:

![](images/review-author-mode.png){width="550" align="left"}

La siguiente captura de pantalla muestra el contenido en el modo *Vista previa*:

![](images/review-preview-mode.png){width="550" align="left"}

**Agregar datos adjuntos a los comentarios** -   Si desea complementar su comentario proporcionando información adicional que está disponible en algún otro archivo, puede adjuntarla a su comentario. Como revisor, puede agregar fácilmente uno o varios archivos del sistema local al comentario. Se puede agregar un archivo a todas las formas de comentarios compatibles: Resaltar, Tachar, Insertar texto o un comentario.

Al insertar cualquiera de los comentarios, aparece la ventana emergente de comentarios. Después de proporcionar comentarios o información adicional en la ventana emergente, puede enviarla pulsando Intro. Una vez agregado el comentario, tiene la opción de agregar un archivo adjunto a ese comentario.

![](images/comment-pop-up-panel.png){width="800" align="left"}

En la captura de pantalla anterior, el documento contiene la ventana emergente del comentario resaltado y el comentario también se agrega en el panel Comentarios. El icono de archivo adjunto ![](images/file-attach-review.svg) está disponible junto con el comentario en ambas ubicaciones.

Siga estos pasos para agregar archivos adjuntos al comentario:

1. Haga clic en el icono *Agregar archivo adjunto* ![](images/file-attach-review.svg) del comentario con el que desea agregar un archivo adjunto.

   Aparecerá el cuadro de diálogo Abrir archivo.

1. Seleccione uno o varios archivos que desee adjuntar.

   Los archivos seleccionados se muestran junto con el comentario en el panel Comentarios.

   En el panel Comentarios puede ver el nombre del archivo y su tamaño. También tiene la opción de quitar un archivo haciendo clic en el icono de eliminación ![](images/Delete_icon.svg) asociado al nombre del archivo.

1. Haga clic en **Enviar**.

   Los archivos adjuntos se cargan y se añaden al comentario.


**Notas adicionales sobre cómo trabajar con datos adjuntos:**

- De forma predeterminada, solo se muestran dos archivos adjuntos a un comentario. Si hay más archivos, el botón **Ver datos adjuntos** de la derecha muestra el número de todos los archivos adjuntos \(que son más de dos\) asociados con el comentario. Puede hacer clic en el número para ver todos los archivos adjuntos. Por ejemplo, si tiene cuatro archivos adjuntos con un comentario, verá +2 en el botón.

![](images/review-view-attachment.png){width="550" align="left"}

- Al pasar el puntero del ratón sobre un archivo adjunto, se proporcionan las opciones para descargarlo o quitarlo. La eliminación de los datos adjuntos solo está disponible si el revisor actual ha agregado ese comentario, como se muestra en la siguiente captura de pantalla:

![](images/current-user-comment-options.png){width="550" align="left"}

Los demás revisores o autores solo obtienen la opción Descargar archivo adjunto.

![](images/other-reviewer-download.png){width="550" align="left"}

- Puede descargar todos los archivos adjuntos asociados a un comentario desde el cuadro de diálogo **Ver archivos adjuntos**. Seleccione los archivos adjuntos y haga clic en el icono **Descargar** en el nivel de comentario.

- También puede eliminar los archivos adjuntos asociados a un comentario en el cuadro de diálogo **Ver archivos adjuntos**. Seleccione los archivos adjuntos y haga clic en el icono **Eliminar**.

![](images/attach-files-comments-panel.png){width="550" align="left"}


**Panel de condiciones** -   Si el tema tiene contenido condicional, verá el icono **Condiciones** \(![](images/conditions-icon.svg)\) a la derecha. Al hacer clic en el icono **Condiciones**, se abre el panel Condiciones, que le permite resaltar el contenido según las condiciones disponibles en el tema.

:   De manera predeterminada, la opción **Resaltar todas las condiciones** está habilitada, todas las condiciones están seleccionadas, todo el contenido se muestra y el contenido condicionado se muestra resaltado tanto en el modo de revisión como de vista previa.

:   Puede deshabilitar la opción **Resaltar todas las condiciones** y ver todo el contenido presente en el tema como texto normal sin resaltados.

![](images/review-conditions-panel.png){width="350" align="left"}

Puede elegir ocultar o mostrar una condición específica.

- Si oculta una condición, el contenido que tenga esa condición no se resaltará en el modo de revisión.
- Si muestra una condición, el contenido condicionado se resaltará en el modo de revisión. Por ejemplo, en la siguiente captura de pantalla, solo el contenido usa dos condiciones: `win` y `mac` está resaltado.


![](images/review-condition-normal-mode.png){width="650" align="left"}

En el modo de vista previa, se muestra el contenido no condicional y el contenido condicional que utiliza las dos condiciones mostradas: `win` y `mac`. No se muestra el contenido condicional restante para el cual se ocultan las condiciones.

**Revisión en tiempo real** -   El panel Comentarios se actualiza en tiempo real con comentarios y comentarios o acciones realizadas por el autor en los comentarios.

- Varios revisores podrán dejar comentarios o responder a comentarios simultáneamente en el mismo documento. Puede averiguar quién está revisando el documento actualmente pasando el ratón sobre el icono de usuario en la esquina superior derecha de la pantalla.

- Si un tema forma parte de varias tareas de revisión, los comentarios realizados en una tarea no se muestran en la otra tarea.

- Al hacer clic en el icono Comentario obsoleto \(![](images/outdated-comment-icon.svg)\), se muestran las diferencias entre la versión más reciente y la versión comentada del documento. Los números de versión \(de las versiones que se comparan\) se muestran en la parte superior de los documentos.

  ![](images/comments-page-review-mode.png){width="800" align="left"}

  >[!NOTE]
  >
  > Cuando pasa el ratón por encima del icono Comentario obsoleto, se muestra el número de versión del tema en el que se ha añadido el comentario. Por ejemplo, si se ha proporcionado un comentario en la versión 1.0, se muestra lo mismo.

- Al hacer clic en un comentario obsoleto, se abre la versión de ese comentario en el panel izquierdo. La versión anterior se muestra en el panel izquierdo y la versión actual en el derecho. Todos los comentarios de la versión obsoleta se importan en el lado izquierdo. Puede comparar la versión anterior con la versión actual.

**Filtrar comentarios** -   Puede filtrar los comentarios de un documento para ver comentarios específicos según sea necesario. Para filtrar comentarios, haga clic en el icono **Filter** \(![](images/filter-search-icon.svg)\) que aparece en el menú a la derecha del cuadro de texto Buscar comentarios del panel Comentarios.

Seleccione una o más de las siguientes opciones de filtrado en el cuadro de diálogo **Tipo de filtro** y haga clic en **Aplicar**.

- **Tipo de revisión** - Filtrar según el tipo de comentarios - Resaltar, eliminar, insertar o comentar.
- **Estado de revisión**: filtre según el estado del comentario como Aceptado, Rechazado o Ninguno.
- **Revisores**: filtre según el nombre del revisor.

- **Versiones**: filtra según los comentarios recibidos en una versión concreta del tema.

  Al utilizar los filtros, los comentarios del panel derecho se filtran según la selección y el número de comentarios del panel izquierdo se actualiza en consecuencia.


Para quitar el filtro y ver todos los comentarios, anule la selección de todos los filtros del cuadro de diálogo **Tipo de filtro** y haga clic en **Aplicar**.

**Tema principal:**[ Revisar temas o asignaciones](review.md)
