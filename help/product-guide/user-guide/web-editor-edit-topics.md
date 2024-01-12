---
title: Editar temas en el editor web
description: Aprenda a editar temas en el editor web. AEM Obtenga información acerca de las distintas funciones de edición para modificar los archivos de temas en las guías de la.
exl-id: 8da37a81-e8c3-434f-b3f4-4723d87c2ade
feature: Authoring, Web Editor
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 0%

---

# Editar temas en el editor web {#id2056B040VUI}

El Editor Web incluye una serie de características de edición que permiten crear o modificar fácilmente los archivos de temas. En términos generales, realizaría los siguientes pasos para editar un tema en el Editor Web.

>[!IMPORTANT]
>
> Si aparece un error de aplicación mientras trabaja en el Editor Web, actualice la página para seguir trabajando.

1. Para realizar cambios en el tema, haga clic dentro del límite de texto del elemento requerido y comience a realizar ediciones.

1. Para insertar un elemento específico, haga clic en al final del elemento después del cual desea insertar el nuevo elemento y haga clic en el icono de elemento requerido en la barra de herramientas. También puede utilizar el método abreviado de teclado `Alt+Enter` para invocar el **Insertar elemento** emergente.

   Aparecerá una lista de elementos que se pueden utilizar en el tema. AEM Guías de realiza una colocación inteligente de los elementos según su ubicación válida en el tema.

   >[!NOTE]
   >
   > También puede elegir qué icono se mostrará en la barra de herramientas configurando la variable `ui_config.json` archivo ubicado en - `/etc/designs/fmdita/clientlibs/xmleditor/`. Para obtener más información acerca de cómo personalizar características, póngase en contacto con el administrador del sistema.

1. Cuando haya terminado de editar el documento, haga clic en **Guardar**.

   >[!NOTE]
   >
   > AEM Si no desea confirmar los cambios en el repositorio de la, haga clic en **Cerrar** y haga clic en **Cerrar sin guardar** en el cuadro de diálogo Cambios no guardados.

   **Actualizar el explorador mientras edita los archivos**
Las Guías del Experience Manager proporcionan la compatibilidad para actualizar el explorador mientras edita el contenido en el Editor Web. Esta función le ayuda a seguir editando contenido en caso de que encuentre un error de aplicación mientras trabaja. Si pulsa el botón de actualización del explorador mientras se abren uno o más archivos con cambios no guardados para su edición, se le advertirá de que se pueden perder los cambios no guardados. Tiene la opción de cancelar la operación de actualización y guardar los archivos para conservar los cambios.

   Incluso al actualizar el explorador, las vistas de los paneles izquierdo y derecho se conservan en el editor web. Guías del Experience Manager restaura el último estado guardado de los archivos abiertos en el Editor Web al actualizar el explorador. Por ejemplo, los archivos abiertos en el panel Repositorio se vuelven a abrir. El panel Mapa se conserva junto con el mapa abierto anteriormente.

   El tema activo o el mapa DITA se vuelve a abrir en el área de edición de contenido.

   El panel derecho también se vuelve a abrir y muestra la misma vista que antes de la actualización.

   **Indicador de copia de trabajo**
AEM Guías de trabajo proporciona el indicador de copia de trabajo que muestra si la \(copia de trabajo\) actual del archivo está sincronizada con la versión guardada o no. Si ha realizado cambios en la copia actual y no ha guardado el archivo, aparecerá una marca \* junto con el título en la ficha de archivo del tema. Este indicador actúa como un recordatorio para guardar los cambios y desaparece al guardar el archivo.

   ![](images/working-copy-text-update-indicator.png){width="550" align="left"}

   AEM Guías también indica si la última copia \(de trabajo\) guardada del archivo está sincronizada con la versión guardada o no. Si hay cambios sin guardar entre la copia de trabajo y la última versión guardada, aparecerá una marca \* junto con la información de la versión que se muestra en la esquina superior derecha de la ficha del archivo del tema. Este indicador sirve como recordatorio para guardar y crear una versión a partir de la copia \(de trabajo\) actual del archivo.

   ![](images/version-update-indicator.png){width="550" align="left"}


**Tema principal:**[ Trabajar con el editor web](web-editor.md)
