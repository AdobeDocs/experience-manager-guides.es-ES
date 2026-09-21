---
title: Notas de versión | Se han corregido problemas en la versión del paquete de servicio 1 de Adobe Experience Manager Guides 5.2.0
description: Obtenga información acerca de las correcciones de errores en la versión 5.2.0 del Service Pack 1 de Adobe Experience Manager Guides
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
source-git-commit: 429d2abf0aad8722ac30c08c9c9d134be0759ff4
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 0%
---
# Se han corregido problemas en la versión 5.2.0 del paquete de servicio 1 (septiembre de 2026)

Este artículo cubre los errores corregidos en varias áreas de la versión 5.2.0 del paquete de servicio 1 de Adobe Experience Manager Guides.

Obtenga información acerca de [instrucciones de actualización para el Service Pack 1 versión 5.2.0](upgrade-instructions-5-2-0-sp1.md).

## Creación

- En pantallas de baja resolución, el cuadro de diálogo Insertar palabra clave no aparece al insertar una palabra clave desde la barra de herramientas, mientras que se abre como se espera al utilizar la opción **Más**. (GUIDES-48304)
- Al insertar una referencia cruzada mediante la opción **vínculo web**, se agrega un vínculo `scope=local` y se modifica el valor `href`, en lugar de insertar un vínculo `scope=external` como se esperaba. (GUIDES-48457)
- Guardar un mapa de referencia genera una referencia rota en lugar de resolverse en el mapa correcto cuando un autor mueve el mapa al que se hace referencia mientras otro autor le agrega simultáneamente una referencia en un mapa no guardado. (GUIDES-47467)
- Los términos alfanuméricos agregados al diccionario siguen marcados por el corrector ortográfico de AEM en lugar de ignorarse. (GUIDES-48587)
- Al alternar el enfoque entre los campos **Width** y **Height** del cuadro de diálogo de propiedades de la imagen con tamaños basados en unidades como `in`, `mm` o `px`, los valores siguen aumentando gradualmente en lugar de permanecer estables. (GUIDES-45929)

## Editor 2.0

- Espacio en blanco introducido inmediatamente antes de que se elimine una etiqueta en línea dentro de una celda de tabla `<entry>`. (GUIDES-49144)
- Al insertar un elemento en la posición `tgroup`, se muestra una advertencia **#text no se permite aquí**, lo que impide que se inserte una tabla normal en esa posición. (GUIDES-47446)
- Al copiar una tabla de una hoja de cálculo de Excel y pegarla en el nuevo editor, todo el contenido de las celdas copiadas se coloca en una sola celda de tabla en lugar de distribuirse entre las celdas correspondientes. (GUIDES-47435)
- Un botón **Exportar como PDF** personalizado configurado a través de `editor_toolbar.json` se procesa y se puede hacer clic en él en el modo de vista previa, pero no realiza ninguna acción cuando se hace clic en él. (GUIDES-47402)
- Al abrir ciertos temas que contienen tablas, se agrega una etiqueta `<foreign>` inesperada con dos columnas nuevas, incluso cuando no se realizaron cambios en el tema. (GUIDES-46748)
- Cuando una ecuación de MathML se inserta como `conref`, no se representa correctamente. (GUIDES-46601)
- Los elementos de MathML y SVG no representan su conjunto completo de atributos, lo que provoca que las clases CSS personalizadas y los atributos condicionales aplicados a estos elementos se rompan. (GUIDES-46371)
- El atributo **Scale** no se aplica a las imágenes en la vista Autor. (GUIDES-45996)
- Al aplicar un atributo `scale` a una tabla, la tabla no se representa con el tamaño configurado en los modos Autor y Vista previa. (GUIDES-45984)
- Al pegar imágenes copiadas de fuentes externas como Paint o la Herramienta de recorte, no se inserta la imagen en el tema. (GUIDES-45983)
- Si se copia y pega `<keywords>` dentro de `<topicmeta>` dentro de `<keydef>` o `<topicref>`, las palabras clave se insertan dentro de etiquetas externas no deseadas. (GUIDES-45800)
- En la Vista de etiquetas de una tabla, al pulsar la tecla de flecha hacia arriba cuando el cursor se coloca en la celda directamente debajo de una etiqueta de entrada contraída, se omite la etiqueta contraída y el cursor se mueve al principio del documento. (GUIDES-45408)
- Al realizar cualquier operación desde la barra de herramientas contextual de la tabla, se cierra la barra de herramientas inesperadamente, interrumpiendo las siguientes operaciones de la tabla. (GUIDES-45405)
- La opción **Editar MathML** se muestra incorrectamente en modo de solo lectura o cuando otro usuario desprotege un archivo, lo que permite a los usuarios actualizar el contenido de MathML aunque el archivo no deba poder editarse. (GUIDES-45172)
- Después de usar **Insertar después** o **Insertar antes** desde la vista Esquema o ruta de exploración, el cursor se mueve a una posición arbitraria en lugar de dentro de la etiqueta recién agregada. (GUIDES-45147)
- Al arrastrar y soltar con la Vista de etiquetas habilitada, la selección de contenido junto con etiquetas XML o DITA parciales deja etiquetas huérfanas no deseadas, lo que da como resultado contenido o vista incorrectos. (GUIDES-28191)

