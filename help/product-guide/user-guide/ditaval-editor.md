---
title: Uso del editor DITAVAL
description: Obtenga información sobre cómo crear y editar archivos DITAVAL con el Editor DIVATAL en Adobe Experience Manager Guides. Descubra cómo el editor DITAVAL admite archivos DITAVAL en las vistas de autor y origen.
exl-id: f3901a4f-1925-42aa-b773-0d6f18175ce8
feature: Authoring, DITAVAL Editor
role: User
source-git-commit: a49234698e040c7441ea0f82265f4b7936a95dfc
workflow-type: tm+mt
source-wordcount: '1501'
ht-degree: 0%

---

# editor DITAVAL {#ditaval-editor}

Los archivos DITAVAL se utilizan para generar una salida condicional. En un solo tema, puede añadir condiciones utilizando atributos de elemento para condicionar el contenido. A continuación, se crea un archivo DITAVAL en el que se especifican las condiciones que deben recopilarse para generar contenido y qué condición debe excluirse de la salida final.

Adobe Experience Manager Guides permite crear y editar fácilmente archivos DITAVAL con el editor DITAVAL. El editor DITAVAL recupera los atributos (que pueden utilizarse como condiciones) definidos en el sistema y puede utilizarlos para crear o editar ficheros DITAVAL. Para obtener más información acerca de la creación y administración de condiciones en Adobe Experience Manager, consulte la sección [Administración de etiquetas](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=es) en la documentación de Adobe Experience Manager.

Las secciones siguientes describen las opciones disponibles para un archivo DITAVAL en Experience Manager Guides.

