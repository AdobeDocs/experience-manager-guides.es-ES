---
title: Notas de versión | Novedades de la versión 2024.10.0 de Adobe Experience Manager Guides
description: Obtenga información sobre las funciones nuevas y mejoradas de la versión 2024.10.0 de Adobe Experience Manager Guides
role: Leader
source-git-commit: b5ee4610811209719c7f0ff4bd03d8ae55f2d934
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 1%

---

# Novedades de la versión 2024.10.0 (octubre de 2024)

Este artículo cubre las funciones nuevas y mejoradas introducidas con la versión 2024.10.0 de Adobe Experience Manager Guides as a Cloud Service.

Para ver la lista de problemas corregidos en esta versión, consulte [Problemas solucionados en la versión 2024.10.0](fixed-issues-2024-10-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2024.10.0](../release-info/upgrade-instructions-2024-10-0.md).


## Mejoras de publicación

En la versión 2024.10.0 de se realizaron las siguientes mejoras en la publicación de contenido:




### Mejoras en la publicación de fragmentos de contenido

Experience Manager Guides también proporciona algunas mejoras útiles en los fragmentos de contenido:

- Experience Manager Guides permite publicar un tema o sus elementos en un fragmento de contenido.

- Puede publicar y ver los fragmentos de contenido de un tema desde la sección **Salidas** en las **Propiedades del archivo**.


- Puede crear fácilmente variaciones de fragmentos de contenido filtrando el contenido con condiciones mientras publica en un fragmento de contenido.

- Utilice la nueva interfaz de asignación para seleccionar y publicar fácilmente los elementos en un fragmento de contenido.

Ahora, la publicación de fragmentos de contenido solo reemplaza el contenido asignado en lugar de sobrescribir el fragmento de contenido completo. Esta función permite que un fragmento de contenido contenga datos de varias fuentes, como varios temas o el editor de fragmentos de contenido.

![Agregue el modelo de fragmento y los detalles de asignación en el cuadro de diálogo Publish como fragmento de contenido](assets/content-fragment-mapping.png)

Para obtener más información, vea [Fragmentos de contenido de Publish](../user-guide/publish-content-fragment.md).


### Variantes de fragmentos de experiencias de Publish basadas en filtros de condición

Experience Manager Guides permite publicar un tema o sus elementos en un Fragmento de experiencia. Ahora, también puede crear variantes de Fragmento de experiencia utilizando los filtros DITAVAL o de condición y reutilizarlas en diferentes canales o para diferentes audiencias.

Obtenga más información sobre cómo [Fragmentos de experiencias de Publish](../user-guide/publish-experience-fragment.md).


### Ajuste preestablecido de AEM Sites reorganizado para facilitar su uso

La configuración se ha reorganizado para ayudarle a configurar rápidamente el ajuste preestablecido de salida y generar la salida de AEM Sites.
Puede crear los ajustes preestablecidos de AEM Sites existentes seleccionando la opción **Usar asignación de componentes heredados** en el cuadro de diálogo **Nuevo ajuste preestablecido de salida**.

Vea las fichas **General**, **Contenido** y **Referencia de mapa cruzado** en los ajustes preestablecidos de AEM Sites:
- **General**: Contiene las configuraciones generales para generar el resultado. Puede especificar el sitio y la ruta de acceso de salida, eliminar o sobrescribir las páginas de salida existentes, eliminar las páginas generadas anteriormente para los temas eliminados, seleccionar la plantilla de diseño, conservar los archivos temporales y especificar el flujo de trabajo de generación posterior.
- **Contenido**: contiene la configuración aplicable al contenido para la generación de resultados. Se pueden seleccionar los filtros, la línea de base del mapa DITA y las propiedades de metadatos para la publicación.
- **Referencias de mapas cruzados**: esta lista contiene temas que contienen referencias de mapas cruzados con ámbito =&quot;peer&quot;. Se puede especificar el contexto de publicación para una lista de referencias de mapas cruzados con scope=&quot;peer&quot; para los temas disponibles en otros mapas DITA. Esta pestaña aparece si utiliza la versión de Experience Manager Guides (UUID).



