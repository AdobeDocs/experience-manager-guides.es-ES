---
title: Migración de contenido no DITA
description: Obtenga información sobre cómo migrar contenido no DITA
exl-id: cf437fb8-ed33-47af-aa7e-ffd8acd232da
feature: Migration
role: Admin
level: Experienced
source-git-commit: cddbd7a19d4dfaa3f6549ed1bd511eeeb02acbb2
workflow-type: tm+mt
source-wordcount: '2940'
ht-degree: 0%

---

# Migración de contenido no DITA {#id181AH0R02HT}

Esta sección le guía a través del proceso de migración para migrar documentos que no son DITA al formato DITA. AEM Guides proporciona migración desde las siguientes fuentes:

- [Microsoft Word](#id1949B040Z5Z)

- [documentos de InDesign](#id195AD0B0K5Z)

- [XHTML](#id1949B04L0Y4)

- [Documentos de FrameMaker no estructurados](#id1949B050VUI)

- [Cualquier otro documento estructurado](#id1949B0590YK)


## Migrar documentos de Microsoft Word {#id1949B040Z5Z}

AEM Guides permite migrar los documentos existentes de Word \(`.docx`\) a documentos de tipo de tema DITA. Es necesario especificar las ubicaciones de las carpetas de entrada y salida junto con otros parámetros y el documento se convierte en un documento DITA. Según el contenido, podría tener un archivo .dita y un archivo .ditamap.

Para poder convertir un documento de Word correctamente, el documento debe estar bien estructurado. Por ejemplo, el documento debe tener un Título, seguido de Título 1, Título 2, etc. Cada uno de los encabezados debe tener algún contenido. Si el documento no está bien estructurado, es posible que el proceso no funcione según lo esperado.

De manera predeterminada, AEM Guides usa el marco de trabajo de transformación [Word a DITA \(Word2DITA\)](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/word2dita-intro.html). Esta transformación depende del archivo de configuración de [asignación de estilo a etiqueta](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html). Para poder utilizar correctamente la transformación de Word2DITA, debe tener en cuenta las siguientes directrices para preparar el documento de Word para la conversión:

>[!NOTE]
>
> Si realiza cambios en el archivo de configuración de asignación de estilo a etiqueta predeterminado, debe actualizar y utilizar las directrices que confirmen la actualización de la asignación de estilo.

- Asegúrese de que el documento comienza con un Título; este Título se asigna al título del mapa DITA. Además, el Título debe ir seguido de algún contenido normal.

- Después del Título, debe haber Encabezado 1, Encabezado 2, etc. Cada encabezado debe tener algún contenido. Los Encabezados se convierten en nuevos temas de tipo Concepto. La jerarquía de los temas generados se ajusta a los niveles de Encabezado del documento. Por ejemplo, el Encabezado 1 precederá al Encabezado 2 y el Encabezado 2 al contenido del Encabezado 3.

- El documento debe tener al menos un contenido de tipo Título.

- Asegúrese de que no tiene ninguna imagen agrupada. Si ha agrupado imágenes en el documento, desagrupe todas esas imágenes.

- Quitar todos los encabezados y pies de página.

- Los estilos en línea como negrita, cursiva y subrayado se convierten en elementos `b`, `i` y `u`.

- Todas las listas ordenadas y sin ordenar se convierten en `ol` y `ul` elementos. Esto también se aplica a listas anidadas, listas dentro de tablas, notas o notas al pie.

- Todos los hipervínculos se convierten en `xref`.

- El nombre de archivo de los archivos convertidos se basa en el texto de encabezado seguido de un número de archivo. El número de archivo es un número secuencial basado en la posición del texto del encabezado en el documento. Por ejemplo, si el texto de un encabezado es &quot;Encabezado de muestra&quot; y es el décimo encabezado del documento, el nombre de archivo resultante para este tema será similar a Ejemplo\_Encabezado\_10.dita.


Realice los siguientes pasos para convertir los documentos de Word existentes en un documento de tipo de tema DITA:

1. Utilice el Administrador de paquetes para descargar el archivo /libs/fmdita/config/w2d\_io.xml.

1. Personalice el archivo w2d\_io.xml descargado.

1. Añada el archivo en la siguiente ubicación del repositorio Git de Cloud Manager:

   /apps/fmdita/config/w2d\_io.xml

   El archivo `w2d_io.xml` contiene los siguientes parámetros configurables:

   - En el elemento `inputDir`, especifique la ubicación de la carpeta de entrada donde están disponibles los documentos de Word de origen. Por ejemplo, si los documentos de Word están almacenados en una carpeta denominada `wordtodita` en la carpeta `projects`, especifique la ubicación como: `/content/dam/projects/wordtodita/`

   - En el elemento `outputDir`, especifique la ubicación de la carpeta de salida o mantenga la ubicación de salida predeterminada para guardar el documento DITA convertido. Si la carpeta de salida especificada no existe en DAM, el flujo de trabajo de conversión crea la carpeta de salida.

   - Para el elemento `createRev`, especifique si se va a crear una nueva versión del tema DITA convertido \(`true`\) o no \(`false`\).

   - En el elemento `s2tMap`, especifique la ubicación del archivo de asignación que contiene asignaciones para estilos de documento de Word a elementos DITA. La asignación predeterminada se almacena en el archivo ubicado en:

     ```
     /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
     ```

     >[!NOTE]
     >
     > Para obtener más información acerca de la estructura del archivo `word-builtin-styles-style2tagmap.xml` y cómo personalizarlo, consulte [Asignación de estilo a etiqueta](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html) en la *Guía del usuario de DITA para editores*.

   - En el elemento props2Propagate, especifique las propiedades que deben pasarse al mapa DITA. Esta propiedad es necesaria para pasar metadatos predeterminados como dc:title, dc:subject, dam:keywords, dam:category de metadatos de documento a recursos DITA convertidos.

1. Ejecute la canalización de Cloud Manager para implementar la configuración actualizada.

1. AEM Después de configurar los parámetros requeridos en el archivo `w2d_io.xml`, inicie sesión en la interfaz de usuario de Assets y ábrala en la página de inicio de sesión de la página de inicio de sesión de.

1. Vaya a la ubicación de la carpeta de entrada \(`wordtodita`\).

1. Cargue los documentos de origen de Word en esta carpeta. Para obtener información sobre cómo cargar contenido en DAM, consulte [Cargar contenido DITA existente](migrate-content-upload-existing-dita-content.md#).


Con el bloque `config` `/config`, puede definir uno o varios bloques de configuraciones para la conversión. El flujo de trabajo de conversión se ejecuta y el resultado final en forma de tema DITA se guarda en la ubicación especificada en el elemento `outputDir`.

**Actualizaciones de personalización para usuarios existentes**

Si es un usuario existente del as a Cloud Service de AEM Guides y actualiza de la versión de agosto de 2021 a la versión de enero de 2022 o superior, actualice las propiedades dadas ya que se han movido pocos archivos.

>[!NOTE]
>
> Esta actualización solo es aplicable si ya está utilizando el flujo de trabajo de conversión de Microsoft Word a DITA.

- Ruta de archivo: /apps/fmdita/config/w2d\_io.xml
- Cambie el valor de `<s2tMap>` de /apps/dxml/word2dita/word-builtin-styles-style2tagmap.xml a /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
- Realice los cambios necesarios en el repositorio de Git de Cloud Manager, ya que para el servicio en la nube todos los archivos de /apps se superponen a través de Git de Cloud Manager.

## Migrar documentos de Adobe InDesign {#id195AD0B0K5Z}

AEM Guides le permite convertir documentos de InDesign. Al igual que el FrameMaker, el InDesign también le permite crear documentos no estructurados y estructurados. Los documentos no estructurados utilizan los estilos de párrafo y carácter para dar formato al contenido. El documento estructurado utiliza elementos y sus atributos correspondientes.

El proceso de conversión requiere la asignación de los formatos de estilo de párrafo y carácter a los elementos DITA relevantes. Del mismo modo, en el caso de los documentos estructurados, el fichero de asignación contendrá una asignación uno a uno de elementos y atributos de InDesign con elementos y atributos DITA.

El proceso de conversión implica las siguientes acciones en el servidor:

- El archivo *Lenguaje de marcado de InDesign* \(IDML\) se ha desempaquetado en un directorio de trabajo.
- El archivo designmap.xml se lee para localizar las historias de InDesign individuales.
- Todas las historias se combinan en una sola instancia XML, las historias &quot;vacías&quot; se descartan.
- Se exportan todos los gráficos incrustados.
- Conversión previa de estructuras estándar como tablas y gráficos al formato DITA.
- Asignación de estilo o estructura a la salida final en función del archivo de asignación.
- Creación y validación de temas DITA individuales y ficheros de mapa DITA.
- Eliminación de archivos temporales.

En términos generales, el proceso de conversión requiere que [Prepare los archivos de InDesign para la conversión](appendix.md#id195DBF0045Z)[apendice.md\#id195DBF0045Z](appendix.md#id195DBF0045Z) y [Prepare el archivo de asignación para la migración de InDesign a DITA](appendix.md#id194AF0003HT)[apendice.md\#id194AF0003HT](appendix.md#id194AF0003HT). A continuación, deberá seguir el procedimiento dado para ejecutar el proceso de conversión.

Realice los siguientes pasos para convertir los documentos de InDesign existentes en un documento de tipo de tema DITA:

1. AEM Inicie sesión en la aplicación y abra el modo CRXDE Lite.

1. Vaya al archivo de configuración predeterminado disponible en la siguiente ubicación:

   `/libs/fmdita/config/idml2dita_io.xml`
1. Para crear una configuración personalizada según sus necesidades, cree un nodo de superposición de la carpeta `config` dentro del nodo `apps`.

1. Copie los siguientes archivos o carpetas de la carpeta `libs` a la carpeta de aplicaciones:

   - `/fmdita/config/idml2dita_io.xml`
   - `/fmdita/idml2dita/config`
   - `/fmdita/idml2dita/xsl`

1. Vaya al archivo de configuración disponible en el nodo `apps`:

   `/apps/fmdita/config/idml2dita_io.xml`

1. Agregue la asignación de las configuraciones presentes en la carpeta `idml12dita` dentro del archivo `idml2dita_io.xml`.
1. Agregue las siguientes propiedades en el archivo `idml2dita_io.xml`:

   ```
   <entry          key="idml2DitaConfig">/apps/fmdita/idml2dita/config</entry>
   
   <entry key="idml2DitaXsl">/apps/fmdita/idml2dita/xsl</entry>
   ```

1. Cree un nodo de superposición de la carpeta `config` dentro del nodo `apps`.


   Configure los siguientes parámetros en el archivo `idml2dita_io.xml`:

   - En el elemento `inputDir`, especifique la ubicación de la carpeta de entrada donde están disponibles los documentos de InDesign de origen. Por ejemplo, si los documentos de InDesign están almacenados en una carpeta denominada `indesigntodita` en `projects`, especifique la ubicación como: `/content/dam/idmlfiles/indesigntodita/`

   - En el elemento `outputDir`, especifique la ubicación de la carpeta de salida o mantenga la ubicación de salida predeterminada para guardar el documento DITA convertido. Si la carpeta de salida especificada no existe en DAM, el flujo de trabajo de conversión crea la carpeta de salida.

   - En el elemento `mapStyle`, especifique la ubicación del archivo de asignación que contiene asignaciones para estilos de documento de InDesign a elementos DITA. La asignación predeterminada se almacena en el archivo ubicado en:

     ```
     /stmap.adobeidml.xml
     ```

     >[!NOTE]
     >
     > Para obtener más información acerca de la estructura del archivo `stmap.adobeidml.xml` y cómo personalizarlo, consulte la sección [apéndice.md\#id194AF0003HT](appendix.md#id194AF0003HT) del Apéndice.

1. Guarde el archivo `idml2dita_io.xml`.

1. AEM Después de configurar los parámetros requeridos en el archivo `idml2dita_io.xml`, inicie sesión en la interfaz de usuario de Assets y ábrala en la página de inicio de sesión de la página de inicio de sesión de.

1. Vaya a la ubicación de la carpeta de entrada \(`indesigntodita`\).

1. Cargue los documentos del InDesign de origen en esta carpeta. Para obtener información sobre cómo cargar contenido en DAM, consulte [Cargar contenido DITA existente](migrate-content-upload-existing-dita-content.md#).


## Migrar documentos XHTML {#id1949B04L0Y4}

AEM Guides permite convertir los documentos XHTML existentes en documentos de tipo de tema DITA. Es necesario especificar las ubicaciones de las carpetas de entrada y salida junto con otros parámetros y los documentos se convierten al formato DITA. Puede utilizar dos métodos para convertir los documentos estructurados de HTML:

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

  Observe que cada etiqueta `ul` debe tener el atributo `class` establecido en `book`. Del mismo modo, cada `class` de la etiqueta `li` debe establecerse en `topicref`.

- Si utiliza estilos en línea, convierta los estilos en línea a clases de estilos basadas en CSS en el archivo XHTML. A continuación, utilice la asignación de atributos de estilo para convertir estos estilos basados en clases al atributo DITA `outputclass` en el archivo DITA convertido.

  Al generar la salida del HTML AEM o del sitio de la a partir de estos archivos DITA, los atributos `outputclass` se pueden utilizar para aplicar la clase de estilo en el HTML AEM o sitio de la generado para que coincida con el contenido del HTML de origen.


Aparte de las consideraciones para crear el archivo ZIP, el documento XHTML también debe estar bien estructurado. Por ejemplo, el documento debe tener un *Título*, seguido de *Encabezado 1*, *Encabezado 2*, etc. Cada uno de los encabezados debe tener algún contenido. Si el documento no está bien estructurado, es posible que el proceso de migración no funcione según lo esperado.

Para convertir el documento XHTML existente en un tema DITA, realice los siguientes pasos:

1. Utilice el Administrador de paquetes para descargar el archivo /libs/fmdita/config/h2d\_io.xml.

1. Personalice el archivo h2d\_io.xml descargado.

1. Añada el archivo en la siguiente ubicación del repositorio Git de Cloud Manager:

   /apps/fmdita/config/h2d\_io.xml

   El archivo `h2d_io.xml` contiene los siguientes parámetros configurables:

   - En el elemento `inputDir`, especifique la ubicación de la carpeta de entrada donde están disponibles los documentos XHTML de origen. Por ejemplo, si los documentos XHTML están almacenados en una carpeta denominada `xhtmltodita` en la carpeta `projects`, especifique la ubicación como: `/content/dam/projects/xhtmltodita/`

   - En el elemento `outputDir`, especifique la ubicación de la carpeta de salida o mantenga la ubicación de salida predeterminada. Si la carpeta de salida especificada no existe en DAM, el flujo de trabajo de conversión crea la carpeta de salida.

   - Para el elemento `createRev`, especifique si se va a crear una nueva versión del tema DITA convertido \(`true`\) o no \(`false`\).

1. Ejecute la canalización de Cloud Manager para implementar la configuración actualizada.

1. AEM Después de configurar los parámetros requeridos en el archivo `w2d_io.xml`, inicie sesión en la interfaz de usuario de Assets y ábrala en la página de inicio de sesión de la página de inicio de sesión de.

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

1. Cargue los documentos XHTML de origen en esta carpeta. Para obtener información sobre cómo cargar contenido en DAM, consulte [Cargar contenido DITA existente](migrate-content-upload-existing-dita-content.md#).


Con el bloque `<config> </config>`, puede definir uno o varios bloques de configuraciones para la conversión. El flujo de trabajo de conversión se ejecuta y el resultado final en forma de tema DITA se guarda en la ubicación especificada en el elemento `outputDir`.

## Migrar documentos de FrameMaker no estructurados {#id1949B050VUI}

AEM Guides permite convertir los documentos de FrameMaker no estructurado \(`.fm` y `.book`\) existentes en documentos DITA. El primer paso es crear asignaciones de estilos mediante el FrameMaker y guardar esa configuración en un archivo .sts. A continuación, si está utilizando DITA personalizado, puede asignar los elementos personalizados con los formatos de FrameMaker de origen en el archivo `ditaElems.xml`. Por ejemplo, si ha creado un elemento personalizado denominado `impnote` para administrar todas las notas importantes, puede definir este elemento personalizado en el archivo `ditaElems.xml`. Una vez definido este elemento personalizado, AEM Guides no generaría un error al convertir el documento de FrameMaker que contiene el elemento `impnote`.

Además, si desea especificar atributos adicionales con el elemento DITA personalizado o válido, puede definirlos en el archivo style2attrMap.xml. Por ejemplo, puede especificar el atributo `type` con el valor `important` que se pasará con el elemento `impnote`. Esta información adicional se puede especificar en el archivo style2attrMap.xml.

Además de especificar

Para convertir los documentos de FrameMaker no estructurados existentes al formato DITA, realice los siguientes pasos:

1. Cree asignaciones de estilos en el FrameMaker y guarde esa configuración en un archivo .sts.

1. Utilice el Administrador de paquetes para descargar el archivo /libs/fmdita/config/ditaElems.xml.

1. Si tiene elementos DITA personalizados, defina los del archivo `ditaElems.xml` disponibles en la siguiente ubicación:

   `/libs/fmdita/config/ditaElems.xml`

1. Cree una copia del archivo ditaElements.xml en la siguiente ubicación del repositorio Git de Cloud Manager:

   `/apps/fmdita/config/ditaElems.xml`

1. Vaya al archivo de configuración disponible en el nodo `apps`:

   `/apps/fmdita/config/ditaElems.xml`

   El archivo `ditaElems.xml` contiene un solo parámetro configurable:

   - En el parámetro `elem`, especifique el nombre del elemento personalizado que desea utilizar en los documentos DITA convertidos. Este elemento se transferiría tal cual en los documentos DITA generados.

1. Si desea especificar atributos adicionales, defina los del archivo `style2attrMap.xml` disponibles en la siguiente ubicación:

   `/libs/fmdita/config/style2attrMap.xml`

1. Cree un nodo de superposición de la carpeta `config` dentro del nodo `apps`.

1. Vaya al archivo de configuración disponible en el nodo `apps`:

   `/apps/fmdita/config/style2attrMap.xml`

   El archivo `style2attrMap.xml` contiene los siguientes parámetros configurables:

   - En el parámetro `fmStyle`, especifique el formato de origen utilizado en el documento de FrameMaker que desea asignar.

   - En el elemento `ditaAttr`, especifique el atributo DITA que desea asignar con el formato de origen.

   - En el elemento `ditaVal`, especifique el valor del atributo asignado. Si no tiene ningún valor, puede dejar esta entrada en blanco.

1. Guarde el archivo `style2attrMap.xml`.

1. AEM Después de configurar los parámetros requeridos en el archivo `style2attrMap.xml`, inicie sesión en la interfaz de usuario de Assets y ábrala en la página de inicio de sesión de la página de inicio de sesión de.

1. Desplácese hasta el documento de FrameMaker que desee convertir y haga clic en él.

   Aparecerá la consola de mapas DITA con la lista de ajustes preestablecidos de salida disponibles para generar resultados.

1. Seleccione el formato de salida DITA y configure los parámetros necesarios.

   >[!NOTE]
   >
   > Debe utilizar el mismo archivo de configuración \(.sts\) que creó en el FrameMaker. Especifique también el Nombre de configuración y la Ruta de destino.

1. Haga clic en el icono **Generar** para iniciar el proceso de generación de resultados.


Con el bloque `<attrMap> </attrMap>`, puede definir uno o varios bloques de configuraciones para la conversión. Según el contenido, podría tener un archivo .dita y un archivo .ditamap como archivos convertidos.

## Migrar cualquier otro documento estructurado {#id1949B0590YK}

AEM Guides permite convertir los documentos estructurados existentes en documentos DITA válidos. Debe especificar las ubicaciones de las carpetas de entrada y salida, la ubicación del archivo de transformación, la extensión con la que se guardará la salida final y si se requiere o no una nueva versión del documento.

Para convertir los documentos estructurados existentes al formato DITA, realice los siguientes pasos:

1. Utilice el Administrador de paquetes para descargar el archivo /libs/fmdita/config/XSLConfig.xml.

1. Cree una copia del archivo XSLConfig.xml en la siguiente ubicación del repositorio Git de Cloud Manager:

   `/apps/fmdita/config/XSLConfig.xml`

   El archivo `XSLConfig.xml` contiene los siguientes parámetros configurables:

   - En el elemento `inputDir`, especifique la ubicación de la carpeta de entrada donde están disponibles los documentos estructurados de origen. Por ejemplo, si los documentos estructurados están almacenados en una carpeta denominada `xsltodita` de la carpeta `projects`, especifique la ubicación como: `/content/dam/projects/xsltodita/`

   - En el elemento `outputDir`, especifique la ubicación de la carpeta de salida o mantenga la ubicación de salida predeterminada. Si la carpeta de salida especificada no existe en DAM, el flujo de trabajo de conversión crea la carpeta de salida.

   - En el elemento `xslFolder`, especifique la ubicación de la carpeta donde se almacenan los archivos de transformación XSL.

   - En el elemento ``xslPath``, especifique la ubicación del archivo .XSL principal que se utiliza para iniciar el proceso de conversión.

   - En el elemento ``outputExt``, especifique las extensiones de archivo del archivo de salida final que se crea a partir de la secuencia de transformación.

   - Para el elemento `createRev`, especifique si se va a crear una nueva versión del tema DITA convertido \(`true`\) o no \(`false`\).

1. Guarde el archivo `XSLConfig.xml`.

1. AEM Después de configurar los parámetros requeridos en el archivo `XSLConfig.xml`, inicie sesión en la interfaz de usuario de Assets y ábrala en la página de inicio de sesión de la página de inicio de sesión de.

1. Vaya a la ubicación de la carpeta de entrada \(`xsltodita`\).

1. Cargue los documentos estructurados de origen en esta carpeta. Para obtener información sobre cómo cargar contenido en DAM, consulte [Cargar contenido DITA existente](migrate-content-upload-existing-dita-content.md#).


Con el bloque `<config> </config>`, puede definir uno o varios bloques de configuraciones para la conversión. El flujo de trabajo de conversión se ejecuta y el resultado final en forma de tema DITA se guarda en la ubicación especificada en el elemento `outputDir`.

**Tema principal:**[ Migrar contenido existente](migrate-content.md)
