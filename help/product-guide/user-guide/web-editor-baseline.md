---
title: Crear y administrar líneas de base desde el editor web
description: AEM Cree y administre líneas de base desde el editor web en Guías de. Obtenga información sobre cómo crear líneas de base a partir de etiquetas y aplicar filtros a las líneas de base.
exl-id: 14f87bdd-3042-46f9-853e-e9ded81b10ed
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: c4c5fa16daf3f713f85783152094c8af59eb4f8c
workflow-type: tm+mt
source-wordcount: '1699'
ht-degree: 0%

---

# Crear y administrar líneas de base desde el editor web {#id223MB0ZF043}

>[!TIP]
>
> AEM Se recomienda utilizar esta función Línea base del Editor Web si ha actualizado a la versión de marzo as a Cloud Service de Guías de la versión o posterior.

AEM Guías de proporciona la función Línea base integrada dentro del Editor web que permite a los usuarios crear líneas de base y utilizarlas para publicar o traducir temas de diferentes versiones. También pueden publicar varios ajustes preestablecidos de salida del mismo mapa DITA en paralelo.

## Crear una línea base

Puede crear una línea base desde el Editor Web realizando los siguientes pasos:

1. En el panel Repositorio, abra el fichero de mapa DITA en la vista Mapa.
1. Haga clic en **Administrar** pestaña. El **Línea base** El panel muestra las líneas de base del mapa DITA.

   ![Panel Línea base](images/baseline-manage.png){width="800" align="left"}

