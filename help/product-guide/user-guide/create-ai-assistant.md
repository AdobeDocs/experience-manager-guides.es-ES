---
title: Creación de temas y asignaciones con el Asistente de IA
description: Obtenga información sobre cómo crear borradores de nuevos temas y mapas DITA a partir de notas, especificaciones o contenido pegado con el Asistente de IA y, a continuación, revíselos antes de guardarlos.
source-git-commit: b9dc9674244cbcf20fba1f51665afb4440172cdb
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 0%
---

# Creación del primer borrador del contenido

La habilidad **Crear** en el modo Agente del Asistente de IA le ayuda a generar el primer borrador de contenido estructurado a partir de notas, especificaciones, imágenes de pizarra, capturas de pantalla u otros materiales de referencia disponibles. La aptitud identifica automáticamente el tipo de tema DITA adecuado, como Concepto, Tarea, Referencia o Resolución de problemas, en función del contenido y de las plantillas de tema disponibles en el repositorio, lo que reduce el esfuerzo manual necesario para estructurar y crear contenido.

Puede adjuntar un archivo, seleccionar un archivo existente como referencia para el tono y el estilo, y especificar la carpeta donde desea guardar el contenido generado. Para crear el primer borrador del contenido deseado, siga estos pasos:

1. Inicie sesión en Experience Manager Guides.
1. En la página de inicio, seleccione **Ayudante de IA** en la barra de navegación. Asegúrese de que el administrador habilite el [Asistente de IA en modo automático](../install-conf-guide/workspace-settings.md).

1. Seleccione **Crear** en el panel Asistente de IA.

   La solicitud de inicio aparece en el cuadro de solicitud: *Crear contenido de borrador que haga referencia a los archivos adjuntos y que tenga un tono de contenido similar al de [archivo]*

1. Adjunte sus notas, especificaciones u otros archivos de referencia al indicador mediante cualquiera de los siguientes métodos:

   - **Usando acceso directo**: escriba `/` en el campo Preguntar y, a continuación, elija **Agregar referencia de repositorio** para elegir el archivo del repositorio (o **Agregar archivos del dispositivo** para cargar el archivo desde el equipo).

   - **Usando los iconos Adjuntar archivos o Agregar contexto (+)**: Agregue archivos desde el sistema local.

   - **Arrastrar y soltar**: Arrastre y suelte el archivo que desea redactar desde el sistema directamente en el espacio de solicitud.

1. *(Opcional)* En la solicitud de inicio, seleccione `[file]`. Seleccione el tema existente cuyo tono desee que coincida con el borrador. Puede elegir el tema del repositorio o de una colección. El nombre del tema reemplaza a `[file]` en la solicitud.

   ![Seleccione el marcador de posición de archivo para elegir el tema](images/sample-create.png){width="650"}

1. Seleccione **Enviar**.

   El asistente de IA analiza el contenido y enumera cada paso que completa.

1. Responda a cualquier pregunta de seguimiento de AI Assistant para proporcionar los detalles necesarios para generar el contenido.

   ![Seleccione el marcador de posición de archivo para elegir el tema](images/folder-create.png){width="650"}

1. Seleccione **Vista previa** para revisar el tema generado.

   Compruebe cada borrador con el material de origen y los tipos de tema que solicitó.

   ![](images/preview-create.png)

1. Seleccione una de las siguientes opciones:

   - **Aceptar** para guardar el tema en la carpeta confirmada
   - **Rechazar** para descartar los cambios sin guardar nada. Puede proporcionar un motivo para rechazar el contenido del borrador e introducir un mensaje que especifique los cambios que desee. El asistente de IA utiliza sus comentarios para revisar el contenido del borrador.

     El tema ya está disponible en el repositorio.

     ![](images/accept-reject-create.png)

Después de que el Ayudante de IA cree un tema, puede abrirlo en el Editor y refinar el contenido mediante mensajes de seguimiento. Esto le permite mejorar el tema de forma iterativa sin iniciar una nueva conversación. Cada cambio propuesto se muestra en la vista previa con **Control de cambios** habilitado, lo que le permite revisar las modificaciones antes de aplicarlas.

Por ejemplo, para refinar el título de un tema generado:

1. Abra el tema recién creado en el Editor desde el cuadro de diálogo Ayudante de IA.

   ![](images/editor-create-agent.png)

1. En el panel Asistente de IA, escriba un mensaje de seguimiento, como `Improve the title of this topic to make it generic.`

   ![](images/follow-up-prompt.png)

1. Seleccione **Enviar**.

   El asistente de IA analiza y sugiere un nuevo título.

1. Seleccione **Vista previa** para revisar los cambios propuestos.

   La vista previa muestra el título revisado con las marcas de revisión, destacando lo que se ha modificado.

   ![](images/review-change.png)

1. Seleccione **Aceptar** para aplicar los cambios al tema.

   ![](images/final-output-create.png)

Puede seguir perfeccionando otros elementos del tema, como párrafos, pasos o tablas, proporcionando indicadores adicionales en la misma conversación.





