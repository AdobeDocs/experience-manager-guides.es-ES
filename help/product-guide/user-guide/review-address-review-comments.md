---
title: Comentarios de revisión de direcciones
description: AEM Aprenda a dirigir los comentarios de revisión como autor en las guías de. Descubra cómo un autor puede editar, filtrar, aceptar o rechazar comentarios en un documento.
exl-id: 4c969788-f700-4fd6-8afa-8e5b411b59f3
feature: Reviewing
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1031'
ht-degree: 0%

---

# Comentarios de revisión de direcciones {#id2056B0X0KBI}


Como autor, puede dirigir los comentarios de un tema mediante el Editor Web. Los comentarios se cargan en función de la tarea de revisión seleccionada en el panel Revisar. Para obtener más información, consulte **Revisar** panel ![](images/active-review-tasklist-icon.svg) descripción de la función en [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS) sección.

En las secciones siguientes se describen las formas de editar comentarios en el Editor Web.

Un autor puede dirigir comentarios en un documento desde el Editor Web. Se proporcionan indicadores visuales que indican si los comentarios insertados \(texto\), eliminados o resaltados. Además, el tipo de comentario se menciona en la parte superior de cada entrada de comentario.

>[!NOTE]
>
> Al dirigirse a los comentarios de revisión \(para un documento de revisión activo\), asegúrese de que no abre el tema de revisión en varias pestañas con la vista de etiquetas completa habilitada, no cambie entre los modos de vista Autor y Origen.

![](images/comments-page-web-editor_cs.png){width="800" align="left"}

En el modo Editor web, el panel derecho contiene los iconos Revisar y Cambios rastreados. El panel Revisar muestra todos los comentarios realizados por los revisores en el documento. El **Cambios seguidos** el panel muestra el estado de todos los comentarios insertados y eliminados del documento.

- **A**: seleccione una tarea de revisión para ver los comentarios de revisión. Si el tema se ha compartido para su revisión en varias tareas de revisión, verá esas tareas en esta lista desplegable.

  Cuando selecciona una tarea de revisión de la lista, puede ver los comentarios realizados por los revisores de dicha tarea. Puede dirigir los comentarios de revisión de forma independiente en las tareas, lo que significa que cualquier actualización de un comentario solo es visible para los revisores de esa tarea respectiva.

- **B:**  Seleccionar **Revisar detalles** ![](images/active-review-info-icon.svg) en el **Comentarios** panel para ver más información sobre la tarea de revisión:

   - **Nombre**: Nombre de la tarea de revisión
   - **Revisar versión**: Muestra la versión asociada con la tarea de revisión seleccionada. Esto le ayuda a realizar un seguimiento de la versión que ha compartido para su revisión
   - **Estado**: Estado actual de la tarea de revisión.

  >[!NOTE]
  >
  > Si el mapa raíz de la tarea de revisión es diferente del mapa raíz de creación, muestra la información sobre él para indicar que el mapa raíz de creación y de revisión no coinciden.

- **C**: si ha actualizado el tema después de iniciar la revisión, al hacer clic en el icono Revertir tema a versión de revisión se revierte la copia de trabajo a la versión compartida para revisión. Esto facilita la incorporación de los comentarios de revisión directamente en la versión compartida para revisión. Después de incorporar los comentarios, puede guardar los cambios en la versión revertida o crear una nueva revisión del tema. Si elige crear una nueva revisión del tema, se crea una nueva rama a partir de la versión del tema compartida para su revisión. Por ejemplo, si ha compartido la versión de `1.2` de un tema para revisarlo mientras la versión de creación actual es `1.3`, puede utilizar este icono para volver a la versión `1.2` para incorporar comentarios de revisión. Si elige crear una nueva revisión después de incorporar cambios en la versión `1.2`, luego una nueva rama con versión `1.2.0` se crea para el tema.

  Normalmente, después de incorporar los comentarios de revisión, le gustaría combinar los cambios de la última versión del tema. Para ello, utilice el [Combinar](web-editor-features.md#id205DF04E0HS) función para obtener todas las actualizaciones realizadas después de compartir el tema para su revisión.

- **D**: abra la vista en paralelo para mostrar la versión comentada del tema. Como se ve en la captura de pantalla anterior, la sección situada más a la izquierda es la última versión del tema, en la que puede realizar cambios. La siguiente sección es la versión comentada del tema. A medida que navega entre los comentarios del tema, la vista lateral cambia y muestra esa versión del tema en el que se realizó el comentario. Cada comentario del panel de comentarios está vinculado al texto correspondiente de esta sección. Ayuda a identificar el texto comentado. Los comentarios se muestran en el orden del texto comentado en el documento.

  Puede ver el número de versión en la parte superior de la vista lateral. Al hacer clic de nuevo en este icono, se oculta la versión comentada del tema.

- E: importar directamente los comentarios \(o Tachado\) insertados y eliminados del tema. Después de hacer clic en el icono Importar, todas las inserciones y eliminaciones de texto se muestran en la copia de trabajo del tema. Ahora, hay dos formas de aceptar o rechazar comentarios.

  Si desea incorporar el cambio sugerido \(inserción o eliminación\) de uno en uno, simplemente haga clic con el botón derecho en el comentario del contenido y seleccione Aceptar cambio o Rechazar cambio. Según su selección, el comentario se acepta o se rechaza. En caso de comentarios aceptados, el contenido se añade al contenido; y en caso de rechazo, se elimina del contenido. Además, el estado del comentario cambia en el panel Revisar.

  ![](images/import-comment-accept-web-editor_cs.png){width="800" align="left"}

  También puede utilizar la función de revisión del panel derecho para aceptar o rechazar comentarios. Al hacer clic en cualquier comentario, se resalta el comentario en el documento.

  ![](images/changes-tab_cs.png){width="800" align="left"}

  >[!IMPORTANT]
  >
  > La función de importar comentarios solo funciona en los documentos que no han cambiado desde que se compartieron para su revisión. Si ha realizado algún cambio después de enviar el documento para su revisión, recibirá un aviso a **Forzar importación** comentarios en el documento. Sin embargo, si lo hace, se perderán todas las actualizaciones realizadas en el documento. El **Forzar importación** La alerta también se muestra si el documento se crea fuera de y luego se comparte para su revisión. Puede continuar e importar los comentarios.

  Cuando acepte o rechace un comentario, éste se quitará de la lista Cambios realizados. Esto también sirve como indicador de cuántas observaciones deben abordarse en el documento.

- **F**: en el menú Más opciones, descargue todos los archivos adjuntos disponibles en el tema de revisión.
- **G**: busque un texto dentro de los comentarios.
- **H**: aceptar o rechazar un comentario.

- **I**: aplique un filtro en los comentarios. Puede filtrar para ver los comentarios basándose en el Tipo de revisión \(todos, resaltados, eliminados, insertados o notas adhesivas\), Estado de la revisión \(todos, aceptados, rechazados o ninguno\), Revisores \(todos los revisores o revisores específicos\)\) o Versiones del tema.


**Tema principal:**[ Revisar temas o mapas](review.md)
