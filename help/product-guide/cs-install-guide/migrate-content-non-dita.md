---
title: Migración de contenido no DITA
description: Obtenga información sobre cómo migrar contenido no DITA
exl-id: cf437fb8-ed33-47af-aa7e-ffd8acd232da
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '2889'
ht-degree: 0%

---

# Migración de contenido no DITA {#id181AH0R02HT}

Esta sección le guía a través del proceso de migración para migrar documentos que no son DITA al formato DITA. AEM Guías de proporciona migración desde las siguientes fuentes:

- [Microsoft Word](#id1949B040Z5Z)

- [documentos de InDesign](#id195AD0B0K5Z)

- [XHTML](#id1949B04L0Y4)

- [Documentos de FrameMaker no estructurados](#id1949B050VUI)

- [Cualquier otro documento estructurado](#id1949B0590YK)


## Migrar documentos de Microsoft Word {#id1949B040Z5Z}

AEM Guías de le permite migrar los documentos existentes de Word \(`.docx`\) en documentos de tipo de tema DITA. Es necesario especificar las ubicaciones de las carpetas de entrada y salida junto con otros parámetros y el documento se convierte en un documento DITA. Según el contenido, podría tener un archivo .dita y un archivo .ditamap.

Para poder convertir un documento de Word correctamente, el documento debe estar bien estructurado. Por ejemplo, el documento debe tener un Título, seguido de Título 1, Título 2, etc. Cada uno de los encabezados debe tener algún contenido. Si el documento no está bien estructurado, es posible que el proceso no funcione según lo esperado.

AEM De forma predeterminada, las guías de la comunidad de usuarios utilizan la [Marco de trabajo de transformación de Word a DITA \(Word2DITA\)](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/word2dita-intro.html). Esta transformación depende de la variable [asignación de estilo a etiqueta](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html) archivo de configuración. Para poder utilizar correctamente la transformación de Word2DITA, debe tener en cuenta las siguientes directrices para preparar el documento de Word para la conversión:

>[!NOTE]
>
> Si realiza cambios en el archivo de configuración de asignación de estilo a etiqueta predeterminado, debe actualizar y utilizar las directrices que confirmen la actualización de la asignación de estilo.

- Asegúrese de que el documento comienza con un Título; este Título se asigna al título del mapa DITA. Además, el Título debe ir seguido de algún contenido normal.

- Después del Título, debe haber Encabezado 1, Encabezado 2, etc. Cada encabezado debe tener algún contenido. Los Encabezados se convierten en nuevos temas de tipo Concepto. La jerarquía de los temas generados se ajusta a los niveles de Encabezado del documento. Por ejemplo, el Encabezado 1 precederá al Encabezado 2 y el Encabezado 2 al contenido del Encabezado 3.

- El documento debe tener al menos un contenido de tipo Título.

- Asegúrese de que no tiene ninguna imagen agrupada. Si ha agrupado imágenes en el documento, desagrupe todas esas imágenes.

- Quitar todos los encabezados y pies de página.

- Los estilos en línea como negrita, cursiva y subrayado se convierten en `b`, `i`, y `u` elementos.

- Todas las listas ordenadas y sin ordenar se convierten en `ol` y `ul` elementos. Esto también se aplica a listas anidadas, listas dentro de tablas, notas o notas al pie.

- Todos los hipervínculos se convierten en `xref`.

- El nombre de archivo de los archivos convertidos se basa en el texto de encabezado seguido de un número de archivo. El número de archivo es un número secuencial basado en la posición del texto del encabezado en el documento. Por ejemplo, si el texto de un encabezado es &quot;Encabezado de muestra&quot; y es el décimo encabezado del documento, el nombre de archivo resultante para este tema será similar a Ejemplo\_Encabezado\_10.dita.


Realice los siguientes pasos para convertir los documentos de Word existentes en un documento de tipo de tema DITA:

1. Utilice el Administrador de paquetes para descargar el archivo /libs/fmdita/config/w2d\_io.xml.

1. Personalice el archivo w2d\_io.xml descargado.

1. Añada el archivo en la siguiente ubicación del repositorio de Git de Cloud Manager:

   /apps/fmdita/config/w2d\_io.xml

   El `w2d_io.xml` contiene los siguientes parámetros configurables:

   - En el `inputDir` , especifique la ubicación de la carpeta de entrada donde están disponibles los documentos de Word de origen. Por ejemplo, si los documentos de Word están almacenados en una carpeta denominada `wordtodita` in `projects` y, a continuación, especifique la ubicación como: `/content/dam/projects/wordtodita/`

   - En el`outputDir` , especifique la ubicación de la carpeta de salida o mantenga la ubicación de salida por defecto para guardar el documento DITA convertido. Si la carpeta de salida especificada no existe en DAM, el flujo de trabajo de conversión crea la carpeta de salida.

   - Para el `createRev` , especifique si se va a crear una nueva versión del tema DITA convertido \(`true`\) o no \(`false`\).

   - En el `s2tMap` , especifique la ubicación del archivo de asignación que contiene asignaciones para estilos de documento de Word a elementos DITA. La asignación predeterminada se almacena en el archivo ubicado en:

     ```
     /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
     ```

     >[!NOTE]
     >
     > Para obtener más información sobre la estructura de `word-builtin-styles-style2tagmap.xml` y cómo puede personalizarlo, consulte [Asignación de estilo a etiqueta](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html) in *Guía del usuario de DITA para editores*.

   - En el elemento props2Propagate, especifique las propiedades que deben pasarse al mapa DITA. Esta propiedad es necesaria para pasar metadatos predeterminados como dc:title, dc:subject, dam:keywords, dam:category de metadatos de documento a recursos DITA convertidos.

1. Ejecute la canalización de Cloud Manager para implementar la configuración actualizada.

1. Después de configurar los parámetros necesarios en la variable `w2d_io.xml` AEM , inicie sesión en la interfaz de usuario de Assets y ábrala.

1. Vaya a la ubicación de la carpeta de entrada \(`wordtodita`\).

1. Cargue los documentos de origen de Word en esta carpeta. Para obtener información sobre la carga de contenido en DAM, consulte [Cargar contenido DITA existente](migrate-content-upload-existing-dita-content.md#).


Uso del `config` `/config` , puede definir uno o varios bloques de configuraciones para la conversión. El flujo de trabajo de conversión se ejecuta y la salida final en forma de tema DITA se guarda en la ubicación especificada en la `outputDir` Elemento.

**Actualizaciones de personalización para usuarios existentes**

AEM Si ya es usuario de Guías de as a Cloud Service y actualizadas de la versión de agosto de 2021 a la versión de enero de 2022 o superior, actualice las propiedades dadas porque se han movido pocos archivos.

>[!NOTE]
>
> Esta actualización solo es aplicable si ya está utilizando el flujo de trabajo de conversión de Microsoft Word a DITA.

- Ruta de archivo: /apps/fmdita/config/w2d\_io.xml
- Cambiar el valor de `<s2tMap>` de /apps/dxml/word2dita/word-builtin-styles-style2tagmap.xml a /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
- Realice los cambios necesarios en el repositorio Git de Cloud Manager, ya que para el servicio en la nube todos los archivos de /apps se superponen a través de Git de Cloud Manager.

## Migrar documentos de Adobe InDesign {#id195AD0B0K5Z}

AEM Guías de le permite convertir documentos de InDesign. Al igual que el FrameMaker, el InDesign también le permite crear documentos no estructurados y estructurados. Los documentos no estructurados utilizan los estilos de párrafo y carácter para dar formato al contenido. El documento estructurado utiliza elementos y sus atributos correspondientes.

El proceso de conversión requiere la asignación de los formatos de estilo de párrafo y carácter a los elementos DITA relevantes. Del mismo modo, en el caso de los documentos estructurados, el fichero de asignación contendrá una asignación uno a uno de elementos y atributos de InDesign con elementos y atributos DITA.

El proceso de conversión implica las siguientes acciones en el servidor:

- El *Lenguaje de marcado de InDesign* El archivo \(IDML\) se ha desempaquetado en un directorio de trabajo.
- El archivo designmap.xml se lee para localizar las historias de InDesign individuales.
- Todas las historias se combinan en una sola instancia XML, las historias &quot;vacías&quot; se descartan.
- Se exportan todos los gráficos incrustados.
- Conversión previa de estructuras estándar como tablas y gráficos al formato DITA.
- Asignación de estilo o estructura a la salida final en función del archivo de asignación.
- Creación y validación de temas DITA individuales y ficheros de mapa DITA.
- Eliminación de archivos temporales.

En general, el proceso de conversión requiere lo siguiente [Preparar archivos de InDesign para la conversión](appendix.md#id195DBF0045Z)[apéndice.md\#id195DBF0045Z](appendix.md#id195DBF0045Z) y [Preparar el archivo de asignación para la migración de InDesign a DITA](appendix.md#id194AF0003HT)[apéndice.md\#id194AF0003HT](appendix.md#id194AF0003HT), a continuación, debe seguir el procedimiento dado de ejecución del proceso de conversión.

Realice los siguientes pasos para convertir los documentos de InDesign existentes en un documento de tipo de tema DITA:

1. AEM Inicie sesión en la aplicación y abra el modo CRXDE Lite.

1. Vaya al archivo de configuración predeterminado disponible en la siguiente ubicación:

   `/libs/fmdita/config/idml2dita_io.xml`

1. Cree un nodo de superposición de `config` carpeta dentro de `apps` nodo.

1. Vaya al archivo de configuración disponible en la `apps` nodo:

   `/apps/fmdita/config/idml2dita_io.xml`

   Configure los siguientes parámetros en la `idml2dita_io.xml` archivo:

   - En el `inputDir` , especifique la ubicación de la carpeta de entrada donde están disponibles los documentos de InDesign de origen. Por ejemplo, si los documentos de InDesign se almacenan en una carpeta denominada `indesigntodita` in `projects` y, a continuación, especifique la ubicación como: `/content/dam/idmlfiles/indesigntodita/`

   - En el`outputDir` , especifique la ubicación de la carpeta de salida o mantenga la ubicación de salida por defecto para guardar el documento DITA convertido. Si la carpeta de salida especificada no existe en DAM, el flujo de trabajo de conversión crea la carpeta de salida.

   - En el `mapStyle` , especifique la ubicación del fichero de mapa que contiene asignaciones para estilos de documento de InDesign a elementos DITA. La asignación predeterminada se almacena en el archivo ubicado en:

     ```
     /stmap.adobeidml.xml
     ```

     >[!NOTE]
     >
     > Para obtener más información sobre la estructura de `stmap.adobeidml.xml` y cómo puede personalizarlo, consulte la sección [apéndice.md\#id194AF0003HT](appendix.md#id194AF0003HT) en el apéndice.

1. Guarde el archivo `idml2dita_io.xml`.

1. Después de configurar los parámetros necesarios en la variable `idml2dita_io.xml` AEM , inicie sesión en la interfaz de usuario de Assets y ábrala.

1. Vaya a la ubicación de la carpeta de entrada \(`indesigntodita`\).

1. Cargue los documentos del InDesign de origen en esta carpeta. Para obtener información sobre la carga de contenido en DAM, consulte [Cargar contenido DITA existente](migrate-content-upload-existing-dita-content.md#).


## Migrar documentos XHTML {#id1949B04L0Y4}

AEM Guías de le permite convertir los documentos XHTML existentes en documentos de tipo de tema DITA. Es necesario especificar las ubicaciones de las carpetas de entrada y salida junto con otros parámetros y los documentos se convierten al formato DITA. Puede utilizar dos métodos para convertir los documentos estructurados de HTML:

- Cargar todos los documentos en la carpeta de entrada o
- Cree un ZIP de todos los documentos junto con los archivos multimedia y cárguelo en la carpeta de entrada. Este método se utiliza generalmente para un conjunto de archivos de HTML vinculados entre sí y con una tabla de contenido \(index.html\). El archivo index.html contiene vínculos a todos los archivos de HTML del conjunto.

Tanto si se cargan todos los ficheros de forma individual como agrupados en un ZIP, el proceso de conversión crea una asignación uno a uno entre los ficheros de HTML y los ficheros DITA resultantes. Esto significa esencialmente que hay un archivo .dita creado para cada archivo .html en la carpeta de entrada.

Se deben tener en cuenta los siguientes puntos a la hora de cargar los documentos en un archivo ZIP:

- Todos los temas a los que se hace referencia deben colocarse dentro del archivo ZIP.

- Se debe hacer referencia a todos los archivos multimedia referenciados dentro de los archivos de tema mediante un vínculo relativo.

- Cree un archivo index.html y agregue vínculos a los temas que desee agregar en el índice. Este fichero index.html se utiliza para crear el fichero de mapa DITA. En el archivo index.html, también puede crear una lista de temas anidados como se muestra en el siguiente ejemplo de código:

  ```
  <?xml version="1.0" encoding="UTF-8"?>
  <html
  xmlns="http://www.w3.org/1999/xhtml">
      <head>
          <title>Sample Index File</title>
      </head>
      <body>
          <h1>Sample Index</h1>
          <div class="content">
              <ul class="book">
                  <li class="topicref">
                      <a href="Topic1.html">Topic 1</a>
                      <ul class="book">
                          <li class="topicref">
                              <a href="Topic1-1.html">Topic 1.1</a>
                          </li>
                          <li class="topicref">
                              <a href="Topic1-2.html">Topic 1.2</a>
                          </li>
                      </ul>
                  </li>
                  <li class="topicref">
                      <a href="Topic2.html">Topic 2</a>
                  </li>
              </ul>
          </div>
      </body>
  </html>
  ```

  Observe que cada `ul` la etiqueta debe tener el valor `class` atributo establecido en `book`. Del mismo modo, cada `li` de la etiqueta `class` se debe establecer en `topicref`.

- Si utiliza estilos en línea, convierta los estilos en línea a clases de estilos basadas en CSS en el archivo XHTML. A continuación, utilice la asignación de atributos de estilo para convertir estos estilos basados en clases a DITA `outputclass` en el fichero DITA convertido.

  Al generar la salida del HTML AEM o del sitio de la a partir de estos archivos DITA, la variable `outputclass` Los atributos de se pueden utilizar para aplicar la clase de estilo en el HTML AEM o sitio de la aplicación generado para que coincida con el contenido del HTML de origen.


Aparte de las consideraciones para crear el archivo ZIP, el documento XHTML también debe estar bien estructurado. Por ejemplo, el documento debe tener un *Título*, seguido de *Encabezado 1*, *Encabezado 2*, etc. Cada uno de los encabezados debe tener algún contenido. Si el documento no está bien estructurado, es posible que el proceso de migración no funcione según lo esperado.

Para convertir el documento XHTML existente en un tema DITA, realice los siguientes pasos:

1. Utilice el Administrador de paquetes para descargar el archivo /libs/fmdita/config/h2d\_io.xml.

1. Personalice el archivo h2d\_io.xml descargado.

1. Añada el archivo en la siguiente ubicación del repositorio de Git de Cloud Manager:

   /apps/fmdita/config/h2d\_io.xml

   El `h2d_io.xml` contiene los siguientes parámetros configurables:

   - En el `inputDir` , especifique la ubicación de la carpeta de entrada donde están disponibles los documentos XHTML de origen. Por ejemplo, si los documentos XHTML se almacenan en una carpeta denominada `xhtmltodita` in `projects` y, a continuación, especifique la ubicación como: `/content/dam/projects/xhtmltodita/`

   - En el`outputDir` , especifique la ubicación de la carpeta de salida o mantenga la ubicación de salida predeterminada. Si la carpeta de salida especificada no existe en DAM, el flujo de trabajo de conversión crea la carpeta de salida.

   - Para el `createRev` , especifique si se va a crear una nueva versión del tema DITA convertido \(`true`\) o no \(`false`\).

1. Ejecute la canalización de Cloud Manager para implementar la configuración actualizada.

1. Después de configurar los parámetros necesarios en la variable `w2d_io.xml` AEM , inicie sesión en la interfaz de usuario de Assets y ábrala.

1. *\(Opcional\)* También puede agregar la sección de vínculos relacionados a los documentos convertidos. Siga estos pasos para habilitar esta función:

   >[!NOTE]
   >
   > De forma predeterminada, la sección de vínculos relacionados no se crea en los documentos convertidos.

   1. Utilice el Administrador de paquetes para descargar el archivo /libs/fmdita/html2dita/h2d.xsl.

   2. Busque el siguiente parámetro:

      `<xsl:param name="generate-related-links" select="false()"/>`

   3. Establezca el valor del parámetro anterior en `true()`.

   4. Confirme el archivo actualizado en la siguiente ubicación del repositorio Git de Cloud Manager:

      /libs/fmdita/html2dita/

   5. Ejecute la canalización de Cloud Manager para implementar la configuración actualizada.

1. Vaya a la ubicación de la carpeta de entrada \(`xhtmltodita`\).

1. Cargue los documentos XHTML de origen en esta carpeta. Para obtener información sobre la carga de contenido en DAM, consulte [Cargar contenido DITA existente](migrate-content-upload-existing-dita-content.md#).


Uso del `<config> </config>` , puede definir uno o varios bloques de configuraciones para la conversión. El flujo de trabajo de conversión se ejecuta y la salida final en forma de tema DITA se guarda en la ubicación especificada en la `outputDir` Elemento.

## Migrar documentos de FrameMaker no estructurados {#id1949B050VUI}

AEM Guías de le permite convertir el FrameMaker desestructurado existente \(`.fm` y `.book`\) documentos en documentos DITA. El primer paso es crear asignaciones de estilos mediante el FrameMaker y guardar esa configuración en un archivo .sts. A continuación, si utiliza DITA personalizado, puede asignar los elementos personalizados con los formatos de FrameMaker de origen en la `ditaElems.xml` archivo. Por ejemplo, si ha creado un elemento personalizado denominado `impnote` para gestionar todas las notas importantes, puede definir este elemento personalizado en la variable `ditaElems.xml` archivo. AEM Una vez definido este elemento personalizado, las guías de recursos no generarían un error al convertir el documento de FrameMaker que contiene `impnote` Elemento.

Además, si desea especificar atributos adicionales con el elemento DITA personalizado o válido, puede definirlos en el archivo style2attrMap.xml. Por ejemplo, puede especificar la variable `type` atributo con el valor de `important` que se transmitirá con el `impnote` Elemento. Esta información adicional se puede especificar en el archivo style2attrMap.xml.

Además de especificar

Para convertir los documentos de FrameMaker no estructurados existentes al formato DITA, realice los siguientes pasos:

1. Cree asignaciones de estilos en el FrameMaker y guarde esa configuración en un archivo .sts.

1. Utilice el Administrador de paquetes para descargar el archivo /libs/fmdita/config/ditaElems.xml.

1. Si tiene elementos DITA personalizados, defina los mismos en la `ditaElems.xml` archivo disponible en la siguiente ubicación:

   `/libs/fmdita/config/ditaElems.xml`

1. Cree una copia del archivo ditaElems.xml en la siguiente ubicación del repositorio de Git de Cloud Manager:

   `/apps/fmdita/config/ditaElems.xml`

1. Vaya al archivo de configuración disponible en la `apps` nodo:

   `/apps/fmdita/config/ditaElems.xml`

   El `ditaElems.xml` contiene un único parámetro configurable:

   - En el `elem` , especifique el nombre del elemento personalizado que desea utilizar en los documentos DITA convertidos. Este elemento se transferiría tal cual en los documentos DITA generados.

1. Si desea especificar atributos adicionales, defina los mismos en la variable `style2attrMap.xml` archivo disponible en la siguiente ubicación:

   `/libs/fmdita/config/style2attrMap.xml`

1. Cree un nodo de superposición de `config` carpeta dentro de `apps` nodo.

1. Vaya al archivo de configuración disponible en la `apps` nodo:

   `/apps/fmdita/config/style2attrMap.xml`

   El `style2attrMap.xml` contiene los siguientes parámetros configurables:

   - En el `fmStyle` , especifique el formato de origen utilizado en el documento de FrameMaker que desea asignar.

   - En el`ditaAttr` , especifique el atributo DITA que desea asignar con el formato de origen.

   - En el `ditaVal` , especifique el valor del atributo asignado. Si no tiene ningún valor, puede dejar esta entrada en blanco.

1. Guarde el archivo `style2attrMap.xml`.

1. Después de configurar los parámetros necesarios en la variable `style2attrMap.xml` AEM , inicie sesión en la interfaz de usuario de Assets y ábrala.

1. Desplácese hasta el documento de FrameMaker que desee convertir y haga clic en él.

   Aparecerá la consola de mapas DITA con la lista de ajustes preestablecidos de salida disponibles para generar resultados.

1. Seleccione el formato de salida DITA y configure los parámetros necesarios.

   >[!NOTE]
   >
   > Debe utilizar el mismo archivo de configuración \(.sts\) que creó en el FrameMaker. Especifique también el Nombre de configuración y la Ruta de destino.

1. Haga clic en **Generar** para iniciar el proceso de generación de resultados.


Uso del `<attrMap> </attrMap>` , puede definir uno o varios bloques de configuraciones para la conversión. Según el contenido, podría tener un archivo .dita y un archivo .ditamap como archivos convertidos.

## Migrar cualquier otro documento estructurado {#id1949B0590YK}

AEM Guías de le permite convertir los documentos estructurados existentes en documentos DITA válidos. Debe especificar las ubicaciones de las carpetas de entrada y salida, la ubicación del archivo de transformación, la extensión con la que se guardará la salida final y si se requiere o no una nueva versión del documento.

Para convertir los documentos estructurados existentes al formato DITA, realice los siguientes pasos:

1. Utilice el Administrador de paquetes para descargar el archivo /libs/fmdita/config/XSLConfig.xml.

1. Cree una copia del archivo XSLConfig.xml en la siguiente ubicación del repositorio Git de Cloud Manager:

   `/apps/fmdita/config/XSLConfig.xml`

   El `XSLConfig.xml` contiene los siguientes parámetros configurables:

   - En el `inputDir` , especifique la ubicación de la carpeta de entrada donde están disponibles los documentos estructurados de origen. Por ejemplo, si los documentos estructurados se almacenan en una carpeta denominada `xsltodita` in `projects` y, a continuación, especifique la ubicación como: `/content/dam/projects/xsltodita/`

   - En el`outputDir` , especifique la ubicación de la carpeta de salida o mantenga la ubicación de salida predeterminada. Si la carpeta de salida especificada no existe en DAM, el flujo de trabajo de conversión crea la carpeta de salida.

   - En el `xslFolder` , especifique la ubicación de la carpeta donde se almacenan los archivos de transformación XSL.

   - En el ``xslPath`` , especifique la ubicación del archivo .XSL principal que se utiliza para iniciar el proceso de conversión.

   - En el ``outputExt`` especifique las extensiones de archivo del archivo de salida final que se crea a partir de la secuencia de transformación.

   - Para el `createRev` , especifique si se va a crear una nueva versión del tema DITA convertido \(`true`\) o no \(`false`\).

1. Guarde el archivo `XSLConfig.xml`.

1. Después de configurar los parámetros necesarios en la variable `XSLConfig.xml` AEM , inicie sesión en la interfaz de usuario de Assets y ábrala.

1. Vaya a la ubicación de la carpeta de entrada \(`xsltodita`\).

1. Cargue los documentos estructurados de origen en esta carpeta. Para obtener información sobre la carga de contenido en DAM, consulte [Cargar contenido DITA existente](migrate-content-upload-existing-dita-content.md#).


Uso del `<config> </config>` , puede definir uno o varios bloques de configuraciones para la conversión. El flujo de trabajo de conversión se ejecuta y la salida final en forma de tema DITA se guarda en la ubicación especificada en la `outputDir` Elemento.

**Tema principal:**[ Migrar contenido existente](migrate-content.md)
