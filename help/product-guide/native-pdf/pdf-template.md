---
title: Creación y personalización de plantillas de PDF nativas
description: Obtenga información sobre cómo crear y personalizar plantillas de PDF nativas.
exl-id: 7660da8e-8a1e-4493-b99b-9b5de9a7483f
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: a6c87e6f9a68962488e70985a0513dcb05eaa9cd
workflow-type: tm+mt
source-wordcount: '1151'
ht-degree: 0%

---

# plantilla de PDF {#PDF-template}

El uso de una plantilla garantiza la coherencia en el diseño y la estructura del contenido. Como las plantillas están predefinidas, puede evitar volver a trabajar en los problemas de formato que surgen para cada proyecto nuevo o actualización. Las plantillas permiten diseñar diseños de página, aplicar estilos al contenido y aplicar diversas configuraciones para personalizar el PDF.

## Plantillas de PDF personalizadas y de fábrica

Hay algunas plantillas de fábrica de muestra listas para usar, que los desarrolladores pueden usar como plantillas base para crear plantillas personalizadas según sus requisitos organizativos.



## Creación de una nueva plantilla de PDF {#create-pdf-template}

Puede crear plantillas de PDF personalizadas con diseños de página específicos y definir el formato para los componentes del diseño de página (como TDC, índice, glosario) o los componentes DITA (como encabezado, párrafo, lista) mediante hojas de estilo.

Para crear una nueva plantilla de PDF, realice los siguientes pasos:

1. En el Editor Web, vaya a **Output** pestaña.
1. Seleccionar **Plantillas** <img src="./assets/template.png" alt= "icono de plantillas" width="25"> en el panel izquierdo.

   <img src="assets/create-pdf-template.png" alt="Crear plantilla de PDF" width="400">

