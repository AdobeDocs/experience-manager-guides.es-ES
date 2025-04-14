---
title: Panel derecho en el editor
description: Conozca el panel derecho en el editor. Obtenga información acerca de la interfaz y las funciones de Editor en Adobe Experience Manager Guides.
feature: Authoring, Features of Web Editor
role: User
source-git-commit: 6e7d600da4373cb046e6adad3c5afe3164c9d0fa
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

**Atributos**: El panel desplegable **Atributos** está disponible en las vistas Diseño, Autor y Source. Puede añadir, editar o eliminar fácilmente los atributos.

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
> Incluso si el tema contiene contenido referenciado, puede agregar atributos mediante el panel de propiedades.

Si el administrador ha creado un perfil para atributos, obtendrá esos atributos junto con sus valores configurados. Con el panel de propiedades de contenido, puede elegir esos atributos y asignarlos al contenido relevante del tema. De este modo, también puede crear contenido condicional, que luego puede utilizar para crear resultados condicionales. Para obtener más información acerca de cómo generar resultados mediante ajustes preestablecidos condicionales, vea [Usar ajustes preestablecidos de condición](generate-output-use-condition-presets.md#).



## Propiedades del archivo

Vea las propiedades del archivo seleccionado seleccionando el icono Propiedades del archivo en el panel derecho. La función Propiedades del archivo está disponible en los cuatro modos o vistas siguientes: Diseño, Autor, Source y Vista previa.

Las propiedades del archivo tienen las dos secciones siguientes:

**General**

La sección General le permite acceder a las siguientes funciones:

![propiedades de archivo](images/file-properties-general.png){width="300" align="left"}

- **Nombre de archivo**: muestra el nombre de archivo del tema seleccionado. El nombre de archivo está enlazado mediante un hipervínculo a la página de propiedades del archivo seleccionado.
- **ID**: muestra el ID del tema seleccionado.
- **Etiquetas**: estas son las etiquetas de metadatos del tema. Se establecen en el campo de etiquetas de la página de propiedades. Puede escribirlos o seleccionarlos en la lista desplegable.  Las etiquetas aparecen debajo de la lista desplegable. Para eliminar una etiqueta, seleccione el icono en forma de cruz situado junto a la etiqueta.
- **Editar más propiedades**: puede editar más propiedades desde la página de propiedades del archivo.
- **Idioma**: muestra el idioma del tema. Se establece desde el campo language en la página de propiedades.
- **Creado el**: muestra la fecha y la hora en que se creó el tema.
- **Modificado el**: muestra la fecha y la hora en que se modificó el tema.
- **Bloqueado por**: muestra el usuario que bloqueó el tema.
- **Estado del documento**: puede seleccionar y actualizar el estado del documento del tema abierto actualmente. Para obtener más información, vea [Estado del documento](web-editor-document-states.md#).

>[!NOTE]
>
> Puede copiar los valores de atributo de los distintos campos de las propiedades del archivo en el portapapeles.

**Referencias**

La sección Referencias le permite acceder a las siguientes funciones:

![](images/file-properties-references.png){width="300" align="left"}

- **Utilizado en**: el Utilizado en referencias enumera los documentos a los que se hace referencia o se utiliza el archivo actual.
- **Vínculos de salida:** Los vínculos de salida enumeran los documentos a los que se hace referencia en el documento actual.

De forma predeterminada, puede ver los archivos por títulos. Al pasar el ratón por encima de un archivo, puede ver el título y la ruta del archivo como información sobre herramientas.

>[!NOTE]
>
> Como administrador, también puede elegir ver la lista de archivos por nombres de archivo en el Editor. Seleccione la opción **Nombre de archivo** de la sección **Archivos del editor muestran la configuración** en **Preferencias de usuario**.

>[!NOTE]
>
> Todas las referencias utilizadas en y salientes se hipervinculan a los documentos. Puede abrir y editar fácilmente los documentos vinculados.

Además de abrir archivos, también puede realizar muchas acciones utilizando el menú **Opciones** de la sección Referencias. Algunas de las acciones que puede realizar son Editar, Vista previa, Copiar UUID, Copiar ruta, Agregar a colecciones, Propiedades.

## Revisión

Al seleccionar el icono Revisar, se abre el panel de revisión, en el que puede seleccionar una tarea de revisión para el documento abierto actualmente y ver los comentarios.

![](images/review-panel-before-opening.png){width="300" align="left"}

Si ha creado varios proyectos de revisión, puede seleccionar uno de la lista desplegable y acceder a los comentarios de revisión.

Con el panel de revisión, puede ver y publicar respuestas a los comentarios proporcionados sobre el tema. Puede aceptar o rechazar los comentarios uno por uno.

>[!NOTE]
>
> El cuadro de comentarios y el cuadro de respuesta admiten entradas de varias líneas y permiten a los usuarios expandirlas según sea necesario para proporcionar comentarios completos así como respuestas detalladas a los comentarios. Puedes usar **Shift** + **Enter** para ir a la línea siguiente mientras escribes los comentarios o respuestas.

Para obtener más información, vea [Comentarios de revisión de direcciones](review-address-review-comments.md#).

## Seguimiento de cambios

Con la función Cambios rastreados del panel derecho, puede ver la información de todas las actualizaciones realizadas en un documento. También puede buscar actualizaciones específicas realizadas en el documento.

>[!NOTE]
>
> La característica de cambios realizados muestra todas las actualizaciones de las que se ha realizado un seguimiento mediante la característica Habilitar/Deshabilitar el seguimiento de cambios de la [barra de fichas](#tab-bar).

## Schematron

&quot;Schematron&quot; hace referencia a un lenguaje de validación basado en reglas que se utiliza para definir pruebas para un archivo XML. El editor admite archivos de Schematron. Puede importar los archivos de Schematron y también editarlos en el Editor. Con un fichero de Schematron se pueden definir determinadas reglas y, a continuación, validarlas para un tema DITA o un mapa.

Aprenda a trabajar con archivos de Schematron en Experience Manager Guides, consulte [Compatibilidad con archivos de Schematron](./support-schematron-file.md).



**Tema principal:**[ Introducción al editor](web-editor.md)
