---
title: Notas de versión | Novedades de la versión 2025.04.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las funciones nuevas y mejoradas de la versión 2025.04.0 de Adobe Experience Manager Guides
role: Leader
exl-id: 5d28119b-641f-402b-833c-6f7554e7c273
source-git-commit: fe7d81f1826fe4ee0c716df36daabe3c5efd8994
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 3%

---

# Novedades de la versión 2025.04.0 (abril de 2025)

Este artículo cubre las funciones nuevas y mejoradas introducidas con la versión 2025.04.0 de Adobe Experience Manager Guides as a Cloud Service.

Para ver la lista de problemas corregidos en esta versión, consulte [Problemas solucionados en la versión 2025.04.0](fixed-issues-2025-04-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2025.04.0](../release-info/upgrade-instructions-2025-04-0.md).

## Atributo &quot;Format&quot; añadido para vínculos de referencia

Adobe Experience Manager Guides ahora agrega un atributo **format** para los vínculos de referencia dentro del Editor. Este atributo se muestra en la **vista de Source** e indica claramente el tipo de archivo, como:

- Para los archivos con una extensión **.pdf**, el formato se establecerá en **pdf**
- Para los archivos con una extensión **.html**, el formato se establecerá en **html**
- Para los archivos con **.dita** o **.ditamap**, el formato se establecerá en **dita**

Además, los archivos con una extensión **.xml** también tendrán el formato establecido en **dita**. Para los archivos sin extensión, el formato se deja en blanco. Además, para cualquier vínculo de referencia con un ámbito establecido en **external**, el formato se establecerá en **html** independientemente de la extensión de archivo de los vínculos de referencia.

## La línea base exportada ahora incluye el estado del documento

La característica Exportar línea de base ahora incluye el **estado del documento** junto con detalles clave como el título, el nombre de archivo, el tipo de archivo y el número de versión en la instantánea de línea de base. Esta mejora mejora la gestión de la línea de base al proporcionar una visión general más completa de la línea de base.

Para obtener más información, vea [Crear y administrar líneas de base desde la consola de mapas](../user-guide/web-editor-baseline.md#manage-baselines).

## Experiencia de búsqueda mejorada para el panel de contenido reutilizable

Experience Manager Guides presenta una experiencia de búsqueda mejorada en el panel Contenido reutilizable. Con esta actualización, la búsqueda de cualquier palabra clave ahora analiza todos los archivos añadidos como contenido reutilizable, y no solo los abiertos, lo que garantiza que encuentre la posición exacta de la palabra clave en todas las ocurrencias, ya sean contenedores abiertos o contraídos. Además, cuando borra la barra de búsqueda, se conserva el estado original de todos los contenedores, lo que proporciona una funcionalidad de búsqueda más eficiente y fácil de usar.

Para obtener más información, vea [Contenido reutilizable](../user-guide/web-editor-features.md#reusable-content).


## Actualización de la versión de Java para contenedores de microservicio

En el caso de entornos de nube habilitados para microservicios, realizaremos la transición a Java 21, lo que garantiza que los procesos de generación DITA-OT y PDF nativos existentes no se vean afectados. El flujo de trabajo existente de DITA-OT 3 seguirá funcionando perfectamente con Java 21.  Además, DITA-OT 4 estará completamente operativo, lo que permitirá a los usuarios generar PDF utilizando DITA-OT y PDF nativo, así como producir salidas para sitios de AEM nativos y otros formatos.
