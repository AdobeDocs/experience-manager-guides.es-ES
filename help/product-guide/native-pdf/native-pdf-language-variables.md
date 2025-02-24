---
title: PDF nativo | Compatibilidad con variables de idioma
description: Usar variables de idioma en las plantillas de salida y de salida de PDF
exl-id: 2335a7d5-251b-4266-8bba-9c9935e7bbf4
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 6e9c998aa5c36b7e0dbb9d594dbf223017164698
workflow-type: tm+mt
source-wordcount: '1594'
ht-degree: 0%

---

# Compatibilidad con variables de idioma

Adobe Experience Manager Guides proporciona la función para utilizar variables de idioma. Puede utilizar variables de idioma para definir cadenas localizadas en la salida de PDF o para localizar cualquier texto estático en las plantillas de salida. Puede utilizar estilos CSS para localizar las cadenas procedentes de un archivo CSS.

## Usar variables de idioma en la salida de PDF

Puede utilizar variables de idioma para definir una versión localizada de las etiquetas predeterminadas como Nota, Precaución y Advertencia o texto estático en la salida de PDF. El nombre de la variable es el mismo para todos los idiomas, pero puede tener valores diferentes para los distintos idiomas. Puede actualizar el valor de estas variables en uno o más idiomas y, a continuación, el valor localizado se selecciona automáticamente en la salida de PDF.

Por ejemplo, puede tener las siguientes maneras de presentar la etiqueta `Note` en la salida de PDF:

- Inglés: Nota

- Francés: Remarque

- Alemán: Hinweis

<img alt= "salida al documento que contiene las variables de idioma" src="./assets/language-variable-output.png" width="550">

*Una nota de ejemplo en los idiomas inglés, francés y alemán.*

>[!NOTE]
>
> Si el valor de cualquier variable no está definido en un idioma determinado, AEM Guides elige la cadena del idioma de la interfaz de usuario (interfaz de usuario de la aplicación) como mecanismo de reserva.
>
> Si no ha definido el valor en el idioma de la interfaz de usuario, busca inglés (`en_us`) o bien selecciona el valor inglés (`en`) y muestra lo mismo en la salida de PDF.

## Tipos de variables de idioma

AEM Guides admite dos tipos de variables: variables de aplicación y de usuario.

### Variables de la aplicación

AEM Guides proporciona un conjunto de variables de aplicación predefinidas o listas para usar. Puede utilizar estas variables predefinidas para agregar información sobre un documento específico de AEM Guides. Por ejemplo, la variable `chapter-number`, si se incluye en una página, muestra el número de capítulo al que pertenece la página. La variable `author-label` muestra el nombre del autor del documento.

>[!NOTE]
>
> Puede anular el valor de una variable de aplicación.


### Variables de usuario

También puede crear nuevas variables de idioma. Por ejemplo, puede crear una variable de usuario Publicador para la etiqueta del publicador del documento.

>[!NOTE]
>
>  Debe tener privilegios administrativos para crear variables de usuario y editar las variables de aplicación.

<img alt="ventana de variables de idioma" src="./assets/add-language-variables.png" width="550">

*Agregue y vea las variables de idioma de un idioma seleccionado.*

## Añadir una nueva variable de idioma

1. En el editor, vaya al panel izquierdo y seleccione **Variables de idioma**. Esta opción está disponible en la sección Más.
1. Seleccione **Editar** para abrir la ventana **Variables de idioma**. La aplicación y las variables de usuario presentes en el idioma seleccionado se enumeran en orden alfabético. Los valores se muestran según el idioma seleccionado. Por ejemplo, si selecciona el idioma francés, &quot;Tip&quot; se muestra como &quot;Conseil&quot;.
1. En el menú desplegable **Idioma**, seleccione el idioma en el que desee editar una variable.

   >[!NOTE]
   >
   > Si no ve los idiomas deseados, habilite el idioma deseado en la configuración de **Configurar idiomas**. Seleccionar configuración <img src="./assets/settings-icon.svg" width="25"> para abrir el cuadro de diálogo **Configurar idiomas**.

1. Escriba el nombre de la variable en la columna **Nombre** y su valor en la columna **Valor**.

   >[!NOTE]
   >
   >Puede utilizar cualquier contenido de HTML como valor de variable para mostrar el valor de la variable en un formato específico. Por ejemplo, puede agregar la etiqueta `<b>` al valor de la variable para mostrar el Publicador en negrita.

