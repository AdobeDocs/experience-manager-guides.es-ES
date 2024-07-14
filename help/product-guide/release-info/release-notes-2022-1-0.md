---
title: Notas de la versión de  [!DNL AEM Guides], enero de 2022
description: Lanzamiento de enero de  [!DNL Adobe Experience Manager Guides] as a Cloud Service
exl-id: b2da77fa-f17c-440b-be59-acaafcd9a57c
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '2441'
ht-degree: 0%

---

# Lanzamiento de enero de [!DNL Adobe Experience Manager Guides] as a Cloud Service

## Actualización a la versión de enero

As a Cloud Service Actualice la configuración actual de [!DNL Adobe Experience Manager Guides] (más adelante denominada [!DNL AEM Guides] as a Cloud Service) realizando los siguientes pasos:
1. Consulte el código Git de los Cloud Service y cambie a la rama configurada en la canalización de Cloud Service correspondiente al entorno que desee actualizar.
1. Actualice la propiedad `<dox.version>` en el archivo `/dox/dox.installer/pom.xml` de su código Git de Cloud Service a 2022.1.78.
1. Confirme los cambios y ejecute la canalización de Cloud Service para actualizar a la versión de enero del as a Cloud Service [!DNL AEM Guides].

## Matriz de compatibilidad

As a Cloud Service Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con [!DNL AEM Guides] en la versión de enero de 2022.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| No compatible | Actualización 4 de 2020 y posterior |
| | |


### Conector de oxígeno

| [!DNL AEM Guides] versión de nube | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2022.1.0 | 2.4.0 | 2.4.0 | 2,2 | 2,2 |
|  |  |  |  |  |


## Nuevas funciones y mejoras

### Publicación basada en artículos

Con la versión de enero, hemos introducido una función de publicación basada en artículos integrada en el editor web. Puede utilizar la función de publicación basada en artículos para generar de forma incremental el resultado de uno o más temas o publicar el contenido en una plataforma de base de conocimiento.

Esta función permite a los usuarios crear el mapa DITA de forma aditiva y publicar temas cuando estén listos. Una vez publicado el mapa, utilice la función de publicación basada en artículos para lograr una publicación incremental solo para los artículos actualizados.

![Publicación basada en artículos](assets/article-based-publishing.png)

AEM Además de la, puede utilizar esta función única para publicar sus artículos en cualquier portal de la base de conocimiento como Salesforce. AEM Esta función también incluye una plantilla de contenido OOTB, basada en los componentes principales de la base de datos, que le permite crear un repositorio basado en el conocimiento del contenido técnico. Lo bueno de esta plantilla es que es completamente personalizable para adaptarse a los requisitos de su organización y también puede admitir casos de uso como portales de intranet corporativos.
También puede filtrar los artículos en función de su estado del documento y la hora de modificación.

Esta publicación de artículos basada en las necesidades sobre la marcha no solo le proporciona un control completo sobre la publicación de contenido, sino que también reduce el tiempo total para publicar el contenido actualizado.
A medida que publica artículos con esta plantilla, también puede transferir los metadatos a las páginas publicadas.
Para obtener más información, consulte *Publicación basada en artículos desde el editor web* en la Guía del usuario.

### Editor web mejorado

Se han introducido muchas mejoras y nuevas funciones en el editor web:

* También se ha agregado compatibilidad con el esquema de temas en el Editor web. Ahora puede crear y utilizar el esquema de asunto mediante el panel Esquema del asunto. Con la adición del esquema de asunto, ahora puede utilizar sus propios metadatos y taxonomía corporativos.

![Esquema del asunto](assets/subject-scheme-panel.png)

* En esta versión se ha introducido una nueva herramienta de punto interactivo de glosario para administrar los glosarios de forma masiva. Con esta herramienta, puede convertir rápidamente texto en glosario y glosario en términos en lote para un mapa seleccionado o temas abiertos.

![Punto interactivo del glosario](assets/glossary-hotspot-tool.png)

* Funcionalidad de actualización añadida en el panel Contenido reutilizable que le permite actualizar rápidamente el contenido reutilizable en los archivos de referencia.
* El nuevo indicador de copia de trabajo le muestra si su archivo actual (copia de trabajo) está sincronizado con la versión guardada o no.

![Indicador de versión](assets/version-update-indicator.png)

* El filtro de búsqueda en el panel del repositorio y el cuadro de diálogo de exploración de archivos se han mejorado para ofrecer más opciones de filtrado, que se pueden personalizar aún más.

![Filtros de búsqueda en el repositorio](assets/repository-filter-search.png)

* Ahora puede cargar archivos .docx desde el Editor web.

### Autor con FrameMaker

