---
title: Ejemplos
description: Lista de ejemplos de personalización
source-git-commit: fc0b19ac44ca9cbc1e9c5cf046f9a0a24f2a1794
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---


# Ejemplos

En este paquete también proporcionamos algunos ejemplos de personalización (disponibles en `guides_extension/src`). A continuación se muestra una breve descripción de cada uno de ellos.

1. [Menú contextual](./examples/file_options.ts)
En este ejemplo hemos personalizado el menú contextual `file_options`, para quitar las opciones `Delete` y `Edit`, y reemplazar la opción `Duplicate` con una opción `Download`.

2. [Panel izquierdo](./examples/left_panel_container.ts)
En este ejemplo, hemos personalizado `left tab panel` para que tenga otro `tab` titulado &quot;EXTENSIÓN DE PRUEBA&quot;, y un `tab panel` correspondiente con una etiqueta: `Test Tab Panel`

3. [Panel derecho](./examples/right_panel_container.ts)
En este ejemplo hemos personalizado `right tab panel` para que tenga otro `tab` titulado &quot;EXTENSIÓN DE PRUEBA&quot;, y un `tab panel` correspondiente con una etiqueta: `New Tab Panel`

4. [Panel Repositorio](./examples/repository_panel.ts)

5. [Barra de herramientas](./examples/toolbar.ts)
En este ejemplo hemos reemplazado los botones `Insert Element`, `Insert Paragraph`, `Insert Numbered List`, `Insert Bulleted List` con un solo botón `More Insert Options` que contiene todos estos elementos.

[Revisar ejemplos de aplicaciones]

1. [Cuadro de herramientas de anotaciones](./examples/review_app_examples/annotation_extension.ts)
AEM En este ejemplo, se ha agregado otro botón al cuadro de herramientas de anotación que abre el tema de revisión actual en la vista de datos de.

2. [Revisar comentario](./examples/review_app_examples/review_comment.ts)
En este ejemplo, se ha agregado, reemplazado el nombre de usuario por información de usuario (que consta del nombre completo y el título del comentarista), se ha agregado un ID de comentario único, un icono mailTo y se han agregado campos de entrada para mencionar la gravedad y el motivo del comentario.
También hemos agregado un botón `accept with modification` en los comentarios del lado del editor XML que abre un cuadro de diálogo.

3. [Respuesta de comentario](./examples/review_app_examples/comment_reply.ts)
En este ejemplo hemos añadido, reemplazado el nombre de usuario por información de usuario (que consiste en el nombre completo y el título del comentarista) y añadido un icono mailTo en el encabezado del comentario.

4. [Panel de revisión en línea](./examples/review_app_examples/inline_review_panel.ts)
En este archivo, calculamos y asignamos el ID de comentario único, mencionado en los ejemplos `Review Comment` y `Comment Reply`.
   - El método `setCommentId` establece el ID de comentario único para cada comentario según el recuento de comentarios.

   - `setUserInfo` establece el valor de userInfo, usando el nombre completo y el título de cada comentario.

   - El `onNewCommentEvent` garantiza que se llame al método `setUserInfo` para cada comentario o respuesta nuevo.

   - La función `updatedProcessComments` se ejecuta para cada nuevo evento de comentario y garantiza que se llame a `setCommentId` si se obtiene un nuevo evento de comentario.

5. [Panel de revisiones de temas](./examples/review_app_examples/topic_reviews.ts): Este archivo amplía el [Panel de revisiones en línea](./examples/review_app_examples/inline_review_panel.ts) para que las personalizaciones agregadas también funcionen en el lado de la aplicación de revisión.

6. [Aceptar con cuadro de diálogo de modificación](./examples/review_app_examples/accept_with_modification_dialog.ts)
Este es un ejemplo de adición de nuevos widgets a la aplicación. Aquí hemos creado un nuevo cuadro de diálogo, que tiene dos campos de texto de entrada: `Revised Text` y `Adjudicator Comment Rationale`

7. [Guardar revisión](./examples/save_revision.ts)
Este es un ejemplo de cómo actualizar un cuadro de diálogo existente. En esta sección agregamos un botón para publicar. Permitimos modificar el contenido del cuadro de diálogo. Consulte su json aquí: [`save_revision`](./jsons/dialogs/save_revision.json)

![Aceptar Con Cuadro De Diálogo De Modificación](./imgs/accept_with_modification_dialogue.png)

Este es el panel de revisión antes y después de la personalización:

![Panel de revisión;](./imgs/review_panel.png)
![Aceptar Con Cuadro De Diálogo De Modificación](./imgs/customised_review_panel.png)