1. Seleccionar **Agregar variable de idioma** <img src="./assets/add-language-variable.svg" width="25"> para agregar una nueva variable de idioma al idioma seleccionado. Al agregar una variable a un idioma, se agrega automáticamente a todos los idiomas. No se puede crear una variable con el mismo nombre que una variable existente. Se muestra un error.

>[!NOTE]
>
> Si no selecciona **Agregar variable de idioma**, la variable no se crea ni se agrega a la lista

## Exportar e importar variables de idioma

Experience Manager Guides proporciona compatibilidad para exportar e importar las variables de idioma presentes en el idioma seleccionado. Puede exportar fácilmente todas las variables de idioma junto con los valores definidos. Esto incluye variables de aplicación y de usuario. Utilice el archivo exportado para realizar los cambios deseados en los valores o localizarlos en otros idiomas.

También puede importar el archivo XML, que contiene las variables de idioma. Experience Manager Guides solo importa las variables de idioma que ya están definidas, incluidas las variables de aplicación y de usuario. No importa ninguna variable que aún no esté definida.

### Exportar variables de idioma

Para exportar las variables de idioma de un idioma, selecciona el idioma en la lista desplegable y selecciona **Exportar** <img src="./assets/language-variable-export-icon.svg" alt="icono de exportación" width="25">.
Crea un archivo XML con el formato `language_variable_<ln>`, donde `<ln>` es el código del idioma seleccionado. Por ejemplo, `language_variable_en.xml` para inglés y `language_variable_fr.xml` para francés.

>[!NOTE]
> 
>Si hay cambios sin guardar en las variables de idioma, no se pueden exportar. Guarde los cambios para ver la **exportación** habilitada Icono <img src="./assets/language-variable-export-icon.svg" alt="icono de importación" width="25">.

### Importar variables de idioma

Para importar las variables de idioma:

1. Seleccione un idioma en el menú desplegable y seleccione **Importar** <img src="./assets/language-variable-import-icon.svg" width="25">.
2. Busque y seleccione el XML, que contiene las variables de idioma. Por ejemplo, language_variable_en.xml.
Puede importar archivos XML en el siguiente formato:

```
<?xml version="1.0" encoding="UTF-8"?>
<variables>    
<variable id="note-important">Important: </variable>    
<variable id="note-caution">Avertir: </variable>    
<variable id="image-with-text">Text and image &lt;img src=&quot;/content/dam/assets/images/image_with_text.png&quot; /&gt; </variable> 
</variables> 
```

Las variables con el mismo ID se importan una vez importado el archivo. Los valores de las variables del idioma seleccionado se actualizan con los del archivo XML.  Se muestra un mensaje sobre el número de variables actualizadas.

>[!NOTE]
> 
><ul><li>Si el archivo no es un archivo XML o si contiene un formato incorrecto que no se asigna con las variables de idioma, verá un error que indica que hay un problema con el archivo XML. 
&gt;<li>Si el archivo no contiene variables con el mismo ID, verá una advertencia que indica que no se encuentra ninguna variable de idioma coincidente en el archivo importado.

### Opciones de una variable de idioma

Pase el ratón sobre la variable para ver el menú **Opciones** correspondiente.

<img width="550" alt="menú opciones para variables de idioma" src="./assets/language-variable-user-options.png">

*Use el menú&#x200B;**Opciones**para eliminar, obtener una vista previa o duplicar una variable de idioma.*

Puede obtener una vista previa de las variables aplicación y usuario. Para ver cómo se muestra el valor de la variable en la salida, seleccione **Vista previa** en el menú **Opciones** de la variable seleccionada.
También puede elegir **Eliminar** o **Duplicar** las variables de usuario. Al eliminar una variable de un idioma, se elimina automáticamente de todos los idiomas.

### Editar o revertir las variables de la aplicación

También puede editar los valores de una variable de aplicación. Posteriormente, puede revertir una variable de aplicación al valor original. **Restablecer** <img src="./assets/application-variable-revert.svg" width="25"> aparece para una variable de aplicación con un valor modificado.

## Usar variables de idioma en las plantillas de salida

Debe agregar variables de idioma en los documentos localizados. Puede insertar estas variables de idioma dentro del diseño de página que aparece en las distintas páginas de los documentos localizados. Por ejemplo, puede agregar la variable de idioma para `author-name` que aparece en el área de encabezado del diseño de página (o cualquier otra parte como el pie de página o el cuerpo).



<img alt="diseño de página de un pdf" src="./assets/language-variable-page-layout.png" width="550">


