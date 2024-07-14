---
title: Notas de versión | Se han corregido problemas en la versión 2024.06.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2024.06.0 de Adobe Experience Manager Guides as a Cloud Service.
exl-id: 608e5b2c-72af-4498-9b63-935e698231d4
source-git-commit: d525775afeeb89754762ff514126b1c3a3307b3f
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 3%

---

# Se han corregido problemas en la versión 2024.06.0

Este artículo cubre los errores corregidos en varias áreas de la versión 2024.06.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 2024.06.0](whats-new-2024-06-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2024.06.0](upgrade-instructions-2024-06-0.md).

## Creación

- La operación de copiar y pegar de temas que superan los 15 KB falla con un error inesperado. (17171)
- La funcionalidad para cambiar el estado del documento desde el panel **Propiedades del archivo** no funciona correctamente y cambia al estado *Borrador*. (17088)
- Al cambiar la configuración del editor XML mediante un perfil de carpeta personalizado, `ui_config.json` se actualiza con un archivo incorrecto. (17011)
- En el panel **Repositorio**, la búsqueda **Filtro** no conserva el valor del campo **Desprotegido por** al volver a abrir el cuadro de diálogo **Filtro avanzado**. (16935)
- Las imágenes vinculadas de los temas no aparecen en la línea de base después de la creación de la versión. (16931)
- Los paneles de contenido reutilizables no muestran elementos cuando las **preferencias de usuario** están configuradas para ver archivos por **Filename**. (16896)
- Los subelementos dentro del elemento de título de tabla no se pueden procesar en el modo **Preview** de Experience Manager Guides. (16691)
- La ejecución del script posterior al proceso falla debido a la excepción **FileNotFoundException**. (16517)
- Los vídeos de Vimeo no admiten la funcionalidad de pantalla completa en Experience Manager Guides. (15996)
- Al pegar secuencias de texto con formato previo largas en elementos `<pre>` o `<codeblock>`, se trunca el texto. (15859)
- La eliminación de contenido se produce debido a GUID duplicados cuando las plantillas se instalan mediante código pero no se procesan. (15858)
- Experience Manager Guides no puede adherirse al atributo **Rol de procesamiento** en el modo **Vista previa**. (15787)
- El editor elimina intermitentemente el texto adicional que hay más allá del área seleccionada.  (15708)
- Imposibilidad de copiar y pegar tablas grandes de documentos o HTML de Word en el Editor Web. (15369)
- La función **Copiar** produce un error en las carpetas vacías del as a Cloud Service de Experience Manager Guides. (15353)
- Falta de API o eventos para capturar la adición de atributos a un elemento o la inserción de un nuevo elemento. (15351)
- No se puede agregar la etiqueta `<data>` dentro de la etiqueta `<ol>` en el editor web. (15161)
- Cuando Unified Shell está habilitado, el cuadro de diálogo **Administración de etiquetas de versión** muestra incorrectamente **Contenido principal** para las versiones sin etiquetas. (15039)
- Los archivos grandes se cargan lentamente en el Editor Web, con un retraso de unos segundos. (14958)
- Al presionar la tecla **Enter** en una celda de tabla dentro del texto, el párrafo no se divide como se esperaba. (14251)
- La Guía DITA del Experience Manager no puede almacenar en déclencheur la función **Guardar** después de usar la función de sangría automática. (16482)
- Los temas de la revisión no aparecen en el orden correcto. (16319)
- En la vista **Autor**, se produce un problema al copiar y pegar al usar espacios sin saltos, lo que provoca el desbordamiento del texto. (15541)

- En el elemento `<othermeta>` dentro de `<topicmeta>`, al agregar `<conref>` a otro mapa DITA, el identificador de mapa también se anexa junto con el identificador del elemento. (15226)
- `<conref>` no se puede actualizar desde el panel **Atributos** al realizar cambios. (15209)
- Al seleccionar una imagen dentro de una celda de tabla, se selecciona toda la celda. (15188)

## Publicación


- La vinculación entre mapas cruzados no puede mostrar todas las asignaciones principales en la configuración del contexto de publicación de un vínculo que tiene `peer @scope`. (16700)
- Al agregar o quitar atributos nuevos o existentes, los atributos antiguos se conservan en los **ajustes preestablecidos de condición**. (15890)
- El contenido de idioma RTL no se gestiona correctamente en la salida de publicación del PDF nativo. (15709)
- El primer PDF no tiene versiones cuando se genera una salida de PDF nativo. (10305)
- En el PDF nativo, los temas DITA anidados se muestran incorrectamente en la tabla de contenido (TOC). (16742)
- Las miniaturas generadas desde Dynamic Media para archivos de vídeo no se conservan en la salida publicada. (15656)
- La generación de salida falla al publicar el PDF nativo en un procesador ARM64. (16968)

## Administración

- La edición de una instantánea existente y la selección de una versión específica déclencheur errores de aplicación. (14451)

## Traducción

- Los proyectos de traducción no agregan nuevos trabajos de idioma a Adobe Experience Manager 6.5 SP18 con la versión de octubre de 2023 de Experience Manager Guides. (15398)

## Cloud Service

- La navegación de las herramientas de Adobe Experience Manager no responde. (17118)
- La fase de transformación de compilación en la implementación de Cloud Service falla con errores del código base de DITA. (14432)

## Informes

- La **Lista de temas** inexacta cuenta en la IU de Experience Manager Guides debido a propiedades sin aplicar parches al copiar recursos DITA afecta a los informes generados para un mapa DITA. (15529)
- Los temas que contienen referencias externas con *%20* en la dirección URL muestran referencias de archivo rotas. (15347)


## Problemas conocidos

El Adobe ha identificado los siguientes problemas conocidos para la versión 2024.06.0:

- La publicación del PDF nativo falla cuando se agrega contenido de Vimeo al tema.
- Las **propiedades del tema** no se muestran según el formato seleccionado en los campos de metadatos de un diseño de página.
- No se puede hacer clic en `xrefs` en la vista **Assets** cuando Dynamic Media está habilitado.
