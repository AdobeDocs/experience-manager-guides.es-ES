---
title: PDF nativo | Usar variables en la salida del PDF
description: Uso de variables en la salida de PDF y en las plantillas de salida
feature: Output Generation
role: Admin
level: Experienced
exl-id: 96e54aee-52df-4af1-97fd-34986f553be4
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '1446'
ht-degree: 0%

---

# Variables en la salida PDF

Un variable es un par de datos de nombre-valor que sirve como una pieza de información reutilizable. Esto hace que su contenido portátil y fácil de actualizar. Cuando modifica un variable o su valor, se actualizan todos los Ocurrencia de ese variable o valor.



## Crear una variable nueva

Siga estos pasos para crear una variable:

![Crear una variable nueva](assets/add-variable-default.png){width="800" align="left"}

*Cree variables y defina sus valores.*


1. En el editor web, vaya a la ficha **Output**.
1. Seleccionar **variables** <img alt= "icono de variable" src="./assets/variables-icon.svg" width="25"> en el panel izquierdo.
1. Seleccionar **Editar** <img alt= "Editar icono de lápiz" src="./assets/edit_pencil_icon.svg" width="25"> para abrir el editor de **Variables**.
Las variables se enumeran en orden alfabético.
1. Introduzca el nombre del variable en la **columna Nombre** y su valor en la **columna Valor** .
   >[!TIP]
   >
   >Puede utilizar cualquier contenido de HTML como valor de variable para mostrar el valor de la variable en un formato específico. Por ejemplo, puede agregar un `<b>` etiqueta al valor de variable para mostrar el valor **Experience Manager Guías** en negrita. También puede agregar imágenes del repositorio como valores.

1. Seleccionar **Agregar variable** <img alt= "Icono Agregar" src="./assets/add-icon.svg" width="25"> para agregar una variable nueva. No se puede crear una variable con el mismo nombre que una variable existente. Se muestra un error.

   >[!NOTE]
   >
   >Si no selecciona **Agregar variable** <img alt= "Icono Agregar" src="./assets/add-icon.svg" width="25">, la variable no se crea y se agrega a la lista.

De este modo, puede crear variables con valores predeterminados. Por ejemplo:
* Nombre del producto: Experience Manager Guides
* Número de versión: 2300
* Fecha de versión: 01/01/2023


### Editar una variable

Puede editar una variable de dos formas:

**Del panel Variables del lado izquierdo**

1. Seleccione una variable en el panel **Variables**.
1. Pase el ratón sobre la variable para ver el menú **Opciones** y luego seleccione la opción **Editar**.
1. En el cuadro de diálogo **Editar variable**, puede editar el valor predeterminado de la variable seleccionada.
1. Haga clic en **Listo**.

**Del editor de variables**

1. Seleccionar **variables** <img alt= "icono de variable" src="./assets/variables-icon.svg" width="25"> en el panel izquierdo.
1. Seleccionar **Editar** <img alt= "Editar icono de lápiz" src="./assets/edit_pencil_icon.svg" width="25"> para abrir el **editor de variables** .

1. En el **editor Variables** , puede editar el valor del variable seleccionado.

Debe guardar los cambios realizados en el **editor Variables** para colocarlos vista en el **panel Variables** de la izquierda.

>[!NOTE]
>
> Si edita cualquier valor variable, Adobe Experience Manager Guías actualiza simultáneamente todas las referencias donde corresponda.

### Search y previsualización una variable

Puede buscar y previsualizar el valor de una variable. Escriba una cadena en el cuadro de búsqueda del panel **Variables**. Busca tanto en función del nombre de la variable como de su valor.
Puede obtener una vista previa de una variable de dos formas:

La vista previa de la variable muestra el valor predeterminado. Por ejemplo, si ha definido el valor predeterminado de la variable ProductName como &quot;Adobe Experience Manager Guides&quot;, muestra este valor en la vista previa.

