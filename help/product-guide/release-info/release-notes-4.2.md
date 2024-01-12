---
title: Notas de versión | Versión 4.2 de las guías de Adobe Experience Manager
description: Obtenga información acerca de las correcciones de errores y cómo actualizar a las versiones 4.2 de las guías de Adobe Experience Manager
exl-id: 8a7fef77-63af-462f-89c5-054ab31e079b
feature: Release Notes
role: Leader
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1391'
ht-degree: 1%

---

# Versión 4.2 de las guías de Adobe Experience Manager (febrero de 2023)

Esta nota de la versión cubre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en la versión 4.2 de las guías de Adobe Experience Manager (más adelante referida como *AEM Guías de*).

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 4.2 de las guías de Adobe Experience Manager](whats-new-4.2-release.md).

## AEM Actualice a la versión 4.2 de las guías de la

AEM Puede actualizar fácilmente su versión actual de Guías de la a la versión 4.2. AEM Antes de continuar con la actualización a la versión 4.2 de las guías del usuario, debe tener en cuenta los siguientes puntos:
* Si utiliza las versiones 4.0, 4.1 o 4.1.x, puede actualizar directamente a la versión 4.2.
* Si utiliza la versión 3.8.5, debe actualizar a la versión 4.0 antes de actualizar a la versión 4.2.
* Si su versión es anterior a la 3.8.5, consulte la *AEM Guías de actualización* de la guía de instalación específica del producto.

>[!NOTE]
>
>AEM AEM Debe instalar el paquete de servicio de antes de actualizar la versión de las guías de usuario.

Para obtener más información, consulte [Instrucciones de actualización](assets/Adobe-Experience-Manager-Guides-Upgrade-Instructions-EN.pdf).

## Matriz de compatibilidad

AEM En esta sección se enumera la matriz de compatibilidad para las aplicaciones de software compatibles con la versión 4.2 de las Guías de la aplicación para la administración de aplicaciones (Guides).

### Adobe Experience Manager

**No UUID**
Paquete de servicio 15, 14, 13 o 12 de la versión 6.5

**UUID**
Paquete de servicio 15, 14, 13 o 12 de la versión 6.5

Para obtener más información, consulte la *Requisitos técnicos* de la guía Instalar y configurar guías de Adobe Experience Manager.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.2 (no UUID) | 2022 o superior | 2020.2 o superior* | 2022 o superior | 2020.3 o superior |
| 4.2 (UUID) | 2022 o superior | 2020.2 o superior* | 2022 o superior | 2020.4 o superior |
| | | | |

AEM *La línea de base y las condiciones creadas en la versión de FMPS a partir de 2020.2 son compatibles con las versiones de FMPS.

### Conector de oxígeno

| Versión | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.2 (no UUID) | 2.1-regular-4 | 2.1-regular-4 | 1,6 | 1,6 |
| 4.2 (UUID) | 2.8-uuid-8 | 2.8-uuid-8 | 2,3 | 2,3 |
|  |  |   |

## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

### Creación

* El panel izquierdo se rompe al añadir una pestaña. (11126)
* Los cambios en el HTML del editor web causan problemas con `<dl>` y `<dlentry>`. (11024)
* Algunos atributos no se tratan como condicionales y causan problemas. (10895)
* Tres niveles o más anidados `<indexterm>` no están anidadas en la exportación de PDF nativa. (10799)
* El contenido desaparece en el cuerpo de una tarea al cambiar de la vista Autor a Fuente. (10735)
* Los comentarios de revisión no se colocan correctamente en una tarea de revisión. (10625)
* `<conref>` una nota dentro de una etiqueta para no se muestra en el modo de vista previa. (10559)
* Al pulsar Retroceso al final de un elemento de la lista, se elimina toda la lista. (10540)
* La pantalla se muestra en blanco en Chrome v106 al arrastrar y soltar cualquier elemento de la interfaz de usuario (por ejemplo, del panel Condiciones ). (10524)
* Falta el botón Sangría automática en la barra de herramientas de **Origen** vista. (10448)
* El primer carácter de un elemento de lista se pierde a veces cuando la lista se crea en el editor.( 10447)
* **Deshacer** o **Rehacer** no funciona correctamente en algunos archivos. (10373)
* Los metadatos personalizados no se conservan en la acción de copiar y pegar. (10367)
* Se produce un error al realizar una copia (ctrl+c) y pegar (ctrl+v) del contenido. (10304)
* El panel Esquema no muestra contenido cuando se cambia del modo Autor al Modo Origen. (10296)
* El submapa no se crea cuando hace referencia a un mapa principal en las plantillas DITA. (10231)
* Los problemas de navegación se producen en el Editor Web después de la actualización 4.0. (10159)
* La opción Deshacer del Editor XML lleva al usuario al principio de la página. (10091)
* Las propiedades del nodo se eliminan después de la operación de copiar y pegar de un recurso. (10053)
* Los ficheros de SVG añadidos a los temas DITA no se muestran en el modo de vista previa del editor. (10010)
* Los resultados de búsqueda para buscar y reemplazar dentro del Editor Web no se pueden leer en el modo Oscuro. (9978)
* No existe ningún cargador al crear un mapa a partir de la plantilla de mapa. (9891)
* La referencia en la plantilla de tema no funciona y el ID de hash copiado no se actualiza en la copia de contenido. (9890)
* No se muestra ninguna opción para examinar los temas o la plantilla de asignación dentro de las subcarpetas del tema o la carpeta de asignación. (9889)
* No hay opción para crear una nueva plantilla en las subcarpetas de temas o mapas. (9888)
* El Editor XML no actualiza las imágenes de los temas. (9500)
* mimeType está codificado para la creación y actualización de recursos DITA. (8979)
* Se inserta un guión normal al seleccionar Guión de no separación en la **Insertar carácter especial** diálogo. (8919)
* El nombre del creador de la versión en el Historial de versiones es &quot;fmdita-serviceuser&quot; para los archivos cargados mediante la interfaz de usuario de Assets. (8910)
* La opción Editar no funciona para imágenes mientras se trabaja en la vista de columna de la interfaz de usuario de Recursos. (8758)
* El tema DITA no se actualiza automáticamente con los cambios realizados en **Propiedades** página. (8745)
* Al mover elementos dentro del tema en el editor web, los ID asignados en los elementos se sobrescriben con los ID asignados automáticamente. (7895)

