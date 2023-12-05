---
title: Usar ajustes preestablecidos de condición
description: AEM Conozca el uso de ajustes preestablecidos de condición en las guías de la. AEM Obtenga información sobre cómo crear, editar, copiar y eliminar ajustes preestablecidos de condición en la aplicación de.
exl-id: f6865a34-abdd-4d23-b903-0211bebd13b7
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 1%

---

# Usar ajustes preestablecidos de condición {#id1825FL004PN}

Se pueden definir atributos en los temas DITA y utilizar el ajuste preestablecido de condición para especificar lo que sucede con el atributo en la salida final. Por ejemplo, puede agregar atributos como la versión 1.0 y la versión 2.0 en el contenido y utilizar un ajuste preestablecido de condición para incluir la versión 1.0 para la versión 1.0 y excluir la versión 2.0. Del mismo modo, puede añadir atributos como SO Windows y OS Linux al contenido y, a continuación, incluir o excluir el contenido relevante para la salida final según el sistema operativo.

Puede crear ajustes preestablecidos de condición de dos formas:

* Desde el editor web: permite crear y administrar los ajustes preestablecidos de condición para un mapa DITA desde el editor web.
* Desde el tablero de mapas: permite crear y gestionar los ajustes preestablecidos de condición para un mapa DITA desde el tablero de mapas.


## Ajustes preestablecidos de condición desde el editor web

Las guías del Experience Manager permiten administrar los ajustes preestablecidos de condición desde el Editor web y utilizarlos dentro de los Ajustes preestablecidos de salida para generar el resultado final.
Puede crear y ver los ajustes preestablecidos de condición, ver los atributos y administrar las acciones para el mapa actual desde el **Ajustes preestablecidos** en el Editor Web.

<img src="images//manage-condtions-presets.png" alt= "Ajustes preestablecidos de condición en el editor web" width="800" border="1px">



### Crear un ajuste preestablecido de condición

El **Ajustes preestablecidos** La vista de proporciona información detallada sobre los ajustes preestablecidos de condición, como sus atributos, valores y acciones.
Puede crear un ajuste preestablecido de condición de los temas realizando los siguientes pasos:

1. En el **Repositorio** , abra el fichero de mapa DITA en la vista Mapa.
1. Seleccione el **Administrar** pestaña.
1. Seleccionar **Ajustes preestablecidos** a la izquierda. Se mostrará la lista de ajustes preestablecidos de condiciones definidos para el mapa DITA.
1. Seleccione el icono + junto a **Ajustes preestablecidos** para abrir **Nuevo ajuste preestablecido de condición** diálogo.
1. Introduzca un nombre único para el ajuste preestablecido.

   >[!NOTE]
   >
   > Verá un error si el campo de nombre está vacío o si introduce un carácter no válido o un nombre que sea el mismo que un ajuste preestablecido de condición existente. Puede utilizar un guión &quot;-&quot; o un guion bajo &quot;_&quot; como separador.

1. Seleccionar **Crear**.
El nuevo ajuste preestablecido de condición se añade a la lista.
1. Haga doble clic en un ajuste preestablecido de condición para ver los atributos y las acciones.
El **Atributos** el panel muestra todos los atributos añadidos a cualquier referencia presente en el mapa. El panel derecho muestra únicamente las condiciones que ha añadido a los ajustes preestablecidos de condición.
1. Siga uno de estos procedimientos para agregar los atributos:
   * Seleccione uno o varios atributos para añadir todos los valores debajo de ellos al ajuste preestablecido de condición. Por ejemplo, puede seleccionar la variable `platform` para añadir todos sus valores.
   * Seleccione uno o varios valores de atributo para añadirlos al ajuste preestablecido de condición. Por ejemplo, puede seleccionar la variable `Unix` y `Win` valores del atributo de plataforma
   * Seleccione cualquier par de atributo y valor y arrástrelo al panel central. Por ejemplo, puede seleccionar la variable `Unix` valor del atributo platform y arrástrelo.
   * **Seleccionar todo** para añadir todos los atributos y sus valores al ajuste preestablecido de condición.
De forma predeterminada, la acción de un atributo es `Include`.

1. Seleccionar **Añadir**. Puede repetir este paso para agregar más atributos. Los atributos que agregue se moverán del panel central al derecho.
1. Seleccione Eliminar de la barra de acciones de la parte superior para eliminar los atributos seleccionados en el panel derecho.
1. (Opcional) Si es necesario, puede anular la acción aplicada a los atributos.
Realice una de las siguientes acciones:
   * Para cualquier atributo, seleccione una de las siguientes acciones de la lista desplegable Acción.
      * Incluir
      * Excluir
      * Passthrough
      * Indicador
   * Seleccione varias filas de atributos en el panel derecho y elija una acción en la barra de acciones de la parte superior. Por ejemplo, puede seleccionar Excluir acción para los atributos seleccionados.
1. Seleccionar **Guardar** para guardar el ajuste preestablecido de condición.

   >[!NOTE]
   >
   > Verá una advertencia si selecciona otro ajuste preestablecido o lo cierra sin guardarlo.

