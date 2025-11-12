---
title: Repositorio en la página de inicio
description: Conozca el Repositorio en la página de inicio. Obtenga información sobre la interfaz y las funciones del repositorio en Adobe Experience Manager Guides en la página de inicio.
feature: Authoring
role: User
source-git-commit: 1919e622b1b148d16bcdb85f79e2a1cd706fe33e
workflow-type: tm+mt
source-wordcount: '1298'
ht-degree: 0%

---

# Conocer la interfaz del repositorio

El Repositorio sirve como espacio centralizado para mejorar la capacidad de detección de carpetas y archivos. Proporciona una vista de lista tabular completa de carpetas y archivos con varias columnas, lo que ofrece detalles contextuales para todos los archivos y recursos.

Esta interfaz unificada optimiza varias funciones, incluida la creación de nuevos archivos o carpetas, la edición de archivos, la carga de recursos y la búsqueda de archivos con opciones de filtrado sólidas, lo que garantiza la eficacia y la facilidad de uso.

![](images/repository-view-home.png){align="left"}

La interfaz del repositorio se divide en las siguientes secciones:

- Barra de navegación del repositorio
- Vista tabular del repositorio

## Barra de navegación del repositorio

La barra de navegación del Repositorio, situada en la parte superior de la interfaz del Repositorio, proporciona un acceso rápido a las acciones esenciales que se enumeran.

![](images/tab-bar-repository-view.png){align="left"}


- **Panel de navegación de carpetas**: Muestra una vista de árbol jerárquica de las carpetas del repositorio, lo que permite una navegación sin problemas. Este panel solo muestra información de nivel de carpeta. Cuando se selecciona una carpeta desde aquí, su contenido, archivos y subcarpetas se muestran en la vista Repositorio. Puede mostrar u ocultar este panel con el icono resaltado a continuación.

  ![](images/folder-navigation-panel.png){align="left"}

- **Rutas de exploración**: indica la ruta de acceso actual dentro del repositorio y muestra la jerarquía de carpetas que conducen a la carpeta actual. Puede seleccionarlo para volver a una carpeta específica dentro de la jerarquía.

  ![](images/breadcrumbs.png){width="650" align="left"}

- **Actualizar**: actualiza el repositorio para reflejar los cambios más recientes.
- **Cargar Assets**: permite cargar recursos directamente en la carpeta actual, tal como se indica en las rutas de exploración.
- **Nuevo**: habilita la creación de nuevos temas, mapas y carpetas dentro de la carpeta actual tal como se resalta en las rutas de exploración.
- **Ayudante de IA**: Una potente herramienta impulsada por IA diseñada para mejorar su productividad mediante características de ayuda inteligentes. La característica [AI Assistant](./ai-assistant.md) solo está disponible actualmente para Adobe Experience Manager as a Cloud Service.
- **Más acciones**: Proporciona acceso a opciones adicionales. Al seleccionar este botón, se abre un menú con las siguientes opciones:
   - **Assets**: lo lleva a un destino basado en su configuración.
      - **Cloud Services**: Si usas Cloud Services, al seleccionar la opción **Assets** accederás a la página Navegación de AEM.
      - **Software On-Premise**: Si utiliza Adobe Experience Manager Guides (4.2.1 y versiones posteriores), al seleccionar la opción **Assets**, se le redirigirá a la ruta de archivo actual en la interfaz de usuario de Assets.
   - **Configuración de Workspace**: lo lleva al cuadro de diálogo **Configuración de Workspace**. Para obtener más información, vea [Configurar las opciones de Workspace](../cs-install-guide/workspace-settings.md).
- **Expandir vista**: permite expandir la vista de página mediante el icono **Expandir**. En esta vista, la barra de encabezado está oculta, lo que maximiza el espacio de contenido. Para volver a la vista estándar, utilice el icono Exit the expand view.

## Vista tabular del repositorio

El Repositorio sirve como espacio central que proporciona una lista tabular de todas las carpetas y archivos. Ofrece las siguientes funciones:

- **Personalizar**: puede modificar las columnas mostradas mediante la opción **Personalizar** ubicada en la esquina superior derecha de la vista Repositorio. Esta opción le permite mostrar u ocultar cualquier columna y también reorganizar las columnas según sea necesario. Las columnas **Name** o **Title** son obligatorias y ambas no se pueden deshabilitar a la vez. Otros campos, como **Tipo de archivo**, **UUID**, **Estado del documento**, **Bloqueado por**, **Creado el** y **Modificado el**, se pueden habilitar o deshabilitar según sea necesario. Puede reorganizarlos simplemente arrastrando y soltando.

  ![](images/customize-repo-view.png){width="350" align="left"}

- **Cambio de tamaño de columna**: Es posible cambiar el tamaño de las columnas seleccionando opciones en el menú desplegable de columnas.

- **Ordenar**: las columnas Nombre, Título, Creado el y Última modificación admiten la ordenación en orden ascendente o descendente, a las que se puede acceder mediante el menú desplegable de columna.

- **Editando el archivo**:

   - Puede seleccionar uno o varios archivos de la lista para editarlos.
   - Después de seleccionar los archivos deseados mediante la casilla de verificación, la opción **Editar** estará disponible en la esquina superior derecha de la vista Repositorio.
   - Al seleccionar **Editar** se abren los archivos seleccionados en la interfaz del Editor, donde podrá empezar a editar el archivo.

     ![](images/edit-repo-view.png){align="left"}

