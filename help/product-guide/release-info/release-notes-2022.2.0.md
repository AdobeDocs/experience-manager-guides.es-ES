---
title: Notas de la versión para [!DNL AEM Guides], versión de febrero de 2022
description: Lanzamiento de febrero de [!DNL Adobe Experience Manager Guides] as a Cloud Service
exl-id: eb7ff475-bb5b-4d32-b291-024147fbfed1
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '974'
ht-degree: 0%

---

# Lanzamiento de febrero de [!DNL Adobe Experience Manager Guides] as a Cloud Service

## Actualización a la versión de febrero

Actualice el actual [!DNL Adobe Experience Manager Guides] as a Cloud Service (denominado posteriormente [!DNL AEM Guides] as a Cloud Service) realizando los siguientes pasos:
1. Consulte el código Git de los Cloud Service y cambie a la rama configurada en la canalización de Cloud Service correspondiente al entorno que desee actualizar.
1. Actualizar `<dox.version>` propiedad en `/dox/dox.installer/pom.xml` de su código Git de Cloud Service a 2022.2.114.
1. Confirme los cambios y ejecute la canalización de Cloud Service para actualizar a la versión de febrero de [!DNL AEM Guides] as a Cloud Service.

## Matriz de compatibilidad

En esta sección se muestra la matriz de compatibilidad para las aplicaciones de software compatibles con [!DNL AEM Guides] Versión as a Cloud Service de febrero de 2022.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| No compatible | Actualización 4 de 2020 y posterior |
| | |


### Conector de oxígeno

| [!DNL AEM Guides] Versión de Cloud | Ventanas de conector de oxígeno | Conector de oxígeno Mac |
| --- | --- | --- |
| 2022.2.0 | 2.4.0 | 2.4.0 |
|  |  |  |


## Nuevas funciones y mejoras

### Publicación nativa de PDF

En la versión de febrero de también se añadió la compatibilidad para crear un PDF nativo [!DNL AEM Guides] as a Cloud Service. Se ha introducido un nuevo motor de publicación con las siguientes funciones:
* Creación de una plantilla CSS
* Crear diferentes plantillas de página
* Plantillas de PDF de diseño que incluyen plantillas CSS y de página
* Publicación de contenido de temas y mapas en formato de PDF

### Compatibilidad con la ruta del sitio de la base de conocimiento en la publicación basada en artículos

[!DNL AEM Guides] as a Cloud Service proporciona la función de publicación basada en artículos para generar de forma incremental un resultado de uno o más temas o publicar el contenido en una plataforma de base de conocimiento. Con la versión de febrero, tiene una opción adicional para elegir la ruta del sitio de la Base de conocimiento en la que se debe publicar el tema o el mapa. Una vez seleccionada la ruta, la salida se genera en la ruta especificada.

### Mejoras del editor web

Se han añadido muchas mejoras y nuevas funciones en el editor web:

* **Diálogo mejorado al cerrar el archivo**

[!DNL AEM Guides] as a Cloud Service le pide que guarde los cambios y desbloquee los archivos bloqueados cuando intente cerrar un archivo abierto en el Editor Web. Las peticiones de datos se muestran según el **Pedir registro de entrada al cerrar** y **Pedir una nueva versión al cerrar** opciones configuradas por el administrador.

Según la configuración, tiene la opción de guardar los cambios y crear una nueva versión del documento. O bien, también puede proteger el archivo y guardar los cambios realizados en la versión actual.

![Cierre de archivo](assets/file-close-save-changes-unlock.png)

Para obtener más información, consulte *Escenarios de archivo, cerrar y guardar* en la Guía del usuario.

* Se ha añadido un espacio de no separación al pallet de caracteres.  A **de no separación** el espacio impide un salto de línea automático en un punto concreto de un documento de HTML. AEM El editor web admite un espacio de no separación tanto para la salida del sitio de la página como para la salida del HTML 5 de la página de.

* Al cargar una imagen desde el editor web, se muestra un cuadro de diálogo de confirmación si ya existe una imagen con el mismo nombre. Puede mantener ambos archivos: el existente y el nuevo, o sobrescribir el archivo existente y guardar solo el nuevo.

* Si algún usuario ha bloqueado cualquier archivo para editarlo, un administrador puede liberar el bloqueo y proteger el archivo. Esta función resulta útil cuando es necesario editar algunos archivos pero han sido bloqueados por usuarios que no están disponibles para proteger el archivo

### Tablero de mapas

Cuando selecciona descargar el mapa DITA, la solicitud se pone en cola y recibe una notificación cuando el mapa está listo para descargarse. AEM Puede elegir descargar el archivo de asignación inmediatamente o descargarlo más tarde desde el vínculo proporcionado en la bandeja de entrada de notificaciones de la.

![Descarga de mapa](assets/download-map-prompt.png)

### Revisión

Puede mencionar los detalles en el campo de descripción de la tarea de revisión y se mostrará en el correo electrónico enviado al revisor.

## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

### Publicación basada en artículos

* La publicación basada en artículos no publica artículos basados en la línea de base seleccionada. (8771)
* Los archivos DITAVAL no se respetan en la publicación basada en artículos. (8770)
* No se puede realizar la publicación basada en artículos para el perfil de Salesforce cuando el tipo de registro es FAQ y el contenido del campo de artículo es Question. (8448)
* No se puede realizar la publicación basada en artículos para el perfil de Salesforce cuando el tipo de registro es Manual. (8447)

### Editor web

* Arrastrar y soltar una condición no funciona en temas DITA. (8761)
* Faltan atributos al agregar un capítulo al mapa de libros mediante arrastrar y soltar desde la vista Favoritos. (8746)
* La edición de las propiedades de una imagen (altura, anchura) provoca un error de aplicación. (8722)
* Los vínculos rotos no aparecen en el panel Esquema de la vista de origen. (8590)
* El Editor XML elimina la etiqueta de nueva línea en el bloque de código. (8522)
* Glossentry se muestra como una Nota cuando se crea una Glossentry. (8384)
* xref no se puede insertar ni siquiera en ubicaciones válidas. (8354)
* La lista de elementos (Alt+Intro) aparece atenuada en el tema Oscuro/Más oscuro. (7913)
* La lista de plantillas de mapa de **Crear** option(menú de puntos suspensivos) del panel Repositorio no es según la variable **Perfil de carpeta** en Preferencias de usuario. (5918)
* Los ID de elemento no se generan automáticamente para los elementos añadidos desde la función Reutilizar contenido de la barra de herramientas principal. (5826)

### IU de Assets

* La edición de imágenes no funciona como se espera en el servidor de la nube. (8768)
* En el panel Historial de versiones, la sección Versión actual muestra una marca de tiempo incorrecta y se ha modificado mediante información. (8765)
* AEM La carga de archivos DITAVAL en el servidor en la nube falla cuando se utiliza la herramienta de escritorio de la. (8707)
* El segundo usuario administrador no se puede agregar como primer usuario administrador a una carpeta. (8430)
* Las propiedades no únicas de un recurso no se copian cuando se copia y se pega el recurso. (8241)

### Cambios de uso

* En el panel Revisar del editor web, si un nombre de usuario es largo, los iconos para aceptar/rechazar no se muestran claramente. (8793)
* En el **Buscar y reemplazar** , aparece un icono no deseado al pasar el ratón por encima en la sección de resultados. (8775)
* El icono personalizado no se selecciona en la propiedad y, en su lugar, se muestra el icono predeterminado para los informes generados con el botón Generar informe. (8573)
