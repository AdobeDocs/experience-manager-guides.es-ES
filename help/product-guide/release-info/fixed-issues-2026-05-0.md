---
title: Notas de versión | Se han corregido problemas en la versión 2026.05.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2026.05.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 4a22e6f8e2505a5e2a990ec38571913c838d0ea1
workflow-type: tm+mt
source-wordcount: '1255'
ht-degree: 0%

---

# Se han corregido problemas en la versión 2026.05.0

Este artículo cubre los errores corregidos en varias áreas de la versión 2026.05.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información acerca de las nuevas características y mejoras, vea [Novedades de la versión 2026.05.0](whats-new-2026-05-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2026.05.0](upgrade-instructions-2026-05-0.md).

## Creación

- Al seleccionar una imagen en el Editor mediante el cuadro de diálogo **Seleccionar archivo**, solo se muestran los formatos de trama (como JPG, PNG y GIF). Los archivos vectoriales (como .ai y .eps) no se muestran y no se pueden seleccionar. (GUIDES-45110)
- En el momento de la actualización, la configuración `tagsView` está desactivada de forma predeterminada, aunque su valor predeterminado en `ui_config.json` esté establecido en `true`. (GUIDES-44651)
- En el Editor, las referencias de archivo se muestran como GUID en lugar de como rutas de archivo a pesar de la configuración de `xmleditor.uuid`. (GUIDES-42438)
- Cuando se aplican esquemas de asunto con valores de clave similares en un tema DITA, se resaltan con colores casi idénticos, lo que dificulta su distinción e identificar qué esquema se aplica. (GUIDES-38472)
- Al editar una asignación de esquema de asunto en la vista de autor, al agregar el elemento `hasInstance` se déclencheur automáticamente el cuadro de diálogo de selección de archivos, lo que requiere que los autores inserten un elemento `href` no deseado que apunte a un recurso de AEM. Además, el panel **Propiedades de contenido** no se puede cargar para estos mapas, lo que impide que los autores actualicen los atributos de los elementos en la vista Autor y requiere que utilicen la vista Source para actualizar los atributos. (GUIDES-38164)
- Al editar un archivo `.ditaval`, los comentarios XML agregados en la vista de Source se quitan al cambiar a la vista Autor y, a continuación, volver a la vista de Source. (GUIDES-33228)


## Administración de recursos

- Al crear un tema en una carpeta con espacios en su nombre, se crea incorrectamente una carpeta duplicada en la que los espacios se sustituyen por guiones y el tema se guarda allí en lugar de en la carpeta original. (GUIDES-41938)
- Durante la primera traducción de mapas grandes, se crean archivos XML vacíos para el idioma de destino, lo que aumenta la carga del servidor y ralentiza el rendimiento. (GUIDES-41613)
- En entornos basados en BD, los vínculos DITA internos válidos aparecen como vínculos rotos en **Propiedades del recurso**, aunque funcionen correctamente en el Editor y en la salida publicada. (GUIDES-35048)

## Publicación

- Cuando los cambios en un ajuste preestablecido de salida en un perfil de carpeta se aplican a asignaciones existentes, se restablece el **contexto de publicación** guardado para el ajuste preestablecido de AEM Sites. (GUIDES-38377)
- El símbolo de marca comercial (®) no aparece en la portada de la salida de PDF nativo cuando se utiliza el elemento `tm` dentro del título de un mapa o un mapa de libros. (GUIDES-28832)
- Al publicar un mapa mediante una plantilla de PDF nativa, el **título del mapa** no incluye contenido de los elementos secundarios utilizados en el mapa `title`, y el filtrado de contenido correspondiente no se aplica al título. (GUIDES-33730)
- Los vínculos del mismo nivel de asignación cruzada en la salida de AEM Sites no se pueden resolver cuando apuntan a un(a) `topicref` que usa `chunk="to-content"`. (GUIDES-37873)
- Durante la publicación, los archivos asociados con el indicador basado en DITAVAL se mueven a una nueva carpeta generada por el sistema en lugar de permanecer en la ubicación relativa esperada en la salida. (GUIDES-37564)
- Cuando se utilizan varios archivos DITAVAL con condiciones en conflicto, la salida nativa de PDF falla. (GUIDES-37484)

## Línea de base

- Las referencias a temas dentro de un mapa se muestran incorrectamente como indirectas cuando se utiliza una DITA-OT personalizada, aunque se haga referencia a ellas directamente. Este problema se ha resuelto con la nueva experiencia de línea de base. (GUIDES-19286)
- Las referencias con `scope="peer"` se incluyen incorrectamente en el contexto de línea de base, lo que hace que la publicación tarde más de lo esperado. Este problema se ha resuelto con la nueva experiencia de línea de base. (GUIDES-30048)

## Plataforma

- Cuando se abren temas o mapas grandes, la instancia de autor deja de responder y, en algunos casos, es necesario reiniciar. (GUIDES-43547)

