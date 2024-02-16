---
title: Notas de versión | Guías de Adobe Experience Manager as a Cloud Service, versión de agosto de 2022
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

Actualice las guías de Adobe Experience Manager actuales as a Cloud Service (más adelante denominadas *AEM Guías de as a Cloud Service*) realizando los siguientes pasos:
1. Consulte el código Git de los Cloud Service y cambie a la rama configurada en la canalización de Cloud Service correspondiente al entorno que desee actualizar.
1. Actualizar `<dox.version>` propiedad en `/dox/dox.installer/pom.xml` de su código Git de Cloud Service a 2022.8.167.
1. Confirme los cambios y ejecute la canalización de Cloud Service AEM para actualizar a la versión de agosto de las guías de la aplicación as a Cloud Service de la.

## Matriz de compatibilidad

AEM En esta sección se muestra la matriz de compatibilidad para las aplicaciones de software compatibles con las guías de la versión de Agosto de 2022 as a Cloud Service por las Guías de.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| No compatible | Actualización 4 de 2020 y posterior |
| | |

AEM *La línea de base y las condiciones creadas en la versión de FMPS a partir de 2020.2 son compatibles con las versiones de FMPS.

### Conector de oxígeno

| AEM Versión de Guides as a Cloud de | Ventanas de conector de oxígeno | Conector de oxígeno Mac |
| --- | --- | --- |
| 2022.8.0 | 2.7.5 | 2.7.5 |
|  |  |  |


## Nuevas funciones y mejoras

AEM En la versión de agosto de, Guides as a Cloud Service proporciona muchas mejoras y nuevas funciones:

### Vista Presentación en el editor de mapas

Ahora puede ver el diseño completo de un mapa DITA en el Editor de mapas. Cuando se abre un mapa para editarlo, se abre el **Diseño** vista del Editor de mapas. En esta vista, puede ver la jerarquía de mapas en una vista de árbol y también organizar o estructurar los temas en un mapa.

![vista de diseño](assets/layout-view-map.png)

La vista Presentación contiene una barra de herramientas independiente que le ayuda a realizar muchas tareas sobre los temas presentes en un mapa.
Puede insertar referencias de temas, grupos de temas y definiciones de claves en un mapa. Puede reorganizar los temas presentes en un mapa moviéndolos hacia arriba, hacia abajo, a la izquierda o a la derecha. También puede arrastrar y soltar los temas para moverlos en un mapa. El editor de mapas también proporciona los iconos para bloquear o desbloquear archivos, comprobar el historial de versiones y realizar una administración de etiquetas de versión.


La vista Presentación también proporciona el **Opciones de vista** para mostrar u ocultar el número de línea, mostrar u ocultar la casilla de verificación, o mostrar el nombre de archivo o el título de los temas de un mapa.


![view-options](assets/view-options.png)

También puede ver los temas en función de los filtros condicionales aplicados.

Además de organizar los temas en el archivo de asignación, también puede agregar, mover, copiar, pegar o eliminar referencias utilizando **Opciones** menú disponible para un elemento en la vista Presentación. También puede arrastrar y soltar un tema o un mapa desde el panel del repositorio al mapa abierto en el Editor de mapas.

El panel derecho muestra las Propiedades de contenido y las Propiedades de mapa en la vista Diseño del Editor de mapas. Los atributos en línea definidos para el tema seleccionado se muestran en relación con el tema en la vista Presentación. Por ejemplo, puede encontrar rápidamente todos los temas que tienen el atributo de plataforma definido como `IOS`.

Ahora también puede establecer la información de metadatos para los temas o el mapa. Puede definir el título de navegación, el texto de vínculo, la descripción breve y las palabras clave para el tema o el mapa seleccionado.

![panel derecho de vista de diseño](assets/layout-inline-attributes.png)

Para obtener más información, consulte *Vista Presentación* de Uso de las guías de Adobe Experience Manager as a Cloud Service.

### Atributos en línea en la configuración del editor

