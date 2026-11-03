---
title: Asistente de IA agente para la capacidad de etiquetado inteligente
description: Aprenda a utilizar el asistente de inteligencia artificial aplicada a la agencia para la capacidad de etiquetado inteligente de temas y mapas en una sola operación.
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 01ef49b5e26c31359559d9849e6726f704393cd7
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 0%
---

# Etiquetado inteligente con el asistente de IA

La habilidad Etiquetado inteligente, disponible en el modo Agentic del asistente de IA a través de Adobe CX Enterprise Coworker, hace que el etiquetado de su contenido sea más rápido, fácil y coherente. Analiza el contenido y recomienda las etiquetas relevantes en función de la taxonomía de su organización, lo que elimina la necesidad de revisar manualmente el contenido e identificar las etiquetas aplicables. El administrador puede configurar las taxonomías que se usan para generar recomendaciones de etiquetas mediante [configuración de Workspace](../install-conf-guide/workspace-settings.md#general) al seleccionar los áreas de nombres relevantes para el área de trabajo.

Mantenga el control revisando las etiquetas sugeridas y eligiendo aplicarlas o rechazarlas antes de confirmar su selección. Esto reduce el esfuerzo manual, mejora la precisión del etiquetado y ayuda a mantener metadatos coherentes en toda la documentación.


## Aplicar etiquetas a uno o varios temas con la habilidad de etiquetado inteligente

Siga estos pasos para utilizar el Asistente de IA para aplicar etiquetas a uno o varios temas con la habilidad de etiquetado inteligente:

1. Inicie sesión en Experience Manager Guides.
1. En la página de inicio, seleccione **Ayudante de IA** en la barra de navegación. Asegúrese de que el administrador habilite el [Asistente de IA en modo automático](../install-conf-guide/workspace-settings.md).
1. Añada el tema para el que desea generar recomendaciones de etiquetas mediante uno de los siguientes métodos:

   - **Uso de mensajes sugeridos**: para el primer chat en el área de respuesta, seleccione **Sugerir etiquetas para un mensaje de archivo**. La solicitud se agrega automáticamente al espacio de solicitud. Seleccione `[file]` y, a continuación, elija el tema del repositorio o una colección en el cuadro de diálogo **Seleccionar archivo**. Puede seleccionar un tema del cuadro de diálogo **Seleccionar archivo**.

     ![Acceder al panel del Asistente de inteligencia artificial aplicada a la agencia con las indicaciones sugeridas](images/suggested-prompts.png){width="650"}

   - **Usando acceso directo**: escriba `/` en el campo Preguntar, luego elija **Agregar referencia de repositorio** para elegir un tema del Repositorio (o **Agregar archivos del dispositivo** para cargar un tema desde el equipo) y escriba un mensaje como *Sugerir etiquetas para un archivo*.

   - **Arrastrar y soltar**: Arrastre y suelte uno o varios temas en el espacio Preguntar y escriba un mensaje como *Sugerir etiquetas para un archivo*.

     ![Para acceder al panel del Asistente de inteligencia artificial aplicada a la agencia, arrastre y suelte un tema o mapa](images/dragging-prompts.png){width="650"}

   - **Especificar rutas de acceso temáticas**: escriba `@` seguido de las rutas de acceso separadas por comas para varios temas de las mismas asignaciones o de otras diferentes, e introduzca un mensaje como *Sugerir etiquetas para un archivo*.

     ![Adición masiva al panel del Asistente de inteligencia artificial aplicada a la agencia](images/topics-path-add.png){width="650"}

1. Seleccione **Enviar**.

1. El asistente de IA analiza el contenido del tema y genera recomendaciones de etiquetas.

   ![Interfaz del panel del Asistente de inteligencia artificial aplicada a la agencia mientras analiza y piensa](images/guides-ai-analysis.png){width="650"}

1. Revise las etiquetas sugeridas de la siguiente manera:

   >[!NOTE]
   >
   > Para los temas que ya contienen etiquetas, el Ayudante de IA muestra las etiquetas existentes. Estas etiquetas son de solo lectura y no se pueden modificar ni eliminar.

   - Para un solo tema, puede **aceptar** las recomendaciones para aplicarlas o **rechazarlas** si no son necesarias.

     ![Respuesta del panel del Asistente de inteligencia artificial aplicada a la agencia después del análisis del contenido](images/guides-ai-tags-review.png){width="650"}

   - Para varios temas:
     1. Seleccione **Vista previa** para revisar las recomendaciones de etiquetas generadas por IA.

        ![Previsualización del análisis masivo del panel del Asistente de inteligencia artificial aplicada a la agencia](images/topics-tag-preview.png){width="650"}

     1. Revise las etiquetas sugeridas para cada tema y elija una de las siguientes acciones:
        - **Acepte todo** para aplicar todas las etiquetas sugeridas para todos los temas.
        - **Rechazar todo** para descartar todas las etiquetas sugeridas para todos los temas.
        - **Borrar todas las sugerencias** para quitar todas las etiquetas sugeridas para un tema específico.
        - Seleccione el icono **X** junto a una etiqueta para eliminar una sugerencia de etiqueta individual.

          ![Cuadro de diálogo de vista previa de análisis en masa del panel del Asistente de inteligencia artificial ](images/topics-tag-preview-dialog.png){width="650"}

1. Cuando acepta las etiquetas sugeridas, la habilidad Etiquetado inteligente agrega las etiquetas generadas por IA a las etiquetas ya aplicadas al contenido.

Una vez completada la revisión, el Asistente de IA muestra un resumen de las etiquetas aplicadas al tema y las recomendaciones de etiquetas rechazadas.

![Resumen de la respuesta del panel del Asistente de inteligencia artificial ](images/topic-tag-summary.png){width="650"}

## Aplicación de etiquetas a varios temas de un mapa mediante la habilidad de etiquetado inteligente

Siga estos pasos para utilizar el Asistente de IA para aplicar etiquetas a varios temas de un mapa con la habilidad de etiquetado inteligente:

1. Inicie sesión en Experience Manager Guides.
1. En la página de inicio, seleccione **Ayudante de IA** en la barra de navegación. Asegúrese de que el administrador haya activado el asistente de IA en modo automático.
1. Añada el mapa para el que desea generar recomendaciones de etiquetas utilizando cualquiera de los siguientes métodos, tal como se describe en los temas:

   - **Uso de mensajes sugeridos**: para el primer chat en el área de respuesta, seleccione **Sugerir etiquetas para un mensaje de archivo**. La solicitud se agrega automáticamente al espacio de solicitud. Seleccione `[file]` y, a continuación, elija el mapa del repositorio o una colección en el cuadro de diálogo **Seleccionar archivo**.

   - **Arrastrar y soltar**: Arrastre y suelte un mapa en el espacio Preguntar y escriba un mensaje como *Sugerir etiquetas para un archivo*.

   - **Usando acceso directo**: escribe `/` en el campo Preguntar, luego elige **Agregar referencia de repositorio** para elegir un mapa del Repositorio (o **Agregar archivos del dispositivo** para cargar un mapa desde tu equipo) e ingresa una solicitud como *Sugerir etiquetas para un archivo*.

     ![Etiquetado masivo del Asistente de IA agente](images/ai-map-selection.png){width="650"}

1. Seleccione **Enviar**.
Un mensaje indica que la asignación seleccionada contiene varios temas. Seleccione **Seleccionar temas** para elegir los temas para los que desea recomendaciones de etiquetas.

   ![Etiquetado masivo del Asistente de inteligencia artificial aplicada a la agencia al seleccionar temas](images/ai-select-topics.png){width="650"}

1. En el cuadro de diálogo **Seleccionar temas**, seleccione los temas para los que desea recomendaciones de etiquetas.\
   El cuadro de diálogo **Seleccionar temas** proporciona lo siguiente:

   - **Lista de temas:** Muestra todos los temas del mapa seleccionado. Seleccione los temas para los que desea generar recomendaciones de etiquetas.
   - **Panel de vista previa:** muestra una vista previa del tema seleccionado junto con las etiquetas existentes.
   - **Filtro:** Filtre los temas para mostrar solo los que tengan **Etiquetas agregadas** o **No se agregaron etiquetas**.

     ![Cuadro de diálogo Seleccionar temas al aplicar etiquetas](images/select-dialog.png){width="650"}

1. Seleccione **Confirmar**. El Asistente de IA analiza los temas seleccionados y muestra el número de recomendaciones de etiquetas generadas para cada tema.
1. Seleccione **Vista previa** para revisar las recomendaciones de etiquetas generadas por IA.
1. Revise las etiquetas sugeridas para cada tema y elija una de las siguientes acciones:
   - **Aceptar** para aplicar todas las etiquetas sugeridas para todos los temas.
   - **Rechazar** para descartar todas las etiquetas sugeridas para todos los temas.
   - **Borrar todas las sugerencias** para quitar todas las etiquetas sugeridas para un tema específico.
   - Seleccione el icono **X** junto a una etiqueta para eliminar una sugerencia de etiqueta individual.

     >[!NOTE]
     >
     > Para los temas que ya contienen etiquetas, el Ayudante de IA muestra las etiquetas existentes. Estas etiquetas son de solo lectura y no se pueden modificar ni eliminar.

   ![Cuadro de diálogo de vista previa de etiquetado masivo del Asistente de inteligencia artificial agente](images/preview-dialog.png){width="650"}

1. Cuando acepta las etiquetas sugeridas, la habilidad de etiquetado inteligente agrega las etiquetas generadas por IA a las etiquetas ya aplicadas al contenido.

Una vez finalizada la revisión, el Asistente de IA muestra un resumen de las etiquetas aplicadas a cada tema y de las recomendaciones de etiquetas rechazadas.

