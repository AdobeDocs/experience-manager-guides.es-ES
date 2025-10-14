---
title: Crear y administrar líneas de base desde el editor web
description: Cree y administre líneas de base desde el editor web en AEM Guides. Obtenga información sobre cómo crear líneas de base a partir de etiquetas y aplicar filtros a las líneas de base.
feature: Authoring, Features of Web Editor, Publishing
role: User
hide: true
exl-id: f43bc3ae-b7b6-4a8c-b42d-28ec02d0d1d6
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '1699'
ht-degree: 0%

---

# Crear y administrar líneas de base desde el editor web {#id223MB0ZF043}

>[!TIP]
>
> Se recomienda utilizar esta función Línea base del Editor Web si ha actualizado a la versión de AEM Guides as a Cloud Service de marzo o posterior.

AEM Guides proporciona la característica Línea base integrada en el Editor Web que permite a los usuarios crear líneas de base y utilizarlas para publicar o traducir temas de distintas versiones. También pueden publicar varios ajustes preestablecidos de salida del mismo mapa DITA en paralelo.

## Crear una línea base

Puede crear una línea base desde el Editor Web realizando los siguientes pasos:

1. En el panel Repositorio, abra el fichero de mapa DITA en la vista Mapa.
1. Haga clic en la ficha **Administrar**. El panel **Línea de base** muestra las líneas de base del mapa DITA.

   ![Panel de línea base](images/baseline-manage.png){width="800" align="left"}

