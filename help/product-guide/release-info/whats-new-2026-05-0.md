---
title: Notas de versión | Novedades de la versión 2026.05.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las funciones nuevas y mejoradas de la versión 2026.05.0 de Adobe Experience Manager Guides
role: Leader
source-git-commit: 2c9e91a85bb9cfbfec05dbe5c2e9eae9e240d571
workflow-type: tm+mt
source-wordcount: '1031'
ht-degree: 0%

---

# Novedades de la versión 2026.05.0 (mayo de 2026)

Este artículo cubre las funciones nuevas y mejoradas introducidas con la versión 2026.05.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener la lista de problemas corregidos en esta versión, vea [Problemas corregidos en la versión 2026.05.0](fixed-issues-2026-05-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2026.05.0](../release-info/upgrade-instructions-2026-05-0.md).

## Introducción a Editor 2.0

Editor 2.0 (también conocido como Nuevo editor) proporciona una creación simplificada, lo que le permite crear contenido de forma más eficaz en los modos de etiqueta y sin etiqueta a través de una experiencia más intuitiva. La versión ofrece un rendimiento mejorado, con cargas de página más rápidas y una edición más suave incluso para temas grandes y complejos. También ofrece una mayor estabilidad al abordar las lagunas clave de creación, especialmente en torno a la navegación y el comportamiento del cursor. Además, una interfaz moderna ofrece una interfaz de usuario actualizada y fácil de usar que equilibra la funcionalidad con la facilidad de uso. Para obtener más información, vea [Introducción al editor](../user-guide/web-editor.md).

Este es un vídeo introductorio que resalta las capacidades de Editor 2.0.

