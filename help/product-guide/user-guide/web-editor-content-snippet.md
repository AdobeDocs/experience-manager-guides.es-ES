---
title: Inserción de un fragmento de contenido desde la fuente de datos
description: AEM Utilice los datos de su fuente de datos en las guías de la. Aprenda a insertar un fragmento de contenido desde la fuente de datos. Cree un tema con el generador de temas.
exl-id: fbd5eff2-451b-49d6-ba77-6eb271e94349
feature: Authoring, Features of Web Editor
role: User
source-git-commit: 2e5bf87b65cca6b522fcb97db1f40f98f020927a
workflow-type: tm+mt
source-wordcount: '2389'
ht-degree: 0%

---

# Uso de datos de la fuente de datos

A **fuente de datos** es un sistema en el que se almacenan y administran los datos de su organización. Estos son los sistemas de registro como JIRA, bases de datos SQL, PIM o PLM. AEM Guías de proporciona la función para conectarse con la fuente de datos y utilizar los datos de ellas.

También puede conectarse a archivos de datos JSON mediante un conector de archivo. Cargue el archivo JSON desde el equipo o navegue desde los recursos de Adobe Experience Manager. A continuación, cree fragmentos de contenido o temas utilizando los generadores.

## Panel Fuentes de datos

Seleccionar **Fuentes de datos** ![fuente de datos](images/data-source-icon.svg) en el panel izquierdo para ver las fuentes de datos conectadas. El panel Fuentes de datos se abre y muestra todas las fuentes de datos conectadas.

En función de la configuración, el administrador puede configurar un conector de fuente de datos:

<details>
<summary> Cloud Services </summary>


- Si utiliza la versión de octubre de 2023 o posterior, aprenda a [configuración de un conector de origen de datos desde la interfaz de usuario](../cs-install-guide/conf-data-source-connector-tools.md) en la Guía de instalación y configuración de Cloud Service.

- Si utiliza la versión de julio de 2023 o septiembre de 2023, aprenda a [configuración de un conector de fuente de datos](../cs-install-guide/conf-data-source-connector.md) en la Guía de instalación y configuración de Cloud Service.

</details>

<details>    
<summary>  Software On-Premise </summary>

- Si utiliza la versión 4.3.1 o posterior de, aprenda a [configuración de un conector de origen de datos desde la interfaz de usuario](../cs-install-guide/conf-data-source-connector-tools.md) en la Guía de instalación y configuración in situ.

- Si está utilizando la versión 4.3, aprenda a [configuración de un conector de fuente de datos](../cs-install-guide/conf-data-source-connector.md) en la Guía de instalación y configuración in situ.
</details>


>[!NOTE]
>
> Verá las fuentes de datos para las que el administrador ha configurado el conector.


## Mostrar vista de lista o vista de mosaico

Puede alternar entre la vista de lista o la vista de mosaico para ver los distintos orígenes de datos en forma de lista o como mosaicos.

Seleccione una fuente de datos para ver los generadores de fragmentos de contenido y los generadores de temas disponibles para la fuente de datos seleccionada.

### Vista de lista  ![](images/data-sources-list-view-icon.svg)

![](images/data-sources-list-view.png){width="300" align="left"}

*Lista de fuentes de datos conectadas.*

### Vista en mosaico   ![](images/data-sources-tile-view-icon.svg)

![](images/data-sources-tile-view.png){width="300" align="left"}

*Vea las fuentes de datos conectadas en mosaico.*

Los datos de las fuentes de datos se pueden utilizar de dos maneras:
- Insertar un fragmento de contenido
- Crear un tema



## Inserción de un fragmento de contenido desde la fuente de datos

AEM Guías de proporciona la función para conectarse con la fuente de datos. Puede recuperar los datos, insertarlos en los temas y editarlos. Puede crear fácilmente un fragmento de contenido mediante el generador de fragmentos de contenido y reutilizarlo dentro de sus temas.

Realice los siguientes pasos para crear un fragmento de contenido mediante el generador de fragmentos de contenido e insertarlo en el tema:

1. Seleccionar **Fuentes de datos** ![](images/data-source-icon.svg)   en el panel izquierdo para ver las fuentes de datos conectadas.

1. Seleccione una fuente de datos para ver los generadores de fragmentos de contenido disponibles para la fuente de datos seleccionada.

   ![](images/code-snippet-generator.png){width="300" align="left"}

   *El panel Fuentes de datos enumera los generadores de fragmentos de contenido disponibles.*

1. Seleccionar **Añadir** para agregar un nuevo generador de fragmentos de contenido. El **Añadir generador de fragmentos de contenido** se abre el panel.