1. En el panel **Línea de base**, seleccione el icono + en la parte superior derecha para empezar a crear una línea de base.
1. Escriba un nombre para la línea de base en **Nombre**.
1. En **Configuración**, puede elegir la opción **Actualización manual** o la opción **Actualización automática**:

   **Actualización manual**: puede crear manualmente una línea de base estática con una versión específica de los temas y contenido referenciado disponible en una fecha y hora específicas, o con una etiqueta definida para una versión de los temas:

   - En **Seleccionar la versión basada en,** seleccione una de las siguientes opciones:


      1. **Fecha** &lt;marca de tiempo\>: elige la versión de los temas en la fecha y hora especificadas.
      1. **Etiqueta**: seleccione esta opción para elegir los temas según la etiqueta aplicada. Si los temas tienen etiquetas especificadas, estas se enumeran en la lista desplegable. Puede elegir una etiqueta de la lista. También puede agregar una etiqueta en el cuadro de texto.

         Para las referencias directas en líneas de base estáticas, las etiquetas se extraen de la última versión guardada del mapa. Por ejemplo, si ha creado las etiquetas `Label Release 1.0` y `Label Release 1.1` para las versiones 1.0 y 1.1 del Tema A y, a continuación, agrega el Tema A al mapa guardado como versión 1.0. En este caso, puede ver las etiquetas `Label Release 1.0` y `Label Release 1.1` en el menú desplegable para etiquetas de línea de base estáticas.


         Al seleccionar **Etiqueta,** puede elegir las referencias directas e indirectas.
         - Para las referencias directas dentro del mapa DITA, se le ofrece la opción de utilizar la última versión de temas que no tienen la etiqueta especificada aplicada.

           >[!NOTE]
           >
           > Si escribe una etiqueta que no existe y selecciona la opción **No crear una línea de base**, la creación de la línea de base falla y muestra un mensaje de error cerca del nombre de la línea de base en el panel Línea de base.

         - Para las referencias indirectas dentro del mapa DITA, se ofrece una opción adicional para utilizar la versión más reciente de temas que no tengan aplicada la etiqueta especificada. También puede elegir **Seleccionar automáticamente** para el contenido referenciado, y el sistema selecciona automáticamente la versión del contenido referenciado correspondiente a la versión del contenido en el que se hace referencia.

         Una vez seleccionada una etiqueta o versión como en la fecha, todos los temas a los que se hace referencia y los archivos multimedia dentro del mapa se seleccionan según corresponda. Esta selección de temas no se muestra en la interfaz de usuario, pero se guarda en el servidor.

   **Actualización automática**: seleccione esta opción para la creación de la línea de base para elegir automáticamente los temas según la etiqueta aplicada a ellos.

   Las líneas bases creadas con la configuración de actualización automática se actualizan dinámicamente. Si genera una línea de base, descarga una línea de base o crea un proyecto de traducción utilizando una línea de base, los archivos se seleccionan dinámicamente en función de las etiquetas actualizadas. Por ejemplo, si ha utilizado la versión 1.2 de un tema con Label Release 1.0 para la línea de base y ha actualizado la versión 1.5 con Label Release 1.0 más adelante, la línea de base se actualizará dinámicamente y se utilizará la versión 1.5.

   ![Crear una línea de base](images/dynamic-baseline.png){width="300" align="left"}

   - **Etiquetas**: Si los temas tienen etiquetas especificadas, usa la lista desplegable **Etiquetas** para elegir entre las [etiquetas enumeradas](#labels-list).
Las etiquetas seleccionadas primero reciben una prioridad mayor que las posteriores.

     >[!NOTE]
     >
     >Mientras se extraen las etiquetas, aparece un cargador y la lista desplegable está desactivada.

     Para las líneas de base dinámicas, las etiquetas se extraen de la última versión guardada y de la copia de trabajo actual del mapa. Por ejemplo, si ha creado etiquetas   `Label Release A.1.0 ` y `Label Release A.1.1` para las versiones 1.0 y 1.1 del Tema A y las etiquetas `Label Release B.1.0` y `Label Release B.1.1` para las versiones 1.0 y 1.1 del Tema B. A continuación, puede agregar el Tema A al Mapa A en la versión 1.0 y el Tema B al Mapa A en 1.0* (copia de trabajo). En este caso, puede ver `Label Release A.1.0 `, `Label Release A.1.1`, `Label Release B.1.0` y `Label Release B.1.1` en el menú desplegable de etiquetas de línea de base dinámicas.

1. **Referencias indirectas**: para las referencias indirectas dentro del mapa DITA, se le ofrecen las siguientes opciones:

   - **Seleccionar automáticamente**: puede elegir **Seleccionar automáticamente** para el contenido referenciado y el sistema selecciona automáticamente la versión del contenido referenciado correspondiente a la versión del contenido en el que se hace referencia.

   - **Usar etiqueta seleccionada**: puede crear una línea de base con la etiqueta seleccionada definida para una versión de los temas.
   - **Usar la última versión o la copia de trabajo**: usar la última versión de los temas que no tengan aplicada la etiqueta especificada o, si no se ha creado ninguna versión, usar la copia de trabajo de los temas para crear la línea de base.
1. Haga clic en **Aplicar**.

Se crea la línea base. La creación de la línea de base se produce de forma asíncrona, por lo que puede seguir trabajando en otros archivos en el Editor Web. Una vez creada la línea base, aparece un mensaje emergente que confirma que se ha creado la línea base y también recibe una notificación en la bandeja de entrada para el mismo.

## Administrar líneas base

Puede gestionar las líneas base existentes mediante las distintas funciones del tablero de mandos Línea base.

- Puede buscar una línea base existente mediante el cuadro de texto del panel Línea base. Utilice el icono **Aplicar filtro** para mostrar todas las líneas de base o enumerarlas con el estado de creación Correcto, En curso o Error.
- Utilice el icono **Actualizar** del panel Línea base para volver a comprobar todas las líneas base y mostrar una nueva lista de líneas base para el mapa DITA abierto en la vista Mapa.
- Puede ver o editar el contenido de una línea de base estática existente si hace doble clic en la línea de base de la lista en el panel **Línea de base**. La ventana de edición de línea base del centro muestra el fichero de mapa DITA, el contenido o los temas del mapa y el contenido referenciado.

  >[!NOTE]
  >
  >La operación de edición para líneas de base estáticas solo se recomienda para un pequeño número de cambios de referencia. No se recomienda la operación de edición para cambiar la versión del mapa DITA principal, ya que debe volver a calcular todas las referencias. Esto puede provocar un error en la actualización de la línea base para mapas DITA grandes. Para los mapas DITA más grandes, se puede crear una nueva línea base o editar las propiedades de la línea base.
  >
  >La operación Editar (Edit) en el caso de una instantánea dinámica permite editar las propiedades de la instantánea, ya que las referencias para las instantáneas dinámicas se generan durante la ejecución mediante las etiquetas.

  ![opciones de una línea de base](images/baseline-options.png){width="800" align="left"}



  También se pueden realizar las siguientes operaciones en la instantánea desde el menú Opciones (Options):

### Duplicar una línea base

Puede duplicar una línea base y modificarla según sus necesidades.
![duplicar una línea de base](images/baseline-duplicate.png){width="300" align="left"}
*Duplique una línea de base basándose en una etiqueta o cree una copia exacta.*

1. Seleccione **Duplicar** del menú Opciones de una línea de base. Se abre el cuadro de diálogo **Duplicar línea de base**.
>[!NOTE]
>
>El nombre predeterminado de la línea de base es `<selected baseline name>`_sufijo (como sample-baseline_1). Puede cambiar el nombre según sus necesidades.

   En **Seleccionar la versión basada en**, puede elegir la opción **Copia exacta** o la opción **Etiqueta**:

   - **Copia exacta**: Experience Manager Guides selecciona la misma versión de todos los temas y crea una copia exacta de la línea de base duplicada.
   - **Etiqueta**: usando la lista desplegable, puede elegir una de las [etiquetas enumeradas](#labels-list). Experience Manager Guides selecciona las versiones de los temas con la etiqueta seleccionada para ellas, mientras que para los demás temas, selecciona la versión de la línea de base duplicada. Por ejemplo, si selecciona la etiqueta `Release 1.0` en el menú desplegable, entonces selecciona las versiones de los temas para los que ha definido esta etiqueta. Para todos los demás temas, selecciona la versión de la línea de base duplicada.
1. Haga clic en **Duplicar**.

- **Cambiar nombre** o **Eliminar** una línea de base existente.
- Agregue, quite o realice cambios en las etiquetas existentes desde la opción **Administrar etiquetas** para las líneas de base estáticas. Si el administrador ha configurado etiquetas predefinidas, estas se mostrarán en la lista desplegable Añadir etiqueta. Para obtener más información sobre cómo agregar etiquetas, consulte [Usar etiquetas](web-editor-use-label.md#).

  >[!NOTE]
  >
  > El proceso para agregar o quitar etiquetas se produce de forma asíncrona, por lo que puede seguir trabajando en otros archivos en el Editor Web. Una vez añadida o eliminada la etiqueta, se muestra un mensaje emergente que confirma que la etiqueta se ha añadido o eliminado, y también recibe una notificación en la bandeja de entrada para el mismo.

- **Editar propiedades** de una línea de base estática existente que haya establecido al crear la línea de base.
- Exportar la instantánea de una línea de base en un archivo de Microsoft Excel con la opción **Exportar línea de base**.


### Lista de etiquetas {#labels-list}

Las etiquetas enumeradas en la lista desplegable se basan en los siguientes criterios:
- Las etiquetas deben añadirse a una de las versiones de los temas del mapa DITA (en la que se crea la línea base).
- Y sólo se tienen en cuenta las referencias de primer nivel (temas o submapas) del mapa DITA para seleccionar las etiquetas.



## Filtros de línea base

Con el icono Filtros del panel **Filtros de línea de base**, puede aplicar filtros en la línea de base abierta en la ventana de edición de línea de base:

![filtros de línea base](images/baseline-filter.png){width="300" align="left"}

- Filtre los archivos en función de sus nombres o ubicación.
- Filtre los archivos en función de los valores de diferentes columnas, como Tipo de archivo, Tipo de referencia, etc.
- Seleccione las columnas que desea mostrar en la ventana de edición de la instantánea.

>[!NOTE]
>
> Puede hacer clic en un encabezado de columna y ordenar los archivos en función de las columnas de la ventana de edición de línea de base.

**Guardar o restablecer una línea de base**

Una vez que haya editado la línea de base, puede hacer clic en el botón **Guardar** de la parte superior para guardar los cambios en la línea de base. Puede hacer clic en el botón **Restablecer** si no desea guardar el cambio y restablecer la línea de base. Al hacer clic en el botón **Restablecer**, aparece una advertencia que indica que se perderán los cambios que no se hayan guardado.

**Tema principal:**&#x200B;[&#x200B; Trabajar con el editor web](web-editor.md)