AEM Guías de ahora permite la configuración de **Atributos en línea** por su administrador desde el **Configuración del editor**. También puede añadir nuevos atributos en línea o eliminar los existentes del **Atributos en línea** en la pestaña Configuración del editor.
Los Atributos en línea configurados definidos para un tema se muestran con respecto al tema en la vista Presentación.

![Configuración del editor](assets/editor-settings-inline-attributes.png)


### Filtros adicionales en la vista Repositorio

Ahora la búsqueda de filtros en la vista del repositorio es más potente. Dos nuevos criterios de búsqueda, **Última modificación** y **Etiquetas** AEM se han agregado para filtrar los archivos y limitar la búsqueda en el repositorio de:
* **Última modificación**: puede buscar archivos que se hayan modificado por última vez después de una fecha seleccionada pero antes de una fecha seleccionada. También tiene la opción de utilizar los criterios predefinidos y buscar los archivos que se han modificado por última vez en las últimas 2 horas, la semana pasada, el mes pasado o el año pasado.
* **Etiquetas**: también puede buscar archivos que tengan etiquetas específicas aplicadas. Puede escribir la etiqueta o seleccionarla en la lista desplegable.

![Filtros de vista de repositorio](assets/repo-filter-search.png)


## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

* El índice Lucene obsoleto se utiliza en /core/article-publish/src/main/java/com/adobe/dxml/article/publish/util/DoxUtils.java (9291)
* El archivo Node.js actualizado no se utiliza para la publicación. (9835)
* El tema DITA no se actualiza automáticamente con los cambios realizados en la **Propiedades** página. (8745)
* Cuando se añade un elemento Frontmatter a un mapa de libros DITA, no funciona correctamente. (9507)
* PDF nativo | Se genera un PDF en blanco al utilizar **Generación rápida** para varios archivos cuando se selecciona un elemento vacío. (9822)
* PDF nativo | El apéndice se publica como un capítulo en la salida del PDF. (9829)
* PDF nativo | Cuando se edita una imagen de SVG, no se muestra actualizada en el diseño de página. (9069)
* Se inserta un carácter de guión normal cuando se `Nonbreaking Hyphen` se inserta utilizando la variable **Insertar carácter especial** diálogo. (8919)
* El Editor XML no muestra imágenes actualizadas en los temas si se han editado. (9500)
* Al publicar la salida mediante el Editor, los ajustes preestablecidos no se pueden eliminar del **Output** pestaña. (9100)
* Los submapas de un mapa DITA no se extraen mediante la función **Seleccionar todo** del menú de los tres puntos. (9814)
* No se pueden arrastrar y soltar plantillas de temas o asignaciones desde **Plantillas** a la plantilla de asignación personalizada en el editor web. (9846)
* No se puede crear un nuevo tema o plantilla de mapa en la subcarpeta de un mapa o plantilla de tema. (9888)
* No hay ninguna opción para examinar los temas o mapas presentes dentro de las subcarpetas de un mapa o plantilla de tema. (9889)
* Cuando se actualiza y se guarda un fichero de Schematron junto con el fichero DITA, no se muestra el panel derecho (si el fichero DITA rompe las validaciones presentes en el fichero de Schematron). (986)
* Se puede crear un nuevo ajuste preestablecido de salida duplicado si su nombre es el mismo que el de un ajuste preestablecido existente. (9997)
* Las imágenes de SVG se dañan y no se publican correctamente al generar la salida del HTML. (9949)


## Problemas conocidos

El Adobe AEM de ha identificado los siguientes problemas conocidos para la versión de Guías de as a Cloud Service para agosto de 2022.

### Problemas conocidos con la solución

Utilice la solución dada para los siguientes problemas conocidos:

* La vista Presentación no está visible en el editor de mapas.

  **Solución**: Actualice ui_config.json en el Perfil de carpetas.

* Symbols.json se sobrescribe, por lo que se produce el problema 8919.

  **Solución**: el archivo symbol.json actualizado debe combinarse con el archivo symbol.json anulado.

### Otros problemas conocidos

* Si se seleccionan varios archivos en la sección de resultados que se muestra al realizar una búsqueda en el repositorio y luego se arrastran y sueltan en la vista de autor, solo se agrega un archivo.
