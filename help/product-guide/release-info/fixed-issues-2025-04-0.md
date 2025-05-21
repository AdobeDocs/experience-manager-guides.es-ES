---
title: Notas de versión | Se han corregido problemas en la versión 2025.04.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2025.04.0 de Adobe Experience Manager Guides as a Cloud Service.
exl-id: ad3e95b5-4903-4387-8e4d-c4b9ba77fee2
source-git-commit: 70078864379eedd82ae21da70614055c60f0b114
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 3%

---

# Se han corregido problemas en la versión 2025.04.0

Este artículo cubre los errores corregidos en varias áreas de la versión 2025.04.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 2025.04.0](whats-new-2025-04-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2025.04.0](upgrade-instructions-2025-04-0.md).

## Creación

- El cuadro de inserción de caracteres especiales del Editor no se carga para la configuración regional en alemán. (24537)
- Los comentarios y etiquetas añadidos al guardar una nueva versión de un archivo DITAVAL no se guardan en el Historial de versiones con la nueva versión. (24076)
- Las referencias salientes y entrantes bajo **Propiedades del archivo** en el panel derecho no se actualizan correctamente al cambiar entre archivos de asignación. Este problema se produce específicamente cuando los archivos de mapa contienen un gran número de referencias. (23344)
- El filtro Repositorio no conserva el orden de los filtros personalizados definidos en `ui_config.json`. (21193)
- Al eliminar varias líneas de texto en un elemento `codeblock`, se crea un espacio vacío que no se puede eliminar de la vista Autor. (20672)
- No se pueden generar nuevos identificadores para elementos cuando dichos elementos se agregan mediante fragmentos o se crean mediante plantillas, incluso cuando la opción **Generar automáticamente ID** está habilitada en `XMLEditorConfig`. (21734)
- Al crear un nuevo recurso DITA a partir de plantillas DITA, se copian las propiedades de replicación de las plantillas DITA correspondientes. (25145)
- No se puede acceder a las propiedades del archivo desde el panel del repositorio si el nombre de la carpeta principal incluye el carácter &quot;&amp;&quot;. (25762)
- El cierre de un archivo de tema permite guardarlo como una nueva versión, incluso cuando el tema está bloqueado. Este problema ocurre específicamente cuando la opción **Pedir nueva versión al cerrar** está habilitada en `XMLEditorConfig`. (23875)
- La anchura máxima actual del panel del repositorio oculta los títulos de temas y mapas cuando la jerarquía de contenido está profundamente anidada. (27751)

## Publicación

- En la salida heredada de AEM Sites, los vínculos de sección dentro de los temas anidados de un mapa no se resuelven correctamente cuando se establecen manualmente en el modo Source o el contenido se importa desde un origen externo. En lugar de ir a la sección deseada, se redirige al tema principal que contiene el tema anidado. (26103)
- Si falta el atributo `scope=external` en los vínculos externos de un tema DITA, la publicación de HTML5 falla sin indicar los archivos en los que falta este atributo en los registros de errores, especialmente cuando el microservicio está habilitado. (25969)
- No se pueden incrustar vínculos de vídeo en el PDF nativo aunque la opción **Incrustar archivos multimedia** esté habilitada en el ajuste preestablecido de PDF. (9989)
- No se pueden pasar las propiedades de metadatos para asignar las páginas de aterrizaje generadas mediante la nueva publicación de AEM Sites. (27288)

## Administración

- El estado del documento de la copia de trabajo de un tema se muestra con todas las versiones de ese tema en la IU Traducción y Línea de base. (20674)


## Revisión

- Al actualizar los detalles de una tarea de revisión en el panel Revisar, no se confirma si la actualización se ha realizado correctamente o no. (8051)

## Traducción

- Las traducciones enviadas a través de Experience Manager Guides no incluyen los recursos adjuntos, lo que provoca que el botón **Iniciar** del trabajo de traducción no esté disponible para los usuarios.

## Problemas conocidos

Adobe ha identificado los siguientes problemas conocidos para la versión 2025.04.0:

- El recuento de referencias en la IU de Línea base no se actualiza al editar la Línea base. Solo se actualiza cuando se guardan los cambios. (28015)
- Cuando hay varias pestañas abiertas en el Editor, realizar una operación **Deshacer** en la vista **Source** de un archivo revierte la última edición, pero también cambia a la pestaña abierta anteriormente. (27891)
- La opción **Corrección ortográfica de AEM** aparece en la lista desplegable **Menú**, incluso cuando la opción **Corrección ortográfica del explorador** está habilitada en la configuración del Editor. (27993)
- Se crea una versión adicional que se muestra en el panel **Historial de versiones** cuando edita una imagen en la interfaz de usuario de Assets y la guarda. (28001)
- Se inserta automáticamente una línea vacía al pegar contenido nuevo en una línea nueva dentro de un elemento `codeblock`.(27842)
- Al cambiar entre ajustes preestablecidos que utilizan la misma Línea de base, se desactiva el botón **Guardar** para el ajuste preestablecido actual. (28025)
- Un tema de un mapa DITA no se puede publicar en la salida de AEM Sites cuando se utiliza como `keydef` y `topicref` en sus submapas. (22269)
- Se produce un error de aplicación cuando se editan varios temas de un mapa y se cierran con la opción **Cerrar todo**, con la opción **Preguntar al guardar la versión al cerrar** habilitada.(27931)

Adobe ha identificado el siguiente problema conocido con una solución alternativa:

+++En la salida de AEM Sites, las imágenes se rompen cuando Línea base no se aplica durante la publicación. (28043)
***Solución alternativa:*** Estos recursos se pueden publicar desde la **interfaz de usuario de Assets**, después de lo cual el vínculo estará operativo.
+++