### Administración

* La copia de un recurso de mapa DITA (desde la IU de recursos ) provoca líneas de base erróneas en el recurso copiado. (11218)
* AEM El mensaje de advertencia no se muestra en la carga de un archivo que supere el límite permitido en el (2 GB de forma predeterminada). (10817)
* Editor web: línea de base | El comportamiento de la columna Última es diferente en el nuevo tablero de línea de base dentro del Editor Web. (10808)
* Traducción | El trabajo de traducción no se ha iniciado debido a un /libs/fmdita/i18n/ja.json no válido. (10543)
* Traducción | Se produce un error en un proyecto de traducción de ámbito creado desde el panel de traducción (traducción humana). (10526)
* Traducción | El procesamiento posterior se bloquea para toda la carpeta de idioma cuyos recursos estén presentes en un proyecto de traducción activo. (10332)
* Traducción| Los metadatos y las etiquetas no se propagan a las copias traducidas. (4696)
* Aparecen varias ventanas emergentes para cualquier recurso si se cambia la versión y se guarda en el Editor de líneas de base. (10399)
* La pérdida de sesión se produce en com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210). (10279)
* El archivo de vídeo no aparece en la línea de base si la carpeta principal contiene espacio en el nombre. (10031)

### Publicación

* La regeneración de temas no funciona para algunos escenarios. (10635)
* La publicación del PDF no consigue generar la salida para un ajuste preestablecido duplicado (de un ajuste preestablecido existente). (10584)
* El botón Ver registro no funciona en caso de que falle la generación del PDF para un ajuste preestablecido. (10576)
* Publishlistener no muestra los datos solicitados en los registros de información y también contiene algunos registros no deseados.( 10567)
* PDF nativo | La generación del PDF falla con una excepción de puntero nulo. (10950)
* PDF nativo | conkeyref no se está resolviendo en la salida generada. (10564)
* PDF nativo | Se producen problemas con los metadatos de un mapa al que hay que hacer referencia en la salida del PDF.( 10556)
* PDF nativo | Se producen problemas al girar el encabezado de Tabla. (10555)
* PDF nativo | Se producen problemas al eliminar temas que tienen un rol de procesamiento=&#39;resource-only&#39;. (10554)
* PDF nativo | Las referencias clave vacías se muestran en la salida del PDF. (10553)
* PDF nativo | Anidado `<indexterm>` no están anidadas en la exportación de PDF nativa. (10521)
* PDF nativo | El PDF nativo utiliza un estilo en línea en lugar del nombre de clase para las etiquetas generadas. (10498)
* PDF nativo | Todos los temas anidados en los apéndices se transforman en h1 en el HTML temporal.( 10454)
* PDF nativo | No se pueden ocultar los temas de front-matter de la tabla de contenido. (10355)
* PDF nativo | Atributo de marco de tabla no propagado al HTML temporal (como clase). (10353)
* PDF nativo | Los archivos temporales del HTML agregan las clases colsep y rowsep a <td> y <th> incluso si su valor es 0 en el DITA de origen. (10352)
* PDF nativo | Al reiniciar los números de página en el diseño del capítulo, se inicia aleatoriamente la numeración desde el final del capítulo anterior. (10154)
* PDF nativo | Las referencias clave para los keydefs con vínculos de imagen o externos no se resuelven. (10063)
* PDF nativo | El apéndice se muestra como un capítulo en el PDF generado. (9829)
* La pestaña Plantilla del editor xml no se muestra a los administradores de perfil de carpeta. (10266)
* La publicación de línea de base falla en el PDF generado mediante FrameMaker Publishing Server 2020. (10551)
* Error de aplicación al hacer clic en el botón Editar después de seleccionar todos los ajustes preestablecidos mediante la casilla de verificación Ajustes preestablecidos de salida en la ventana emergente Generación rápida. (10388)
* Si la pestaña Salida del editor web tiene más ajustes preestablecidos, la sección de ajustes preestablecidos no se puede desplazar verticalmente y no muestra todos los ajustes preestablecidos disponibles. (9787)
* No se pueden eliminar los ajustes preestablecidos del flujo de trabajo de salida al publicar mediante el editor. (9100)
* El vínculo de igual a igual se representa como texto normal en lugar de como vínculo en la página generada. (7774)

## Problema conocido

El Adobe AEM de ha identificado el siguiente problema conocido de la versión 4.2 de las Guías de usuario de:

* Los usuarios pueden realizar operaciones de revisión incluso después de completar la tarea de revisión.
