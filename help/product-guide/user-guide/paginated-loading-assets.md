---
title: Explicación de las mejoras de rendimiento en Experience Manager Guides
description: Obtenga información sobre cómo la carga paginada de archivos y carpetas mejora el rendimiento en Experience Manager Guides.
feature: Authoring, Publishing
role: User
source-git-commit: e4019ae1e605bd26f7df676a4fab8c632fd8fa8e
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 0%
---

## Carga paginada de archivos y carpetas

>[!NOTE]
>
> Esta función está habilitada de forma predeterminada. Para deshabilitarlo, póngase en contacto con el equipo de éxito del cliente.

Experience Manager Guides utiliza una API paginada para cargar archivos y carpetas. En lugar de cargar todo el contenido a la vez, las carpetas se cargan progresivamente por lotes y se recuperan los recursos adicionales automáticamente al desplazarse o al seleccionar la opción **Cargar más**.

La ordenación se realiza en el servidor, por lo que al aplicar un criterio de ordenación se obtienen los resultados recién ordenados en lugar de reordenar los datos ya cargados en el explorador. Las operaciones comunes, como cambiar el nombre, eliminar, agregar y mover, ya no cargan una carpeta completa. En su lugar, solo actualizan el elemento afectado o la primera página de resultados. La funcionalidad *Buscar siempre un archivo en el Explorador* ya no está disponible. Para cualquier recurso, puede seguir utilizando el menú contextual para localizar el archivo en el Explorador.

Las secciones siguientes describen cómo se aplica cada una de ellas a diferentes interfaces, paneles y cuadros de diálogo.

### Tabla del repositorio inicial

- **Exploración**: Utiliza desplazamiento infinito. El primer lote de recursos se carga inicialmente; los lotes posteriores se anexan automáticamente mientras se desplaza. Al cambiar de carpeta, se borra la lista actual y se cargan los recursos de la carpeta recién seleccionada.
- **Cambiar nombre**: in situ; sin actualización de carpeta.
- **Eliminar**: la carpeta raíz se actualiza para mostrar el primer lote de recursos.
- **Agregar**: el nuevo archivo se inserta en la parte superior (de la carpeta actual). Los metadatos adicionales, como el estado del documento, el estado del bloqueo, el tipo de archivo, la fecha de creación y otros detalles se recuperan en una única solicitud en segundo plano por lotes y se rellenan automáticamente después de un tiempo.
- **Mover**: al mover un archivo a la carpeta activa, se agrega en la parte superior; al mover un archivo fuera de la carpeta activa, se actualiza la carpeta a su primer lote de recursos.
- **Botón Actualizar**: vuelve a cargar la carpeta activa y muestra el primer lote de recursos.
- **Ordenar**: muestra la primera página ordenada con desplazamiento infinito.
- **Panel de navegación de carpetas**: al abrir una carpeta, se carga el primer lote de recursos, con la opción **Cargar más** anexada para los lotes siguientes.

  ![paginación para el panel de navegación de carpetas](images/home-tree-pagination.png){width="650"}

### Colecciones

- Al agregar un archivo, se inserta en la parte superior de la carpeta sin actualizar la carpeta.
- Al abrir una carpeta, se carga el primer lote de recursos, con la opción **Cargar más** anexada para los lotes siguientes.

  ![paginación para colección](images/collections-paginated.png){width="650"}


### Explorer

- **Carpeta raíz**: Desplazamiento infinito. El primer lote de recursos se carga inicialmente; los lotes posteriores se anexan automáticamente mientras se desplaza.
- **Carpetas secundarias**: al expandir una carpeta se carga el primer lote de recursos, con la opción **Cargar más** anexada para los lotes siguientes.

  ![paginación para el explorador](images/explorer-pagination.png){width="650"}

- **Cambiar nombre**: Sucede in situ sin actualizar la carpeta.
- **Eliminar**: la carpeta raíz se actualiza para mostrar el primer lote de recursos.
- **Agregar o duplicar**: el nuevo archivo aparece en la parte superior de la carpeta.
- **Mover**: al mover entre carpetas no relacionadas, se actualiza la carpeta de origen a su primer lote de recursos y se agrega el elemento en la parte superior del destino (cargando el primer lote de recursos del destino si aún no estaba abierto).
- **Actualizar**: Un nuevo botón de actualización en el encabezado del panel Explorador vuelve a cargar el nivel raíz y muestra el primer lote de recursos.

### Panel Buscar

- La exploración de los resultados de búsqueda utiliza desplazamiento infinito. El primer lote de recursos se carga inicialmente; los lotes posteriores se anexan automáticamente mientras se desplaza.

### Panel Plantilla

- El nivel raíz solo muestra las categorías **map** y **topic**. Al expandir una subcarpeta, se carga el primer lote de recursos, con la opción **Cargar más** anexada para los lotes siguientes.

### Cuadro de diálogo Seleccionar ruta

- Cada nodo de carpeta carga el primer lote de recursos, con la opción **Cargar más** anexada para los lotes siguientes.

  ![paginación para seleccionar cuadro de diálogo de ruta](images/select-path-pagination.png){width="650"}

- Cuando el cuadro de diálogo se abre y navega a una ruta de destino específica, el árbol se expande automáticamente de la raíz al destino. Las carpetas de la ruta se cargan con un tamaño de página mayor, mientras que la carpeta de destino se carga con el tamaño de lote estándar.