Ahora puede crear y publicar sus documentos en FrameMaker. El FrameMaker se envía con un conector incorporado a Adobe Experience Manager. En FrameMaker, dispone de una interfaz fácil de usar que le permite mantener las versiones de sus documentos en un entorno distribuido y colaborativo.

Una vez creado el contenido, FrameMaker permite publicar los documentos en diferentes formatos: PDF, HTML 5, EPUB y DITA. También puede realizar las distintas operaciones de administración de archivos, como desprotección, desprotección con dependientes, protección, actualización, etc.
Para crear con FrameMaker en [!DNL AEM Guides], utilice la versión de FrameMaker 2020.4 o superior del as a Cloud Service.

### Nuevo panel de traducción

Se ha introducido un nuevo panel de traducción en el Editor web con las siguientes funciones:

* Ordenar, buscar y filtrar la lista de temas.
* Filtrar contenido por tipo de referencia: referencias directas o indirectas.
* Navegación sencilla para encontrar un proyecto existente al iniciar una solicitud de traducción.
* Se ha introducido un mecanismo de traducción en varios idiomas para evitar la creación de varios proyectos para cada idioma cuando la solicitud de traducción se inicia para más de un idioma.
* Se ha introducido una configuración para ocultar la pestaña de traducción en el panel de mapas. De forma predeterminada, está visible. Puede elegir traducir contenido mediante el panel de mapas o el Editor web.

![Panel de traducción](assets/translation-from-web-editor.png)

### Publicación mejorada

* Los autores ahora pueden pasar metadatos de nivel de tema y mapa a la publicación DITA-OT. Esto resulta útil cuando las plantillas de PDF personalizadas están diseñadas para utilizar propiedades de metadatos de archivo como etiquetas, autor, estado del documento, etc.

![metadatos DITA-OT](assets/custom-meta-data-output-preset.png)

* AEM Se ha agregado una nueva configuración para permitir que los usuarios conserven o eliminen las versiones de los temas que se eliminan cuando se usa la opción **Eliminar y crear** en la generación de resultados del sitio de la.

### Administración de archivos mejorada

Ahora se pueden ver las siguientes mejoras mientras se trabaja con archivos en AEM Assets:
* Se ha introducido una nueva experiencia de carga de archivos y un nuevo cuadro de diálogo para elegir una estrategia de resolución de conflictos.

![Conflicto de carga de archivo](assets/file-upload-name-conflict.png)

* Capacidad para crear una nueva versión del archivo cargado con la posibilidad de evitar sobrescribir un archivo desprotegido.
* Ahora puede ver una previsualización de imágenes directamente desde la vista Historial de versiones. Además, para los ficheros DITA y no DITA, el Historial de versiones muestra la información de la versión actual por separado.

![Miniatura del historial de versiones](assets/version-history-preview-image.png)

* AEM Cada vez que el usuario crea un fichero DITA, el nombre de fichero por defecto aparece en minúscula alineado con el escenario de creación de la carpeta Nativa de la carpeta de la.

### Nueva función de exportación de informes

Los informes son muy útiles para identificar el estado del contenido. [!DNL AEM Guides] as a Cloud Service proporciona varios informes para tomar el control del contenido. Ahora, no solo puede ver los informes, sino también exportar los datos del informe en un archivo CSV para verlos y compartirlos con su equipo más grande. Los datos del informe pueden darle un vistazo rápido a los vínculos rotos o a las imágenes que faltan.

![Exportación de informe](assets/export-report.png)

### Mejora de la experiencia de actualización de Oxygen DAM

AEM Al actualizar archivos desde el Servidor de en Oxygen, aparece un mensaje de advertencia si no ha guardado los archivos en la sesión actual de Oxygen. Puede optar por cancelar la operación de actualización para guardar los archivos no guardados. Sin esta función, los usuarios perdían información no guardada en sus documentos.


### Otras mejoras de las funciones

* Ahora puede crear una nueva plantilla de **proyecto Dita** en la ruta **/apps/projects/templates**.
* Ahora descargue el archivo predeterminado **ui_config.json** de sus perfiles de carpeta. Se puede usar para combinar cambios personalizados del archivo **ui_config.json** existente al actualizar.
* No es necesario borrar la caché del explorador aunque haya nuevas versiones de los archivos JS presentes.

## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

### Editor web

