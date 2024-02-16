---
title: Notas de versión | Guías de Adobe Experience Manager as a Cloud Service, versión de febrero de 2023
description: Lanzamiento de febrero de las guías de Adobe Experience Manager as a Cloud Service
exl-id: c639b136-11ed-4a8b-a595-4bb5da879747
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '870'
ht-degree: 0%

---

# Lanzamiento de febrero de 2023 de las guías de Adobe Experience Manager as a Cloud Service

Esta nota de la versión cubre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en la versión de febrero de 2023 de las guías de Adobe Experience Manager (más adelante denominados *AEM Guías de as a Cloud Service*).

Para obtener más información sobre las nuevas funciones y mejoras, consulte [AEM Novedades de la versión de febrero de 2023 de Guías de la as a Cloud Service](whats-new-2023-2-0.md).

## Actualización a la versión de febrero de 2023

AEM Actualice la configuración as a Cloud Service de las guías de usuario actuales realizando los siguientes pasos:
1. Consulte el código Git de los Cloud Service y cambie a la rama configurada en la canalización de Cloud Service correspondiente al entorno que desea actualizar.
2. Actualizar `<dox.version>` propiedad en `/dox/dox.installer/pom.xml` de su código Git de Cloud Service a 2023.2.235.
3. Confirme los cambios y ejecute la canalización de Cloud Service AEM para actualizar a la versión de febrero de 2023 de las guías de la as a Cloud Service.

## AEM Pasos para indexar el contenido existente (solo si se encuentra en una versión anterior a la versión de septiembre de Guías de as a Cloud Service)

Realice los siguientes pasos para indexar el contenido existente y utilice el nuevo texto de búsqueda y reemplazo a nivel de mapa:

* Ejecute una solicitud de POST al servidor (con la autenticación correcta): `http://<server:port>/bin/guides/map-find/indexing`.
(Opcional: puede pasar rutas específicas de los mapas para indexarlas, de forma predeterminada se indexarán todas las asignaciones || Ejemplo : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Por ejemplo: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Una vez completado el trabajo, la solicitud de GET anterior responderá correctamente y mencionará si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.

## Matriz de compatibilidad

AEM En esta sección se muestra la matriz de compatibilidad para las aplicaciones de software compatibles con las guías de la versión de febrero de 2023 as a Cloud Service por las guías de la aplicación de.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| AEM Versión de Guides as a Cloud de | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.02.0 | No compatible | 2022 o superior |
| | | |

AEM *La línea de base y las condiciones creadas en la versión de FMPS a partir de 2020.2 son compatibles con las versiones de FMPS.

### Conector de oxígeno

| AEM Versión de Guides as a Cloud de | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.02.0 | 2.8-uuid-8 | 2.8-uuid-8 | 2,3 | 2,3 |
|  |  |  |  |

## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

### Creación

* Los cambios en el HTML del editor web causan problemas con `<dl>` y `<dlentry>`. (11024)
* Algunos atributos no se tratan como condicionales y causan problemas. (10895)
* Tres niveles o más anidados `<indexterm>` no están anidadas en la exportación de PDF nativa. (10799)
* El contenido desaparece en el cuerpo de una tarea al cambiar de la vista Autor a Fuente. (10735)
* Los comentarios de revisión no se colocan correctamente en una tarea de revisión. (10625)
* **Deshacer** o **Rehacer** no funciona correctamente en algunos archivos. (10373)
* Los metadatos personalizados no se conservan en la acción de copiar y pegar. (10367)
* La opción Deshacer del Editor XML lleva al usuario al principio de la página. (10091)
* Las propiedades del nodo se eliminan después de la operación de copiar y pegar de un recurso. (10053)
* mimeType está codificado para la creación y actualización de recursos DITA. (8979)
* El nombre del creador de la versión en el Historial de versiones es &quot;fmdita-serviceuser&quot; para los archivos cargados mediante la interfaz de usuario de Assets. (8910)
* AEM Los fragmentos de contenido no se pueden copiar y pegar cuando se instala Guías de en la nube. (11315)
* El explorador (editor web) se bloquea al cargar contenido con el esquema personalizado. (11211)

### Administración

* La copia de un recurso de mapa DITA (desde la IU de recursos ) provoca líneas de base erróneas en el recurso copiado. (11218)
* AEM El mensaje de advertencia no se muestra en la carga de un archivo que supere el límite permitido en el (2 GB de forma predeterminada). (10817)
* Editor web: línea de base | El comportamiento de la columna Última es diferente en el nuevo tablero de línea de base dentro del Editor Web. (10808)
* Traducción | El trabajo de traducción no se ha iniciado debido a un /libs/fmdita/i18n/ja.json no válido. (10543)
* Traducción | Se produce un error en un proyecto de traducción de ámbito creado desde el panel de traducción (traducción humana). (10526)
* Traducción | El procesamiento posterior se bloquea para toda la carpeta de idioma cuyos recursos estén presentes en un proyecto de traducción activo. (10332)
* Aparecen varias ventanas emergentes para cualquier recurso si se cambia la versión y se guarda en el Editor de líneas de base. (10399)
* La fuga de sesión se produce en `com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210)`. (10279)

### Publicación

* La regeneración de temas no funciona para algunos escenarios. (10635)
* Publishlistener no muestra los datos solicitados en los registros de información y también contiene algunos registros no deseados.( 10567)
* PDF nativo | Al crear un ajuste preestablecido de salida con la opción &quot;Añadir a perfil de carpeta&quot;, la generación del PDF falla con una excepción de puntero nulo. (10950)
* PDF nativo | Se producen problemas al girar el encabezado de Tabla. (10555)
* PDF nativo | Anidado `<indexterm>` no están anidadas en la exportación de PDF nativa. (10521)
* PDF nativo | Todos los temas anidados en los apéndices se transforman en h1 en el HTML temporal. (10454)
* La publicación de línea de base falla en el PDF generado mediante FrameMaker Publishing Server 2020. (10551)
* PDF nativo | Agregando `xref` a una imagen no procesa la imagen en el PDF generado. (11346)
* PDF nativo | La etiqueta de imagen agrega el atributo display-inline a todas las imágenes. (10653)
* PDF nativo | Los comentarios del borrador están ocultos de forma predeterminada en la salida generada. (10560)
* PDF nativo | el título de navegación no se respeta para topichead. (10509)
