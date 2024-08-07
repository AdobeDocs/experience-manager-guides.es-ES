---
title: Notas de versión | Novedades de la versión de junio de 2023 de Adobe Experience Manager Guides
description: Conozca las funciones nuevas y mejoradas de la versión de junio de 2023 de Adobe Experience Manager Guides as a Cloud Service
exl-id: 625f9702-2b91-4622-9fec-282f47f1d7a6
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 0%

---

# Novedades de la versión de junio de 2023 de Adobe Experience Manager Guides as a Cloud Service

Este artículo cubre las funciones nuevas y mejoradas de la versión de junio de 2023 de Adobe Experience Manager Guides (más adelante denominadas *AEM Guides as a Cloud Service*).

Para obtener más información sobre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en esta versión, consulte [Notas de la versión](release-notes-2023-6-0.md).

## Informe Vínculos rotos en el editor web

AEM Guides permite comprobar la integridad general de los documentos técnicos y generar informes desde el editor web. Ahora, en la versión de junio de 2023 de AEM Guides, se incluye la función para ver y corregir los vínculos rotos. Este es un informe útil que le ayuda a administrar los vínculos rotos. Puede ver fácilmente los vínculos rotos presentes en el mapa DITA y también corregirlos.
![](assets/broken-link-report.png){width="800" align="left"}

Una vez corregido un vínculo, no se muestra en la lista de vínculos rotos.