>[!VIDEO](https://video.tv.adobe.com/v/3484007)


>[!NOTE]
>
> Póngase en contacto con el equipo de éxito del cliente de AEM Guides para habilitar Editor 2.0 en su entorno.

A continuación se indican las mejoras que facilitan y hacen que la creación de contenido sea más eficaz.

### Interfaz de usuario y experiencia rediseñadas

Una interfaz actualizada mejora la facilidad de uso general, lo que hace que la navegación y la creación de contenido sean más intuitivas y coherentes.

- **CSS más enriquecido para los elementos en los modos de creación y vista previa**: La CSS predeterminada mejorada para los elementos proporciona un estilo mejorado y una mejor coherencia visual en los modos de creación y vista previa.

  ![](assets/rich-css.png){width="650"}

- **Compatibilidad con temas oscuros**: La compatibilidad con un tema oscuro en el área de edición de contenido mejora la experiencia de creación para los usuarios que prefieren trabajar con una interfaz oscura.

  ![](assets/dark-theme.png){width="650"}

- **Configuración del editor consolidada en el nivel de usuario**: Un nuevo panel de configuración centralizado que proporciona a los autores un mejor control sobre el comportamiento del editor, lo que permite a los usuarios administrar las preferencias con mayor facilidad desde una sola ubicación. Las opciones de configuración incluyen la capacidad de habilitar/deshabilitar:

   - Espacios de no separación en el modo Autor
   - Configuración de visibilidad de etiquetas con atributos o sin atributos
   - Comentarios XML en el modo Autor
   - Menú de inserción rápida para insertar elementos en el editor

  ![](assets/editor-settings-dialog.png){width="350"}


  Para obtener más información acerca de cómo configurar las opciones del Editor, vea [Opciones del editor](../user-guide/config-editor-settings.md).

- **Mejor representación del contenido condicional en el modo Autor**: el contenido condicional se muestra más claramente en el modo Autor, lo que ayuda a los autores a identificar y administrar las variaciones de forma más eficaz. Para obtener más información, vea [Condiciones](../user-guide/web-editor-left-panel.md#conditions) en el panel izquierdo del editor.

  ![](assets/multiple-conditions-applied_cs-editor-2-0.png){width="650"}

### Funciones de creación mejoradas

Proporciona herramientas mejoradas y flexibilidad para optimizar los flujos de trabajo de creación y edición de contenido.

- **Ver atributos junto con elementos en el modo de etiqueta**: Los autores ahora pueden ver atributos de elementos con el modo de etiqueta, lo que ofrece una mejor visibilidad y control sobre el contenido estructurado. Para configurar esta característica, vea [Configuración del editor](../user-guide/config-editor-settings.md).

  ![](assets/config-tags-attributes.png){width="650"}

- **Menú de inserción rápida**: permite agregar elementos directamente mientras se edita en el modo Autor en la posición del cursor sin desplazarse a la barra de herramientas. Los elementos utilizados con frecuencia también se pueden configurar en la sección Favoritos mediante Configuración del editor para acceder más rápidamente. Para obtener detalles, vea [Editar temas](../user-guide/web-editor-edit-topics.md).

  ![](assets/quick-insert-menu.png){width="650"}

- **Capacidad para ver, editar e insertar comentarios XML en el modo Autor**: permite a los autores ver, editar e insertar comentarios XML directamente en el modo Autor para obtener una mejor visibilidad del contenido. Para configurar esta característica, vea [Configuración del editor](../user-guide/config-editor-settings.md).

  ![](assets/config-xml-comments.png){width="650"}

- **Modo paralelo**: permite la visualización simultánea de los modos Autor y Source, con ambas vistas en perfecta sincronización para facilitar la comparación, edición y validación de los cambios de contenido. Para obtener más información, vea [Vistas del editor](../user-guide/web-editor-views.md).

  ![](assets/side-by-side-editor-2-0.png){width="650"}

- **Creación de tablas mejorada**: Mejora la experiencia general de creación de tablas con interacciones más intuitivas y eficientes para crear y administrar tablas.

   - Interacciones fluidas e intuitivas: inserte filas y columnas fácilmente, junto con la compatibilidad de arrastrar y soltar para reordenar filas y columnas.
   - Barra de herramientas contextual: Acceda a acciones específicas de la tabla, como formato, alineación, combinación y otras acciones adicionales directamente dentro de la tabla.
   - Configuración de tablas: Añada varias filas o columnas en una sola acción, reduciendo los pasos repetitivos y mejorando la eficacia.

  ![](assets/config-table.png){width="650"}

  Para obtener información detallada, vea [Trabajar con tablas](../user-guide/web-editor-other-features.md#work-with-tables-in-the-new-editor).

### Rendimiento mejorado para temas grandes

El nuevo editor mejora la experiencia de trabajar con temas grandes y complejos al ofrecer una representación de contenido más rápida, una funcionalidad más fiable de deshacer y rehacer y un marcador sucio para indicar claramente los cambios no guardados.

## Acceda a la ruta y el UUID de referencias en archivos desde el panel Propiedades de contenido

Ahora, puede usar **Ruta del vínculo** para ver la ruta relativa de la referencia seleccionada y **UUID del vínculo** para ver su identificador único desde el panel de propiedades de contenido. También puede copiar la ruta absoluta completa y el UUID asociado directamente desde la interfaz mediante los iconos junto a Ruta de vínculo y UUID de vínculo, lo que facilita el seguimiento y la reutilización de los recursos vinculados.

Para obtener más información, vea [Propiedades del contenido](../user-guide/web-editor-right-panel.md#content-properties).

## Revisar mejoras

Se han realizado las siguientes mejoras de revisión como parte de esta versión:

- Ahora puede habilitar **Recordatorios automatizados** para programar notificaciones de AEM y recordatorios de correo electrónico para los revisores, tanto antes de la fecha de vencimiento de una tarea de revisión como después de que haya vencido. Puede configurar varios recordatorios en cada caso, con recordatorios de vencimiento anticipado enviados en una secuencia definida y recordatorios de vencimiento activados después de que la tarea se marque como vencida, según la programación de recordatorios configurada. Para obtener información detallada, vea [Enviar temas para revisión](../user-guide/review-send-topics-for-review.md).

- Los revisores ahora pueden acceder al Historial de versiones para los temas que se están revisando, lo que les permite ver y comparar versiones previamente revisadas y actualizadas del mismo tema en tareas de revisión anteriores. Esto ayuda a los revisores a validar los cambios realizados desde ciclos de revisión anteriores y a mantener la continuidad mediante la revisión de comentarios, etiquetas y otros detalles relacionados dentro del contexto de revisión actual. Para obtener más información, vea [Historial de versiones del revisor](../user-guide/review-topics.md#version-history-for-the-reviewer).

## Nueva experiencia de línea de base introducida en Experience Manager Guides

>[!NOTE]
>
> Póngase en contacto con el equipo de éxito del cliente de AEM Guides para habilitar una nueva línea de base en su entorno.

La administración de líneas de base grandes y complejas es ahora más rápida, estable y fácil de escalar con la **nueva experiencia de línea de base**, basada en una arquitectura de línea de base rediseñada. Esta actualización aborda los desafíos de rendimiento y fiabilidad de larga data, al tiempo que preserva los flujos de trabajo existentes.

Disponible como mejora beta, esta actualización proporciona una solución a los problemas comunes, como la carga lenta, los estados de línea de base incoherentes y la capacidad de administración limitada, al ofrecer una experiencia de línea de base más rápida, estable y predecible, con compatibilidad añadida para la automatización y las operaciones de línea de base a gran escala. Las principales mejoras son las siguientes:

- Rendimiento y escalabilidad mejorados
- Consistencia del back-end y IU más sólida
- Mayor visibilidad de filtrado, navegación y dependencias

Para obtener más información, vea [Nueva experiencia de línea de base (Beta) en Experience Manager Guides](../user-guide/web-editor-baseline-v2.md).






