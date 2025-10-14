---
title: Notas de versión | Novedades de la versión 2025.10.0 de Adobe Experience Manager Guides
description: Obtenga información sobre las funciones nuevas y mejoradas de la versión 2025.10.0 de Adobe Experience Manager Guides
role: Leader
source-git-commit: f9b879d6d374334a08a1d3b0a47b0cb419f02140
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 3%

---

# Novedades de la versión 2025.10.0 (octubre de 2025)

Este artículo cubre las funciones nuevas y mejoradas introducidas con la versión 2025.10.0 de Adobe Experience Manager Guides as a Cloud Service.

Para ver la lista de problemas corregidos en esta versión, consulte [Problemas solucionados en la versión 2025.10.0](fixed-issues-2025-10-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2025.10.0](../release-info/upgrade-instructions-2025-10-0.md).


## Ahora, el nombre de la configuración del editor se ha cambiado a configuración de Workspace y se puede acceder a ella desde la página principal

Para mejorar la navegación y la facilidad de uso, se han introducido las siguientes mejoras:

- Se cambió el nombre de la **configuración del editor** en Experience Manager Guides a **configuración de Workspace**.
- Ahora se puede acceder al menú **Más acciones** (el menú de tres puntos), que antes solo estaba disponible en la interfaz de la consola Editor y Mapa, desde la [Página principal](../user-guide/intro-home-page.md).

  ![](assets/workspace-settings.png)

## Identifique y corrija fácilmente los ID duplicados en los temas y asignaciones de la vista Autor

Experience Manager Guides ahora incluye un botón **ID duplicados** en el editor para ayudarle a identificar y corregir rápidamente los ID duplicados presentes en un solo tema o asignación. Cuando se detectan ID duplicados, este botón aparece en la esquina inferior izquierda de la interfaz del editor en la vista **Autor**. Al seleccionar el botón, se muestra en una ventana emergente una lista de todas las instancias con ID duplicados. Al seleccionar una instancia, se resalta el contenido correspondiente del tema o asignación, lo que permite localizar y corregir los ID duplicados desde el panel derecho.

Para obtener más información, vea [Características adicionales en el editor](../user-guide/web-editor-other-features.md).

![](assets/duplicate-element-IDs.png){width="350" align="left"}

## Mejoras en los filtros Repositorio e Informes

El filtro **Bloqueado por** en Filtros avanzados en el repositorio y el filtro **Autor** en los informes de mapas DITA ahora cargan listas de usuarios gradualmente a medida que se desplaza, en lugar de todos a la vez. Esta carga paginada mejora la velocidad y hace que trabajar con conjuntos de datos de usuario grandes sea más eficiente y fluido.

## Acceder al estado de las tareas de revisión directamente desde el panel Revisar

Como iniciador de una tarea de revisión, ahora puede comprobar el estado de la tarea de revisión directamente desde el panel Revisar. Con las mejoras más recientes, el cuadro de diálogo **Actualizar tarea** del panel Revisar incluye una nueva opción **Comprobar estado de revisión**. Al seleccionar esta opción, accederá directamente al panel de revisión, donde podrá ver el estado de las tareas de cada revisor, lo que permitirá acceder más rápidamente al progreso de las tareas sin necesidad de cambiar de contexto.

Para obtener más información, vea [Solicitar una nueva revisión o cerrar una tarea de revisión como autor](../user-guide/review-close-review-task.md).

![](assets/check-review-status-icon.png){width="350" align="left"}



## API para rastrear el estado posterior al procesamiento de carpetas o recursos

Ahora hay disponible una nueva API para rastrear el estado posterior al procesamiento de recursos y carpetas individuales. Esto resulta especialmente útil en equipos que utilizan flujos de trabajo automatizados, donde la publicación solo debe producirse después de que el contenido se haya procesado por completo. La API ofrece una forma fiable de confirmar la preparación, lo que reduce el riesgo de errores de publicación causados por un procesamiento incompleto.

Para obtener más información, consulte la [API para rastrear el estado posterior al procesamiento de carpetas o recursos](../api-reference/track-post-processing-status.md).