*El autor y el nombre de la marca están localizados en la salida de PDF generada para el idioma francés.*

Para insertar una variable de idioma como su `copyright-label` en el área de encabezado, realice los siguientes pasos:

1. Abra el diseño de página necesario para editarlo.

   >[!NOTE]
   >
   > Ver la sección [Personalizar un diseño de página](../native-pdf/components-pdf-template.md#customize-a-page-layout-customize-page-layout) para abrir un diseño de página y personalizarlo o editarlo.

1. Seleccione el encabezado para activarlo e insertar una variable.
1. Seleccionar **Insertar variable**  <img src="./assets/insert-language-variable.svg" width="25"> en la barra de herramientas.
1. En el elemento emergente **Insertar variable**, seleccione el nombre de la variable de idioma que desea insertar y haga clic en **Insertar** para insertarla en el área de encabezado.

   >[!NOTE]
   >
   > También puede introducir la cadena de búsqueda en el cuadro de texto. Los nombres de las variables que contienen la cadena dada se filtran y se muestran en la lista.
   > La variable de idioma seleccionada se inserta en el área de encabezado.



<img alt="insertar variable en el área de encabezado" src="./assets/language-variable-header.png" width="550">

*Se agregó el `copyright-label` en el área de encabezado.*

### Aplicar estilo de contenido a variables de idioma

Además del valor que asigna a una variable de idioma, también puede utilizar etiquetas de HTML para mostrar el valor de la variable en un formato específico. Por ejemplo, puede mostrar el valor de `publisher-label` en negrita.

- También puede dar formato a los estilos de los valores mediante la etiqueta <span>. Por ejemplo, con la variable de idioma page-number, puede mostrar el número de página en formato de número romano en inglés y especificar el formato para otros idiomas.

  Valor para inglés:
  `<span data-field="page-number" data-format="upper-roman">1</span>`

  Valor para tamil:
  `<span data-field="page-number" data-format="tamil">1</span>`

Del mismo modo, puede agregar variables de idioma y dar formato a otros campos enumerados en la función Insertar campos de los diseños de página. Para obtener más información sobre cómo agregar campos, vea [Agregar campos y metadatos](../native-pdf/design-page-layout.md#add-fields-metadata).

- También puede agregar imágenes localizadas en los valores. Por ejemplo, puede añadir un icono de imagen en el lenguaje de número de capítulo y obtener imágenes localizadas del icono en la salida de PDF.

  En inglés, el valor de la variable para una imagen puede ser como `<img src="banner-en.jpg">`, y para la misma variable en alemán, puede ser `<img src="banner-de.jpg">`. Por lo tanto, recoge las imágenes en función del idioma.

## Localice las cadenas mediante estilos CSS

Con los estilos CSS, también puede localizar las cadenas utilizadas en Numeración automática, como Capítulo, Sección, Figura y Tabla. Como estas cadenas provienen de archivos CSS, no puede localizarlas mediante variables de idioma. Para localizar estas cadenas, puede crear estilos CSS para cada idioma en el que desee localizarlas.
Por ejemplo, puede utilizar la siguiente CSS para mostrar el prefijo del capítulo y el formato de número correspondiente en varios idiomas.
Por ejemplo, puede utilizar la siguiente CSS para mostrar el capítulo como Hoofdstuk en alemán y el número de capítulo en formato decimal. Mientras que para japonés, puede utilizar el formato de número japonés para mostrar los números de capítulo en la tabla de contenido.

```
// for English
h1:before {
  counter-increment: h11;
  content: "Chapter " counter(h11, decimal)".";
}

// for German
:root:lang(de) h1:before {
  content: "Hoofdstuk " counter(h11, decimal)".";
}

// for Japanese
:root:lang(ja) h1:before {
  content: "章 " counter(h11, japanese-formal)".";
}
```

Las siguientes capturas de pantalla muestran las cadenas localizadas en la salida de PDF en alemán y japonés

<img alt=" salida en japonés con variable de idioma" src="./assets/localize-chapter-german.png" width="550">



<img alt="Salida en alemán con variable de idioma" src="./assets/localize-chapter-japanese.png" width="550">



### Dar formato a los prefijos

Con los estilos CSS, también puede dar formato a los prefijos. Por ejemplo, puede dar formato a la etiqueta `Note` para que aparezca en color rojo en la salida PDF de varios idiomas.

```
.note .prefix-content 
{
color: red;
} 
```
