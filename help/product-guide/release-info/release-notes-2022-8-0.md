---
title: Notas de versión | Adobe Experience Manager Guides as a Cloud Service, versión de agosto de 2022
description: Versión de agosto de Adobe Experience Manager Guides as a Cloud Service
exl-id: a01bfe8a-4715-438c-bb94-aa1d31f6662d
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1169'
ht-degree: 0%

---

# Versión de agosto de Adobe Experience Manager Guides as a Cloud Service

## Actualización a la versión de agosto

Actualice la configuración actual del as a Cloud Service de Adobe Experience Manager Guides (más adelante denominado *AEM Guides as a Cloud Service*) realizando los siguientes pasos:
1. Consulte el código Git de los Cloud Service y cambie a la rama configurada en la canalización de Cloud Service correspondiente al entorno que desee actualizar.
1. Actualice la propiedad `<dox.version>` en el archivo `/dox/dox.installer/pom.xml` de su código Git de Cloud Service a 2022.8.167.
1. Confirme los cambios y ejecute la canalización de Cloud Service para actualizar a la versión de agosto de AEM Guides as a Cloud Service.

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con la versión as a Cloud Service de AEM Guides de agosto de 2022.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| No compatible | Actualización 4 de 2020 y posterior |
| | |

AEM *La línea de base y las condiciones creadas en la versión de FMPS a partir de 2020.2 son compatibles con las versiones de FMPS.

### Conector de oxígeno

| Versión de AEM Guides as a Cloud | Ventanas de conector de oxígeno | Conector de oxígeno Mac |
| --- | --- | --- |
| 2022.8.0 | 2.7.5 | 2.7.5 |
|  |  |  |


## Nuevas funciones y mejoras

AEM Guides as a Cloud Service ofrece muchas mejoras y nuevas funciones en la versión de agosto:

### Vista Presentación en el editor de mapas

Ahora puede ver el diseño completo de un mapa DITA en el Editor de mapas. Cuando abre un mapa para editarlo, se abre la vista **Diseño** del Editor de mapas. En esta vista, puede ver la jerarquía de mapas en una vista de árbol y también organizar o estructurar los temas en un mapa.

![vista de diseño](assets/layout-view-map.png)

La vista Presentación contiene una barra de herramientas independiente que le ayuda a realizar muchas tareas sobre los temas presentes en un mapa.
Puede insertar referencias de temas, grupos de temas y definiciones de claves en un mapa. Puede reorganizar los temas presentes en un mapa moviéndolos hacia arriba, hacia abajo, a la izquierda o a la derecha. También puede arrastrar y soltar los temas para moverlos en un mapa. El editor de mapas también proporciona los iconos para bloquear o desbloquear archivos, comprobar el historial de versiones y realizar una administración de etiquetas de versión.


La vista Presentación también proporciona las **Opciones de vista** para mostrar u ocultar el número de línea, mostrar u ocultar la casilla de verificación o mostrar el nombre de archivo o el título de los temas de un mapa.


![opciones de vista](assets/view-options.png)

También puede ver los temas en función de los filtros condicionales aplicados.

Además de organizar los temas del archivo de asignación, también puede agregar, mover, copiar, pegar o eliminar referencias mediante el menú **Opciones** disponible para un elemento en la vista Presentación. También puede arrastrar y soltar un tema o un mapa desde el panel del repositorio al mapa abierto en el Editor de mapas.

El panel derecho muestra las Propiedades de contenido y las Propiedades de mapa en la vista Diseño del Editor de mapas. Los atributos en línea definidos para el tema seleccionado se muestran en relación con el tema en la vista Presentación. Por ejemplo, puede buscar rápidamente todos los temas que tengan el atributo de plataforma definido como `IOS`.

Ahora también puede establecer la información de metadatos para los temas o el mapa. Puede definir el título de navegación, el texto de vínculo, la descripción breve y las palabras clave para el tema o el mapa seleccionado.

![panel derecho de vista de diseño](assets/layout-inline-attributes.png)

Para obtener más información, consulte la sección *Vista de diseño* en Uso del as a Cloud Service de Adobe Experience Manager Guides.

### Atributos en línea en la configuración del editor