1. En el **Plantillas** , seleccione la **+** junto a **Plantillas** y elija **Plantilla de PDF**.
1. En el **Nueva plantilla de PDF** , seleccione una plantilla de fábrica que desee utilizar como base para crear la plantilla personalizada. También puede utilizar el cuadro de búsqueda para buscar una plantilla.
1. Especifique un título para la plantilla.

   >[!NOTE]
   >
   >  También puede obtener una vista previa de una miniatura para la plantilla al crear y duplicar una plantilla. Editar o eliminar la miniatura utilizando [**Propiedades**](#properties-option) en el **Opciones** después de crear la plantilla.

1. Haga clic en **Crear**.

   La nueva plantilla se crea y se agrega en **Plantillas** panel.

## Duplicación de una plantilla de PDF {#duplicate-pdf-template}

Si desea crear una nueva plantilla con los mismos diseños de página y formato que los de una plantilla existente, puede crear una copia. Una vez duplicada una plantilla, puede personalizar aún más sus componentes según sea necesario.

Para duplicar una plantilla de PDF existente, siga los siguientes pasos:

1. En el Editor Web, vaya a **Output** pestaña.
1. Seleccionar **Plantillas** <img src="./assets/template.svg" alt= "icono de plantillas" width="25"> en el panel izquierdo. Esto abre el **Plantillas** ventana.
1. Pase el ratón sobre la plantilla que quiera duplicar y seleccione la **...** *Opciones* y elija **Duplicar** en el menú contextual.

   Esto abre el **Duplicar plantilla de PDF** diálogo.

   <img src="assets/duplicate-template.png" alt="Duplicar plantilla de PDF" width="350">

   *Seleccione una plantilla para duplicarla, previsualice la miniatura y actualice el título en la **Duplicar plantilla de PDF**diálogo.*

1. Especifique un título para la plantilla.

   El **Título** El campo se rellena previamente como una copia del mismo título que la plantilla de origen. Verá un mensaje de error si existe la plantilla con el mismo título.



1. Para especificar un título preferido, quite el título rellenado previamente y especifique un título.
1. Clic **Duplicar**.

   Se crea una plantilla duplicada y se añade en **Plantillas**.

## Otras operaciones en las plantillas

También puede realizar las siguientes operaciones en las plantillas desde el **Opciones** menú:

<img src="assets/PDF-template-options.png" alt="Duplicar plantilla de PDF" width="350">

### Eliminar

Seleccione la opción Eliminar para eliminar la plantilla seleccionada. A continuación, seleccione Sí en el mensaje de confirmación.
El ajuste preestablecido se elimina del **Plantillas**.

### Propiedades{#properties-option}

Seleccione esta opción para ver y editar las propiedades de la plantilla. Puede obtener una vista previa de la miniatura existente para la plantilla. También puede editar o eliminar la miniatura. También puede cambiar el título y la descripción de la plantilla.

### Ver en la IU de Assets

Seleccione esta opción para ver la plantilla en la interfaz de usuario de Assets. Al abrir la ubicación raíz de la plantilla, puede ver todos los recursos de la plantilla.

Una vez creada la plantilla personalizada, puede elegirla en Diseños de página en el ajuste preestablecido de salida del PDF.

Obtenga información sobre cómo [publicación de una salida de PDF](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/output-gen/web-editor/native-pdf-web-editor.html?lang=en).

>[!NOTE]
>
>Si la carpeta tiene un perfil de carpeta configurado, solo verá las plantillas de PDF que estén configuradas en el perfil de carpeta.

En función de la configuración, el administrador puede configurar las plantillas:

+++ Cloud Services

Para obtener más información sobre la configuración de perfiles globales y de nivel de carpeta, consulte [Configuración de plantillas](../cs-install-guide/conf-folder-level.md#id1889D0IL0Y4) de la Guía de instalación y configuración para Cloud Service.

+++

+++ Software On-Premise

Para obtener más información sobre la configuración de perfiles globales y de nivel de carpeta, consulte [Configuración de plantillas de creación](../install-guide/conf-folder-level.md#create-custom-authoring-template-id1917d0eg0hj) de la guía de instalación y configuración in situ.

+++

## Personalización de una plantilla de PDF {#customize-pdf-template}

Puede personalizar las plantillas mediante la modificación de los componentes de la plantilla y la aplicación de formatos de estilo mediante hojas de estilo.

Para personalizar una plantilla de PDF, realice los siguientes pasos:

1. En el Editor Web, vaya a **Output** pestaña.
1. Expanda la barra lateral izquierda y seleccione **Plantillas**.

   Esto abre el **Plantillas** panel.

1. Para ver los componentes de una plantilla, siga uno de estos procedimientos:

   * Seleccione el icono > situado junto a una plantilla o haga doble clic en su nombre.
   * Pase el ratón sobre cualquier plantilla y seleccione el ... (**Opciones** ) y elija **Editar** en el menú contextual.

   De forma predeterminada, se abre la **Configuración** en el editor de plantillas.

   <img src="assets/customize-pdf-template.png" alt="Personalizar plantilla de PDF" width="350">

   >[!NOTE]
   >
   >  El administrador puede descargar las plantillas más recientes desde la siguiente ruta y reemplazar las existentes:
   >
   > `/libs/fmdita/pdf`

   Los distintos componentes de plantilla que puede personalizar se clasifican en las siguientes secciones:

   * Diseños de página: normalmente, un PDF contiene páginas diferentes, como una portada o una página de título, índice, capítulo, índice, citas, etc. La sección Diseños de página permite diseñar el aspecto de las diferentes páginas que compondrían el PDF. Para obtener más información, consulte [Diseños de página](../native-pdf/components-pdf-template.md#page-layouts).

     Además de la apariencia, también puede definir la disposición de los elementos de página, como el encabezado, el pie de página y las áreas de contenido de una página. Para obtener más información sobre cómo personalizar el diseño de una página, consulte [Creación y personalización de diseños de página](components-pdf-template.md#create-customize-page-layout).

   * Hojas de estilo: la configuración de la sección Hojas de estilo permite personalizar el aspecto de los componentes del diseño de página, como la TDC, el índice, el glosario, las citas, etc. Además, también se pueden personalizar estilos para el contenido DITA como encabezados, párrafos, listas, etc. Para obtener más información sobre el uso de las hojas de estilo, consulte [Uso de hojas de estilo para personalizar el PDF](components-pdf-template.md#stylesheet-customization).
   * Recursos: Almacene los archivos de recursos que necesite para personalizar o diseñar plantillas de PDF. Los recursos, como logotipos, fuentes personalizadas, imágenes de fondo y mucho más, se almacenan en Recursos.
También puede utilizar los recursos presentes en cualquier otra ubicación del repositorio. No es necesario crear recursos duplicados para cada plantilla y puede mantenerlos en una carpeta compartida y utilizarlos en todas las plantillas de PDF nativas.

     Para obtener más información sobre el uso de los recursos, consulte [Trabajo con recursos](components-pdf-template.md#work-with-resources).

   * Settings: configure los ajustes de salida para generar un PDF con la plantilla. Esta sección le permite definir la asignación de plantillas para varias páginas de un PDF, la página de inicio del capítulo, los marcadores de impresión, las citas, etc.

   También puede organizar el orden en que deben aparecer en la salida final del PDF.
Para obtener más información sobre la aplicación de la configuración, consulte [Configuración avanzada del PDF](components-pdf-template.md#advanced-pdf-settings).


1. Para personalizar un componente de plantilla, haga doble clic en un componente de plantilla o seleccione el icono > que hay antes.

   Por ejemplo, haga doble clic en *Diseños de página* o seleccione la opción *>* icono antes *Diseños de página* para ver los diseños de página disponibles.

   >[!NOTE]
   >
   >También puede actualizar una miniatura y la descripción de la plantilla mediante el [**Propiedades**](#properties-option) en el **Opciones** menú.

1. Cuando haya realizado los cambios deseados, seleccione *Guardar todo* (o `Ctrl+S`).
