---
title: Notas de versión | Se han corregido problemas en la versión 5.0.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 5.0.0 de Adobe Experience Manager Guides.
exl-id: dcc97f9b-f1c0-45bc-84eb-8c0c1a857b6a
TQID: https://experienceleague.adobe.com/L91ThAocmv3mZYa905W4PM5dtK2katbFjGiY0Mi73qg
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0eid: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8id: d6596f3f-92a7-43ec-b444-237db6adad05id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0efid: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 1246
ht-degree: 5%

---

# Se han corregido problemas en la versión 5.0.0 (marzo de 2025)

Este artículo cubre los errores corregidos en varias áreas de la versión 5.0.0 de Adobe Experience Manager Guides.


Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 5.0.0](whats-new-5-0-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 5.0.0](upgrade-instructions-5-0-0.md).


## Creación

- Al actualizar condiciones desde el perfil de carpeta, todos los grupos de condiciones se pierden y las condiciones se acoplan. (23526)
- Al cambiar el valor de las filas de encabezado de una tabla en el panel **Propiedades de contenido**, no se aplica el valor actualizado. (23213)
- Para las transiciones de estado de documento de Guías posteriores, se requiere una actualización de la página. (19421)
- Al agregar temas en el mapa DITA mediante el cuadro de diálogo de elementos **Referencia de tema** en la vista **Autor**, los temas seleccionados se insertan en orden inverso al de su selección. (8031)
- Al cambiar entre la vista **Autor** y la vista **Source**, se eliminan los espacios iniciales de `<pre>` o `<codeblock>` elementos y el archivo se guarda con esta eliminación. (19987)
- El estado del documento marcado como **Listo** vuelve a **Borrador** antes de guardar una nueva versión, lo que hace que el estado **Listo** no persista en ninguna versión del documento. (20006)
- Cuando los elementos de la lista se mueven fuera de la etiqueta para, se pierde el contenido del elemento de la lista. (22764)
- Al agregar temas en el mapa DITA mediante el cuadro de diálogo de elementos **Referencia de tema** en la vista **Autor**, los temas seleccionados se insertan en orden inverso al de su selección. (22858)
- Al agregar nuevas referencias de temas en el mapa DITA mediante el cuadro de diálogo de elementos **Referencia de temas** en la vista **Diseño**, las referencias agregadas se muestran como vínculos rotos. (22859)
- Cuando hace clic con el botón secundario en la etiqueta `<simpletable>` dentro de un tema, la opción **Rename** no se muestra. (22860)
- Al insertar un(a) `xref` que utiliza referencias basadas en claves con texto de vínculo, el texto del vínculo no se muestra en Experience Manager Guides. (18775)
- Si arrastra y suelta una imagen dentro de un tema en la vista **Autor**, la referencia de imagen se romperá y se perderán datos. (25769)
- Al buscar archivos en el repositorio mediante la funcionalidad **Buscar y filtrar**, no se pueden seleccionar varios archivos. (25104)
- Al copiar una imagen de cualquier producto externo (por ejemplo, MS PowerPoint) y pegarla en Guides, la funcionalidad para cargar el recurso sobre la marcha para utilizarlo en los saltos de archivo. (24983)
- Si arrastra un(a) `topicref` sobre otro (en la vista **Autor** o **Diseño**), se solicitará una confirmación para el reemplazo en lugar de anidar y, al seleccionar **No** en el cuadro de diálogo de confirmación, se seguirá reemplazando el contenido, lo que provocará la pérdida de datos. (18602)
- No se pueden agregar varios métodos abreviados a un único evento, ni se puede agregar un argumento a un evento al activarlo desde un método abreviado. (19066)
- Al volver a cargar el explorador, se vuelve a abrir la pestaña de imagen previamente cerrada. (19267)
- Si se selecciona parcialmente el texto de un párrafo o elemento de la lista y se arrastra fuera del elemento, se perderá contenido al cambiar entre las vistas **Autor** y **Source**. (25790)

## Publicación