Una vez creado un ajuste preestablecido de condición, aparece en **Ajustes preestablecidos** de los ajustes preestablecidos de Output. Obtenga más información sobre cómo [Salida del PDF de publicación](../web-editor/native-pdf-web-editor.md).

### Cambiar nombre de ajuste preestablecido de condición

Realice los siguientes pasos para cambiar el nombre de un ajuste preestablecido de condición:

1. Pase el ratón sobre un ajuste preestablecido de condición desde **Ajustes preestablecidos** panel.
1. Seleccionar **Cambiar nombre** en el menú Opciones para abrir **Cambiar nombre de ajuste preestablecido de condición** diálogo.
1. Edite el nombre del ajuste preestablecido de condición.
1. Clic **Cambiar nombre**.

### Duplicación de un ajuste preestablecido de condición

Siga estos pasos para duplicar un ajuste preestablecido de condición:

1. Pase el ratón sobre un ajuste preestablecido de condición desde **Ajustes preestablecidos** panel.
1. Seleccionar **Duplicar** en el menú Opciones para abrir **Duplicar ajuste preestablecido de condición** diálogo.
   >[!NOTE]
   >
   > El nombre predeterminado del ajuste preestablecido es `<selected condition preset name>_1`. Puede cambiar el nombre según sus necesidades.

1. Clic **Duplicar**.

### Eliminar ajuste preestablecido de condición

Siga estos pasos para eliminar los ajustes preestablecidos de condición:

1. Pase el ratón sobre un ajuste preestablecido de condición desde **Ajustes preestablecidos** panel.
1. Seleccionar **Eliminar** en el menú Opciones para abrir **Eliminar ajuste preestablecido de condición** diálogo.
1. Haga clic en **Eliminar**.



## Ajustes preestablecidos de condición desde el tablero de mapas


### Crear un ajuste preestablecido de condición

Siga estos pasos para crear un ajuste preestablecido de condición:

1. Seleccionar **Ajustes preestablecidos** de la consola de mapas DITA.
1. Clic **Crear** botón.
1. Introduzca un nombre para el ajuste preestablecido en **Condición de nombre**.
1. Seleccione una de las siguientes acciones predeterminadas de **Establecer acción predeterminada en** lista desplegable:

   * Incluir
   * Excluir
   * Passthrough
   * Indicador La acción se establece como acción predeterminada para todos los atributos, independientemente de si se añaden o no al ajuste preestablecido de condición.

   Por ejemplo, tiene 15 atributos de condición en el documento y ha incluido cuatro de ellos en el ajuste preestablecido de condición. Si selecciona **excluir** como acción predeterminada, se aplica a los 15 atributos.

1. Siga uno de estos procedimientos para agregar los atributos:
   * Clic **Añadir** a un atributo del ajuste preestablecido de condición. Puede repetir este paso para agregar más atributos.
   * Clic **Añadir todo** para añadir todos los atributos al ajuste preestablecido de condición.
1. \(Opcional\) Si es necesario, puede anular la acción predeterminada aplicada a los atributos en el paso 4. Realice una de las siguientes acciones:
   * Seleccionar varios atributos, elegir una acción de **Definir la acción para las condiciones seleccionadas como** y haga clic en **Aplicar**.
   * Seleccione una acción para un atributo de la **Acción** menú desplegable.
1. Haga clic en **Guardar**.

### Edición de un ajuste preestablecido de condición

Puede realizar cambios en un ajuste preestablecido de condición existente para cambiar las acciones aplicadas a los atributos en el ajuste preestablecido de condición. Siga estos pasos para editar un ajuste preestablecido de condición:

1. Seleccionar **Ajustes preestablecidos** de la consola de mapas DITA.
1. Clic **Editar** botón.
1. Realice los cambios necesarios para todos los atributos en el ajuste preestablecido de condición.
1. Haga clic en **Guardar**.

### Crear una copia de un ajuste preestablecido de condición

Puede crear una copia de un ajuste preestablecido de condición y, a continuación, modificarlo según sus necesidades. Realice los siguientes pasos para crear una copia de un ajuste preestablecido de condición:

1. Seleccionar **Ajustes preestablecidos** de la consola de mapas DITA.
1. Clic **Duplicar** botón.

   >[!NOTE]
   >
   > El nombre predeterminado del ajuste preestablecido es `<selected condition preset name>_Duplicate`

   Puede cambiar el nombre según sus necesidades.

1. \(Opcional\) Realice los cambios necesarios para todos los atributos del ajuste preestablecido de condición.
1. Haga clic en **Guardar**.

### Eliminar ajuste preestablecido de condición

Puede eliminar uno o más ajustes preestablecidos de condición del **Ajuste preestablecido de condición** de la consola de mapas DITA. Siga estos pasos para eliminar los ajustes preestablecidos de condición:

1. Seleccionar **Ajustes preestablecidos** de la consola de mapas DITA.
1. Seleccione los ajustes preestablecidos\(s\) de condición que desee eliminar.
1. Clic **Eliminar** botón.
1. Clic **Eliminar** para confirmar la acción.

**Tema principal:**[ Generación de salida](generate-output.md)