- [Crear archivo DITAVAL](#create-ditaval-file)
- [Editar archivo DITAVAL](#edit-ditaval-file)
- [Vistas del editor de archivos DITAVAl](#ditaval-editor-views)
- [Trabajar con el archivo DITAVAL en la interfaz de usuario de Assets](#working-with-ditaval-files-in-the-assets-ui)

## Crear archivo DITAVAL

Siga estos pasos para crear un archivo DITAVAL:

1. En el panel Repositorio, seleccione el icono **Nuevo archivo** y, a continuación, seleccione **Tema** en el menú desplegable.

   ![](images/new-file-option.png){width="300" align="left"}

   También puede acceder a esta opción desde la [página principal de Experience Manager Guides](./intro-home-page.md) y desde el menú de opciones de una carpeta en la vista Repositorio.

2. Se muestra el cuadro de diálogo **Nuevo tema**.

3. En el cuadro de diálogo **Nuevo tema**, proporcione los siguientes detalles:
   - Título del tema.
   - \(Opcional\)* El nombre de archivo del tema. El nombre del archivo se sugiere automáticamente en función del tema Título. Si el administrador ha habilitado nombres de archivo automáticos basados en la configuración de UUID, no verá el campo Nombre.
   - Una plantilla en la que se basará el tema. Para un archivo DITAVAL, selecciona **Ditaval** en la lista desplegable.
   - Ruta de acceso donde desea guardar el archivo de tema. De forma predeterminada, la ruta de la carpeta seleccionada actualmente en el repositorio se muestra en el campo Ruta.

   ![](images/new-topic-dialog-ditaval.png){width="300" align="left"}


4. Seleccione **Crear**.

El tema se crea en la ruta de acceso especificada. Además, el tema se abre en el Editor para editarlo.

![](images/ditaval-file-editor.png){align="left"}

## Editar archivo DITAVAL

Cuando crea un tema DITAVAL, se abre en el Editor para editarlo. Para editar un tema DITAVAL existente, navegue hasta la carpeta o asignación donde se encuentra el tema DITAVAL y, a continuación, seleccione **Editar** del menú **Opciones**.

El editor DITAVAL permite realizar varias tareas como se indica a continuación, utilizando las opciones de la barra de herramientas del editor.

### Opciones de barra de herramientas del editor

#### Menú desplegable

La lista desplegable Menú proporciona acceso a las acciones de edición, Buscar y reemplazar, Historial de versiones, Etiqueta de versión, Combinar, Crear tarea de revisión, Rastrear cambios y Etiquetas.
Para obtener más información, vea [Opciones desplegables de menú](./web-editor-toolbar.md#menu-dropdown)

#### Agregar prop

Añada una sola propiedad al archivo DITAVAL.

![](images/ditaval-editor-props-new.png){width="650" align="left"}

En la primera lista desplegable se enumeran los atributos DITA permitidos que se pueden utilizar en el fichero DITAVAL.

La segunda lista desplegable muestra los valores configurados para el atributo seleccionado. A continuación, la siguiente lista desplegable muestra las acciones que se pueden configurar en el atributo seleccionado. Los valores permitidos en la lista desplegable de acciones son: `include`, `exclude`, `passthrough` y `flag`. Para obtener más información sobre estos valores, vea la definición del elemento [prop](http://docs.oasis-open.org/dita/dita/v1.3/errata01/os/complete/part3-all-inclusive/langRef/ditaval/ditaval-prop.html#ditaval-prop) en la documentación DITA de OASIS. Para obtener detalles sobre la acción de las propiedades agregadas en los atributos, vea [Acciones para la propiedad](#actions-for-property).

#### Agregar prop de revisión

Para añadir un número de revisión específico a una etiqueta en XML, se puede utilizar la opción Add rev prop. Esto añade un atributo rev a la etiqueta, con el valor definido en el campo Valor junto con la acción seleccionada para la propiedad. Este atributo de revisión se puede utilizar posteriormente para filtrar el contenido XML relevante en función del número de revisión especificado al generar la salida.

![](images/ditaval-rev-props.png){width="650" align="left"}

#### Añadir todas las props

Si desea añadir todas las propiedades o atributos condicionales definidos en el sistema con un solo clic, utilice la función Añadir todas las propiedades. Los valores permitidos en la lista desplegable de acciones son: `include`, `exclude`, `passthrough` y `flag` A continuación se mencionan los detalles de estas acciones.

>[!NOTE]
>
> Si ya existen todas las propiedades condicionales definidas en el fichero DITAVAL, no se pueden añadir más propiedades. Aparece un mensaje de error en este escenario.


![](images/ditaval-all-props-new.png){width="650" align="left"}



##### Acciones para la propiedad

Hay mayoritariamente cuatro acciones disponibles para una propiedad determinada que se pueden utilizar y que se enumeran de la siguiente manera:

**Incluir:** Incluir el contenido en la salida. Este es el comportamiento predeterminado a menos que se establezca lo contrario.

**Excluir:** Excluir el contenido de la salida (si se excluyen todos los valores del atributo en particular).

**Paso a través:** Incluya el contenido en el resultado y conserve el valor del atributo como parte del flujo de salida para que un motor de tiempo de ejecución lo procese más, por ejemplo, filtrando en tiempo de ejecución basándose en la configuración de usuario individual.

**Agregar marcas:** Para marcar contenido en la salida, puede establecer la marca como la acción para el atributo deseado en el archivo. También puede aplicar diferentes estilos de indicador mediante la lista desplegable **Estilo de indicador**, tal como se muestra en el siguiente fragmento.


![](images/ditaval-flag-style.png){width="650" align="left"}


- **Color de fondo**: seleccione el tono, la saturación y el contraste del color de fondo. El valor HEX correspondiente se actualizará automáticamente según su selección. También puede cambiar el formato del espacio de color mediante la lista desplegable para elegir entre HEX, RGB y HSB.


![](images/ditaval-background-color.png){width="650" align="left"}



- **Color del texto**: seleccione el tono, la saturación y el contraste del color del texto. El valor HEX correspondiente se actualizará automáticamente según su selección. También puede cambiar el formato del espacio de color mediante la lista desplegable para elegir entre HEX, RGB y HSB.


![](images/ditaval-text-color.png){width="650" align="left"}



- **Opciones de estilo**: puede agregar algunas opciones de estilo, como Negrita, Cursiva, Subrayado, Sobrescribir o Subrayado doble.


![](images/ditaval-styling-option.png){width="650" align="left"}



- **Indicadores de inicio y finalización**: puede insertar imágenes como indicadores de inicio y finalización mediante el botón **Agregar indicador**. Para elegir imágenes, usa **Examinar Assets** para seleccionar del repositorio de Guías o **Agregar archivo** para cargar desde tu sistema local. Además, puede especificar texto alternativo para las imágenes.


![](images/ditaval-start-end-flags.png){width="650" align="left"}



- **Conflicto de estilo**: resuelve los conflictos que se producen cuando un solo elemento contiene varias propiedades con distintos estilos de indicador. En estos casos, se selecciona el valor definido en las propiedades de conflicto de estilo, que actúa de manera efectiva como selector de valores predeterminado para los colores del fondo y del texto.


![](images/ditaval-style-conflict.png){width="650" align="left"}


#### Información de la versión y Guardar como nueva versión

La función Información de la versión y Guardar como nueva versión combina el seguimiento de versiones y el guardado de contenido en una sola funcionalidad.
Para obtener más información, vea [Guardar como nueva versión](./web-editor-toolbar.md#version-information-and-save-as-new-version)


#### Bloquear/desbloquear

Bloquea o desbloquea el archivo actual. Bloquear un archivo le proporciona acceso de escritura exclusivo al archivo.
Para obtener más información, vea [Bloquear y desbloquear el archivo](./web-editor-toolbar.md#lockunlock)


### Guarde el contenido

Una vez que haya terminado de editar su archivo DITAVAL, seleccione **Guardar** en la barra de fichas.

>[!NOTE]
>
> Si cierra el archivo sin guardarlo, se perderán los cambios. Si no desea confirmar los cambios en el repositorio de Adobe Experience Manager, seleccione **Cerrar** y, a continuación, seleccione **Cerrar sin guardar** en el cuadro de diálogo **Cambios no guardados**.

## Vistas del editor DITAVAL

El editor DITAVAL de Adobe Experience Manager Guides admite la visualización de archivos DITAVAL en dos modos o vistas diferentes:

**Autor**:   Esto es una vista típica de Lo que se ve es lo que se obtiene \(WYSISYG\) del editor DITAVAL. Puede agregar o quitar propiedades mediante la interfaz de usuario simple, que presenta las propiedades, sus valores y las acciones en la lista desplegable. En la vista Autor, tiene las opciones para insertar una propiedad individual e insertar todas las propiedades con un solo clic.

También puede encontrar la versión del archivo DITAVAL en la que está trabajando pasando el puntero sobre el nombre del archivo.

**Source**:   La vista Source muestra el XML subyacente que conforma el archivo DITAVAL. Además de realizar ediciones de texto normales en esta vista, un autor también puede agregar o editar propiedades mediante el Catálogo inteligente.

Para invocar el catálogo inteligente, coloque el cursor al final de cualquier definición de propiedad y escriba &quot;&lt;&quot;. El editor mostrará una lista de todos los elementos XML válidos que puede insertar en esa ubicación.

![](images/ditaval-source-view-new.png)


## Uso de archivos DITAVAL en la interfaz de usuario de Assets

También puede crear un archivo DITAVAL desde la interfaz de usuario de Assets. Los pasos para crear un nuevo tema de DITAVAL son los siguientes:

1. En la interfaz de usuario de Assets, vaya a la ubicación en la que desea crear el archivo DITAVAL.

1. Seleccione **Crear** \> **Tema DITA**.

1. En la página Modelo, seleccione Plantilla de archivo DITAVAL y seleccione **Siguiente**.

1. En la página Propiedades, especifique **Title** y **Name** para el archivo DITAVAL.

   >[!NOTE]
   >
   > El nombre se sugiere automáticamente en función del Título del archivo. Si desea especificar manualmente el nombre del archivo, asegúrese de que el nombre no contenga espacios, apóstrofos ni llaves, y termine con .ditaval.

1. Seleccione **Crear**.

   Aparecerá el mensaje Tema creado.

Puede elegir abrir el archivo DITAVAL para editarlo en el editor DITAVAL o guardar el archivo del tema en el repositorio de Adobe Experience Manager.

Siga estos pasos para editar un archivo DITAVAL existente:

1. En la interfaz de usuario de Assets, vaya al archivo DITAVAL que desee editar.

1. Para obtener un bloqueo exclusivo del archivo, selecciónelo y seleccione **Desproteger**.

1. Seleccione el archivo y seleccione **Editar** para abrir el archivo en el editor DITAVAL de Adobe Experience Manager Guides.



