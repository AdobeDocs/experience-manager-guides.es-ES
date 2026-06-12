---
title: Notas de versión | Se han corregido problemas en la versión 2025.11.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2025.11.0 de Adobe Experience Manager Guides as a Cloud Service.
exl-id: a86621c3-c4e1-4538-8700-dd9c22be440f
TQID: https://experienceleague.adobe.com/VSfdJPL26DZFuIyfEcTk2eGjCSbJ5JY4f5B-W63lkjI
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: c38bc65b-dea9-4a6e-9de3-3daf1d2b388b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 699
ht-degree: 3%

---

# Se han corregido problemas en la versión 2025.11.0

Este artículo cubre los errores corregidos en varias áreas de la versión 2025.11.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 2025.11.0](whats-new-2025-11-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2025.11.0](upgrade-instructions-2025-11-0.md).

## Creación

- Si se agrega un elemento `prop` vacío sin atributos ni valores a un archivo DITAVAL, no se podrán agregar elementos `prop` adicionales. (GUIDES-33597)
- Después de actualizar Experience Manager Guides a la versión 2025.08.0, la opción de habilitar o deshabilitar la ficha **Acrolinx** personalizada ya no aparece en **Configuración de Workspace**. (GUIDES-35261)
- CSS personalizado aplicado en un perfil de nivel de carpeta para temas o asignaciones se revierte al estilo predeterminado en el modo de Vista previa al actualizar el explorador. (GUIDES-31098)
- Las operaciones **Deshacer** y **Rehacer** no funcionan según lo esperado en la vista Source del Editor para archivos DITA. (GUIDES-24914, GUIDES-25034)
- Al hacer referencia a un mapa DITA en un tema utilizando el elemento `Xref`, se muestra el nombre de archivo del mapa al que se hace referencia en lugar del título del mapa. (GUIDES-21759)
- Al agregar varios archivos de Schematron para su validación a través del panel derecho de la interfaz del Editor, se muestra un error **Los archivos de Schematron no existen o tienen errores** aunque los archivos agregados sean válidos y no tengan errores. (GUIDES-33731)
- Las ecuaciones de MathML grandes o complejas no se muestran en el Editor. (GUIDES-29095)

## Administración de recursos

- Cuando se vuelve a cargar una imagen editada a través de la interfaz de usuario de Experience Manager Guides, la representación original de la imagen se actualiza, pero el contenido DITA asociado sigue mostrando la versión anterior de la imagen. (GUIDES-33693)
- Al intentar mover dos o más carpetas desde su ubicación de origen a una ubicación diferente (mediante la herramienta de movimiento masivo), la operación falla si los nombres de las carpetas comienzan con la misma cadena (por ejemplo, Product y ProductImages). (GUIDES-29096)
- Al eliminar un recurso buscado de la interfaz de usuario de Omnisearch Assets, se omite el cuadro de diálogo de advertencia **Forzar eliminación** y se elimina directamente el recurso, incluso cuando se hace referencia a él en el contenido DITA existente. (GUIDES-17232)

## Publicación

- Al publicar un mapa DITA con línea de base en AEM Sites (con asignación de componentes heredados), los elementos de mapa con el atributo `processing-role = resource-only` también se publican. (GUIDES-37649)
- En algunos casos, la propiedad `jcr:content/fmUuidOfSource` se encuentra sin aparecer en las páginas de salida de AEM Sites (con asignación de componentes heredados), lo que hace que las páginas de contenido recién creadas no se puedan detectar.
- El filtrado de contenido mediante filtros DITAVal y ajustes preestablecidos condicionales no funciona para la publicación en Salesforce. (GUIDES-33515)
- No se puede crear un ajuste preestablecido de PDF nativo para un mapa si existe una carpeta con el mismo nombre en su jerarquía de contenido. (GUIDES-33012)
- Cuando la salida de PDF nativa se genera usando una línea de base dinámica, el término **PDFProject** se muestra como el título de PDF en lugar del título real del mapa. (GUIDES-31102)
- La generación de resultados nativos de PDF con ciertos valores de atributo `print` en las referencias de temas no funciona como se esperaba. (GUIDES-31101)
- Cuando se mueve una carpeta que contiene asignaciones DITA mediante la interfaz de usuario de Assets o la opción **Mover masivamente**, las colecciones de asignaciones existentes y las colecciones de activación masiva que hacen referencia a esas asignaciones no se cargan. (GUIDES-28355)
- Cuando se mueve una carpeta que contiene un mapa con ajustes preestablecidos de condición, las condiciones no se aplican en la salida generada después del movimiento. (GUIDES-28352)
- Cuando se genera la salida de AEM Sites mediante la asignación de componentes heredados, los temas que utilizan el atributo `copy-to` se publican con el nombre del tema `copy-from` en lugar del nombre establecido en el atributo `copy-to`. (GUIDES-22155)
- La activación de una o más asignaciones DITA desde **tablero de publicación en lotes** genera registros excesivamente grandes. (GUIDES-20746)

## Plataforma

- Registros de errores que se generan al cargar un recurso a través de la interfaz de usuario de Assets o al crear un nuevo archivo desde la interfaz del editor; utilice incorrectamente el término `predecessor` en lugar de `successor` en el mensaje de registro. (GUIDES-35607)

## Problemas conocidos

Adobe ha identificado los siguientes problemas conocidos para la versión 2025.11.0:

- La creación de un tema duplicado con el atributo `copy-to` y su referencia con el atributo `scope=peer` provoca problemas de redirección en la salida de AEM Sites, donde los vínculos se redirigen desde AEM Sites (con asignación de componentes compuestos) a AEM Sites (con asignación de componentes heredados) y viceversa. (GUIDES-37656)