* Los conrefs aparecen en color rojo incluso cuando no están rotos. (8239)
* El valor del atributo condicional no se rellena automáticamente cuando se selecciona Añadir todas las propiedades en el editor DITAVAL. (8234)
* Los autores no pueden insertar una imagen en un tema mediante una ruta relativa. (8112)
* La página Revisar tarea no muestra los archivos multimedia si hay espacios en el nombre del archivo. (8111)
* Las referencias de Ph añadidas en la celda de la tabla se muestran en color rojo. (8083)
* Los vínculos de la tarea de revisión no se actualizarán cuando se muevan los archivos en revisión. (8080)
* El editor web no representa correctamente imágenes que tengan la propiedad de escalado establecida en 75 % o superior. (8073)
* Las imágenes de GIF se representan como imágenes estáticas en el editor web. (8024)
* Un elemento conkeyref de una nota no se muestra en la vista previa del Editor Web ni en la salida. (8006)
* xref a un elemento que es en sí mismo una conref no se resuelve en el editor. (7933)
* El título que tiene la clave no se representa correctamente en la previsualización del editor y en el panel Repositorio. (7909)
* Los fragmentos de código con caracteres especiales no se almacenan correctamente. (7908)
* Al guardar un tema después de aplicar formato a las ecuaciones de MathML, se produce un error. (7954)
* AEM keydef having (tm) no se procesan correctamente en el editor y la salida del sitio de la contenía símbolos de TM duplicados. (7859)
* La operación de arrastrar y soltar un fragmento no funciona según los DTD. (7758)
* El HTML ignora las dimensiones definidas personalizadas para los gráficos. (7718)
* El atributo conrefend no se actualiza cuando se mueve el archivo de origen. (7698)
* El trabajo con documentos de tipo de tema de referencia conduce a varios problemas de interfaz de usuario. (7656)
* Los archivos DITAVAL no se muestran cuando el autor añade ditavalef en un mapa. (7594)
* Se encuentra espacio inesperado en cada elemento `<entry>` vacío cuando se agrega el atributo outputclass al elemento `<tgroup>`. (7532)
* El botón Source no funciona para los temas abiertos a través del panel de mapas. (7465)
* La impresión Pretty inserta líneas y espacios en blanco que se pueden ver cuando el archivo se abre en FrameMaker u oxígeno. (7408)
* AEM Los mapas con href=&quot;/&quot; en cualquiera de los temas no se publican en los sitios de la. (7405)
* Se han encontrado problemas de rendimiento en el editor cuando el mapa raíz tiene un gran número de keydefs. (7400)
* El estado del documento de un mapa con plantilla personalizada no se hereda de su perfil de estados correspondiente. (7359)
* El elemento `<tm>` se representó incorrectamente como elemento de bloque. (7286)
* Las plantillas duplicadas se muestran en el panel de plantillas del editor cuando se crea una nueva plantilla. (5814)
* Las plantillas definidas en ui_config para imágenes para establecer atributos adicionales no se aplican a los casos de arrastrar y soltar. (5713)
* Apariencia predeterminada incorrecta de uicontrol en cascada. (5483)
* Las plantillas personalizadas para Tema/Mapa no muestran nuevos nombres en la interfaz de usuario. Muestra el nombre como &quot;Tema&quot;/&quot;Mapa&quot; en lugar de mostrar el nombre configurado. (4958)
* Capacidad para borrar mapas de raíz de la configuración de preferencias de usuario. (8534)
* Una colección de asignaciones recién creada no aparece en la lista, ni siquiera después de actualizar la página.(8603)
* No se puede cerrar el tema desbloqueado. (8545)
* Cambiar entre el modo de origen y el de autor marca el tema como sucio y requiere que se vuelva a guardar el contenido.(8524)
* El panel Reutilizar contenido se bloquea al buscar caracteres especiales `[` o `*`(8279)
* El cursor no se muestra en la barra de búsqueda cuando se abre el cuadro de diálogo insertar elemento con el método abreviado de teclado Alt+Entrar.(7912)
* La opción Buscar solo busca en nombres de archivo y no en contenido. (7784)


### Conector de oxígeno

* Los archivos cuya carpeta principal tiene caracteres especiales dan error al cargarse en Oxygen. (8054)
* Cuando se abre un documento recién creado en Oxygen, aparece el error &quot;No se puede encontrar el GUID&quot;. (7856)
* AEM La opción de registro se desactiva después de que el archivo se desproteja de los archivos mediante el uso de la opción Editar en oxígeno. (7471)


### Revisión

* La sincronización en tiempo real no funciona para los comentarios. (7661)

### Tablero de mapas

* No se puede ver el contenido de referencia en el título de un tema en la pestaña de temas o informes del panel de asignación. (8263)
* Salida de AEM Sites | jcr:title de la página de Sites generada no se actualiza cuando se actualiza el título de un tema de DITA. (8131)
* Download MAP no descarga los archivos de vídeo utilizados dentro de los temas. (8070)
* Los archivos multimedia no se descargan cuando se utiliza la etiqueta de objeto a través de la API de descarga de bookmap. (8057)
* Se muestra un informe incorrecto en la pestaña Informes si algún tema tiene una referencia a un archivo cuyo título comience por una referencia. (4698)
* El cuadro de diálogo Aplicar etiquetas de la pestaña Línea base no muestra las etiquetas en la lista desplegable. (8455)