1. En el **Línea base** , seleccione el icono + en la parte superior derecha para empezar a crear una línea de base.
1. Introduzca un nombre para la línea base en **Nombre**.
1. Entrada **Configuración**, puede elegir entre **Actualización manual** opción o **Actualización automática** opción:

   **Actualización manual**: Puede crear manualmente una línea base estática con una versión específica de los temas y contenido referenciado disponible en una fecha y hora específicas, o con una etiqueta definida para una versión de los temas:

   - Entrada **Seleccione la versión en función de,** seleccione una de las siguientes opciones:


      1. **Fecha** &lt;time stamp=&quot;&quot;>: elige la versión de los temas en la fecha y hora especificadas.
      1. **Etiqueta**: seleccione esta opción para elegir los temas según la etiqueta aplicada a ellos. Si los temas tienen etiquetas especificadas, estas se enumeran en la lista desplegable. Puede elegir una etiqueta de la lista. También puede agregar una etiqueta en el cuadro de texto.

         Para las referencias directas en líneas de base estáticas, las etiquetas se extraen de la última versión guardada del mapa. Por ejemplo, si ha creado etiquetas `Label Release 1.0` y `Label Release 1.1` para las versiones 1.0 y 1.1 del tema A y, a continuación, añada el tema A al mapa guardado como versión 1.0. En este caso, puede ver las etiquetas `Label Release 1.0` y `Label Release 1.1` en el menú desplegable para etiquetas de línea de base estáticas.


         Al seleccionar **Etiqueta,** puede elegir las referencias directas e indirectas.
         - Para las referencias directas dentro del mapa DITA, se le ofrece la opción de utilizar la última versión de temas que no tienen la etiqueta especificada aplicada.

           >[!NOTE]
           >
           > Si introduce una etiqueta que no existe, seleccione la opción **No crear una línea base** a continuación, la creación de la línea base falla y muestra un mensaje de error cerca del nombre de la línea base en el panel Línea base.

         - Para las referencias indirectas dentro del mapa DITA, se ofrece una opción adicional para utilizar la versión más reciente de temas que no tengan aplicada la etiqueta especificada. También puede elegir **Seleccionar automáticamente** para el contenido referenciado, y el sistema selecciona automáticamente la versión del contenido referenciado correspondiente a la versión del contenido en el que se hace referencia.

         Una vez seleccionada una etiqueta o versión como en la fecha, todos los temas a los que se hace referencia y los archivos multimedia dentro del mapa se seleccionan según corresponda. Esta selección de temas no se muestra en la interfaz de usuario, pero se guarda en el servidor.

   **Actualización automática**: seleccione esta opción para la creación de la instantánea para seleccionar automáticamente los temas según la etiqueta aplicada.

   Las líneas bases creadas con la configuración de actualización automática se actualizan dinámicamente. Si genera una línea de base, descarga una línea de base o crea un proyecto de traducción utilizando una línea de base, los archivos se seleccionan dinámicamente en función de las etiquetas actualizadas. Por ejemplo, si ha utilizado la versión 1.2 de un tema con Label Release 1.0 para la línea de base y ha actualizado la versión 1.5 con Label Release 1.0 más adelante, la línea de base se actualizará dinámicamente y se utilizará la versión 1.5.

   ![Crear una línea base](images/dynamic-baseline.png){width="300" align="left"}

   - **Etiquetas**: si los temas tienen etiquetas especificadas, utilice la variable **Etiquetas** desplegable para elegir de la [etiquetas enumeradas](#labels-list).
Las etiquetas seleccionadas primero reciben una prioridad mayor que las posteriores.

     >[!NOTE]
     >
     >Mientras se extraen las etiquetas, aparece un cargador y la lista desplegable está desactivada.

     Para las líneas de base dinámicas, las etiquetas se extraen de la última versión guardada y de la copia de trabajo actual del mapa. Por ejemplo, si ha creado etiquetas   `Label Release A.1.0 ` y `Label Release A.1.1` para las versiones 1.0 y 1.1 del Tema A y etiquetas `Label Release B.1.0` y `Label Release B.1.1` para las versiones 1.0 y 1.1 del Tema B . A continuación, puede agregar el Tema A al Mapa A en la versión 1.0 y el Tema B al Mapa A en 1.0* (copia de trabajo). En este caso, puede ver lo siguiente  `Label Release A.1.0 `, `Label Release A.1.1`, `Label Release B.1.0`, y `Label Release B.1.1` en el menú desplegable de etiquetas de línea de base dinámica.

1. **Referencias indirectas**: para referencias indirectas dentro del mapa DITA, se ofrecen las siguientes opciones:

   - **Seleccionar automáticamente**: puede elegir entre **Seleccionar automáticamente** para el contenido referenciado, y el sistema selecciona automáticamente la versión del contenido referenciado correspondiente a la versión del contenido en el que se hace referencia.

   - **Usar etiqueta seleccionada**: puede crear una línea base con la etiqueta seleccionada definida para una versión de los temas.
   - **Utilizar la última versión o la copia de trabajo**: utilice la versión más reciente de los temas a los que no se les haya aplicado la etiqueta especificada o, si no se ha creado ninguna versión, utilice la copia de trabajo de los temas para crear la línea base.
1. Haga clic en **Aplicar**.

Se crea la línea base. La creación de la línea de base se produce de forma asíncrona, por lo que puede seguir trabajando en otros archivos en el Editor Web. Una vez creada la línea base, aparece un mensaje emergente que confirma que se ha creado la línea base y también recibe una notificación en la bandeja de entrada para el mismo.

## Administrar líneas base

Puede gestionar las líneas base existentes mediante las distintas funciones del tablero de mandos Línea base.

- Puede buscar una línea base existente mediante el cuadro de texto del panel Línea base. Utilice el **Aplicar filtro** para mostrar todas las líneas base o enumerarlas con el estado de creación Correcto, En curso o Fallido.
- Utilice el **Actualizar** en el panel Línea base para volver a comprobar todas las líneas base y mostrar una nueva lista de líneas base para el mapa DITA abierto en la vista Mapa.
- Para ver o editar el contenido de una línea base estática existente, pulse dos veces en la línea base de la lista de **Línea base** panel. La ventana de edición de línea base del centro muestra el fichero de mapa DITA, el contenido o los temas del mapa y el contenido referenciado.

  >[!NOTE]
  >
  >La operación de edición para líneas de base estáticas solo se recomienda para un pequeño número de cambios de referencia. No se recomienda la operación de edición para cambiar la versión del mapa DITA principal, ya que debe volver a calcular todas las referencias. Esto puede provocar un error en la actualización de la línea base para mapas DITA grandes. Para los mapas DITA más grandes, se puede crear una nueva línea base o editar las propiedades de la línea base.
  >
  >La operación Editar (Edit) en el caso de una instantánea dinámica permite editar las propiedades de la instantánea, ya que las referencias para las instantáneas dinámicas se generan durante la ejecución mediante las etiquetas.

  ![opciones de una línea base](images/baseline-options.png){width="800" align="left"}



  También se pueden realizar las siguientes operaciones en la instantánea desde el menú Opciones (Options):

### Duplicar una línea base

Puede duplicar una línea base y modificarla según sus necesidades.
![duplicar una línea base](images/baseline-duplicate.png){width="300" align="left"}
*Duplique una línea base basada en una etiqueta o cree una copia exacta.*

1. Seleccionar **Duplicar** desde el menú Opciones de una línea base. El **Duplicar línea base** se abre el cuadro de diálogo.
>[!NOTE]
> >El nombre predeterminado de la línea base es `<selected baseline name>`_sufijo (como sample-baseline_1). Puede cambiar el nombre según sus necesidades.

   Entrada **Seleccione la versión según**, puede elegir la opción **Copia exacta** para la opción **Etiqueta** opción:

   - **Copia exacta**: Guías del Experience Manager selecciona la misma versión de todos los temas y crea una copia exacta de la línea base duplicada.
   - **Etiqueta**: En el menú desplegable, puede elegir una de las [etiquetas enumeradas](#labels-list). Guías del Experience Manager selecciona las versiones de los temas con la etiqueta seleccionada definida para ellas, mientras que para los demás temas, selecciona la versión de la línea base duplicada. Por ejemplo, se selecciona la etiqueta `Release 1.0` en el menú desplegable, selecciona las versiones de los temas para los que ha definido esta etiqueta. Para todos los demás temas, selecciona la versión de la línea de base duplicada.
1. Clic **Duplicar**.

- **Cambiar nombre**, o **Eliminar** una línea base existente.
- Añada, quite o realice cambios en etiquetas existentes desde el **Administrar etiquetas** opción para líneas de base estáticas. Si el administrador ha configurado etiquetas predefinidas, estas se mostrarán en la lista desplegable Añadir etiqueta. Para obtener más información sobre cómo añadir etiquetas, consulte [Uso de etiquetas](web-editor-use-label.md#).

  >[!NOTE]
  >
  > El proceso para agregar o quitar etiquetas se produce de forma asíncrona, por lo que puede seguir trabajando en otros archivos en el Editor Web. Una vez añadida o eliminada la etiqueta, se muestra un mensaje emergente que confirma que la etiqueta se ha añadido o eliminado, y también recibe una notificación en la bandeja de entrada para el mismo.

- **Editar propiedades** de una línea base estática existente que haya definido al crear la línea base.
- Exportar la instantánea de una instantánea en un archivo de Microsoft Excel con el **Exportar línea base** opción.


### Lista de etiquetas {#labels-list}

Las etiquetas enumeradas en la lista desplegable se basan en los siguientes criterios:
- Las etiquetas deben añadirse a una de las versiones de los temas del mapa DITA (en la que se crea la línea base).
- Y sólo se tienen en cuenta las referencias de primer nivel (temas o submapas) del mapa DITA para seleccionar las etiquetas.



## Filtros de línea base

Uso del icono Filtros en la **Filtros de línea base** panel puede aplicar filtros en la línea de base abierta en la ventana de edición de la línea de base:

![filtros de línea base](images/baseline-filter.png){width="300" align="left"}

- Filtre los archivos en función de sus nombres o ubicación.
- Filtre los archivos en función de los valores de diferentes columnas, como Tipo de archivo, Tipo de referencia, etc.
- Seleccione las columnas que desea mostrar en la ventana de edición de la instantánea.

>[!NOTE]
>
> Puede hacer clic en un encabezado de columna y ordenar los archivos en función de las columnas de la ventana de edición de línea de base.

**Guardar o restablecer una línea base**

Una vez editada la línea base, puede hacer clic en **Guardar** en la parte superior para guardar los cambios realizados en la línea base. Puede hacer clic en **Restablecer** botón si no desea guardar el cambio y restablecer la línea de base. Al hacer clic en **Restablecer** botón se muestra una advertencia que indica que se perderán los cambios no guardados.

**Tema principal:**[ Trabajar con el editor web](web-editor.md)

