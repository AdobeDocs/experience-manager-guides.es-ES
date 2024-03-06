---
title: Sugerencias inteligentes con tecnología de IA para crear contenido
description: Aprenda a ver y utilizar sugerencias inteligentes con tecnología de IA en el editor web.
source-git-commit: eea4a30b91fd5c28647fd7ea95dd8058ec411adc
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 0%

---



# Sugerencias inteligentes con tecnología de IA para crear contenido

Guías del Experience Manager proporciona el **Sugerencias inteligentes** que le ayuda a crear contenido coherente y preciso.

Mientras crea contenido, la variable **Sugerencias inteligentes** Esta función puede buscar mediante IA y mostrar el contenido existente que es semánticamente similar a su contenido. A continuación, puede elegir el contenido que mejor coincida con el que desee incluir en el tema actual como referencia.

Esto le ayuda a reutilizar contenido existente del repositorio de documentación y a crear contenido coherente. Por ejemplo, está creando un documento que contiene información sobre **Adobe Firefly**, incluido un párrafo sobre **Adobe**. En ese caso, puede ver y agregar rápidamente la referencia de contenido desde otro tema, como **Adobe Photoshop**, que incluye el mismo párrafo.





Cuando se abre un tema en el Editor Web, la variable **Sugerencias inteligentes** el panel aparece a la derecha.

>[!NOTE]
>
> El administrador debe configurar la variable **Sugerencias inteligentes** función. Para obtener más información, consulte [Configuración de las sugerencias inteligentes con tecnología de IA para la creación](../cs-install-guide/conf-smart-suggestions.md) de la Guía de instalación y configuración para Cloud Service.

![Panel de sugerencias inteligentes](images/smart-suggestions-panel.png){width="300" align="left"}

*Ver el **Sugerencias inteligentes**panel.*

Realice los siguientes pasos para ver las sugerencias inteligentes para agregar referencias de contenido adecuadas al tema:

1. Seleccionar **Sugerencias inteligentes** ![icono de sugerencias inteligentes](images/smart-suggestions-icon.svg) para abrir el panel.



   >[!NOTE]
   >
   > En el [perfiles globales o de carpeta](../cs-install-guide/conf-folder-level.md#conf-ai-smart-suggestions)Sin embargo, el administrador debe definir los archivos o carpetas que se van a indizar para las sugerencias inteligentes, el número mínimo de caracteres que debe introducir para ver las sugerencias y el número máximo de sugerencias que puede ver en la lista.

1. Escriba el contenido en el tema para ver las sugerencias relacionadas. Asegúrese de que la longitud de caracteres del contenido supera lo que el administrador ha establecido en el perfil de carpeta para que aparezcan las sugerencias de contenido.

1. Seleccionar **Sugerencias para la etiqueta actual** ![icono de etiqueta actual de sugerencias inteligentes](images/smart-suggestions-current-tag-icon.svg) para ver las sugerencias de creación para la etiqueta actual donde se coloca el puntero del mouse.  Las sugerencias para ver y agregar referencias de contenido desde los archivos indexados se muestran en función del contenido de la etiqueta actual.

   Método abreviado de teclado: **Windows** (*Ctrl* + *K*),  **macOS** (*Comando* + *K*)
1. Seleccionar **Sugerencias para el documento completo**  ![icono de documento completo de sugerencias inteligentes](images/smart-suggestions-complete-document-icon.svg) para ver las sugerencias basadas en el contenido presente en el documento completo.  Las sugerencias inteligentes![icono de sugerencias inteligentes](images/smart-suggestions-complete-document-icon.svg) se muestra junto al contenido donde se encuentra una coincidencia adecuada.

   Método abreviado de teclado: **Windows** ( *Ctrl* + *Shift* +  *K* ),  **macOS** (*Comando* + *Shift* + *K* )

   >[!NOTE]
   >
   > Solo puede ver las sugerencias de la ventanilla actual (el contenido visible en la pantalla). Para ver sugerencias para cualquier otro contenido del documento, desplácese hacia arriba o hacia abajo para mostrarlo en la ventanilla y, a continuación, seleccione ![icono de sugerencias inteligentes](images/smart-suggestions-complete-document-icon.svg) icono .

1. Seleccione el **Sugerencias inteligentes** ![icono de sugerencias inteligentes](images/smart-suggestions-complete-document-icon.svg) junto a las etiquetas agregadas al documento para ver las sugerencias inteligentes.
1. Puede ver las sugerencias inteligentes en la **Reutilización de contenido** cuadro de sugerencias.  Guías del Experience Manager proporciona sugerencias para hacer coincidir exactamente el contenido y el contenido con el mismo significado. Por ejemplo, puede buscar el tema que contenga el número de versión exacto, como &quot;versión 2023.03.12&quot;. También puede buscar &quot;Adobe tiene su sede en San José, California&quot; y encontrar contenido similar como &quot;San José tiene los cuartos de muchas compañías de software como Adobe&quot;.
1. Seleccionar **Información de contenido** ![Información de contenido](images/smart-suggestions-content-info-icon.svg) para ver los detalles.
   ![Panel de información de contenido](images/smart-suggestions-content-information.png){width="300" align="left"}

   *Vea la información detallada sobre la referencia de contenido.*

   1. El título del tema que contiene la referencia de contenido se muestra como un hipervínculo.
   1. Ruta del archivo que contiene la referencia de contenido.
   1. El tipo de referencia donde se hace referencia al contenido.
   1. Los nombres de los ficheros DITA a los que se hace referencia en el tema se muestran como hipervínculos.
1. Seleccionar **Previsualización de contenido sugerido** ![icono de vista previa de sugerencias inteligentes](images/smart-suggestions-preview-icon.svg) para comparar el contenido actual con el contenido sugerido. Esto le ayuda a comparar las diferencias y determinar si desea agregar la referencia de contenido para el contenido sugerido y hacerlo coherente o conservar el contenido actual.

   ![Previsualización de contenido sugerido](images/smart-suggestions-suggested-content-preview.png){width="800" align="left"}

   *Previsualice la comparación entre el contenido actual y el contenido sugerido.*

1. Clic **Aceptar** para añadir la referencia de contenido sugerida en la **Previsualización de contenido sugerido** Cuadro de diálogo.
1. También puede seleccionar **Aceptar** o **Rechazar** en el **Reutilización de contenido** Cuadro de sugerencias para ver las recomendaciones adecuadas.



Esta función inteligente es práctica y minimiza el esfuerzo de búsqueda manual de contenido, lo que le permite concentrarse más en la generación de nuevo contenido. También facilita una mejor colaboración en equipo y ayuda a mantener la coherencia en el contenido creado por varios autores.