Para obtener más información, consulte [Ver y corregir vínculos rotos](../user-guide/reports-web-editor.md#report-broken-links).

## Cambiar nombre y mover archivos en la vista Repositorio

Ahora también puede cambiar el nombre de un archivo o moverlo desde el panel del repositorio. Esta función es útil y ayuda a administrar los archivos fácilmente desde el panel Repositorio. Puede seleccionar un archivo y cambiarle el nombre o moverlo utilizando el menú **Opciones** del archivo seleccionado. AEM Guides muestra un mensaje de éxito al mover o cambiar el nombre de un archivo.

![](assets/rename-move-assets.png){width="650" align="left"}

Para obtener más información sobre el menú Opciones de un archivo, consulte la descripción de la característica **Vista del repositorio** en la sección [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Mejoras del PDF nativo

### Agregar una marca de agua a la salida del PDF para borradores de documentos

Ahora puede agregar una marca de agua a la salida del PDF del documento que aún no está aprobado. Esta marca de agua no aparece si genera el PDF para el documento en el estado de documento &#39;Aprobado&#39;. Por ejemplo, puede agregar una marca de agua Borrador para la salida del PDF.

Para obtener más información, consulte [Agregar una marca de agua a la salida del PDF para los borradores de documentos](../native-pdf/use-javascript-content-style.md#watermark-draft-document).

### Compatibilidad con variables de idioma

AEM Guides proporciona compatibilidad con variables de idioma. Puede utilizar variables de idioma para definir una versión localizada de las etiquetas integradas, como Nota, Precaución y Advertencia o texto estático en la salida del PDF.
Puede añadir las variables de idioma o la versión localizada de las etiquetas a las secciones correspondientes de la salida del PDF y en las plantillas de salida.

#### Variables de idioma en la salida del PDF

Puede utilizar las variables de idioma para definir etiquetas localizadas para elementos como Nota, Precaución y Advertencia. Puede actualizar el valor de estas variables en uno o más idiomas y, a continuación, el valor localizado se selecciona automáticamente en la salida del PDF.
Por ejemplo, puede presentar la etiqueta Nota en la salida del PDF de las siguientes maneras:

* Inglés: Nota
* Francés: Remarque
* Alemán: Hinweis

#### Variables de idioma en las plantillas de salida

Si se desea crear la salida del PDF en varios idiomas, se deben crear distintas plantillas de PDF que contengan texto localizado para cada idioma. Ahora, con la función de variables de idioma, solo debe crear la plantilla una vez. A continuación, para cualquier texto estático que necesite localizar, puede crear las variables de idioma correspondientes y utilizarlas en la plantilla.
Puede crear variables de idioma para texto más largo, como una oración completa o incluso un párrafo. También puede aplicar estilos y utilizar marcado de HTML para dar formato a estas variables de idioma.

Para obtener más información, vea [Compatibilidad con variables de idioma](../native-pdf/native-pdf-language-variables.md).

### AEM Posibilidad de utilizar metadatos de en diseños de PDF

Los metadatos son la descripción o definición del contenido. Estos metadatos se almacenan en el contenido del mapa DITA de origen.

Ahora, en AEM Guides también puede seleccionar las propiedades de metadatos de los recursos y agregarlas al diseño de página. A continuación, AEM Guides selecciona estas propiedades de metadatos de los recursos y los publica en la salida del PDF.


![](assets/native-pdf-metadata-asset.png){width="550" align="left"}

>[!NOTE]
>
> AEM Guides también admite las propiedades de metadatos para los mapas DITA.

Para obtener más información, consulte [Agregar campos y metadatos](../native-pdf/design-page-layout.md#add-fields-metadata).


## Mejoras de Schematron

### Usar instrucciones de informe para comprobar reglas en Schematron

AEM Guides ahora también admite las instrucciones de informe con Schematron. Una instrucción de informe genera un mensaje cuando una instrucción de prueba se evalúa como verdadera. Por ejemplo, si desea que la descripción breve tenga menos de 150 caracteres o menos, puede definir una instrucción de informe para comprobar los temas en los que la descripción breve tenga más de 150 caracteres.

Para obtener más información, consulte [Usar instrucciones de aserción e informe para buscar reglas](../user-guide/support-schematron-file.md#schematron-assert-report).

### Uso de expresiones Regex

También puede utilizar expresiones Regex para definir una regla con la función matches() y luego realizar la validación mediante el archivo Schematron.

Para obtener más información, consulte [Usar expresiones Regex](../user-guide/support-schematron-file.md#schematron-assert-report).


### Definir patrones abstractos

AEM Guides también admite patrones abstractos en Schematron. Puede definir patrones abstractos genéricos y reutilizarlos. Los patrones abstractos pueden simplificar el esquema de Schematron y también ayudarle a administrar y actualizar la lógica de validación.


Para obtener más información, vea [Definir patrones abstractos](../user-guide/support-schematron-file.md#schematron-abstract-patterns).

## AEM Navegue desde el Editor Web hasta la página principal de la

AEM Ahora puede navegar fácilmente desde el Editor Web a la página de inicio de la página de la página de inicio de la.

![](assets/web-editor-launch-page.png){width="800" align="left"}

* AEM Haga clic en el icono **Guías** (![](assets/aem-guides-icon.png) ) para volver a la página Navegación de la.


AEM Para obtener más información, consulte [Página de navegación de la](../user-guide/web-editor-launch-editor.md#id2056BG00RZJ).

## Gestión de definiciones jerárquicas de definiciones de temas y enumeraciones

AEM Guides incluye la potente función de crear mapas de esquema de asunto, que son una forma especializada de mapas DITA que se utilizan para definir sujetos taxonómicos y valores controlados. Ahora, AEM Guides también le permite definir la definición del asunto en un mapa y las definiciones de enumeración en otro mapa. A continuación, puede añadir la referencia de mapa y utilizar el esquema de asunto.
Las referencias de asunto y enumeración se resuelven en el mismo mapa o en el mapa al que se hace referencia.

Para obtener más información sobre la administración de definiciones jerárquicas de definiciones de temas y enumeraciones, consulte la descripción de la característica **Esquema de asunto** en la sección [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Compatibilidad con el formato XLIFF en la traducción

AEM Guides también admite el formato XLIFF (XML Localization Interchange File Format) en traducción. Ahora también puede elegir **Crear un nuevo proyecto de traducción XLIFF** para convertir el contenido XML al formato XLIFF.
Con este formato, puede exportar el contenido al formato XLIFF estándar del sector y, a continuación, proporcionar lo mismo a los proveedores de traducción. Para obtener más información, consulte [Crear un proyecto de traducción](../user-guide/translate-documents-web-editor.md#create-translation-project).

![](assets/translation-project-types.png){width="350" align="left"}



## Panel Favoritos mejorado

AEM Guides le ayuda a crear una colección o una lista de favoritos de sus archivos y carpetas y a utilizarlos fácilmente. Ahora el menú **Opciones** también está disponible en el panel **Favoritos**. Puede cambiar el nombre de la colección seleccionada o eliminarla del menú **Opciones**. Puede seleccionar la opción **Actualizar** para obtener una lista nueva de archivos o carpetas del repositorio. También puede ver el contenido de la carpeta en la interfaz de usuario de Assets.

![](assets/favorites-options.png){width="650" align="left"}

>[!NOTE]
>
> También puede actualizar la lista con el icono **Actualizar** de la parte superior.

Para obtener más información sobre el menú **Opciones** de una colección de favoritos, consulte la descripción de la característica **Favoritos** en la sección [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Cambiar al tema del sistema

Ahora también puede utilizar el tema del dispositivo. Con las **Preferencias de usuario**, puede configurar AEM Guides para que cambie automáticamente entre los temas claro y oscuro en función del tema del dispositivo.

![](assets/device-theme-user-preferences.png){width="550" align="left"}

Para obtener más información, consulte la descripción de la característica **Preferencias de usuario** en la sección [Barra de herramientas principal](../user-guide/web-editor-features.md#id2051EA0G05Z).