- La publicación en Salesforce falla cuando el contenido contiene espacios de no separación. (23664)
- En el caso de los mapas con vínculos rotos, la publicación de Salesforce falla y la barra de progreso se muestra indefinidamente. (24963)
- En los temas con errores como los vínculos rotos, la publicación de Salesforce falla y la barra de progreso se muestra indefinidamente. (22985)
- La publicación nativa de PDF falla en la opción de conformidad **PDF/X-4** con un error que indica que **los documentos PDF/X-4 requieren un título que no esté vacío**. (16904)
- Cuando se usa texto de marcador de posición, no se pueden resolver las referencias cruzadas que usan `<keyref>` en PDF nativo. (19365)
- La generación nativa de PDF falla en el contenido con **atributo chunk** establecido en **to-content**. (21772)
- Al generar una salida nativa de PDF, no se admite el elemento `ditavalref`. (16320)
- Al editar archivos CSS grandes en el editor CSS nativo de PDF, se observa un retraso significativo. (16915)
- Para la publicación basada en HTML5, el indicador DITA-OT generate.copy.outer se aplica automáticamente. (24299)
- La referencia cruzada se convierte en vínculo relativo incluso cuando el **ámbito** del vínculo está establecido en **externo**. (23059)
- Cuando hay un archivo ICC disponible en una ruta de acceso interna, no se puede seleccionar en la configuración de **Imprimir** para el ajuste preestablecido de PDF nativo. (14741)
- Cuando se inician varias solicitudes de publicación para diferentes asignaciones utilizando el mismo ajuste preestablecido de perfil de carpeta, la publicación falla. (18800)
- En el caso de los temas que tengan una propiedad o metadatos multivalor cuando se pasan a DITA OT, se producirá un error en la publicación. (19001)
- El cuadro de diálogo **Editar propiedades** de una línea base no muestra los criterios guardados anteriormente para la línea base dinámica.  (23964)
- La línea base no incluye referencias indirectas cuando el contenido se encuentra en el estado final del documento. (19148)
- La opción **Sanear nombres de páginas y archivos para AEM Sites y otros formatos de salida** se aplica a todos los formatos de salida. (7651)
- Si un vínculo externo contiene un UUID, se incluye en el procesamiento posterior y convierte el vínculo externo en un vínculo UUID, rompiendo así el vínculo en el editor web y también en los sitios de publicación. (22574)


## Administración

- El título y el icono del cuadro de diálogo **Forzar eliminación** no están alineados correctamente en la interfaz de usuario de Assets. (21933)
- Cuando se actualiza cualquier JSON en el perfil de carpeta para la configuración del editor XML, la operación de guardado interrumpe la configuración del editor XML. (22414)
- Al duplicar cualquier perfil de carpeta, su lista de usuarios administradores también se copia del perfil de carpeta original. (19067)
- Al mover carpetas grandes (con un gran volumen de contenido DITA, hasta 200 000 elementos) desde la interfaz de usuario de Assets, se produce un error. (20107)
- Si edita el perfil **Folder** con el shell unificado habilitado, se generará una interfaz de usuario en blanco. (22212)
- Al eliminar carpetas que contienen un gran número de archivos, la operación falla. (17107)
- Cuando cancela o elimina el trabajo de traducción o elimina el proyecto, el panel de traducción muestra el estado **En curso**. (18417)
- Cuando envía dos versiones de un tema sin traducir simultáneamente mediante traducción no heredada y aprueba la segunda versión antes de la primera, se interrumpe el proyecto de traducción con la primera versión. (22200)


## Revisión

- Al seleccionar varios temas para su revisión en un mapa, la notificación por correo electrónico que recibe el revisor indica que todos los temas del mapa están disponibles para su revisión, en lugar de solo los seleccionados. (23214)
- El título y el icono del tema no están alineados correctamente en la interfaz de creación de revisiones. (11670)


## API de

- Se produce un error al crear **Baseline** mediante la API de Guides y al activar el servicio **BaselineUtlis**. (19385)

## Problemas conocidos

Adobe ha identificado los siguientes problemas conocidos para la versión 5.0.0:

- En algunos casos, la funcionalidad de bloqueo de los archivos CSS no funciona como se esperaba, lo que permite a otros usuarios editar y guardar los archivos incluso cuando están bloqueados por otro usuario.
- No se puede salir de la vista de la consola Mapa cuando la Línea base está sucia con el guardado automático habilitado.
- La aplicación de cambios de configuración de ajustes preestablecidos no se refleja en los ajustes preestablecidos que ya se han creado dentro del mapa si el nombre del ajuste preestablecido tiene algún carácter en mayúsculas.
- La posición del color de fondo no está alineada correctamente en la interfaz de usuario de **Panel de la condición**.
- Cuando usa la imagen como `<keyref>`, el **Tipo de referencia** de la imagen no se muestra en el **informe multimedia**.
- Al utilizar imágenes como variables en la plantilla de PDF, no se resuelve en la salida.
- En los informes de **Lista de temas**, se produce un error al ordenar por título los recursos con `<conref>` o `<conkeyref>` en el título, lo que hace que estas entradas siempre aparezcan en la parte superior.
- El cambio del perfil de carpeta no refleja inmediatamente los cambios en la interfaz de usuario sin actualizar el explorador.
- Es posible que las personalizaciones del marco de extensión realizadas antes de Guides 5.0.0 no funcionen según lo previsto.
- La tabla de contenido completa del mapa no se actualiza al publicar selectivamente temas del mapa.
- La publicación de un mapa que contiene un archivo Markdown con referencias de imagen internas produce un error en los servidores de Windows.
- La lista con viñetas no se convierte en lista numerada en Markdown.
- La publicación en un sitio nativo de AEM falla cuando se hace referencia a los archivos de marcado en un mapa.
