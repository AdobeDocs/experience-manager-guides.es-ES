---
title: Usar ajustes preestablecidos de condición
description: Conocer el uso de ajustes preestablecidos de condición en AEM Guides. Aprenda a crear, editar, copiar y eliminar ajustes preestablecidos de condición en AEM.
exl-id: f6865a34-abdd-4d23-b903-0211bebd13b7
feature: Publishing
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '1152'
ht-degree: 1%

---

# Usar ajustes preestablecidos de condición {#id1825FL004PN}

Se pueden definir atributos en los temas DITA y utilizar el ajuste preestablecido de condición para especificar lo que sucede con el atributo en la salida final. Por ejemplo, puede agregar atributos como la versión 1.0 y la versión 2.0 en el contenido y utilizar un ajuste preestablecido de condición para incluir la versión 1.0 para la versión 1.0 y excluir la versión 2.0. Del mismo modo, puede añadir atributos como SO Windows y OS Linux al contenido y, a continuación, incluir o excluir el contenido relevante para la salida final según el sistema operativo.

Puede crear ajustes preestablecidos de condición de dos formas:

- [Desde la consola Mapa](#condition-presets-from-the-map-console)
- [Desde el panel Mapa](#condition-presets-from-the-map-dashboard)


## Ajustes preestablecidos de condición desde la consola de mapas

Experience Manager Guides le permite crear y administrar ajustes preestablecidos de condición desde la consola de mapas y utilizarlos dentro de los **ajustes preestablecidos de salida** para generar el resultado condicional final.

<img src="images/manage-condtions-presets.png" alt= "Ajustes preestablecidos de condición en la consola de mapas" border="1px">

### Crear un ajuste preestablecido de condición

La vista **Ajustes preestablecidos de condición** proporciona información detallada sobre los ajustes preestablecidos de condición, como sus atributos, valores y acciones.

Puede crear un ajuste preestablecido de condición de los temas realizando los siguientes pasos:

1. [Abra el archivo de mapa DITA en la consola de mapas](./open-files-map-console.md).
1. Vaya a **Ajustes preestablecidos de condición** a la izquierda. Se mostrará la lista de ajustes preestablecidos de condiciones definidos para el mapa DITA.
1. Seleccione el icono + junto a **Ajustes preestablecidos de condición** para abrir el cuadro de diálogo **Nuevo ajuste preestablecido de condición**.
1. Introduzca un nombre único para el ajuste preestablecido.

   >[!NOTE]
   >
   > Verá un error si el campo de nombre está vacío o si introduce un carácter no válido o un nombre que sea el mismo que un ajuste preestablecido de condición existente. Puede utilizar un guión &quot;-&quot; o un guion bajo &quot;_&quot; como separador.

1. Seleccione **Crear**.

   El nuevo ajuste preestablecido de condición se añade a la lista.
1. Seleccione el ajuste preestablecido de condición para ver los atributos y las acciones.

   El panel **Atributos** muestra todos los atributos agregados a cualquier referencia presente en el mapa. El panel derecho muestra únicamente las condiciones que ha añadido a los ajustes preestablecidos de condición.
1. Siga uno de estos procedimientos para agregar los atributos:
   - Seleccione uno o varios atributos para añadir todos los valores debajo de ellos al ajuste preestablecido de condición. Por ejemplo, puede seleccionar el atributo `platform` para agregar todos sus valores.
   - Seleccione uno o varios valores de atributo para añadirlos al ajuste preestablecido de condición. Por ejemplo, puede seleccionar los valores `Unix` y `Win` del atributo de plataforma
   - Seleccione cualquier par de atributo y valor y arrástrelo al panel central. Por ejemplo, puede seleccionar el valor `Unix` del atributo de plataforma y arrastrarlo.
   - **Seleccione todos** para agregar todos los atributos y sus valores al ajuste preestablecido de condición. De manera predeterminada, la acción de un atributo es `Include`.

1. Seleccione **Agregar**. Puede repetir este paso para agregar más atributos. Los atributos que agregue se moverán del panel central al derecho.
1. Seleccione **Quitar** de la barra de acciones de la parte superior para eliminar los atributos seleccionados en el panel derecho.
1. (Opcional) Si es necesario, puede anular la acción aplicada a los atributos.

   Realice una de las siguientes acciones:
Para cualquier atributo, seleccione una de las siguientes acciones en la lista desplegable Acción o en la barra de herramientas.

   - Incluir
   - Excluir
   - Passthrough
   - Indicador

   Seleccione varias filas de atributos en el panel derecho y elija una acción en la barra de acciones de la parte superior. Por ejemplo, puede seleccionar la acción **Excluir** para los atributos seleccionados.
1. Seleccione **Guardar** para guardar el ajuste preestablecido de condición.

   >[!NOTE]
   >
   > Verá una advertencia si selecciona otro ajuste preestablecido o lo cierra sin guardarlo.

Una vez creado un ajuste preestablecido de condición, aparecerá en el menú desplegable **Ajustes preestablecidos de condición** de **Ajustes preestablecidos de salida**. Obtenga más información sobre cómo [publicar salida de PDF](../web-editor/native-pdf-web-editor.md).

### Cambiar nombre de ajuste preestablecido de condición

Realice los siguientes pasos para cambiar el nombre de un ajuste preestablecido de condición:

1. Pase el ratón sobre un ajuste preestablecido de condición del panel **Ajustes preestablecidos de condición**.
1. Seleccione **Rename** del menú Opciones para abrir el cuadro de diálogo **Cambiar nombre de ajuste preestablecido de condición**.
1. Edite el nombre del ajuste preestablecido de condición.
1. Seleccione **Cambiar nombre**.

### Duplicación de un ajuste preestablecido de condición

Siga estos pasos para duplicar un ajuste preestablecido de condición:

1. Pase el ratón sobre un ajuste preestablecido de condición del panel **Ajustes preestablecidos de condición**.
1. Seleccione **Duplicar** del menú Opciones para abrir el cuadro de diálogo **Duplicar ajuste preestablecido de condición**.

   >[!NOTE]
   >
   > El nombre predeterminado del ajuste preestablecido es `<selected condition preset name>_1`. Puede cambiar el nombre según sus necesidades.

1. Seleccione **Duplicado**.

### Eliminar ajuste preestablecido de condición

Siga estos pasos para eliminar los ajustes preestablecidos de condición:

1. Pase el ratón sobre un ajuste preestablecido de condición del panel **Ajustes preestablecidos de condición**.
1. Seleccione **Eliminar** del menú Opciones para abrir el cuadro de diálogo **Eliminar ajuste preestablecido de condición**.
1. Seleccione **Eliminar**.



## Ajustes preestablecidos de condición desde el panel Mapa


### Crear un ajuste preestablecido de condición

Siga estos pasos para crear un ajuste preestablecido de condición:

1. Seleccione la ficha **Ajustes preestablecidos de condición** en el tablero de mapas DITA.
1. Seleccione **Crear**.
1. Escriba un nombre para el ajuste preestablecido en **Condición de nombre**.
1. Seleccione una de las siguientes acciones predeterminadas de la lista desplegable **Establecer acción predeterminada en**:

   - Incluir
   - Excluir
   - Passthrough
   - Indicador
La acción se establece como acción predeterminada para todos los atributos independientemente de si se añaden o no al ajuste preestablecido de condición.

   Por ejemplo, tiene 15 atributos de condición en el documento y ha incluido cuatro de ellos en el ajuste preestablecido de condición. Si selecciona **exclude** como acción predeterminada, se aplica a los 15 atributos.

1. Siga uno de estos procedimientos para agregar los atributos:
   - Se seleccionó **Agregar** a un atributo en el ajuste preestablecido de condición. Puede repetir este paso para agregar más atributos.
   - Seleccione **Agregar todo** para agregar todos los atributos al ajuste preestablecido de condición.
1. \(Opcional\) Si es necesario, puede anular la acción predeterminada aplicada a los atributos en el paso 4. Realice una de las siguientes acciones:
   - Seleccione varios atributos, elija una acción de **Establezca la acción para las condiciones seleccionadas en** y seleccione **Aplicar**.
   - Seleccione una acción para un atributo de la lista desplegable **Acción**.
1. Seleccione **Guardar**.

### Edición de un ajuste preestablecido de condición

Puede realizar cambios en un ajuste preestablecido de condición existente para cambiar las acciones aplicadas a los atributos en el ajuste preestablecido de condición. Siga estos pasos para editar un ajuste preestablecido de condición:

1. Seleccione la ficha **Ajustes preestablecidos de condición** en la consola de mapas DITA.
1. Seleccione el botón **Editar**.
1. Realice los cambios necesarios para todos los atributos en el ajuste preestablecido de condición.
1. Seleccione **Guardar**.

### Crear una copia de un ajuste preestablecido de condición

Puede crear una copia de un ajuste preestablecido de condición y, a continuación, modificarlo según sus necesidades. Realice los siguientes pasos para crear una copia de un ajuste preestablecido de condición:

1. Seleccione la ficha **Ajustes preestablecidos de condición** en la consola de mapas DITA.
1. Seleccione el botón **Duplicar**.

   >[!NOTE]
   >
   > El nombre predeterminado del ajuste preestablecido es `<selected condition preset name>_Duplicate`

   Puede cambiar el nombre según sus necesidades.

1. \(Opcional\) Realice los cambios necesarios para todos los atributos del ajuste preestablecido de condición.
1. Seleccione **Guardar**.

### Eliminar ajuste preestablecido de condición

Puede eliminar uno o más ajustes preestablecidos de condición de la ficha **Ajustes preestablecidos de condición** de la consola de mapas DITA. Siga estos pasos para eliminar los ajustes preestablecidos de condición:

1. Seleccione la ficha **Ajustes preestablecidos de condición** en la consola de mapas DITA.
1. Seleccione los ajustes preestablecidos\(s\) de condición que desee eliminar.
1. Seleccione el botón **Quitar**.
1. Seleccione **Quitar** para confirmar la acción.

**Tema principal:**&#x200B;[ Generación de resultados](generate-output.md)
