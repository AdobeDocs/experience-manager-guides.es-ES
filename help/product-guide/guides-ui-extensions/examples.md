---
sidebar_position: 8
source-git-commit: eb3fe92d36bc58a11e47f786a10d5938e2ed0184
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 0%

---


# Ejemplos

En este paquete también hemos proporcionado algunos ejemplos de personalización (disponibles en `guides_extension/src`). A continuación se muestra una breve descripción de cada uno de ellos.

1. [Menú contextual](./../../src/file_options.ts)
En este ejemplo hemos personalizado la variable `file_options` menú contextual, para quitar el `Delete` y `Edit` y reemplace las opciones `Duplicate` opción con un `Download` opción.

2. [Panel izquierdo](../../src/left_panel_container.ts)
En este ejemplo hemos personalizado la variable `left tab panel` para tener otro`tab` titulado &quot;TEST EXTENSION&quot; y una `tab panel` que tiene una etiqueta: `Test Tab Panel`

3. [Panel derecho](../../src/right_panel_container.ts)
En este ejemplo hemos personalizado la variable `right tab panel` para tener otro `tab` titulado &quot;TEST EXTENSION&quot; y una `tab panel` que tiene una etiqueta: `New Tab Panel`

4. [Panel Repositorio](../../src/repository_panel.ts)

5. [Barra de herramientas](../../src/toolbar.ts)
En este ejemplo hemos reemplazado el `Insert Element`, `Insert Paragraph`, `Insert Numbered List`, `Insert Bulleted List` botones con un solo `More Insert Options` botón que contiene todos estos elementos.

[Revisar ejemplos de aplicaciones]

1. [Cuadro de herramientas Anotación](../../src/review_app_examples/annotation_extension.ts)
AEM En este ejemplo, se ha agregado otro botón al cuadro de herramientas de anotación que abre el tema de revisión actual en la vista de datos de.

2. [Revisar comentario](../../src/review_app_examples/review_comment.ts)
En este ejemplo, se ha agregado, reemplazado el nombre de usuario por información de usuario (que consta del nombre completo y el título del comentarista), se ha agregado un ID de comentario único, un icono mailTo y se han agregado campos de entrada para mencionar la gravedad y el motivo del comentario.
También hemos agregado una `accept with modification` en los comentarios del lado del editor XML que abre un cuadro de diálogo.

3. [Respuesta de comentario](../../src/review_app_examples/comment_reply.ts)
En este ejemplo hemos añadido, reemplazado el nombre de usuario por información de usuario (que consiste en el nombre completo y el título del comentarista) y añadido un icono mailTo en el encabezado del comentario.

4. [Panel de revisión en línea](../../src/review_app_examples/inline_review_panel.ts)
En este archivo, calculamos y asignamos el ID de comentario único, mencionado en la variable `Review Comment` y `Comment Reply` ejemplos.
   - El `setCommentId` establece el ID de comentario único para cada comentario en función del recuento de comentarios.

   - El `setUserInfo` establece el valor de userInfo, utilizando el nombre completo y el título de cada comentario.

   - El `onNewCommentEvent` garantiza el `setUserInfo` se llama para cada nuevo comentario o respuesta.

   - El `updatedProcessComments` se ejecuta para cada evento de comentario nuevo y garantiza que `setCommentId` se llama a si recibimos un nuevo evento de comentario.

5. [Panel de revisiones de temas](../../src/review_app_examples/topic_reviews.ts): este archivo amplía [Panel de revisión en línea](../../src/review_app_examples/inline_review_panel.ts) para que las personalizaciones agregadas también funcionen en el lado de la aplicación de revisión.

6. [Cuadro de diálogo Aceptar con modificación](../../src/review_app_examples/accept_with_modification_dialog.ts)
Este es un ejemplo de adición de nuevos widgets a la aplicación. Aquí hemos creado un nuevo cuadro de diálogo, que tiene dos campos de texto de entrada: `Revised Text` y `Adjudicator Comment Rationale`

![Cuadro de diálogo Aceptar con modificación](./imgs/accept_with_modification_dialogue.png)

Este es el panel de revisión antes y después de la personalización:

![Panel de revisión;](./imgs/review_panel.png)
![Cuadro de diálogo Aceptar con modificación](./imgs/customised_review_panel.png)