AEM Guides ahora permite que su administrador configure **Atributos en línea** desde **Configuración del editor**. También puede agregar nuevos atributos en línea o eliminar los existentes de la ficha **Atributos en línea** en Configuración del editor.
Los Atributos en línea configurados definidos para un tema se muestran con respecto al tema en la vista Presentación.

![Configuración del editor](assets/editor-settings-inline-attributes.png)


### Filtros adicionales en la vista Repositorio

Ahora la búsqueda de filtros en la vista del repositorio es más potente. AEM Se han agregado dos nuevos criterios de búsqueda, **Última modificación** y **Etiquetas**, para filtrar los archivos y restringir la búsqueda en el repositorio de la:
* **Última modificación**: puede buscar los archivos que se modificaron por última vez después de una fecha seleccionada pero antes de una fecha seleccionada. También tiene la opción de utilizar los criterios predefinidos y buscar los archivos que se han modificado por última vez en las últimas 2 horas, la semana pasada, el mes pasado o el año pasado.
* **Etiquetas**: también puede buscar archivos que tengan etiquetas específicas aplicadas. Puede escribir la etiqueta o seleccionarla en la lista desplegable.

![Filtros de vista de repositorio](assets/repo-filter-search.png)


## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

* El índice Lucene obsoleto se utiliza en /core/article-publish/src/main/java/com/adobe/dxml/article/publish/util/DoxUtils.java (9291)
* El archivo Node.js actualizado no se utiliza para la publicación. (9835)
* El tema DITA no se actualiza automáticamente con los cambios realizados en la página **Propiedades**. (8745)
* Cuando se añade un elemento Frontmatter a un mapa de libros DITA, no funciona correctamente. (9507)
* PDF nativo | Se genera un PDF en blanco al usar **Generación rápida** para varios archivos cuando se selecciona un elemento vacío. (9822)
* PDF nativo | El apéndice se publica como un capítulo en la salida del PDF. (9829)
* PDF nativo | Cuando se edita una imagen de SVG, no se muestra actualizada en el diseño de página. (9069)
* Se inserta un carácter de guión normal cuando se inserta un carácter `Nonbreaking Hyphen` mediante el cuadro de diálogo **Insertar carácter especial**. (8919)
* El Editor XML no muestra imágenes actualizadas en los temas si se han editado. (9500)
* Al publicar la salida a través del editor, los ajustes preestablecidos no se pueden eliminar de la pestaña **Output**. (9100)
* Los submapas de un mapa DITA no se extraen con la opción **Seleccionar todo** del menú de los tres puntos. (9814)
* No se pueden arrastrar y colocar plantillas de asignación o de tema desde el menú **Plantillas** hasta la plantilla de asignación personalizada en el editor web. (9846)
* No se puede crear un nuevo tema o plantilla de mapa en la subcarpeta de un mapa o plantilla de tema. (9888)
* No hay ninguna opción para examinar los temas o mapas presentes dentro de las subcarpetas de un mapa o plantilla de tema. (9889)
* Cuando se actualiza y se guarda un fichero de Schematron junto con el fichero DITA, no se muestra el panel derecho (si el fichero DITA rompe las validaciones presentes en el fichero de Schematron). (986)
* Se puede crear un nuevo ajuste preestablecido de salida duplicado si su nombre es el mismo que el de un ajuste preestablecido existente. (9997)
* Las imágenes de SVG se dañan y no se publican correctamente al generar la salida del HTML. (9949)


## Problemas conocidos

El Adobe ha identificado los siguientes problemas conocidos para la versión as a Cloud Service de AEM Guides de agosto de 2022.

### Problemas conocidos con la solución

Utilice la solución dada para los siguientes problemas conocidos:

* La vista Presentación no está visible en el editor de mapas.

  **Solución alternativa**: Actualice ui_config.json en el perfil de carpeta.

* Symbols.json se sobrescribe, por lo que se produce el problema 8919.

  **Solución alternativa**: el archivo symbol.json actualizado debe combinarse con el archivo symbol.json reemplazado.

### Otros problemas conocidos

* Si se seleccionan varios archivos en la sección de resultados que se muestra al realizar una búsqueda en el repositorio y luego se arrastran y sueltan en la vista de autor, solo se agrega un archivo.