1. Introduzca la consulta en **Consulta de datos** cuadro de texto.  Seleccionar **Copiar consulta de muestra** para copiar rápidamente una consulta de datos. En lugar de crear manualmente la consulta, puede copiar y pegar la consulta de ejemplo en el **Consulta de datos** cuadro de texto. A continuación, simplemente edite la consulta según sus necesidades de datos.

   >[!NOTE]
   >
   >Experience Manager proporciona diferentes consultas de muestra para todos los recursos en los distintos orígenes de datos. Estos se asignan a la fuente de datos desde la que se recuperan los datos.

1. Si utiliza un conector de archivos, puede cargar el archivo JSON desde el equipo o examinar un archivo JSON desde los recursos de Adobe Experience Manager.

   >[!NOTE]
   >
   > Verá las opciones para cargar o examinar archivos en lugar de una consulta de datos si utiliza un conector de archivo.

1. Seleccione la plantilla que se asigna a la fuente de datos desde el **Plantilla de asignación de datos** desplegable.
Las plantillas listas para usar del origen de datos seleccionado se muestran en la lista desplegable. Por ejemplo, puede ver la plantilla &quot;sql-table&quot; para la fuente de datos denominada &quot;PostgreSQL&quot;.

   >[!NOTE]
   >  
   > Si el administrador ha configurado plantillas personalizadas, también se le mostrarán esas plantillas en la lista desplegable (según las configuraciones de ruta de plantilla realizadas por el administrador).
   >   
   >También puede utilizar las herramientas de Velocity en las plantillas. Obtenga más información sobre cómo [usar las herramientas de Velocity](#use-velocity-tools).

1. El **Recurso** aparece el menú desplegable para algunos conectores como REST Client, Salsify, Akeneo y Microsoft ADO.  Seleccione cualquier recurso del menú desplegable y conéctese a él para crear un fragmento de contenido o un tema con el generador.

   >[!NOTE]
   >
   > El administrador puede configurar los recursos predeterminados o agregar recursos para varias direcciones URL al configurar los conectores de origen de datos.

1. Clic **Buscar** para recuperar los datos del origen de datos y aplicar la plantilla a los datos resultantes de la consulta SQL.

1. Los datos se pueden ver en la vista previa o en la vista de origen DITA.

   1. La vista previa muestra cómo se mostrarán los datos cuando se inserten en el contenido. La vista previa muestra una pequeña fracción de los datos con el formato de la plantilla seleccionada.
Por ejemplo:
      - Si ha seleccionado la plantilla de tabla SQL, puede ver los datos SQL en formato de tabla.
      - Si ha seleccionado la plantilla de lista ordenada por jira, puede ver una lista ordenada para los problemas de Jira.

   1. La vista de origen muestra los datos en la vista de origen DITA.
      ![](images/add-content-snippet-generator.png){width="800" align="left"}
      *Añada un generador de fragmentos de contenido. Ver los datos en modo de origen o vista previa.*

1. Para guardar los resultados de la consulta, escriba el nombre del generador y haga clic en **AÑADIR**.   Se agrega a la lista un nuevo generador de fragmentos de contenido.

   >[!NOTE]
   >
   > Debe seguir la convención de nomenclatura de archivos para el nombre del nuevo generador de contenido. No puede haber un espacio en el nombre del generador de fragmentos de contenido. Tampoco puede guardar un nuevo generador de contenido con el nombre de un generador de contenido existente. Se produce un error.

### Opciones de un generador de fragmentos de contenido

Haga clic con el botón derecho en un generador de fragmentos de contenido para abrir Opciones. Con las opciones, puede realizar las siguientes operaciones:

- **Previsualizar**: utilice esta opción para abrir un panel y ver una pequeña fracción de cómo se muestran los datos en la salida.
- **Insertar**: utilice esta opción para insertar el fragmento de contenido seleccionado en el tema abierto para su edición en el Editor Web. A medida que los datos se insertan como un fragmento, también puede editarlos dentro del tema en el Editor Web.

  >[!NOTE]
  > 
  > La opción Insertar sólo aparece mientras está editando un tema.

- **Editar**: utilice esta opción para realizar cambios en el generador de fragmentos de contenido y guardarlo.
- **Eliminar**: utilice esta opción para eliminar el generador de fragmentos de contenido seleccionado.
- **Duplicar**: utilice esta opción para crear un duplicado o una copia del generador de fragmentos de contenido seleccionado. El duplicado se crea con un sufijo (como generator_1) de forma predeterminada.

### Insertar un fragmento de consulta

También puede utilizar la variable **Insertar fragmento de consulta** ![](images/data-source-icon.svg)   en la barra de herramientas principal para insertar el fragmento de datos en los temas.  Puede seleccionar un generador en la lista desplegable, editar la consulta o cambiar la plantilla e insertar los datos en el tema.

![](images/insert-content-snippet.png){width="800" align="left"}

*Editar e insertar un fragmento de datos.*

## Creación de un tema mediante el generador de temas

Un generador de temas le ayuda a crear temas que contienen datos de sus fuentes. Puede crear rápidamente un generador de temas y, a continuación, generar los temas mediante el generador. Cada tema puede contener datos en varios formatos, como tablas, listas y párrafos.   Por ejemplo, en un tema, puede agregar una tabla que incluya los detalles de todos los productos nuevos y una lista de todos los productos que se suspenderán para su venta.

El generador de temas puede crear los temas que contienen los datos y un mapa DITA para todos los temas. También puede `<conref>` estos temas aparecen en el contenido. Esto le permite mantener los datos sincronizados con la fuente de datos y actualizarlos fácilmente.





### Crear un tema

Realice los siguientes pasos para crear un tema con el generador de temas:

1. Seleccione una fuente de datos para ver los generadores de fragmentos de contenido y los generadores de temas disponibles para la fuente de datos seleccionada.

   ![](images/data-sources.png){width="300" align="left"}

   *Agregar un generador de temas para una fuente de datos conectada.*

1. Seleccionar **Añadir** ![](images/Add_icon.svg) y seleccione **Generador de temas** en el menú desplegable para agregar un nuevo generador de temas. El **Agregar generador de temas** se abre el panel.



1. Introduzca los valores en los campos bajo las siguientes tres pestañas del **Agregar generador de temas** panel:

   **Recuperar configuración**

   ![](images/topic-generator-fetch-configuration.png){width="300" align="left"}

   *Agregue los detalles Consulta de datos, Plantilla de asignación de datos y Nodo raíz para el generador de temas y asígnele un nombre único en el panel Recuperar configuración.*

   1. Introduzca la consulta en **Consulta de datos** cuadro de texto. Seleccionar **Copiar consulta de muestra** para copiar rápidamente una consulta de datos. En lugar de crear manualmente la consulta, puede copiar y pegar la consulta de ejemplo en el **Consulta de datos** cuadro de texto. A continuación, simplemente edite la consulta según sus necesidades de datos.

      >[!NOTE]
      >
      >Experience Manager proporciona diferentes consultas de muestra para todos los recursos en los distintos orígenes de datos. Estos se asignan a la fuente de datos desde la que se recuperan los datos.

   1. Si utiliza un conector de archivos, puede cargar el archivo JSON desde el equipo o examinar un archivo JSON desde los recursos de Adobe Experience Manager.

      >[!NOTE]
      >
      > Verá las opciones para cargar o examinar archivos en lugar de una consulta de datos si utiliza un conector de archivo.

   1. Seleccione la plantilla que se asigna a la fuente de datos desde el **Plantilla de asignación de datos** desplegable.

      >[!NOTE]
      >
      > Si el administrador ha configurado plantillas personalizadas, también se mostrarán dichas plantillas en la lista desplegable (según las configuraciones de ruta de plantilla realizadas por el administrador). Por ejemplo, se puede crear una plantilla de tema que contenga una lista ordenada, tablas, párrafos u otros elementos DITA.

   1. Introduzca el **Nodo raíz**. Este es el nodo en el que desea acceder a los datos. A continuación, el generador de temas crea cada tema en el nivel definido en el nodo raíz. Por ejemplo, puede agregar &quot;problemas&quot; como nodo raíz en Jira. Por lo tanto, si una consulta devuelve 13 problemas, obtendrá 13 temas, un tema para cada problema.

   1. Clic **Buscar** para recuperar los datos del origen de datos y aplicar la plantilla a los datos resultantes de la consulta SQL. La vista previa muestra una pequeña fracción de cómo aparece el tema en el formato de la plantilla seleccionada. Por ejemplo, puede ver un solo problema de Jira con todos los campos resultantes de la consulta.
   1. Introduzca el nombre del generador del tema.

      >[!NOTE]
      > 
      > Debe seguir la convención de nomenclatura de archivos para el nombre del nuevo generador de temas. No puede haber un espacio en el nombre del generador de temas. Tampoco puede guardar un nuevo generador de temas con el nombre de un generador de temas existente. Se produce un error.

   **Configuración de salida**

   ![](images/topic-generator-output-configuration.png){width="300" align="left"}

   *Introduzca los detalles de la convención de nomenclatura de temas y rutas de salida en el panel Configuración de salida. Genere un mapa DITA y asígnele un nombre.*

   1. Introduzca el **Ruta de salida** Especifica dónde desea guardar los temas.
   1. En el **Convenciones de nomenclatura de temas**, puede introducir un valor o una variable con etiquetas de velocidad. Los nuevos temas seguirán la convención. Por ejemplo, puede introducir la variable `$key` para crear temas basados en claves Jira.
   1. Habilitar la opción **Generación de un mapa** si desea crear un mapa que contenga todos los temas generados.
   1. Introduzca el nombre del nuevo mapa DITA.

   >[!NOTE]
   >
   > El generador de temas genera el mapa DITA en la misma ruta de salida que los temas.

   **Metadatos**

   Seleccione las propiedades de metadatos de la lista desplegable para pasarlas a los temas. **Nombre** La lista desplegable enumera las propiedades personalizadas y predeterminadas.

   Por ejemplo, en la siguiente captura de pantalla, `dc:description`, `dc:language`, `dc:title`, y `docstate` son las propiedades predeterminadas para las que se pueden definir los valores. Puede crear una propiedad personalizada como autor y definir su valor.

   ![](images/topic-generator-metadata.png){width="300" align="left"}

   *Agregue las propiedades de metadatos en el panel Metadatos para pasar a los temas.*

1. Introduzca el nombre del generador y haga clic en **Guardar** para guardar los resultados de la consulta. Se agrega un nuevo generador de temas a la lista.

1. Clic **Guardar y generar** para guardar el generador de temas y generar nuevos temas a partir del generador de temas.



   ![](images/edit-topic-generator.png){width="650" align="left"}

   *Generar temas nuevos a partir de un generador de temas existente.*

   >[!NOTE]
   >
   > Si los temas ya existen, el generador actualiza los datos de los temas existentes.

### Opciones para un generador de temas

Haga clic con el botón derecho en un generador de temas para abrir **Opciones**. Con las opciones, puede realizar las siguientes operaciones:

- **Generar**: Esta opción genera los temas para el generador de temas seleccionado. También puede utilizar esta opción para actualizar los temas existentes. Se conecta a la fuente de datos y obtiene los datos actualizados. Al generar el contenido, esta opción está desactivada y se ve un cargador.
  >[!NOTE]
  >
  >Si el tema ya existe, puede sobrescribir los datos del tema o guardarlos como una nueva versión.

  ![](images/generate-topic-options.png)

  *Genere un tema y, si el archivo ya existe, guárdelo como una nueva versión o sobrescriba el tema.*
- **Ver registro**: seleccione esta opción para ver el archivo de registro de generación de contenido. El archivo de registro se abre en una nueva pestaña. Puede ver los errores, advertencias, mensajes de información y excepciones en el archivo de registro. Esta opción está habilitada si ha generado el contenido para el generador de temas seleccionado.

- **Previsualizar**: utilice esta opción para abrir un panel y ver una pequeña fracción de cómo se muestran los datos en la salida.



- **Editar**: utilice esta opción para cambiar y guardar el generador de temas. Esta opción está desactivada mientras se genera el contenido.
- **Eliminar**: utilice esta opción para eliminar el generador de temas seleccionado. Esta opción está desactivada mientras se genera el contenido.
- **Duplicar**: Esta opción crea un duplicado o una copia del generador de temas seleccionado. El duplicado se crea con un sufijo (como `topic-sample_1`) de forma predeterminada.



## Uso de las herramientas de Velocity en las plantillas de fuente de datos {#use-velocity-tools}

Las plantillas de Experience Manager también admiten las herramientas de Velocity (versión 2.0). Estas herramientas le ayudan a aplicar varias funciones a los datos que obtiene de las fuentes de datos. Obtenga más información sobre el uso del [Herramientas de Velocity](https://velocity.apache.org/tools/2.0/generic.html) y las funciones que se pueden aplicar.

Siga estos pasos para utilizar una herramienta Velocity en una plantilla:
1. Edite una plantilla de Velocity en el editor web.
1. Añada una herramienta y su función en la variable `<tool.function>` formato. Por ejemplo:
   - Para generar un número aleatorio con la herramienta matemática, utilice `$mathTool.random`.
   - Para generar la suma de números con la herramienta matemática, utilice `$mathTool.add(num1, num2)`.
1. Utilice la plantilla para crear un fragmento de contenido o un tema.
1. Después de aplicar la plantilla a los datos, se pueden ver los datos en la vista previa o en la vista de origen DITA.




Puede utilizar las siguientes herramientas dentro de las plantillas de Velocity para aplicar varias funciones a los datos que recupere del conector: -`$alternatorTool`
- `$classTool`
- `$contextTool`
- `$conversionTool`
- `$dateTool`
- `$comparisonDateTool`
- `$displayTool`
- `$escapeTool`
- `$fieldTool`
- `$loopTool`
- `$linkTool`
- `$listTool`
- `$mathTool`
- `$numberTool`
- `$renderTool`
- `$resourceTool`
- `$sortTool`
