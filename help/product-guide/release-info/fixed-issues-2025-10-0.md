---
title: Notas de versión | Se han corregido problemas en la versión 2025.10.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2025.10.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: ff3cf777bd348edded29d780031df59bbb03035d
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 3%

---

# Se han corregido problemas en la versión 2025.10.0

Este artículo cubre los errores corregidos en varias áreas de la versión 2025.10.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 2025.10.0](whats-new-2025-10-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2025.10.0](upgrade-instructions-2025-10-0.md).

## Creación

- Cuando hay varios temas o mapas DITA abiertos y uno de los temas está cerrado, el botón **>** que muestra todas las pestañas abiertas se superpone con las pestañas abiertas restantes de la barra de pestañas. (GUIDES-31421)
- Con el **flujo de trabajo de aprobación** habilitado, el botón **Iniciar una nueva versión** no está visible en la barra de herramientas del Editor si el panel izquierdo y el panel de propiedades de contenido están abiertos. (GUIDES-29093)
- Cuando los nombres de fragmento superan la anchura del panel de fragmento, se ajustan incorrectamente en la línea siguiente, lo que da como resultado una superposición con fragmentos adyacentes y afecta a la legibilidad. (GUIDES-22685)
- Cuando se agrega la misma referencia varias veces a un mapa DITA, la vista **Map** muestra el título únicamente de la última ocurrencia, mientras que las anteriores muestran el UUID de la referencia. (GUIDES-9699)
- Los archivos DITAVAL siguen siendo editables, incluso cuando están bloqueados por otro usuario o cuando el servidor tiene **Deshabilitar la edición sin bloquear el archivo** habilitado y el archivo se abre en modo de solo lectura. (GUIDES-27754)
- Los registros de los nodos que faltan se generan a partir de trabajos de limpieza interna que no son necesarios y se marcan incorrectamente como errores, lo que da como resultado archivos de registro agrupados. (GUIDES-31765)


## Publicación

- Al generar PDF, las reglas de filtrado en un archivo DITAVAL se ignoran si algún nombre de propiedad contiene un punto. (GUIDES-33229)
- La publicación de Salesforce falla con un error de aplicación, cuando ya existe un tema con el mismo nombre y dirección URL. (GUÍAS- 32390)
- La publicación en Salesforce muestra un estado correcto en la interfaz de usuario incluso cuando un mapa DITA que contiene un elemento `topichead` no puede publicar los temas incluidos en él. (GUIDES-32143)
- Para el ajuste preestablecido de salida HTML5, la funcionalidad de filtro de búsqueda no funciona en los AEM Assets para el filtrado DITAVAL, ya que los archivos correspondientes no se muestran cuando se selecciona el filtro DITAVAL. (GUIDES-28231)
- Al generar un PDF nativo para un mapa DITA con varios temas, si algún tema contiene un elemento `fig` en un elemento `figgroup` junto con un elemento `title`, el título `figgroup` se representa incorrectamente como un título de capítulo en la tabla de contenido. (GUIDES-23223)
- Al duplicar plantillas de PDF desde la interfaz de usuario de, el UUID también se duplica, lo que provoca que los archivos de plantilla se eliminen y den como resultado salidas de PDF incorrectas. (GUIDES-30456)
- Al generar PDF nativo para un mapa DITA, el título del elemento `example` se representa como `h1` nivel de encabezado, lo que produce incoherencia visual y una estructura de TDC incorrecta. (GUIDES-19958)

## Traducción

- Al ampliar la pantalla de la interfaz de usuario de traducción, el botón **Enviar para traducción** se mueve bajo los puntos suspensivos y se activa incluso sin que se haya seleccionado ningún recurso. (GUIDES-33720)
- Al seleccionar archivos con estado **Fuera de sincronización** en la interfaz de usuario de traducción, y el ancho de la pantalla está restringido debido a que se abren los paneles Izquierdo y Derecho, la etiqueta **Enviar para traducción** se trunca. (GUIDES-33692)

## Revisión

- Cuando un revisor completa una tarea de revisión o el iniciador actualiza la tarea de revisión sin introducir comentarios, el correo electrónico de notificación enviado muestra el comentario anterior más reciente. (GUIDES-33590)

## Problemas conocidos

Adobe ha identificado los siguientes problemas conocidos para la versión 2025.10.0:

- Al abrir una dirección URL con un tema DITA abierto anteriormente o al actualizar un tema DITA abierto, no se encuentra el tema en el repositorio a pesar de que la opción **Buscar siempre los archivos en el repositorio** esté habilitada en las preferencias de usuario. (GUIDES-35565)<br>**Solución alternativa**: seleccione la ficha del tema para localizar el archivo en el repositorio.

- Al crear un nuevo archivo en la vista Autor con varios archivos abiertos, el panel Derecho no se actualiza y muestra datos incorrectos si el cursor se coloca en una etiqueta de elemento de un archivo diferente. (GUIDES-35450)<br>**Solución alternativa**: cambie de pestaña o actualice la página para resolver el problema.

- Al cambiar a la vista Autor desde la vista Source para un tema recién abierto (que inicialmente se abre en el modo Source), el contenido del tema queda en blanco. (GUIDES-35000)<br>**Solución alternativa**: actualice la página o vuelva a abrir el tema para resolver el problema.

- El botón **Actualizar navegación** aparece para los archivos de tema DITA, aunque sólo debería estar disponible para los mapas DITA, los mapas de libros y los esquemas de asunto. (GUIDES-35452)






