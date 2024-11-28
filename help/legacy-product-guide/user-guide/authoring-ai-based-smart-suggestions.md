---
title: Sugerencias inteligentes con tecnología de IA para crear contenido
description: Aprenda a ver y utilizar sugerencias inteligentes con tecnología de IA en el editor web.
source-git-commit: 324b9b1364c14117740a924e825395f7c9d5c424
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 0%

---

# Sugerencias inteligentes con tecnología de IA para crear contenido

Experience Manager Guides proporciona sugerencias inteligentes que le ayudan a crear contenido coherente y preciso.

Mientras crea contenido, la función **Sugerir contenido reutilizable** de la herramienta Asistente de IA puede buscar mediante IA y mostrar el contenido existente que sea semánticamente similar a su contenido. A continuación, puede elegir el contenido que mejor coincida con el que desee incluir en el tema actual como referencia.

Esto le ayuda a reutilizar contenido existente del repositorio de documentación y a crear contenido coherente. Por ejemplo, está creando un documento que contiene información sobre **Adobe Firefly**, incluido un párrafo sobre **Adobe**. En ese caso, puede ver y agregar rápidamente la referencia de contenido desde otro tema, como **Adobe Photoshop**, que incluye el mismo párrafo.
>[!NOTE]
>
> En los [perfiles globales o de nivel de carpeta](/help/product-guide/cs-install-guide/conf-folder-level.md#conf-ai-smart-suggestions), el administrador debe definir los archivos o carpetas que se van a indizar para las sugerencias inteligentes, el número mínimo de caracteres que se deben especificar para ver las sugerencias y el número máximo de sugerencias que se pueden ver en la lista.

Realice los siguientes pasos para ver las sugerencias inteligentes para agregar referencias de contenido adecuadas al tema:


1. Seleccione el contenido del tema para ver las sugerencias relacionadas. Asegúrese de que la longitud de caracteres del contenido supera lo que el administrador ha establecido en el perfil de carpeta para que aparezcan las sugerencias de contenido.
1. En el panel Asistente de IA, seleccione **Sugerir contenido reutilizable** ![icono de sugerencia de contenido reutilizable ](./images/ai-suggest-reusable-content-icon.svg).

1. Seleccione una etiqueta para ver las sugerencias de creación de la etiqueta actual  Las sugerencias para ver y agregar referencias de contenido desde los archivos indexados se muestran en función del contenido de la etiqueta actual. También puede seleccionar varias etiquetas.


1. Seleccione todas las etiquetas para ver las sugerencias en función del contenido presente en el documento completo.  El icono **Sugerir contenido reutilizable** ![ai sugerir contenido reutilizable ](./images/ai-suggest-reusable-content-icon.svg) se muestra junto al contenido donde se encuentra una coincidencia adecuada.



   >[!NOTE]
   >
   > Solo puede ver las sugerencias de la ventanilla actual (el contenido visible en la pantalla). Para ver sugerencias de cualquier otro contenido del documento, desplácese hacia arriba o hacia abajo para mostrarlo en la ventanilla móvil y, a continuación, seleccione **Sugerir contenido reutilizable** ![ai sugerir icono de contenido reutilizable ](./images/ai-suggest-reusable-content-icon.svg).


1. Puede ver las sugerencias inteligentes en el panel Sugerencias.  Experience Manager Guides proporciona sugerencias con contenido que es similar al contexto o tiene el mismo significado. Por ejemplo, puede buscar el tema que contenga el número de versión exacto, como &quot;versión 2023.03.12&quot;. También puede buscar &quot;Adobe tiene su sede en San José, California&quot; y encontrar contenido similar como &quot;San José tiene los cuartos de muchas compañías de software como Adobe&quot;.
1. Seleccione **Información de contenido** ![Información de contenido](images/smart-suggestions-content-info-icon.svg) para ver los detalles.

   ![Panel de información de contenido](images/smart-suggestions-content-information.png){width="300" align="left"}

   *Ver la información detallada sobre la referencia de contenido.*

   1. El título del tema que contiene la referencia de contenido se muestra como un hipervínculo.
   1. Ruta del archivo que contiene la referencia de contenido.
   1. El tipo de referencia donde se hace referencia al contenido.
   1. Los nombres de los ficheros DITA a los que se hace referencia en el tema se muestran como hipervínculos.
1. Seleccione **Vista previa** ![icono de vista previa](./images/expand-icon.svg) para comparar el contenido actual con el contenido sugerido. Esto le ayuda a comparar las diferencias y determinar si desea agregar la referencia de contenido para el contenido sugerido y hacerlo coherente o conservar el contenido actual.

   ![Sugerir vista previa de contenido reutilizable](images/ai-assistant-suggest-reusable-content.png)

   *Vista previa de la comparación entre el contenido actual y el contenido sugerido.*

1. Haga clic en **Aceptar** para agregar la referencia de contenido sugerida en la vista previa de **Sugerir contenido reutilizable**.
1. También puede seleccionar **Aceptar** o **Descartar** en el panel de sugerencias para obtener las recomendaciones adecuadas.


Esta función inteligente es práctica y minimiza el esfuerzo de búsqueda manual de contenido, lo que le permite concentrarse más en la generación de nuevo contenido. También facilita una mejor colaboración en equipo y ayuda a mantener la coherencia en el contenido creado por varios autores.

>[!NOTE]
>
>Las sugerencias inteligentes no conservan los datos más allá de la sesión actual. Para obtener respuestas, las sugerencias inteligentes se basan únicamente en el índice creado en el contenido que reside en la base de datos interna. No se utilizan herramientas de IA externas, lo que garantiza que los datos permanezcan en el sistema.
