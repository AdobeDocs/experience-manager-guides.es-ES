---
title: Notas de versión | Se han corregido problemas en las guías de Adobe Experience Manager, versión 2024.06.0
description: Obtenga información acerca de las correcciones de errores en la versión 2024.06.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: dff625a841ea9fc758de83b1d830ddffa15646cd
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 3%

---


# Se han corregido problemas en la versión 2024.06.0

Este artículo cubre los errores corregidos en varias áreas de la versión 2024.06.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 2024.06.0](whats-new-2024-06-0.md).

Más información [instrucciones de actualización para la versión 2024.06.0](upgrade-instructions-2024-06-0.md).

## Creación

- La operación de copiar y pegar de temas que superan los 15 KB falla con un error inesperado. (17171)
- La funcionalidad para cambiar el estado del documento de la  **Propiedades de archivo** el panel no funciona correctamente y cambia al *Borrador* estado. (17088)
- Al cambiar la configuración del editor XML mediante un perfil de carpeta personalizado, la variable `ui_config.json` se actualiza con un archivo incorrecto. (17011)
- En el **Repositorio** , el panel **Filtrar** la búsqueda no conserva el valor de **Extraído por** al volver a abrir el **Filtro avanzado** Cuadro de diálogo. (16935)
- Las imágenes vinculadas de los temas no aparecen en la línea de base después de la creación de la versión. (16931)
- Los paneles de contenido reutilizables no enumeran los elementos cuando la variable **Preferencias de usuario** están configurados para ver archivos por **Nombre de archivo**. (16896)
- Los subelementos dentro del elemento de título de tabla no se pueden procesar en la **Previsualizar** modo de las Guías del Experience Manager. (16691)
- La ejecución del script posterior al proceso falla debido a **FileNotFoundException** excepción. (16517)
- Los vídeos de Vimeo no admiten la funcionalidad de pantalla completa en las guías del Experience Manager. (15996)
- Pegar secuencias de texto con formato previo largas en `<pre>` o `<codeblock>` lleva a texto truncado. (15859)
- La eliminación de contenido se produce debido a GUID duplicados cuando las plantillas se instalan mediante código pero no se procesan. (15858)
- Las guías del Experience Manager no respetan las **Procesando rol** atributo en **Previsualizar** modo. (15787)
- El editor elimina intermitentemente el texto adicional que hay más allá del área seleccionada.  (15708)
- Imposibilidad de copiar y pegar tablas grandes de documentos o HTML de Word en el Editor Web. (15369)
- El **Copiar** falla para carpetas vacías en las guías del Experience Manager as a Cloud Service. (15353)
- Falta de API o eventos para capturar la adición de atributos a un elemento o la inserción de un nuevo elemento. (15351)
- Incapacidad para agregar `<data>` etiqueta dentro de `<ol>` en el editor web. (15161)
- Cuando Unified Shell está habilitado, la variable **Administración de etiquetas de versión** el cuadro de diálogo aparece incorrectamente **Contenido principal** para versiones sin etiquetas. (15039)
- Los archivos grandes se cargan lentamente en el Editor Web, con un retraso de unos segundos. (14958)
- Pulsando el botón **Entrar** La tecla en una celda de tabla dentro del texto no divide el párrafo como se espera. (14251)
- La Guía DITA del Experience Manager no almacena en déclencheur el **Guardar** después de utilizar la función de sangría automática. (16482)
- Los temas de la revisión no aparecen en el orden correcto. (16319)
- En el **Autor** En la vista de, se produce un problema de copiar y pegar al utilizar espacios sin saltos, que provoca el desbordamiento del texto. (15541)

- Entrada `<othermeta>` elemento dentro de `<topicmeta>`, al añadir un `<conref>`a otro mapa DITA, el ID de mapa también se anexa junto con el ID del elemento. (15226)
- El `<conref>` no se puede actualizar desde el **Atributos** panel al realizar cambios. (15209)
- Al seleccionar una imagen dentro de una celda de tabla, se selecciona toda la celda. (15188)

## Publicación


- La vinculación entre mapas cruzados no puede mostrar todas las asignaciones principales en la configuración del contexto de publicación para un vínculo que tiene la variable `peer @scope`. (16700)
- Al añadir nuevos atributos o eliminar los existentes, los antiguos se conservan en la variable **Ajustes preestablecidos**. (15890)
- El contenido de idioma RTL no se gestiona correctamente en la salida de publicación del PDF nativo. (15709)
- El primer PDF no tiene versiones cuando se genera una salida de PDF nativo. (10305)
- En el PDF nativo, los temas DITA anidados se muestran incorrectamente en la tabla de contenido (TOC). (16742)
- Las miniaturas generadas desde Dynamic Media para archivos de vídeo no se conservan en la salida publicada. (15656)
- La generación de salida falla al publicar el PDF nativo en un procesador ARM64. (16968)

## Administración

- La edición de una instantánea existente y la selección de una versión específica déclencheur errores de aplicación. (14451)

## Traducción

- Los proyectos de traducción no agregan nuevos trabajos de idioma a Adobe Experience Manager 6.5 SP18 con la versión de octubre de 2023 de Guías del Experience Manager. (15398)

## Cloud Service

- La navegación de las herramientas de Adobe Experience Manager no responde. (17118)
- La fase de transformación de compilación en la implementación de Cloud Service falla con errores del código base de DITA. (14432)

## Informes

- Lo impreciso **Lista de temas** Los recuentos en la IU de Guías del Experience Manager de debido a propiedades sin parches al copiar recursos DITA afectan a los informes generados para un mapa DITA. (15529)
- Temas que contienen referencias externas con *%20* en la URL muestran referencias de archivos rotos. (15347)


## Problemas conocidos

El Adobe ha identificado los siguientes problemas conocidos para la versión 2024.06.0:

- La publicación del PDF nativo falla cuando se agrega contenido de Vimeo al tema.
- El **Propiedades del tema** no se muestran según el formato seleccionado en los campos de metadatos de un diseño de página.
- `xrefs` no se pueden seleccionar en **Assets** ver cuándo está habilitado Dynamic Media.