### Referencias de mapas cruzados de ajustes preestablecidos de AEM Sites en el Editor web

La última mejora de Experience Manager Guides introduce referencias cruzadas de mapas en los ajustes preestablecidos de AEM Sites del Editor web.
Las referencias cruzadas en mapas en Experience Manager Guides ayudan a mejorar la navegación por el contenido, aumentar la reutilización del contenido y mejorar la experiencia del usuario.


Se puede especificar el contexto de publicación para una lista de referencias de mapas cruzados a temas disponibles en otros mapas DITA con scope=&quot;peer&quot;. Por ejemplo, el Tema 1 del Mapa A contiene una referencia al Tema 2. El tema 2 puede estar presente en mapas únicos o múltiples.  Puede seleccionar el mapa principal y un ajuste preestablecido específico o la salida publicada más recientemente para cada vínculo.

Si se hace referencia al mismo tema más de una vez en un archivo, puede agregar un contexto de publicación diferente para cada instancia. Esto proporciona una mayor flexibilidad y control sobre su contenido. Por ejemplo, el tema 3 está presente tanto en el mapa B como en el mapa C. El tema 1 contiene dos referencias al tema 3. Puede elegir Mapa B como mapa principal para el primer vínculo y Mapa C como mapa principal para el segundo vínculo.

![Ajuste preestablecido de AEM Sites heredado](assets/aem-sites-legacy.png)

*Especifique el contexto de publicación para los temas vinculados desde la ficha **Referencias de mapas cruzados**&#x200B;del ajuste preestablecido **AEM Sites**.*

Más información sobre [Ajustes preestablecidos de AEM Sites](../user-guide/generate-output-aem-site.md).

### Opción para elegir una jerarquía de archivos plana o anidada para la salida de HTML 5

Ahora, Experience Manager Guides le permite conservar la jerarquía de carpetas plana para los archivos temporales en los que todo el contenido se publica en formato de salida HTML5 y se guarda en una sola carpeta.
Si no decide acoplar la jerarquía de archivos, la salida de HTML5 se genera en una jerarquía de carpetas anidada. Esto implica que la estructura de carpetas original del contenido, con archivos organizados en subcarpetas, se replica en la salida. Esta jerarquía de carpetas anidada permite una organización y categorización de archivos más complejas, lo que facilita la administración y la navegación por grandes volúmenes de datos.


Obtenga más información sobre cómo [generar la salida de HTML5](../user-guide/generate-output-html5.md).


## Mejoras del editor

En la versión 2024.10.0 se han añadido las siguientes mejoras del editor:

### Acceso de solo lectura al modo Autor y Source para archivos bloqueados

Si un fichero DITA o Markdown está bloqueado o extraído por otro usuario, no se puede editar ni cambiar el contenido. Además de la Vista previa, también puede verla como un archivo de solo lectura en el modo Autor o Source.
En modo de solo lectura, puede ver el contenido junto con las etiquetas y atributos en el modo **Autor** o **Source** y editar las propiedades del archivo.

También puede acceder a la vista **Diseño** para obtener mapas DITA de solo lectura.
>[!NOTE]
>
> Los administradores de perfil de carpeta deben actualizar *ui_config.json* para que pueda acceder de manera armoniosa a los archivos de solo lectura en los modos Autor, Source y Diseño.

![editor de archivos bloqueado](./assets/locked-file-editor.png)
*Ver los archivos bloqueados en los modos Autor y Source.*


Aprenda a [abrir archivos bloqueados en los modos Autor y Source](../user-guide/web-editor-edit-topics.md#open-locked-files-in-author-and-source-modes).


### Condiciones agrupadas para la organización de contenido mejorada

Experience Manager Guides ahora le permite agrupar condiciones y presentarlas en una jerarquía anidada, lo que le permite agregar varias condiciones a un solo grupo. Al agrupar las condiciones, puede organizarlas y aplicarlas mejor en todo el contenido.

![condiciones organizadas en una jerarquía anidada](assets/conditions-nested-hierarchy.png){width="300" align="left"}

Obtenga más información acerca de la descripción de la característica **Condiciones** en la sección [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS).




