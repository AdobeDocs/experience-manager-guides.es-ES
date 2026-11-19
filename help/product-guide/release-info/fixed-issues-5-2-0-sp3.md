---
title: Notas de versión | Se han corregido problemas en la versión del paquete de servicio 3 de Adobe Experience Manager Guides 5.2.0
description: Obtenga información acerca de las correcciones de errores en la versión 5.2.0 del Service Pack 3 de Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
source-git-commit: 01aae4f8c25d87d2dd0a0255bedab8d7b091e54d
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 0%
---
# Se han corregido problemas en la versión 5.2.0 del paquete de servicio 3 (noviembre de 2026)

Este artículo cubre los errores corregidos en varias áreas de la versión 5.2.0 del paquete de servicio 3 de Adobe Experience Manager Guides.

Obtenga información acerca de [instrucciones de actualización para el Service Pack 3 de la versión 5.2.0](upgrade-instructions-5-2-0-sp3.md).

## Editor 2.0

- Al copiar una tabla del modo Autor y pegarla en el modo Autor, se eliminan atributos como `colwidth` y cualquier otro atributo definido en `colspec`, lo que provoca que se pierda la configuración de ancho de columna. (GUIDES-52916)
- Cuando se pega una tabla desde Microsoft Word, se crean las celdas de fila de encabezado pero se pierde su contenido. (GUIDES-49847)
- Cuando el código se pega en un elemento `codeblock`, desde Microsoft Word o editores de texto similares, mediante Ctrl+V, se pierden los saltos de línea y los espacios iniciales y el código se acopla en una sola línea. (GUIDES-33247)

## Administración de recursos

- La API de estado del recurso no devuelve el estado correcto para los recursos cuya ruta contiene una coma. (GUIDES-49065)

## Publicación

- Al publicar un mapa DITA con `processing-role=resource-only` elementos en AEM Sites (con asignación de componentes heredados), se generan páginas de sitio huérfanas para esos elementos en escenarios adicionales como `topicgroup` elementos y configuraciones de contenido específicas. (GUIDES-37650)
- El filtrado de ramas genera páginas adicionales para los temas no deseados utilizados como `keydef` (que están marcados como `resource-only ="true"` por DITA-OT). (GUIDES-19701)
- En el tablero de mapas, al seleccionar un ajuste preestablecido diferente, se déclencheur una llamada para recuperar vínculos de igual a igual, lo que da como resultado un procesamiento adicional. (GUIDES-53703)
- En la salida nativa de PDF, las referencias de temas marcadas con el atributo `toc="no"` se siguen incluyendo en la tabla de contenido, lo que da como resultado una tabla de contenido larga y desordenada. (GUIDES-20156)
- En algunos casos, cuando se genera y publica un mapa DITA completo en AEM Sites utilizando una línea de base dinámica, ciertos temas se publican con versiones anteriores o no aprobadas en lugar de las versiones aprobadas actuales. (GUIDES-55646)
- Al procesar un gran número de recursos, `PurgePresetExecutionDataJob` a veces encuentra un `RuntimeNodeTraversalException` no controlado, lo que provoca que el trabajo se quede atascado en un bucle infinito y genere registros excesivos. (GUIDES-53897)
- En la salida nativa de PDF, el atributo `outputclass` establecido en un elemento `topichead` o `topicgroup` no se aplica ni se transfiere a la sección de PDF resultante. (GUIDES-22950)
- En algunos casos, al publicar con el motor nativo de PDF v1, el orden de lectura del contenido con accesibilidad `settingsenabled` es incorrecto. Los números de página de los pies de página se leen antes del contenido principal en lugar de al final. (GUIDES-27790)


## Traducción

- La aplicación de una línea de base a una asignación con muchos recursos retrasa la carga del informe de traducción para el idioma seleccionado, a veces conduce al tiempo de espera de solicitud antes de que se procese el informe. (GUIDES-45508)
- Los grupos de idiomas de la ficha Traducción en Configuración de Workspace no se conservan cuando la carpeta de idioma seleccionada utiliza un código de configuración regional con guiones (por ejemplo, `da-DK`) en lugar de un formato de guion bajo (`da_dk`). (GUIDES-37843)
- Al iniciar una traducción con un proyecto XLIFF, se crea un proyecto vacío que nunca pasa a un estado en curso. (GUIDES-51759)
- La configuración `propagateVersionLabel` del perfil de carpeta global se restablece de forma intermitente a `false` cuando un usuario con la única función Colaborador accede al Editor. (GUIDES-51870)

## Línea de base

- La selección de línea de base guardada de un ajuste preestablecido se muestra incorrectamente como *Sin línea de base* después de eliminarse la línea de base o mientras se sigue creando una línea de base dinámica. (GUIDES-52690)
- En algunos casos, las líneas base dinámicas permanecen atascadas en el estado de procesamiento después de una regeneración fallida, lo que provoca que la generación de exportaciones y salidas utilice temas y versiones de asignación obsoletos sin mostrar ningún error. (GUIDES-56739)

## Revisión

- En escenarios que implican un gran número de tareas de revisión, abrir el panel Revisar o aplicar un filtro de proyecto tarda más de lo esperado en cargar la lista de tareas. (GUIDES-48893)
- El panel de contenido de la IU de revisión muestra una barra de desplazamiento horizontal en determinadas resoluciones de pantalla, incluida la resolución recomendada de 1600 píxeles, lo que provoca que los comentarios de revisión se oculten cuando el contenido se extiende más allá de la anchura del panel. (GUIDES-44082)

## Plataforma

- La API de movimiento, la API de cambio de nombre y la IU de Assets impiden cambiar el nombre de un recurso DITA con un nombre de archivo basado en GUID a un nombre de archivo legible en lenguaje natural. Ahora se puede cambiar el nombre de Assets por nombres de archivo legibles en lenguaje natural, pero aún no se permite cambiar el nombre de un nombre de archivo basado en GUID por otro basado en GUID. (GUIDES-43006, GUIDES-59684)
- Cuando un recurso no DITA, como una imagen, que se migró de una configuración sin UUID a una configuración de UUID se revierte o bifurca a otra versión, su UUID cambia. Las referencias existentes al recurso ya no se resuelven y la imagen aparece rota en los temas que hacen referencia a él. (GUIDES-58414)
- Al instalar el Service Pack de Experience Manager Guides se eliminan las herramientas externas previamente instaladas, como ACS Commons, de la sección **Herramientas** de AEM. (GUIDES-60365)

## Problemas conocidos

Adobe ha identificado los siguientes problemas conocidos para la versión 5.2.0 del paquete de servicio 3:

- Después de instalar el Service Pack, es posible que la validación de Schematron falle con una excepción `NoClassDefFoundError` y no se puedan guardar temas en el Editor. <br>**Solución alternativa:** Actualice el paquete `com.adobe.fmdita.schematron-wrapper` desde la consola web de AEM (`/system/console/bundles`).