## Administración de recursos

- La utilidad de depuración de versiones no se completa en varios casos, incluidos algunos tipos de archivo, recursos a los que les faltan metadatos e informes grandes, en lugar de completar la depuración y generar un informe preciso. (GUIDES-43453)

## Publicación

- Los nombres de archivo que no sean ingleses en los nombres de página generados se sustituyen por guiones, lo que dificulta la identificación del tema o archivo con el que está asociado al publicar la salida de AEM Sites mediante la asignación de componentes heredados. (GUIDES-48387)
- Se han identificado los JAR `jackson-databind` vulnerables (versión 2.9.8) agrupados con AEM Guides en el paquete DITA-OT. (GUIDES-43081)

## Revisión

- Al abrir la vista **en paralelo** en el panel Comentarios, se muestra la copia de trabajo junto a la versión comentada, pero los paneles no se desplazan en sincronización horizontal y al hacer clic en un comentario no se mueve el cursor al texto correspondiente. (GUIDES-44083)

## Plataforma

- Si se usa `scope="external"` para una referencia al contenido de DAM dentro de un tema o asignación, la ruta relativa del recurso se sustituirá con un GUID. (GUIDES-35605)
- Para el contenido creado antes de la migración UUID, al descargar un mapa con las opciones **Conservar jerarquía de archivos** y **Usar nombre de archivo real** seleccionadas incorrectamente, se convierten los valores `href` de los elementos `topicref`, `xref` y `conref` con `scope="external"` a nombres de archivo basados en GUID en lugar de conservar las rutas de archivo relativas originales. Como resultado, las referencias externas se rompen. (GUIDES-46526)
- Al cargar recursos a través de la interfaz de usuario de Assets, no se muestra el estado de carga. (GUIDES-7207)

## Problemas conocidos

- Al realizar una operación de revisión dentro de un bloque de código, se muestra una advertencia **Operación no permitida** en el primer intento, pero la operación se realiza correctamente cuando se repite. (GUIDES-56749)
- Cuando se crea una tarea de revisión para el contenido que contiene `code block`, el formato de tachado no se aplica correctamente después de la importación y el contenido resaltado no aparece en la vista de comparación en paralelo. (GUIDES-56811)
- En algunos casos, la ficha **Lista de temas** del panel Informes no muestra ningún resultado, incluso cuando el mapa contiene varios temas. (GUIDES-56893) <br> **Solución alternativa:** Vuelva a indexar el contenido afectado para reconstruir las relaciones de asignación principal. Los temas se muestran en la pestaña Lista de temas según lo esperado.
- Al seleccionar un elemento de instrucción de procesamiento en la vista Esquema, se resalta toda la etiqueta principal en lugar del elemento seleccionado. (GUIDES-48318)
- Al realizar operaciones de eliminación, pueden producirse algunas incoherencias menores en el movimiento y la navegación del cursor en los mapas de imagen, los elementos estructurados, las etiquetas de formato en línea y los bloques no combinables, lo que a veces provoca un comportamiento inesperado del cursor o la eliminación. (GUIDES-46756)
- Una ecuación de MathML incluida en un bloque `foreign` y `equation` genera un espaciado no deseado, y escribir dentro de la ecuación causa problemas incluso después de ajustar la sangría. (GUIDES-46606)
- No se puede colocar un cursor dentro de un(a) `topicref` dentro de un(a) `reltable` cuando la opción **Mostrar etiquetas** está habilitada y la opción **Mostrar atributos** está deshabilitada en la configuración del Editor. (GUIDES-46565)
- Si presiona la barra espaciadora al principio de un párrafo inmediatamente después del contenido de solo lectura (como un párrafo de referencia), puede eliminar o combinar inesperadamente el párrafo editable, lo que provoca la eliminación inesperada del párrafo editable. (GUIDES-45049)
- Cuando se cambia el nombre de una etiqueta en línea mediante la opción Cambiar nombre de elemento, la ruta de exploración no se actualiza inmediatamente y refleja el cambio solo después de que el cursor se mueva a la etiqueta o de que se cambie el modo de vista. (GUIDES-44993)<br>**Solución alternativa:** Actualice el explorador después de cambiar el nombre de la etiqueta en línea para actualizar la ruta de exploración.
- Cuando se aplican indicadores de condición a elementos como bodydiv, los indicadores se desbordan hasta las etiquetas adyacentes en la vista de etiquetas completas, lo que da como resultado una representación visual incorrecta. (GUIDES-44971)