- **Menú de opciones para carpetas**: puede realizar las siguientes acciones mediante el menú **Opciones** disponible para una carpeta:

  ![](images/options-folder-repo.png){width="350" align="left"}

   - **Nuevo**: crea un nuevo tema, mapa o carpeta DITA.
   - **Cargar Assets**: cargue un archivo de su sistema local a la carpeta seleccionada en el repositorio.
   - **Agregar a colecciones**: Agrega la carpeta seleccionada a favoritos. Puede elegir agregarlo a una colección existente o nueva.
   - **Volver a procesar recursos**: Déclencheur el procesamiento de todos los recursos recién creados y no procesados.

- **Menú de opciones para los archivos**: puede realizar las siguientes acciones mediante el menú **Opciones** de un archivo:

  ![](images/options-file-repo.png){width="350" align="left"}

   - **Editar**: abra el archivo para editarlo.
   - **Editar en oxígeno**: seleccione esta opción para editar el archivo seleccionado en el complemento Conector de oxígeno.

     >[!NOTE]
     >
     >Póngase en contacto con el equipo de éxito del cliente para habilitar esta función en el entorno. Esta opción no está habilitada como parte de la compatibilidad predeterminada. Para obtener más información, consulte la sección [Configurar la opción para editar en Oxígeno](../cs-install-guide/conf-edit-in-oxygen.md) en la Guía de instalación y configuración.

   - **Abrir en la consola de mapas**: Si el archivo seleccionado es un mapa DITA, esta opción abre la consola de mapas.
   - **Abrir en el tablero de mapas**: Si el archivo seleccionado es un mapa DITA, esta opción abre el tablero de mapas.
   - **Bloquear**: bloquea el archivo seleccionado para editarlo.
   - **Vista previa**: obtenga una vista previa rápida del archivo (.dita, .xml, audio, vídeo o imagen) sin abrirlo.
   - **Duplicate**: utilice esta opción para crear un duplicado o una copia del archivo seleccionado.
   - **Mover a**: utilice esta opción para mover el archivo seleccionado a otra carpeta.
   - **Cambiar nombre**: utilice esta opción para cambiar el nombre del archivo seleccionado.
   - **Eliminar**: utilice esta opción para eliminar el archivo seleccionado.
   - **Agregar a**: elige agregar a colecciones o contenido reutilizable.
   - **Copiar**: copia el UUID o la ruta completa del archivo.
   - **Propiedades**: utilice esta opción para abrir la página Propiedades del archivo seleccionado.
   - **Descargar como PDF**: Use la opción para generar la salida de PDF y descargarla.

### Búsqueda y filtrado de experiencias

La opción **Buscar** ayuda a buscar los archivos necesarios en el repositorio principalmente sobre la base de **Título de archivo**, **Nombre de archivo** y **Contenido**. Puede utilizar uno, dos o los tres criterios para la búsqueda. Si no se selecciona ninguno de los criterios, los resultados incluyen elementos comunes a los tres criterios.

![](images/search-in-repository.png){align="left"}

Seleccione el icono **Filtrar búsqueda** \(![Icono de filtro de búsqueda](images/filter-search-icon.svg)\) para abrir el panel Filtro a la derecha.

![](images/Search-filters-repo.png){align="left"}

Tiene las siguientes opciones para filtrar los archivos y limitar la búsqueda:

- **Buscar en**: seleccione la ruta de acceso en la que desea buscar los archivos presentes en el repositorio.

- **Tipo de archivo**: puede buscar todos los **temas DITA**, **mapas DITA**, **archivos DITAVAL**, **archivos de imagen**, **multimedia**, **documentos** y **JSON**.

- **Bloqueado por**: muestra una lista de usuarios. La lista se pagina y se carga asincrónicamente, mostrando un conjunto limitado de usuarios a la vez y recuperando más a medida que se desplaza o navega. Esto mejora la velocidad de carga y el rendimiento general, especialmente cuando se trabaja con un gran número de usuarios.

- **Última modificación**: filtre el contenido en función de la fecha de modificación. Seleccione un intervalo de fechas del calendario o elija una de las siguientes opciones de lapso de tiempo:
   - En la última semana
   - En el último mes
   - En el último año

- **Etiquetas**: filtre el contenido según las etiquetas.

- **elemento DITA**: filtre el contenido en función de varios elementos DITA.

Después de aplicar todos los filtros necesarios, selecciona **Aplicar** en la esquina inferior derecha del panel Filtros.

Los resultados de búsqueda personalizados según el filtro seleccionado aparecen como **lista tabular de archivos solamente** (las carpetas no se muestran). Puede quitar cualquier filtro individualmente o varios filtros al mismo tiempo, y los resultados se actualizan para reflejar la selección actualizada.

![](images/search-results-with-filters.png){align="left"}

Una vez que aparezcan los resultados de la búsqueda, puede seleccionar varios archivos y abrirlos en el editor con el icono **Editar**, o trabajar con todos los resultados enviando los resultados de búsqueda al editor mediante la opción **Mostrar en el panel de búsqueda**.

![](images/post-search-operation.png){align="left"}

**Mostrar en el panel de búsqueda**

La opción **Mostrar en el panel de búsqueda** está disponible después de realizar una búsqueda en el repositorio. Esta característica le permite mostrar todos los resultados de búsqueda en el **panel Buscar** dentro del Editor. Para obtener más información, vea [Panel de búsqueda](./search-panel-explorer.md).

![](images/search-panel-repo.png){align="left"}

