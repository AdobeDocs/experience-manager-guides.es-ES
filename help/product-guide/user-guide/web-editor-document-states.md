---
title: Estado del documento
description: AEM Conozca los tipos de estados de documento en las Guías de. Obtenga información sobre cómo cambiar o ver el estado del documento y utilizar el estado del documento en DLC.
exl-id: 3a68b2ed-b917-4f05-8b2b-d2722a740502
feature: Authoring, Features of Web Editor, Document State
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 0%

---

# Estado del documento {#id1821HC00URO}

AEM Para administrar la preparación de los documentos, las guías de la documentación proporcionan la propiedad de estado del documento para indicar el estado actual del documento. Los estados de documento le ayudan a averiguar rápidamente si un documento es nuevo, está en revisión o revisa el estado completado.

## Tipos de estados de documento

Un documento puede tener cualquiera de los estados de documento definidos en el perfil Estado del documento. Por ejemplo, un documento puede tener cualquiera de los siguientes estados de documento:

- Borrador: indica que el documento se crea y se guarda con los nuevos cambios.
- En revisión: indica que se ha iniciado un flujo de trabajo de revisión para el documento.
- Revisado: indica que el documento ha sido revisado por los usuarios previstos.

Estos estados se establecen manual o automáticamente según la configuración del perfil Estados del documento. Por ejemplo, si el perfil Estado del documento está configurado con el estado de inicio como Borrador y el estado En revisión está definido para los documentos que se están revisando. A continuación, al crear un documento, el estado del documento se establece en *Borrador*. Si inicia una tarea de revisión, el estado del documento cambia a En revisión.

También puede cambiar manualmente el estado del documento para uno o varios documentos. Sin embargo, si decide cambiar el estado del documento para varios documentos, el estado permitido se determina según los estados comunes permitidos para los documentos seleccionados. Por ejemplo, supongamos que ha definido los estados del documento como Borrador, En revisión, Revisado y Listo para publicar, en el mismo orden. En el documento one.dita, el estado se establece en *Borrador* y en el documento dos.dita, el estado se establece en Revisado. Al seleccionar ambos: uno.dita y dos.dita, el estado del documento permitido será *Listo para publicar*. Como dos.dita está en *Revisado* state, el siguiente estado posible para two.dita es only *Listo para publicar*, que se muestra cuando se seleccionan ambos documentos.

>[!NOTE]
>
> Un documento sólo puede existir en un estado a la vez.

## Cambiar estado del documento

Para cambiar el estado de un documento, realice los siguientes pasos:

1. En la interfaz de usuario de Assets, seleccione uno o más documentos para los que desee cambiar el estado del documento.
1. En la barra de herramientas principal, haga clic en **Propiedades**.
1. Seleccione el nuevo estado de la lista **Estado del documento** menú desplegable. Puede seleccionar solo los estados de documento permitidos en la sección Transición de estado del perfil Estado del documento.

   >[!NOTE]
   >
   >Los administradores pueden ver todos los estados de los documentos y cambiar el documento a cualquier estado posible.

1. Haga clic en **Guardar y cerrar**.

## Ver estado del documento

La vista de tarjeta de la interfaz de usuario de Assets muestra el estado actual junto con la fecha de creación y el tamaño del tema o mapa DITA correspondiente.

![](images/document_state.png){width="800" align="left"}

## Usar estados de documento en DLC

Los estados de documento desempeñan un papel importante en la administración del ciclo de vida de los documentos en DLC. Si su organización sigue estrictamente el DLC, tener un mecanismo para controlar la edición de documentos en función de su estado se convierte en una función esencial. Por ejemplo, puede permitir la edición de documentos cuando se encuentren en *Borrador* o *En revisión* estados. Sin embargo, una vez que un documento se revise y esté listo para publicarse, debe haber una forma de evitar nuevas modificaciones de los documentos.

AEM Guías de documentos proporciona un flujo de trabajo de aprobación de documentos, que le ayuda a controlar el ciclo de vida del proceso de desarrollo de documentos. Una vez que un documento está listo para publicarse o ha alcanzado el penúltimo estado, puede marcarlo como aprobado. AEM Una vez aprobado un documento, Guías de la crea una nueva versión del documento y lo convierte en de sólo lectura. A continuación, puede mover el documento para publicarlo o crear una línea base para un procesamiento posterior.

Para iniciar una nueva versión a partir de los documentos marcados como aprobados, un autor debe iniciar una nueva versión. Al iniciar una nueva versión, el estado del documento cambia a *Borrador* otra vez. Al cambiar el estado del documento a *Borrador*, el documento vuelve a ser editable y puede seguir trabajando en la próxima versión.

Para utilizar la función de aprobación de documentos, realice los siguientes pasos:

>[!NOTE]
>
> El administrador debe habilitar la función de flujo de trabajo de aprobación. Para obtener más información, consulte *Habilitar flujo de trabajo de aprobación* de la sección Instalar y configurar las guías de Adobe Experience Manager as a Cloud Service.

1. En el Editor Web, abra el documento que desea marcar para su aprobación.

1. Haga clic en **Marcar como aprobado**![](images/mark_approve_icon.svg) icono.

1. Si el documento se encuentra en el estado para marcarse como aprobado, aparecerá el siguiente cuadro de diálogo:

   ![](images/mark-approved-correct-state.png){width="300" align="left"}

   Si el documento no se puede marcar como aprobado, aparecerá el siguiente mensaje:

   ![](images/mark-approved-incorrect-state.png){width="300" align="left"}

1. Si el documento está listo para marcarse como aprobado, seleccione una etiqueta de la lista desplegable y haga clic en **Aprobar**.

   >[!NOTE]
   >
   > Si el administrador no ha configurado una lista predefinida de etiquetas, se muestra un campo de texto de forma libre para introducir una etiqueta.

1. Una vez que el documento se haya marcado correctamente como aprobado, **Previsualizar** del documento se muestra en modo de solo lectura.

   ![](images/approved-doc-read-only.png){width="650" align="left"}

   >[!NOTE]
   >
   > En el modo Vista previa, todas las opciones de edición se eliminan de la barra de herramientas. Además, la vista Autor y Origen del documento también se ha eliminado de la navegación superior.


Una vez marcado un documento como aprobado, ya no está disponible para su edición. Si desea utilizar el documento para la siguiente versión, debe devolverlo a la *Borrador* estado. Para volver a cambiar el estado de un documento aprobado a *Borrador* modo, realice los siguientes pasos:

1. En un documento aprobado, haga clic **Iniciar una nueva versión** Icono ![](images/approved-restart-draft-mode-icon.svg).

   Aparecerá el mensaje Iniciar nueva versión.

1. Clic **Confirmar**.

   El estado del documento cambia a Borrador y el documento se abre en el Editor Web en modo de edición.


**Tema principal:**[ Trabajar con el editor web](web-editor.md)