**Del panel Variables del lado izquierdo**


1. Seleccione una variable en el panel **Variables**.
1. Pase el ratón sobre la variable para ver el menú **Opciones** y luego seleccione la opción **Vista previa**.

![vista previa de variables desde el panel de variables](assets/variables-panel-preview-default.png){width="550" align="left"}

*Vista previa del valor predeterminado de una variable.*

**Del editor de variables**

1. Pase el ratón sobre la variable de la lista para ver el menú **Opciones**.
1. Seleccionar **vista previa**.




### Duplicar una variable

Puede duplicado un variable y modificar el valor según sus necesidades.


1. Desplácese sobre el variable del lista para vista el menú Opciones ****.
1. Seleccione **Duplicar**.

El nombre predeterminado de la variable es `<selected variable name>` (como &quot;sample&quot;). Puede cambiar el nombre según sus necesidades.

### Eliminar una variable

Puede eliminar una variable de dos formas:

**Del panel Variables del lado izquierdo**

1. Seleccione una variable en el panel **Variables**.
1. Pase el ratón sobre la variable para ver el menú **Opciones** y luego seleccione la opción **Eliminar**.

**Del editor de variables**

1. Pase el ratón sobre la variable de la lista para ver el menú **Opciones**.
1. Seleccione la opción **Delete**.

La variable se elimina de todos los conjuntos de variables.

## Conjuntos de variables para los ajustes preestablecidos de salida

Adobe Experience Manager Guías también admite conjuntos de variable, que permiten asignar valores alternativos a las variables. Por ejemplo, una compañía puede vender dos productos, A y B. Tiene diferentes especificaciones para cada uno de ellos. Estas especificaciones pueden incluir el nombre del producto, el número de versión y la fecha de lanzamiento. Puede haber otras diferencias en la marca. Mediante conjuntos de variable, se define un conjunto diferente de valores para las variables. Cuando genere la salida, elija el conjunto de variables adecuado y produzca la salida requerida.

### Configuración de conjuntos de variables

Debe configurar los conjuntos de variables antes de agregarles variables.



1. Seleccionar **configuración** <img alt= "Icono de configuración" src="./assets/settings-icon.svg" width="25"> para abrir el cuadro de diálogo **Configurar conjuntos de variables**.
   ![configurar conjunto de variables](assets/configure-variable-set.png){width="550" align="left"}
1. Escriba el nombre del conjunto de variables en la columna **Nombre**.
1. Seleccionar **Agregar variable** <img alt= "Icono Agregar" src="./assets/add-icon.svg" width="25"> para agregar un nuevo conjunto de variables. Los conjuntos de variables se enumeran alfabéticamente.
1. Puede seleccionar **Eliminar** para quitar un conjunto de variables.

### Operaciones de conjunto de variables

Todos los conjuntos de variables tienen las mismas variables, pero pueden tener valores diferentes.

Puede ver, editar y previsualizar los valores de un conjunto de variables específico. Seleccione un conjunto de variables de la lista desplegable **Conjuntos de variables**. Los valores se muestran según el conjunto de variables seleccionado.
Cuando edita los valores de las variables de conjuntos de variables específicos, anula los valores predeterminados y cambia los valores del conjunto de variables seleccionado.
Por ejemplo, puede establecer los siguientes valores para los conjuntos de variables *Adobe-set1* y *Adobe-set2* .


**Conjunto de variables 1**: *conjunto de Adobes 1*

* Nombre del producto: ProductA
* Número de versión: 2311
* Fecha de versión: 2/11/2023


**Conjunto de variables 2**: *conjunto de Adobes 2*

* ProductName: ProductB
* Número de versión: 2310
* Fecha de versión: 07/09/2023

Cada variable nueva se agrega a todos los conjuntos de variables. Al eliminar o duplicar una variable, se actualiza para todos los conjuntos de variables.

