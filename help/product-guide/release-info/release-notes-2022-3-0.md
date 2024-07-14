---
title: Notas de la versión de  [!DNL AEM Guides], marzo de 2022
description: Lanzamiento de marzo de  [!DNL Adobe Experience Manager Guides] as a Cloud Service
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

As a Cloud Service Actualice la configuración actual de [!DNL Adobe Experience Manager Guides] (más adelante denominada *[!DNL AEM Guides]as a Cloud Service*) realizando los siguientes pasos:
1. Consulte el código Git de los Cloud Service y cambie a la rama configurada en la canalización de Cloud Service correspondiente al entorno que desee actualizar.
1. Actualice la propiedad `<dox.version>` en el archivo `/dox/dox.installer/pom.xml` de su código Git de Cloud Service a 2022.3.123.
1. Confirme los cambios y ejecute la canalización de Cloud Service para actualizar a la versión de marzo del as a Cloud Service [!DNL AEM Guides].

## Matriz de compatibilidad

As a Cloud Service Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con [!DNL AEM Guides] en la versión de marzo de 2022.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| No compatible | Actualización 4 de 2020 y posterior |
| | |


### Conector de oxígeno

| [!DNL AEM Guides] versión de nube | Ventanas de conector de oxígeno | Conector de oxígeno Mac |
| --- | --- | --- |
| 2022.3.0 | 2.4.0 | 2.4.0 |
|  |  |  |

AEM *La línea de base y las condiciones creadas en la versión de FMPS a partir de 2020.2 son compatibles con las versiones de FMPS.

## Nuevas funciones y mejoras

### Nuevo panel Línea base

[!DNL AEM Guides]: la versión de marzo de as a Cloud Service proporciona la característica Línea base integrada dentro del Editor web. Ahora puede crear líneas de base desde el Editor Web y utilizarlas para publicar o traducir temas de distintas versiones.

Nota: Para el sistema actualizado, actualice el **ui_config.json** más reciente para el perfil de carpeta.

Utilice esta función para crear una línea base con una versión específica de los temas disponibles en una fecha y hora específicas. Además, se obtiene la compatibilidad con la API para crear o actualizar una línea de base con una etiqueta definida para una versión de temas.

![ficha de administración de línea base](assets/baseline-manage.png)

Puede buscar los archivos en función de sus nombres o ubicación. También puede filtrar los temas que se mostrarán en la ventana de edición de la línea de base y ordenarlos según columnas específicas.

![ficha de administración de línea base](assets/baseline-filter.png)

Se ha mejorado aún más el rendimiento del proceso de creación de la línea de base. El proceso de creación de líneas de base es asincrónico, por lo que puede seguir editando otros archivos en el Editor Web mientras se crea la línea de base. Para obtener más información, consulte *Crear y administrar líneas de base desde el Editor web* en la Guía del usuario.

Nota: La ficha Línea base del tablero de mandos de asignación está oculta por defecto. El administrador puede activar la pestaña Línea base en el panel de asignaciones.

### Comportamiento mejorado de actualización del Editor web

Las siguientes mejoras están ahora disponibles con la operación de actualización del explorador en el Editor web:

* Ahora dispone de la asistencia para actualizar el explorador mientras edita su
contenido en el editor web. Si pulsa el icono de actualización del explorador mientras usa uno o más archivos con
los cambios no guardados se abren para su edición y se le pide que guarde los archivos o cancele la acción de actualización.

* Incluso al actualizar el explorador, se conservan las vistas de los paneles izquierdo y derecho.

* El tema activo o el mapa DITA se vuelve a abrir en el área de edición de contenido.

### Mejoras de publicación

El proceso de publicación se mejoró aún más con la versión de marzo de [!DNL AEM Guides] as a Cloud Service:

* AEM Se han respetado las líneas de base para los metadatos de la salida del sitio de la. También puede procesar las propiedades de una versión de línea base como metadatos. Si no se define ninguna línea de base, las propiedades de la última versión se procesan como metadatos.

* Se han agregado las opciones **Nombre de archivo** y **Argumentos de línea de comandos DITA-OT** para los ajustes preestablecidos de salida HTML 5, EPUB y Personalizado. Ahora puede especificar el nombre del archivo con el que desea guardar la salida. También puede especificar los argumentos adicionales que desea que DITA-OT procese al generar resultados.

## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

* No se pueden agregar elementos de contenido anterior y de contenido posterior en un mapa de libros mediante la vista Autor del Editor Web. (7652)
* Saltos del árbol de referencia después de quitar un tema y realizar una operación de movimiento. (8804)
* Se recibe una excepción al ver el contenido después de cargar un recurso. (3638)
* Se produce un error cuando los archivos cuya carpeta principal contiene caracteres especiales en el nombre de archivo se abren en Oxígeno (con el botón **Editar en Oxígeno**). (8918)
* La opción **Localizar en el repositorio** no encuentra ni resalta la asignación DITA en el Editor XML. (8796)
* Filtrar no muestra los resultados adecuados cuando se agregan varios atributos al contenido en el Editor XML. (8795)
* Se produce un error al añadir un usuario como administrador en el perfil de carpeta cuando el ID de usuario es numérico. (8908)

## Problemas conocidos

El Adobe ha identificado el siguiente problema conocido en la versión de marzo de [!DNL AEM Guides] as a Cloud Service.

* Al eliminar las etiquetas en referencias directas, también se eliminan las etiquetas de las referencias indirectas.

* No se puede reflejar el título de línea de base actualizado sin actualizar manualmente el panel de línea de base.

* La función de vista previa de versión del panel Historial de versiones no muestra la vista previa de un tema seleccionado.