## Problemas resueltos disponibles con Editor 2.0

Los siguientes problemas se han corregido y ya no se producen al utilizar Editor 2.0 (también conocido como Nuevo editor):

- Cuando se eliminan dos o más columnas de una tabla, la estructura de la tabla se vuelve incoherente o dañada. (GUIDES-35438)
- Cuando se elimina una columna de una tabla que contiene celdas combinadas, se agrega una nueva columna en blanco. (GUIDES-30147)
- Cuando se inserta una fila nueva en una tabla existente desde el menú de rutas de exploración, la estructura de la tabla cambia inesperadamente, lo que da como resultado la falta de bordes y una columna adicional. (GUIDES-29194)
- En la vista Autor, copiar y pegar una fila de la tabla coloca el contenido fuera de la tabla en lugar de insertarlo como una fila nueva dentro de la tabla. (GUIDES-24372)
- Cuando se copia y pega un elemento de sección seleccionado mediante el arrastre del mouse en el modo Autor, se convierte en elementos de párrafo `(<p>)` en lugar de conservar la estructura de sección. (GUIDES-30023)
- Cuando se edita el texto resaltado dentro de elementos como step o uicontrol, el texto seleccionado no se reemplaza correctamente y se anexa o se antepone, lo que provoca errores de validación. (GUIDES-24371)
- Cuando se establece el ancho de una columna de tabla utilizando valores relativos, las columnas restantes no se ajustan proporcionalmente, lo que provoca que el diseño de la tabla no esté alineado correctamente. (GUIDES-26109)
- Cuando se pega un título de tema copiado con las etiquetas desactivadas, la primera pegado aplica un estilo incorrecto y asigna el tipo en las propiedades de Contenido como tema en lugar de título. (GUIDES-28838)
- Cuando se editan secciones grandes de contenido, el movimiento de desplazamiento no intencionado hace que la vista del editor salte del contenido activo. (GUIDES-35436)
- Cuando se utiliza Retroceso en elementos, el editor se desplaza hasta la parte superior del tema independientemente de la posición del cursor. (GUIDES-32520)
- Cuando se utiliza la tecla de flecha izquierda o derecha para desplazarse fuera de las etiquetas en línea, el cursor salta inesperadamente en el primer intento. (GUIDES-26363)
- La revisión ortográfica de AEM solo funciona para el idioma en-US predeterminado y no respeta otras configuraciones regionales. (GUIDES-14731)
- Cuando se desbloquean temas DITA grandes en el Editor, se vuelve a abrir el mismo tema en una ficha duplicada. Además, se activa una advertencia de límite de etiquetas donde se muestra `NaN` en lugar del recuento real de etiquetas. (GUIDES-34008)
- Las sugerencias de Acrolinx no se resaltan correctamente en el Editor de temas de solo lectura o bloqueados. (GUIDES-29614)
- Al crear un(a) nuevo(a) `reltable` sin una fila de encabezado en la vista Autor, el diseño de la tabla cambia después de agregar un tema a la primera celda, lo que provoca que la siguiente columna se contraiga y dificulta la colocación de temas relacionados. (GUIDES-19555)
- Cuando se agrega un vínculo `xref` a una celda de tabla pequeña en el modo Autor, el vínculo no permanece dentro de la celda y aparece en las celdas adyacentes de la misma fila. (GUIDES-5489)
- Al cambiar de la vista Autor a la vista Source, la posición del cursor no se conserva y el Editor se desplaza de nuevo a la parte superior. Además, en los temas largos, la posición del cursor se pierde y salta aleatoriamente al centro o a la parte superior al alternar entre las vistas Autor y Source. (GUIDES-18114, GUIDES-21164)
- Al presionar *Entrar* dentro de un elemento `<li>`, se crea un nuevo elemento `<li>`, pero al volver a un elemento `<li>` anterior y presionar *Entrar*, el contenido del elemento actual se convierte incorrectamente en un elemento `<p>`, lo que rompe la estructura de la lista. (GUIDES-27505)

## Problemas conocidos

Adobe ha identificado los siguientes problemas conocidos para la versión 2026.05.0:

- Cuando un mapa contiene un(a) `topicref` externo que señala a un recurso no DITA (como `.html` o `.htm`), su vista previa no se muestra en la interfaz de usuario de Assets. (GUIDES-45409)
- En la interfaz de usuario de Assets, el contenido al que se hace referencia mediante `conref` no aparece para los temas de DITA, aunque se muestre correctamente en la vista previa del editor. (GUIDES-45505)<br>**Solución alternativa**: Para dicho contenido, puede utilizar la vista previa del editor.
- Cuando la propiedad `xmleditor.uniquefilenames` está habilitada, los nuevos temas creados con una plantilla no incluyen el título del tema. (GUIDES-44737)
- Las API `getAsset`, `startAssetProcessing` y `getAssetProcessingStatus` no se pueden usar en Java SDK.