También puede obtener una vista previa de los valores de un conjunto de variables.
Por ejemplo, para el conjunto de variables *Adobe-Set1*, ha definido el valor de la variable ProductName como &quot;ProductA&quot; y, a continuación, muestra este valor en la vista previa del editor de variables

![vista previa de variables desde el editor de variables](assets/variables-editor-preview.png){width="550" align="left"}

*Obtener una vista previa del valor que ha definido en el conjunto de variables seleccionado.*

### Restablecer el valor de una variable

Si ha editado el valor, también puede restablecer una variable al valor predeterminado.
Restablecer <img alt= "icono restablecer" src="./assets/application-variable-revert.svg" width="25"> aparece para una variable con un valor modificado.
Por ejemplo, puede restablecer el valor de la variable ProductName al valor predeterminado Guías de Experience Manager.

## Usar variables en las plantillas de PDF nativas

Puede agregar variables mientras genera el resultado de los documentos del producto para que sean portátiles y fáciles de actualizar. Puede insertar estas variables dentro del diseño de página que aparece en las distintas páginas de los documentos. Por ejemplo, puede agregar la variable ProductName que aparece en el área de encabezado del diseño de página (o cualquier otra parte como el pie de página o el cuerpo).



Para insertar una variable como ProductName en el área de encabezado, realice los siguientes pasos:
1. Abra el diseño de página necesario para editarlo.

   >[!NOTE]
   >
   > Ver la sección [Personalizar un diseño de página](../native-pdf/components-pdf-template.md#customize-a-page-layout-customize-page-layout) para abrir un diseño de página y personalizarlo o editarlo.

1. Seleccione el encabezado para activarlo e insertar una variable.

1. Puede insertar la variable de dos formas:

   **Desde el panel Variables de la izquierda**

   * Arrastre una variable desde el **panel Variables** y suéltela en el área del encabezado.

   **Desde la barra de herramientas**

   1. Seleccionar **Insertar variable/campos** <img alt= "icono de variable" src="./assets/variables-icon.svg" width="25">.
   1. En el cuadro de diálogo **Variable**, seleccione el nombre de la variable para insertarla en el área de encabezado.
   1. También puede introducir la cadena de búsqueda en el cuadro de texto. Los nombres de las variables que contienen la cadena dada se filtran y se muestran en la lista. La variable seleccionada se inserta en el área de encabezado. Puede ver el valor predeterminado de la variable.
   1. Para reemplazar una variable, haga doble clic en el valor de la variable y seleccione otra variable en el cuadro de diálogo **Variable**. La variable se reemplaza.


## Generar salida de PDF con variables

Puede generar la salida del PDF con los valores de diferentes variables. Antes de generar el diseño, elija un conjunto de variables en la lista desplegable **Conjunto de variables** de un ajuste preestablecido de salida para elegir sus valores.

![lista desplegable de conjuntos de variables](assets/output-preset-variable-dropdown.png){width="550" align="left"}

*Seleccione un conjunto de variable en la lista desplegable del ajuste preestablecido de salida que desee utilizar para generar la salida en PDF.*

>[!NOTE]
>
> También puede seleccionar (Predeterminado) en el menú desplegable para publicar los valores predeterminados de todas las variables.

Según el conjunto de variables elegido, obtendrá una salida correspondiente a los valores de variable definidos en el conjunto de variables. Por ejemplo, si selecciona el conjunto de variables *Adobe-set1*, el resultado mostrará los valores de las variables tal como se definen en este conjunto.


<img src="assets/variable-pdf-output.png" alt="Salida de PDF con variables" width="500" border="2px">

*Generar la salida del PDF mediante variables en el diseño de página.*

También puede actualizar rápidamente los valores de cualquier conjunto de variables cuando sea necesario y volver a generar la salida. Por ejemplo, si necesita actualizar los detalles de una versión, puede actualizar el valor de la versión en la variable VersionNumber y volver a generar el resultado.
