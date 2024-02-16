---
title: Notas de versión | Guías de Adobe Experience Manager as a Cloud Service, versión de septiembre de 2022
description: Versión de septiembre de Adobe Experience Manager Guides as a Cloud Service
exl-id: f6247f91-43cc-43a4-a6f8-3b1f09d0533f
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1299'
ht-degree: 0%

---

# Versión de septiembre de Adobe Experience Manager Guides as a Cloud Service

## Actualización a la versión de septiembre

Actualice las guías de Adobe Experience Manager actuales as a Cloud Service (más adelante denominadas *AEM Guías de as a Cloud Service*) realizando los siguientes pasos:
1. Consulte el código Git de los Cloud Service y cambie a la rama configurada en la canalización de Cloud Service correspondiente al entorno que desea actualizar.
1. Actualizar `<dox.version>` propiedad en `/dox/dox.installer/pom.xml` de su código Git de Cloud Service a 2022.9.178.
1. Confirme los cambios y ejecute la canalización de Cloud Service AEM para actualizar a la versión de septiembre de las guías de la aplicación as a Cloud Service de la.

## Pasos para indexar el contenido existente

Realice los siguientes pasos para indexar el contenido existente y utilice el nuevo texto de búsqueda y reemplazo a nivel de mapa:
* Ejecute una solicitud de POST al servidor (con la autenticación correcta): `http://<server:port>/bin/guides/map-find/indexin`.
(Opcional: puede pasar rutas específicas de los mapas para indexarlas, de forma predeterminada se indexarán todas las asignaciones || Ejemplo :   `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)
* La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Por ejemplo: `http://<_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)`
* Una vez completado el trabajo, la solicitud de GET anterior responderá correctamente y mencionará si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.


## Matriz de compatibilidad

AEM En esta sección se muestra la matriz de compatibilidad para las aplicaciones de software compatibles con las guías de la versión de septiembre de 2022 as a Cloud Service por las guías de la aplicación de.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| No compatible | Actualización 4 de 2020 y posterior |
| | |

AEM *La línea de base y las condiciones creadas en la versión de FMPS a partir de 2020.2 son compatibles con las versiones de FMPS.

### Conector de oxígeno

| AEM Versión de Guides as a Cloud de | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2022.9.0 | 2.7.13 | 2.7.13 | 2,3 | 2,3 |
|  |  |  |  |


## Nuevas funciones y mejoras

AEM En la versión de septiembre de, Guides as a Cloud Service proporciona muchas mejoras y nuevas funciones:


### Crear una línea base dinámica basada en etiquetas

AEM Ahora, Guías de le proporciona la función para crear líneas de base dinámicas basadas en etiquetas. Si genera una línea de base, descarga una línea de base o crea un proyecto de traducción utilizando una línea de base, los archivos se seleccionan dinámicamente en función de las etiquetas actualizadas. Esta función es útil, ya que no tiene que modificar la línea de base al actualizar las etiquetas.
También puede exportar la instantánea de la instantánea como CSV.

![Crear líneas base](assets/dynamic-baseline.png)

### Buscar y reemplazar el texto en el nivel de mapa

Ahora puede buscar archivos dentro de un mapa que contengan texto específico. El texto buscado se resalta en los archivos. También puede reemplazar la palabra o frase buscada por otra palabra o frase dentro de los archivos.
Seleccione el **Reemplazar** para reemplazar la incidencia actual y el **Reemplazar todo en el archivo** para reemplazar todas las ocurrencias en el archivo seleccionado.

![Buscar Reemplazar en el mapa](assets/map-find-replace.png)

De forma predeterminada, las opciones **Archivo de retirada antes de reemplazar** y **Crear nueva versión tras reemplazar** están seleccionados, por lo que se extrae un archivo antes de reemplazar el texto y se crea una nueva versión después de reemplazar el texto.

### Ver la diferencia de versión de los archivos sin sincronizar en el panel de traducción

Ahora puede elegir traducir el **Fuera de sincronización** archivos basados en los cambios realizados entre las dos versiones de un tema.\
![Panel de traducción](assets/translation-version-diff.png)
En el panel de traducción puede ver fácilmente las diferencias entre la última versión traducida y la versión actual del archivo seleccionado.

![cuadro de diálogo diferencia de versión](assets/version-diff.png)

En función de las diferencias, puede decidir si desea traducir un tema o no.

### IU de metadatos disponible para ajustes preestablecidos de PDF

Puede definir los metadatos a partir del ajuste preestablecido de salida de un mapa DITA. Puede establecer los metadatos de Título, Autor, Asunto y Palabras clave. Estos metadatos se asignan a los metadatos de las propiedades de archivo del PDF de salida.
Estos metadatos anulan los metadatos definidos en el nivel de libro. Puede definir los metadatos específicamente en cada ajuste preestablecido de salida y pasarlos al PDF de salida.

![Metadatos en ajustes preestablecidos](assets/preset-metadata.png)


## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

* Editor web | Al mover elementos dentro de un tema, los ID asignados en los elementos se sobrescriben con los ID asignados automáticamente. (7895)
* Control de cambios | Se pierde contenido cuando se introduce un nuevo elemento con la tecla Intro. (10246)
* No se está creando el submapa al que se hace referencia en el mapa principal de dita-templates. (10231)
* Editor XML | Copiar y pegar no funciona en el modo de autor. (10309)
* Una vez seleccionadas, no se anulará la selección de varias etiquetas de versión. (9561)
* La navegación automática a la ruta del cuadro de diálogo de exploración del sitio no funciona como la exploración de archivos. (9920)
* El panel Esquema no muestra contenido cuando se cambia de **Autor** hasta **Origen** modo. (10319)
* La referencia en un nuevo tema creado con un contenido en la plantilla de tema no funciona. El ID de hash copiado no se actualiza en la copia de contenido. (9890)
* Web-Editor | No existe ningún cargador al crear un mapa a partir de la plantilla de mapa. (9891)
* Nuevo editor de mapas | Se ha añadido texto en negrita o cursiva en el título del mapa y no se conserva si se cambia de **Autor** a la **Diseño** vista. (10218)
* Nuevo editor de mapas | Las condiciones aplicadas a cualquier referencia no se pueden eliminar de la vista Presentación. (10213)
* Nuevo editor de mapas | La aplicación de referencias de condiciones no funciona en la vista Presentación como la vista Autor. (10198)
* Nuevo editor de mapas | Mover a la izquierda del menú contextual elimina la referencia si no se puede mover a la izquierda. (10219)
* Nuevo editor de mapas |El icono se muestra incorrectamente para las referencias en un mapa creado con la vista Presentación. (10197)
* Panel Repositorio | Al hacer clic con el botón derecho en el panel del repositorio se produce un error de aplicación. (10123)
* Buscar y reemplazar | El modo oscuro no se puede leer para los resultados de búsqueda en el editor web. (9978)
* Traducción | Los metadatos y las etiquetas no se propagan a las copias traducidas. (4696)
* Copiar y pegar contenido (ctrl+c/ctrl+v) genera un error en el modo Autor. (10304)
* Plantilla de PDF | Al agregar imágenes de fondo a cualquier diseño de página, se muestra Ruta de imagen absoluta y las imágenes no se muestran en el PDF de salida. (10297)
* PDF nativo | El título y el encabezado del capítulo no funcionan en la publicación de PDF. (9947)
* PDF nativo | `xref` para un concepto no se resuelve correctamente para un tema DITA específico. (10229)
* PDF nativo | No se puede ver el texto de rótulo de una tabla en la salida del PDF generada. (9827)
* PDF nativo | Las referencias de los apéndices no se muestran como apéndices en la salida del PDF. (10182)
* PDF nativo | El atributo Frame de una tabla no se propaga al HTML temporal (como clase). (10353)
* PDF nativo | los ficheros HTML temporales añaden las clases colsep y rowsep a td y el incluso si su valor es 0 en el DITA de origen. (10352)
* PDF nativo | No se aceptan los metadatos para los criterios agregados en el diseño de página. (10377)
* PDF nativo | Error al generar el PDF para contenido específico. (9927)
* PDF nativo | El contenido mediante conkeyref no se muestra en la salida del PDF. (9836)
* PDF nativo | Las referencias clave para los valores de clave con imágenes o vínculos externos no se resuelven. (10063)
* La vista Autor de un mapa no muestra el texto de marcador de posición de la lista de tablas y la lista de figuras. (10330)
* Cuando creamos una nueva línea base, el filtro de línea base ya seleccionado no se aplica. (9954)
* Falta el archivo de vídeo de la línea de base si el nombre de la carpeta principal tiene un carácter de espacio. 10031)
* La creación de la línea base no elige la última versión cuando la zona horaria del usuario es diferente de la del servidor. (10190)
* AEM AEM El método abreviado de teclado Control + F no abre el modal de búsqueda del explorador en la consola Recursos después de instalar las Guías de recursos de la versión 4.1 en la versión 6.5.12 de la versión 4.1 de la aplicación de comandos de la versión de la versión 30000000000000000000000000000000000010000000000000000000000000000000000000000000000000000000000000000000000000000000000 (10189)


## Problemas conocidos

El Adobe AEM de ha identificado los siguientes problemas conocidos para la versión de Guías de as a Cloud Service para septiembre de 2022.


* La línea de base dinámica no está integrada con la publicación de la base de conocimiento.

* Traducción | Aparece el icono Diferencia de versión para el contenido de origen debido a cualquier cambio en el contenido de destino.
