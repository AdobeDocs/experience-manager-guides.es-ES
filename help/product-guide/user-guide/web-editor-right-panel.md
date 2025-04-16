---
title: Panel derecho en el editor
description: Conozca el panel derecho en el editor. Obtenga información acerca de la interfaz y las funciones de Editor en Adobe Experience Manager Guides.
feature: Authoring, Features of Web Editor
role: User
exl-id: 6a0f4ed2-6eca-4b3c-bd3a-3f72f6919b36
source-git-commit: ffc9a9e15f11e7059822b7cf6d4707b83d15a4f4
workflow-type: tm+mt
source-wordcount: '965'
ht-degree: 1%

---

# Panel derecho en el editor

El panel derecho contiene información sobre el documento seleccionado actualmente.

>[!NOTE]
>
> Se puede cambiar el tamaño del panel derecho. Para cambiar el tamaño del panel, coloque el cursor sobre el límite del panel, el cursor cambiará a una flecha de dos puntas, seleccione y arrastre para cambiar el tamaño del ancho del panel.

El panel derecho le permite acceder a las siguientes funciones:

- [Propiedades del contenido](#content-properties)
- [Propiedades del archivo](#file-properties)
- [Revisión](#review)
- [Seguimiento de cambios](#track-changes)
- [Schematron](#schematron)

## Propiedades del contenido

Puede acceder a la función **Propiedades de contenido** seleccionando el icono **Propiedades de contenido** en el panel derecho. El panel **Propiedades de contenido** contiene información sobre el tipo de elemento seleccionado actualmente en el documento y sus atributos.

**Tipo**: puede ver y seleccionar las etiquetas de la jerarquía completa para la etiqueta actual en el menú desplegable.

**Atributos**: el **panel desplegable Atributos** está disponible en las vistas Diseño, Autor y Origen. Puede agregar, editar o eliminar fácilmente los atributos.

<details>
    <summary> Pasos para añadir atributos </summary>


1. Seleccione **Añadir**.

   ![atributos en propiedades de contenido](images/properties-tab-attributes_cs.png){width="300" align="left"}

1. En el panel desplegable **Atributo**, seleccione el atributo en la lista desplegable y especifique el valor de un atributo.  Luego selecciona **Agregar**.

   ![panel de atributos con varios atributos ](images/attributes-multiple-properties.png){width="300" align="left"}

1. Para editar el atributo, pasa el ratón sobre él y selecciona **Editar** ![editar-icono](images/edit_pencil_icon.svg).

1. Para eliminar el atributo, pasa el ratón sobre él y selecciona **Eliminar** ![delete-icon](images/Delete_icon.svg).

</details>


>[!NOTE]
>
> Incluso si el tema contiene contenido al que se hace referencia, puede agregar atributos en él mediante el panel de propiedades.

Si su administrador ha creado un perfil para atributos, obtendrá esos atributos junto con sus valores configurados. Mediante el panel de propiedades de contenido, puede elegir esos atributos y asignarlos a contenido relevantes de su tema. De este modo, también puede crear contenido condicional, que luego puede utilizar para crear resultados condicionales. Para obtener más información acerca de cómo generar resultados mediante ajustes preestablecidos condicionales, vea [Usar ajustes preestablecidos de condición](generate-output-use-condition-presets.md#).



## Propiedades del archivo

Vea las propiedades del archivo seleccionado seleccionando el icono Propiedades del archivo en el panel derecho. La función Propiedades del archivo está disponible en los cuatro modos o vistas siguientes: Diseño, Autor, Source y Vista previa.

Las propiedades del archivo tienen las dos secciones siguientes:

**General**

La sección General le permite acceder a las siguientes funciones:

![propiedades de archivo](images/file-properties-general.png){width="300" align="left"}

- **Nombre de archivo**: muestra el nombre de archivo del tema seleccionado. El nombre de archivo está enlazado mediante un hipervínculo a la página de propiedades del archivo seleccionado.
- **ID**: muestra el ID del tema seleccionado.
- **Etiquetas**: estas son las etiquetas de metadatos del tema. Se establecen desde el campo de etiquetas del Página de propiedades. Puede escribirlos o seleccionarlos en la lista desplegable.  Las etiquetas aparecen en la lista desplegable. Para eliminar un etiqueta, seleccione el icono de cruz situado junto al etiqueta.
- **Editar más propiedades**: puede editar más propiedades desde la página de propiedades del archivo.
- **Idioma**: muestra el idioma del tema. Se establece desde el campo language en la página de propiedades.
- **Creado el**: muestra la fecha y la hora en que se creó el tema.
- **Modificado el**: muestra la fecha y la hora en que se modificó el tema.
- **Bloqueado por**: muestra el usuario que bloqueó el tema.
- **Estado del** documento: se puede seleccionar y actualizar el estado documento del tema abierto actualmente. Para obtener más información, vista [Estado del](web-editor-document-states.md#) documento.

>[!NOTE]
>
> Puede copiar los valores de atributo de los distintos campos de las propiedades de Archivo en el portapapeles.

**Referencias**

La sección Referencias le permite acceder a las siguientes funciones:

![](images/file-properties-references.png){width="300" align="left"}

- **Utilizado en**: el Utilizado en referencias enumera los documentos a los que se hace referencia o se utiliza el archivo actual.
- **Vínculos de salida:** Los vínculos de salida enumeran los documentos a los que se hace referencia en el documento actual.

De forma predeterminada, puede ver los archivos por títulos. Al pasar el ratón por encima de un archivo, puede ver el título y la ruta del archivo como información sobre herramientas.

>[!NOTE]
>
> Como administrador, también puede elegir ver la lista de archivos por nombres de archivo en el Editor. Seleccione la **opción Archivo nombre** de la **sección de configuración** de visualización de archivos del editor en **preferencias** de usuario.

>[!NOTE]
>
> Todas las referencias utilizadas en y salientes están hipervinculadas al documentos. Puede abrir y editar fácilmente los documentos vinculados.

Además de abrir archivos, también puede realizar muchas acciones utilizando el **menú Opciones** en la sección Referencias. Algunas de las acciones que puede realizar incluyen Editar, Vista previa, Copiar UUID, Copiar ruta, añadir a colecciones, Propiedades.

## Revisión

Al seleccionar el icono Revisar, se abre el panel de revisión, en el que puede seleccionar una tarea de revisión para el documento abierto actualmente y ver los comentarios.

![](images/review-panel-before-opening.png){width="300" align="left"}

Si ha creado varios proyectos de revisión, puede seleccionar uno de la lista desplegable y acceder a los comentarios de revisión.

Con el panel de revisión, puede ver y publicar respuestas a los comentarios proporcionados sobre el tema. Puede aceptar o rechazar las comentarios una por una.

>[!NOTE]
>
> El cuadro de comentarios y el cuadro de respuesta admiten entradas de varias líneas y permiten a los usuarios expandirlo según sea necesario para proporcionar una comentarios completa, así como una respuesta detallada al comentarios. Puede usar **Mayús +** Intro **** para ir a la siguiente línea mientras escribe el comentarios o las respuestas.

Para obtener más información, vista [Revisión de direcciones comentarios](review-address-review-comments.md#).

## Seguimiento de cambios

Con la función Cambios rastreados del panel derecho, puede ver la información de todas las actualizaciones realizadas en un documento. También puede buscar actualizaciones específicas realizadas en el documento.

>[!NOTE]
>
> La característica de cambios realizados muestra todas las actualizaciones de las que se ha realizado un seguimiento mediante la característica Habilitar/Deshabilitar el seguimiento de cambios de la [barra de fichas](./web-editor-tab-bar.md).

## Schematron

&quot;Schematron&quot; hace referencia a un lenguaje de validación basado en reglas que se utiliza para definir pruebas para un archivo XML. El editor admite archivos de Schematron. Puede importar los archivos de Schematron y también editarlos en el Editor. Con un fichero de Schematron se pueden definir determinadas reglas y, a continuación, validarlas para un tema DITA o un mapa.

Aprenda a trabajar con archivos de Schematron en Experience Manager Guides, consulte [Compatibilidad con archivos de Schematron](./support-schematron-file.md).



**Tema principal:**[ Introducción al editor](web-editor.md)