### Publicación

* La creación del PDF falla por primera vez cuando se selecciona Enable Versioning. (8053, 8294)
* AEM El carácter de espacio en blanco se agrega automáticamente después de una etiqueta &#39;tm; en la salida del sitio de la. (7964)
* No se pueden ver los vídeos de YouTube AEM en la salida del sitio de. (7401)
* El filtro por etiqueta falla en el contenido referenciado después de que el usuario haga clic en examinar todos los temas en la pestaña de línea de base del panel de mapas. (7388)
* El tema de publicación con el elemento `<tm>` con valor de propiedad SM o reg se muestra incorrectamente en la salida generada. (7239)
* La publicación de línea de base con imagen no selecciona la última versión de la imagen en la salida publicada. (7231)
* Los temas referenciados relacionados se muestran en la pestaña Línea base. (5424)
* La publicación incremental de un tema con conkeyref en su título no funciona como se esperaba. (4474)
* El título de la página no se utiliza para generar la URL de salida aunque se haya marcado esa configuración. (8257)
* Publicación de línea de base que selecciona la versión actual de las imágenes en lugar del nodo inmovilizado. Esto también se ve si una imagen tiene espacios o caracteres especiales en el nombre del archivo. (8274, 8322)
* La publicación incremental falla para el mapa DITA con el esquema de asunto de tipo con mapref. (8218)
* Se agrega nulo cada vez que se agrega un mapa al tablero de Publish en lote. (8695)
* Al utilizar la publicación de línea de base con imagen como referencia en el tema, la imagen no se publica en la salida. (8564)
* AEM La publicación falla con una excepción si se elimina la línea de base utilizada en la publicación del sitio de. (8572)
* La regeneración del tema no funciona. (8091)
* Hay problemas con la publicación de notas al pie en tablas. (4709)

### AEM Assets

* Se han encontrado problemas de rendimiento al realizar la selección/eliminación en un conjunto de contenido enorme en la IU de Assets. (8238)
* La función de búsqueda guardada (recopilación inteligente) se interrumpe si se añade un predicado DITA a los filtros de búsqueda. (8048)
* La reversión de la imagen a una versión anterior no funciona. (DXML-7903)
* La opción Eliminar también está visible para los autores que no tienen permiso para eliminar. (7322)
* La superposición de CCMS para el Editor de Assets interrumpe el procesamiento de la opción Eliminar. (8093)
* No se está eliminando el perfil de documento. (8604)
* Las referencias se rompen al realizar &quot;Seleccionar todo&quot; y mover el contenido multimedia/digital a otra carpeta. (8621)
* Se producen referencias incorrectas en el origen al mover los recursos. (8627)
* La vista de lista fija no se carga. (8542)

### Importación de contenido

* Conversión de HTML a DITA | La tabla con &#39;tr&#39; con entradas &#39;td&#39; vacías provoca filas adicionales en la salida. (8132)
* Conversión de HTML a DITA | El HTML que tiene una tabla con varios tbody falla con una excepción. (7940)
* Conversión de HTML a DITA | se elimina si el HTML de origen tiene comentarios. (7937)
* La importación de ficheros DITA 1.3 hace que algunos href se transformen en vínculos mal formados. (8019)

## Problemas conocidos

El Adobe as a Cloud Service ha identificado los siguientes problemas conocidos para la versión de [!DNL AEM Guides] de enero de 2022.


### Problemas conocidos con la solución

Utilice la solución dada para los siguientes problemas conocidos:

* La autenticación web no funciona para el conector Oxygen en Mac.
  **Solución alternativa**: por ahora, use el conector de oxígeno en Windows.

* En el navegador Firefox, los comentarios de revisión no se pueden importar sin abrir una vista en paralelo.
  **Solución alternativa**: utilice el explorador Chrome por ahora.

* Las referencias se rompen al mover las imágenes o los archivos multimedia que tienen espacio(s) en los nombres de archivo.
  **Solución alternativa**: cambie el nombre del archivo y quite los espacios del nombre del archivo antes de moverlos.

* El tablero de mapas no se carga intermitentemente en la última versión del explorador Chrome.
  **Solución alternativa**: Actualice la página del panel de asignaciones.

### Otros problemas conocidos

* Si Oxygen está conectado con la solución [!DNL AEM Guides] mediante autenticación web, el cierre de sesión falla.
* Las tareas de revisión no se pueden reasignar a los usuarios.
* Hay problemas en la IU de recopilación de mapas, como que el texto está distorsionado y que la funcionalidad **Seleccionar todo** no funciona correctamente.
