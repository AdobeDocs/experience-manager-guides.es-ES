---
title: Comentarios de revisión de direcciones
description: Aprenda a dirigir comentarios de revisión como autor en AEM Guides. Descubra cómo un autor puede editar, filtrar, aceptar o rechazar comentarios en un documento.
exl-id: 4c969788-f700-4fd6-8afa-8e5b411b59f3
feature: Reviewing
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '1024'
ht-degree: 0%

---

# Comentarios de revisión de direcciones {#id2056B0X0KBI}


Como autor, puede dirigir los comentarios de un tema mediante el Editor Web. Los comentarios se cargan en función de la tarea de revisión seleccionada en el panel Revisar. Para obtener más información, vea la descripción de la característica del panel **Revisar** ![](images/active-review-tasklist-icon.svg) en la sección [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS).

En las secciones siguientes se describen las formas de dirigir los comentarios en el Editor Web.

Un autor puede dirigir comentarios en un documento desde el Editor Web. Se proporcionan indicadores visuales que indican si los comentarios insertados \(texto\), eliminados o resaltados. Además, el tipo de comentario se menciona en la parte superior de cada entrada de comentario.

>[!NOTE]
>
> Al dirigirse a los comentarios de revisión \(para un documento de revisión activo\), asegúrese de que no abre el tema de revisión en varias pestañas con la vista de etiquetas completa habilitada, no cambie entre los modos de vista Autor y Source.

![](images/comments-page-web-editor_cs-new.png){align="left"}

En el modo Editor web, el panel derecho contiene los iconos Revisar y Control de cambios. El panel Revisar muestra todos los comentarios realizados por los revisores en el documento. El panel **Control de cambios** muestra el estado de todos los comentarios insertados y eliminados del documento.

- **A**: seleccione una tarea de revisión para ver los comentarios de revisión. Si el tema se ha compartido para su revisión en varias tareas de revisión, verá esas tareas en esta lista desplegable.

  Al seleccionar una tarea de revisión de la lista, puede ver los comentarios realizados por los revisores en esa tarea. Puede dirigir los comentarios de revisión de forma independiente en las tareas, lo que significa que cualquier actualización de un comentario solo es visible para los revisores de esa tarea respectiva.

- **B:** Seleccione **Detalles de la revisión** ![](images/active-review-info-icon.svg) en el panel **Comentarios** para ver más información acerca de la tarea de revisión:

   - **Nombre**: nombre de la tarea de revisión
   - **Versión de revisión**: muestra la versión asociada con la tarea de revisión seleccionada. Esto le ayuda a realizar un seguimiento de la versión que ha compartido para su revisión
   - **Estado**: Estado actual de la tarea de revisión.

  >[!NOTE]
  >
  > Si el mapa raíz de la tarea de revisión es diferente del mapa raíz de creación, muestra la información sobre él para indicar que el mapa raíz de creación y de revisión no coinciden.

- **C**: si ha actualizado el tema después de iniciar la revisión, al seleccionar el icono Revertir tema a la versión de revisión, la copia de trabajo vuelve a la versión que se compartió para revisión. Esto facilita la incorporación de los comentarios de revisión directamente en la versión compartida para revisión. Después de incorporar los comentarios, puede guardar los cambios en la versión revertida o crear una nueva revisión del tema. Si elige crear una nueva revisión del tema, se crea una nueva rama a partir de la versión del tema compartida para su revisión. Por ejemplo, si compartió la versión `1.2` de un tema para su revisión mientras la versión de creación actual es `1.3`, puede utilizar este icono para volver a la versión `1.2` e incorporar comentarios de revisión. Si elige crear una nueva revisión después de incorporar cambios a la versión `1.2`, se crea una rama nueva con la versión `1.2.0` para el tema.

  Normalmente, después de incorporar los comentarios de revisión, le gustaría combinar los cambios de la última versión del tema. Para ello, usa la característica [Merge](web-editor-features.md#id205DF04E0HS) para obtener todas las actualizaciones realizadas después de compartir el tema para su revisión.

- **D**: abre la vista en paralelo para mostrar la versión comentada del tema. Como se ve en la captura de pantalla anterior, la sección situada más a la izquierda es la última versión del tema, en la que puede realizar cambios. La siguiente sección es la versión comentada del tema. A medida que navega entre los comentarios del tema, la vista lateral cambia y muestra esa versión del tema en el que se realizó el comentario. Cada comentario del panel de comentarios está vinculado al texto correspondiente de esta sección. Ayuda a identificar el texto comentado. Los comentarios se muestran en el orden del texto comentado en el documento.

  Puede ver el número de versión en la parte superior de la vista lateral. Si se vuelve a seleccionar este icono, se oculta la versión comentada del tema.

- E: importar directamente los comentarios \(o Tachado\) insertados y eliminados del tema. Después de seleccionar el icono Importar, todas las inserciones y eliminaciones de texto se muestran en la copia de trabajo del tema. Ahora, hay dos formas de aceptar o rechazar comentarios.

  Si desea incorporar el cambio sugerido \(inserción o eliminación\) de uno en uno, simplemente haga clic con el botón derecho en el comentario del contenido y seleccione Aceptar cambio o Rechazar cambio. Según su selección, el comentario se acepta o se rechaza. En caso de comentarios aceptados, el contenido se añade al contenido; y en caso de rechazo, se elimina del contenido. Además, el estado del comentario cambia en el panel Revisar.

  ![](images/import-comment-accept-web-editor_cs-new.png){align="left"}

  También puede utilizar el panel Control de cambios para aceptar o rechazar comentarios. Al seleccionar cualquier comentario, se resalta el comentario en el documento.

  ![](images/changes-tab_cs-new.png){align="left"}

  >[!IMPORTANT]
  >
  > La función de importar comentarios solo funciona en los documentos que no han cambiado desde que se compartieron para su revisión. Si ha hecho algún cambio después de enviar el documento para su revisión, recibirá una alerta para **Forzar importación** comentarios en el documento. Sin embargo, si lo hace, se perderán todas las actualizaciones realizadas en el documento. La alerta **Forzar importación** también se muestra si el documento se crea fuera de y luego se comparte para su revisión. Puede continuar e importar los comentarios.

  Cuando acepte o rechace un comentario, éste se quitará de la lista Cambios realizados. Esto también sirve como indicador de cuántas observaciones deben abordarse en el documento.

- **F**: en el menú Más opciones, descargue todos los archivos adjuntos disponibles en el tema de revisión.
- **G**: busca un texto dentro de los comentarios.
- **H**: aceptar o rechazar un comentario.

- **I**: aplique un filtro en los comentarios. Puede filtrar para ver los comentarios basándose en el Tipo de revisión \(todas, resaltadas, eliminadas, insertadas o notas adhesivas\), Estado de la revisión \(todas, aceptadas, rechazadas o ninguna\), Revisores \(todos los revisores o revisores específicos\)\) o Versiones del tema.


**Tema principal:**[ Introducción a la revisión](review.md)
