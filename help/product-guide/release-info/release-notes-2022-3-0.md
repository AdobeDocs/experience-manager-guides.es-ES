---
title: Notas de la versión para [!DNL AEM Guides], versión de marzo de 2022
description: Lanzamiento de marzo de [!DNL Adobe Experience Manager Guides] as a Cloud Service
exl-id: 885edbb5-dfe4-4bdc-bb66-0df64addb094
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 0%

---

# Lanzamiento de marzo de [!DNL Adobe Experience Manager Guides] as a Cloud Service

## Actualización a la versión de marzo

Actualice el actual [!DNL Adobe Experience Manager Guides] as a Cloud Service (denominado posteriormente *[!DNL AEM Guides]as a Cloud Service*) realizando los siguientes pasos:
1. Consulte el código Git de los Cloud Service y cambie a la rama configurada en la canalización de Cloud Service correspondiente al entorno que desee actualizar.
1. Actualizar `<dox.version>` propiedad en `/dox/dox.installer/pom.xml` de su código Git de Cloud Service a 2022.3.123.
1. Confirme los cambios y ejecute la canalización de Cloud Service para actualizar a la versión de marzo de [!DNL AEM Guides] as a Cloud Service.

## Matriz de compatibilidad

En esta sección se muestra la matriz de compatibilidad para las aplicaciones de software compatibles con [!DNL AEM Guides] Versión as a Cloud Service de marzo de 2022.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| No compatible | Actualización 4 de 2020 y posterior |
| | |


### Conector de oxígeno

| [!DNL AEM Guides] Versión de Cloud | Ventanas de conector de oxígeno | Conector de oxígeno Mac |
| --- | --- | --- |
| 2022.3.0 | 2.4.0 | 2.4.0 |
|  |  |  |

AEM *La línea de base y las condiciones creadas en la versión de FMPS a partir de 2020.2 son compatibles con las versiones de FMPS.

## Nuevas funciones y mejoras

### Nuevo panel Línea base

[!DNL AEM Guides] La versión as a Cloud Service de marzo proporciona la función Línea de base integrada en el Editor web. Ahora puede crear líneas de base desde el Editor Web y utilizarlas para publicar o traducir temas de distintas versiones.

Nota: Para el sistema actualizado, actualice la última **ui_config.json** para el perfil de carpeta.

Utilice esta función para crear una línea base con una versión específica de los temas disponibles en una fecha y hora específicas. Además, se obtiene la compatibilidad con la API para crear o actualizar una línea de base con una etiqueta definida para una versión de temas.

![pestaña administrar línea base](assets/baseline-manage.png)

Puede buscar los archivos en función de sus nombres o ubicación. También puede filtrar los temas que se mostrarán en la ventana de edición de la línea de base y ordenarlos según columnas específicas.

![pestaña administrar línea base](assets/baseline-filter.png)

Se ha mejorado aún más el rendimiento del proceso de creación de la línea de base. El proceso de creación de líneas de base es asincrónico, por lo que puede seguir editando otros archivos en el Editor Web mientras se crea la línea de base. Para obtener más información, consulte *Crear y administrar líneas de base desde el editor web* en la Guía del usuario.

Nota: La ficha Línea base del tablero de mandos de asignación está oculta por defecto. El administrador puede activar la pestaña Línea base en el panel de asignaciones.

### Comportamiento mejorado de actualización del Editor web

Las siguientes mejoras están ahora disponibles con la operación de actualización del explorador en el Editor web:

* Ahora tiene la posibilidad de actualizar el explorador mientras edita el contenido en el Editor web. Si pulsa el icono de actualización del explorador mientras se abren uno o más archivos con cambios no guardados para su edición, se le pedirá que guarde los archivos o cancele la acción de actualización.

* Incluso al actualizar el explorador, se conservan las vistas de los paneles izquierdo y derecho.

* El tema activo o el mapa DITA se vuelve a abrir en el área de edición de contenido.

### Mejoras de publicación

El proceso de publicación se ha mejorado aún más con la versión de marzo de [!DNL AEM Guides] as a Cloud Service:

* AEM Se han respetado las líneas de base para los metadatos de la salida del sitio de la. También puede procesar las propiedades de una versión de línea base como metadatos. Si no se define ninguna línea de base, las propiedades de la última versión se procesan como metadatos.

* El **Nombre de archivo** y **Argumentos de línea de comandos DITA-OT** se han añadido opciones para los ajustes preestablecidos de salida HTML 5, EPUB y Personalizado. Ahora puede especificar el nombre del archivo con el que desea guardar la salida. También puede especificar los argumentos adicionales que desea que DITA-OT procese al generar resultados.

## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

* No se pueden agregar elementos de contenido anterior y de contenido posterior en un mapa de libros mediante la vista Autor del Editor Web. (7652)
* Saltos del árbol de referencia después de quitar un tema y realizar una operación de movimiento. (8804)
* Se recibe una excepción al ver el contenido después de cargar un recurso. (3638)
* Se produce un error cuando los archivos cuya carpeta principal tiene caracteres especiales en el nombre del archivo se abren en Oxígeno (con el **Editar en oxígeno** botón). (8918)
* El **Buscar en el repositorio** no localiza ni resalta el mapa DITA en el Editor XML. (8796)
* Filtrar no muestra los resultados adecuados cuando se agregan varios atributos al contenido en el Editor XML. (8795)
* Se produce un error al añadir un usuario como administrador en el perfil de carpeta cuando el ID de usuario es numérico. (8908)

## Problemas conocidos

El Adobe ha identificado el siguiente problema conocido en la [!DNL AEM Guides] Versión as a Cloud Service de marzo.

* Al eliminar las etiquetas en referencias directas, también se eliminan las etiquetas de las referencias indirectas.

* No se puede reflejar el título de línea de base actualizado sin actualizar manualmente el panel de línea de base.

* La función de vista previa de versión del panel Historial de versiones no muestra la vista previa de un tema seleccionado.
