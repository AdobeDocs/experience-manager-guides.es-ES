---
title: Configuración de la generación de salida
description: Obtenga información sobre cómo configurar los ajustes de generación de resultados
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '3314'
ht-degree: 1%

---

# Configuración de la generación de salida {#id181AI0B0E30}

AEM Guides incluye muchas opciones de configuración para que personalice el proceso de generación de resultados. Este tema cubre todas las configuraciones y personalizaciones que le ayudarán a configurar su proceso de generación de resultados.

## Configure la ficha Línea base en el tablero de mandos de asignación DITA {#id223MD0D0YRM}

Las siguientes pestañas proporcionan instrucciones para ocultar la pestaña Línea de base en el panel de mapas DITA en función de la configuración de Experience Manager Guides: Cloud Service o Local.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración.
1. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar la pestaña de línea de base en el panel de asignaciones.

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `hide.tabs.baseline` | Boolean\(`true/false`\).**Valor predeterminado**: `true` |

>[!NOTE]
>
> Esta configuración está habilitada de forma predeterminada y la pestaña Línea base no está disponible en el panel de asignaciones.

>[!TAB Local]

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.config.ConfigManager**.

1. Seleccione la opción **Ocultar ficha Línea de base**.

1. Haga clic en **Guardar**.

>[!NOTE]
>
> Esta configuración está desactivada de forma predeterminada y la pestaña Línea base está disponible en el panel de asignaciones.

>[!ENDTABS]


## Configuración de la publicación combinada en un sitio de AEM existente {#id1691I0V0MGR}

Si tiene un sitio de AEM con contenido DITA, puede configurar la salida del sitio de AEM para publicar contenido DITA en una ubicación predefinida dentro del sitio. Por ejemplo, en la siguiente captura de pantalla de una página de un sitio de AEM, el nodo `ditacontent` está reservado para almacenar contenido DITA:

![](assets/publish-in-aem-site.png)

Los nodos restantes de la página se crean directamente desde el editor del sitio de AEM. La configuración de publicación para publicar contenido DITA en una ubicación predefinida garantiza que el proceso de publicación de AEM Guides no modifique ningún contenido que no sea DITA.

Es necesario realizar las siguientes configuraciones en el sitio existente para permitir la publicación de contenido DITA en un nodo predefinido:

- Configurar las propiedades de la plantilla del sitio

- Añadir nodos en el sitio para publicar contenido DITA


Las siguientes pestañas proporcionan instrucciones para configurar las propiedades de plantilla del sitio existente en función de la configuración de Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Utilice el Administrador de paquetes para descargar el archivo /libs/fmdita/config/templates/default.

   >[!NOTE]
   >
   > No realice ninguna personalización en los archivos de configuración predeterminados disponibles en el nodo `libs`. Debe crear una superposición del nodo `libs` en el nodo `apps` y actualizar los archivos necesarios solo en el nodo `apps`.

1. Añada las siguientes propiedades:

   | Nombre de la propiedad | Tipo | Valor  |
   |-------------|----|-----|
   | `topicContentNode` | Cadena | Especifique el nombre del nodo donde desea publicar el contenido DITA. Por ejemplo, el nodo predeterminado donde AEM Guides publica contenido DITA es: <br> `jcr:content/contentnode` |
   | `topicHeadNode` | Cadena | Especifique el nombre del nodo donde desea almacenar la información de metadatos del contenido DITA. Por ejemplo, el nodo predeterminado donde AEM Guides almacena información de metadatos es: <br> `jcr:content/headnode` |


La próxima vez que publique contenido DITA con las configuraciones de plantilla del sitio, el contenido se publicará en los nodos especificados en las propiedades `topicContentNode` y `topicHeadNode`.

>[!TAB Local]

1. Inicie sesión en AEM y abra el modo CRXDE Lite.

1. Vaya al nodo de configuración de la plantilla del sitio. Por ejemplo, AEM Guides almacena las configuraciones de plantilla predeterminadas en el siguiente nodo:

   `/libs/fmdita/config/templates/default`

   >[!NOTE]
   >
   > No realice ninguna personalización en los archivos de configuración predeterminados disponibles en el nodo `libs`. Debe crear una superposición del nodo `libs` en el nodo `apps` y actualizar los archivos necesarios solo en el nodo `apps`.

1. Añada las siguientes propiedades:

   | Nombre de la propiedad | Tipo | Valor  |
   |-------------|----|-----|
   | `topicContentNode` | Cadena | Especifique el nombre del nodo donde desea publicar el contenido DITA. Por ejemplo, el nodo predeterminado donde AEM Guides publica contenido DITA es: <br>`jcr:content/contentnode` |
   | `topicHeadNode` | Cadena | Especifique el nombre del nodo donde desea almacenar la información de metadatos del contenido DITA. Por ejemplo, el nodo predeterminado donde AEM Guides almacena información de metadatos es: <br>`jcr:content/headnode` |


La siguiente captura de pantalla muestra las propiedades agregadas en el nodo de plantilla predeterminado de AEM Guides:

![](assets/add-content-node.png){width="800" align="left"}

La próxima vez que publique contenido DITA con las configuraciones de plantilla del sitio, el contenido se publicará en los nodos especificados en las propiedades `topicContentNode` y `topicHeadNode`.

Sin embargo, para los sitios existentes, debe agregar manualmente los nodos `topicContentNode` y `topicHeadNode`.

Realice los siguientes pasos para agregar los nodos necesarios al sitio existente:

1. Inicie sesión en AEM y abra el modo CRXDE Lite.

1. Busque `jcr:content` dentro del nodo del sitio.

1. Agregue `topicContentNode` y `topicHeadNode` nodos con el mismo nombre especificado en las configuraciones de plantilla del sitio.

>[!ENDTABS]

## Configurar ubicación de salida base para la publicación

Las siguientes pestañas proporcionan instrucciones para configurar la ubicación de salida base en función de la configuración de Experience Manager Guides: Cloud Service o Local.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md) para crear el archivo de configuración.

1. En el archivo de configuración, proporcione los siguientes detalles (propiedad) para configurar la ubicación de salida base:

   | PID | Clave de propiedad | Valor de propiedad |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `base.output.path` | **Valor predeterminado:** &quot;/content/dam/fmdita-output&quot; |

>[!TAB Local]

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete *com.adobe.fmdita.config.ConfigManager*.

1. Actualice la propiedad **Base Output Location** para especificar la ruta predeterminada en el repositorio de AEM donde se guardará PDF después de la publicación. Además, si se escribe una ruta de acceso no válida, se revertirá automáticamente a la ruta de acceso predeterminada: `/content/dam/fmdita-outputs`.

1. Haga clic en **Guardar**.

>[!ENDTABS]

## Usar metadatos en la salida de publicación mediante DITA-OT {#id191LF0U0TY4}

AEM Guides proporciona una forma de pasar metadatos personalizados al publicar resultados mediante DITA-OT. Como administrador y publicador, deberá realizar las siguientes tareas para configurar y utilizar metadatos personalizados en el resultado publicado:

- Como administrador, añada los metadatos requeridos en el sistema para que estén disponibles en la página Propiedades del mapa DITA.

- Como administrador, añada los metadatos personalizados a la lista de metadatos para que aparezcan en la consola de mapas DITA.

- Como editor, configure y añada los metadatos personalizados con el mapa DITA y genere la salida requerida.


Para añadir los metadatos necesarios en el sistema, realice los siguientes pasos:

1. Inicie sesión en Adobe Experience Manager como administrador.

1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.

1. Seleccione **Assets** de la lista de herramientas.

1. Haga clic en el mosaico **Esquemas de metadatos**.

   Se muestra la página Forms del esquema de metadatos.

1. Seleccione el formulario **default** de la lista.

   >[!NOTE]
   >
   > Las propiedades mostradas en la página Propiedades de un mapa DITA se toman de este formulario.

1. Haga clic en **Editar**.

1. Añada los metadatos personalizados que desee utilizar en las salidas publicadas. Por ejemplo, agregaremos metadatos de audiencia siguiendo los pasos siguientes:

   1. Desde la lista de componentes **Generar formulario**, arrastre y suelte el componente **Texto de una sola línea** en el formulario.

   2. Seleccione el nuevo campo para abrir **Configuración** del campo.

   3. En la **Etiqueta de campo**, escriba el nombre de los metadatos— Audiencia.

   4. En la configuración **Asignar a propiedad**, especifique/jcr:content/metadata/&lt;nombre de los metadatos\>. Para nuestro ejemplo, lo estableceremos en ./jcr:content/metadata/audience.

   Siga estos pasos para agregar todos los parámetros de metadatos necesarios.

1. Haga clic en **Guardar**.


El nuevo parámetro aparece ahora en la página Propiedades para todos los mapas DITA.

![](assets/properties-page-custom-metadata.PNG)

A continuación, es necesario que los metadatos personalizados estén disponibles en la consola de mapas DITA. Las siguientes pestañas proporcionan instrucciones para que los metadatos personalizados estén disponibles en el tablero de mandos de mapa DITA en función de la configuración de Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Utilice el administrador de paquetes para acceder al archivo metadataList disponible en la siguiente ubicación del repositorio de Git de Cloud Manager:

   /libs/fmdita/config/metadataList

   >[!NOTE]
   >
   > El archivo metadataList contiene una lista de propiedades que se muestran en la lista desplegable **Propiedades** de un mapa DITA en el panel de asignaciones. De forma predeterminada, hay cuatro propiedades enumeradas en este archivo: docstate, dc:language, dc:description y dc:title.

1. Añada los metadatos personalizados que ha añadido en la página de Forms del esquema de metadatos. Para nuestro ejemplo, añada el parámetro de audiencia al final de la lista predeterminada.

>[!TAB Local]

1. Inicie sesión en AEM y abra el modo CRXDE Lite.

1. Acceda al archivo metadataList disponible en la siguiente ubicación:

   /libs/fmdita/config/metadataList

   >[!NOTE]
   >
   > El archivo metadataList contiene una lista de propiedades que se muestran en la lista desplegable **Propiedades** de un mapa DITA en el panel de asignaciones. De forma predeterminada, hay cuatro propiedades enumeradas en este archivo: docstate, dc:language, dc:description y dc:title.

1. Añada los metadatos personalizados que ha añadido en la página de Forms del esquema de metadatos. Para nuestro ejemplo, añada el parámetro de audiencia al final de la lista predeterminada.

1. Haga clic en **Guardar todo**.

>[!ENDTABS]

Ahora los metadatos personalizados se mostrarán en la lista desplegable **Propiedades** de la consola de mapas DITA.

Por último, como editor, debe incluir los metadatos personalizados en el resultado publicado. Para procesar los metadatos personalizados mientras se genera la salida, realice los siguientes pasos:

1. En la interfaz de usuario de Assets, vaya al mapa DITA que desee publicar.

1. Seleccione el fichero de mapa DITA y abra su página de propiedades.

1. En la página Propiedades, especifique el valor de los metadatos personalizados. Para nuestro ejemplo, hemos especificado un valor de External para el parámetro audience.

   ![](assets/properties-page-custom-metadata-value.png)

1. Haga clic en **Guardar y cerrar**.

1. Pulse en el fichero de mapa DITA para abrir la consola de mapas DITA.

1. En la pestaña **Ajustes preestablecidos de salida**, seleccione el ajuste preestablecido de salida que desee utilizar para generar el resultado.

1. Haga clic en **Editar**.

1. En la lista desplegable **Propiedades**, seleccione las propiedades que desee pasar al proceso de publicación.

   ![](assets/props-in-publish-output.PNG)


Las propiedades/metadatos seleccionados se pasan al proceso de publicación y están disponibles en la salida final.

### Validar el paso de metadatos a DITA-OT para su procesamiento (solo para Cloud Service)

Para validar los valores de metadatos pasados a DITA-OT, se puede utilizar un entorno local con un JAR preparado para la nube. Dado que no podemos acceder al sistema de archivos local en la nube, la única manera de validar el archivo de metadatos es a través de un JAR listo para la nube.

- Nombre de archivo: metadata.xml
- Ubicación del archivo: crx-quickstart/profiles/ditamaps/&lt;ditamap-1234\>

  Para acceder a metadata.xml:

   - Inicie sesión en la ubicación del servidor donde se ejecuta la instancia de AEM.
   - Migre a crx-quickstart/profiles/ditamaps/&lt;newly-created-directory-name\>/metadata.xml.
- Formato de archivo de muestra:

  **metadata.xml**

  ```XML
  <?xml version="1.0" encoding="UTF-8" standalone="no"?>
  <root>
     <Path id="/absolutePath/sampleMap.ditamap">
        <metadata>
           <meta isArray="false" key="dc:description">This is a file</meta>
           <meta isArray="false" key="dc:title">Myfile</meta>
           <meta isArray="true" key="multivalueText">One;Two;Three</meta>
        </metadata>
     </Path>
     <Path id="/absolutePath/sampleTopic.dita">
        <metadata>
           <meta isArray="false" key="dc:description">description for the accountability</meta>
           <meta isArray="false" key="dc:title">accountability title</meta>
           <meta isArray="true" key="multivalueText">value1</meta>
        </metadata>
     </Path>
  </root>
  ```


- isArray: Atributo booleano que define si los metadatos son de varios valores \(Array\) o no. Los valores están delimitados por un punto y coma.
- ID de ruta: ruta absoluta al archivo almacenado en el directorio temporal.

>[!NOTE]
>
> Si no hay metadatos específicos para el archivo, la etiqueta &lt;meta\> con la clave no aparecerá como la propiedad para ese archivo en el archivo metadata.xml.

## Configure el campo de argumento de línea de comandos DITA-OT para aceptar metadatos de mapa raíz (solo para Cloud Service)

Para utilizar el campo de argumento de línea de comandos DITA-OT para pasar metadatos de mapa raíz, realice los siguientes pasos:

1. Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración.
1. En el fichero de configuración, proporcione los siguientes detalles \(property\) para configurar el campo del argumento de la línea de comandos DITA-OT en el ajuste preestablecido:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `pass.metadata.args.cmd.line` | Boolean\(`true/false`\).**Valor predeterminado**: `true` |

- Si se establece el valor de la propiedad en **true**, se habilita la funcionalidad de línea de comandos DITA-OT, lo que permite pasar los metadatos a través de la línea de comandos DITA-OT.
- Si se establece el valor de la propiedad en **false**, se deshabilita la funcionalidad de línea de comandos DITA-OT. A continuación, puede utilizar el campo Propiedad en el ajuste preestablecido para pasar los metadatos.

## Personalizar la consola de mapas DITA {#id188HC08M0CZ}

AEM Guides le ofrece la flexibilidad de ampliar las capacidades de la consola de mapas DITA. Por ejemplo, si tiene un conjunto de informes que son diferentes de los disponibles en AEM Guides, puede agregar dichos informes a la consola de mapas. Para personalizar la consola de asignaciones, debe crear una Biblioteca de cliente de AEM \(o ClientLib\) que contenga el código para realizar la funcionalidad que necesita.

>[!NOTE]
>
> No se recomienda la modificación directa a los componentes de la página, ya que se sobrescribirá con las nuevas versiones del producto.

AEM Guides proporciona la categoría `apps.fmdita.dashboard-extn` para personalizar la consola de mapas. Cada vez que se carga la consola de mapas, se ejecuta y carga la funcionalidad creada en la categoría `apps.fmdita.dashboard-extn`.

>[!NOTE]
>
> Para obtener más información acerca de cómo crear la biblioteca de cliente de AEM, vea [Usar bibliotecas del lado del cliente](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html?lang=en).

## Controlar la representación de imágenes durante la generación de salida {#id177BF0G0VY4}

AEM incluye un conjunto de flujos de trabajo predeterminados y controladores de medios para procesar recursos. En AEM, hay flujos de trabajo predefinidos para gestionar el procesamiento de recursos para los tipos MIME más comunes. Normalmente, para cada imagen que carga, AEM crea varias representaciones de la misma en formato binario. Estas representaciones pueden tener un tamaño diferente, con una resolución diferente, con una marca de agua agregada o cualquier otra característica modificada. Para obtener más información sobre cómo administra AEM los recursos, consulte [Procesamiento de Assets mediante controladores de medios y flujos de trabajo](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html?lang=en) en la documentación de AEM.

AEM Guides le permite configurar qué representación de imágenes utilizar en el momento de generar la salida de sus documentos. Por ejemplo, puede elegir una de las representaciones de imágenes predeterminadas o crear una y utilizar la misma para publicar los documentos. La asignación de representación de imágenes para publicar los documentos se almacena en el archivo `/libs/fmdita/config/ **renditionmap.xml**`. Un fragmento del archivo `renditionmap.xml` es el siguiente:

>[!NOTE]
>
> Se recomienda crear una copia del archivo `renditionmap.xml` en la carpeta `apps` para todas las personalizaciones.

```XML
<renditionmap>
   <mapelement>
      <mimetype>image/png</mimetype>
      <rendition output="AEMSITE">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="PDF">original</rendition>
      <rendition output="HTML5">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="HTML5" outputName="ditahtml5">cq5dam.thumbnail.319.319.png</rendition>
      <rendition output="EPUB">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="CUSTOM">cq5dam.web.1280.1280.jpeg</rendition>
   </mapelement>
...
</renditionmap>
```

El elemento `mimetype` especifica el tipo MIME del formato de archivo. El elemento `rendition output` especifica el tipo de formato de salida y el nombre de la representación \(por ejemplo, `cq5dam.web.1280.1280.jpeg`\) que se debe utilizar para publicar el resultado especificado. Puede especificar las representaciones de imágenes que se utilizarán para todos los formatos de salida admitidos: AEM SITE, PDF, HTML5, EPUB y PERSONALIZADO.

Si desea especificar distintas representaciones de imagen para un ajuste preestablecido de salida, puede utilizar el atributo `outputName`, con su valor establecido en el título del ajuste preestablecido, para definir representaciones personalizadas para ajustes preestablecidos de salida específicos bajo el mismo tipo de salida. Esto resulta útil cuando necesita diferentes tamaños o formatos de imagen para diferentes escenarios de publicación.

Por ejemplo:


```XML
<renditionmap>
   <mapelement>
      <mimetype>image/png</mimetype>
      
      <rendition output="HTML5">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="HTML5" outputName="ditahtml5">cq5dam.thumbnail.319.319.png</rendition>
      
   </mapelement>
...
</renditionmap>
```

En las representaciones anteriores, cuando el atributo `outputName` está establecido en `ditahtml5` (título preestablecido), el ajuste preestablecido `ditahtml5` utiliza la imagen en miniatura `cq5dam.thumbnail.319.319.png`. Si no se especifica el atributo `outputName`, todas las salidas de HTML5 utilizarán la imagen más grande `cq5dam.web.1280.1280.jpeg`.

Si la representación especificada no está presente, el proceso de publicación de AEM Guides busca primero la representación web de la imagen dada. Si no se encuentra ni siquiera la representación web, se utiliza la representación original de la imagen.

>[!NOTE]
>
> Estas representaciones de imágenes controlan únicamente la generación de salida. La representación web de una imagen se utiliza al abrir un documento para previsualizarlo o revisarlo.

## Configurar el período de depuración automática para el historial de salida {#id19AAI070V8Q}

Cuando se genera una salida, esta se crea junto con los registros de salida. Para mapas DITA grandes, estos registros pueden ocupar una gran cantidad de espacio en el repositorio. De forma predeterminada, los registros se almacenan en la siguiente ubicación del repositorio:

`/var/dxml/metadata/outputHistory`

Durante un período de tiempo, el tamaño colectivo de todos los archivos de registro podría alcanzar los GB. AEM Guides le permite configurar un periodo de tiempo para mantener estos archivos de registro en el repositorio. Después del período de tiempo especificado, los registros junto con el historial de generación de salida se eliminan del repositorio.

>[!NOTE]
>
> El historial de generación de resultados es la entrada de registro de la lista Salidas generadas de la pestaña Salidas.

La configuración de la función de depuración del historial afecta a la generación de resultados para todas las asignaciones DITA del repositorio. En la ficha Salidas de un mapa DITA, el historial se depura después del número de días especificado y a la hora especificada en la configuración.

>[!NOTE]
>
> La eliminación de los archivos de registro y del historial de generación de resultados no afecta a la salida generada.

Las siguientes pestañas proporcionan instrucciones para establecer un día y una hora para purgar el historial y los registros de salida en función de la configuración de Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para establecer un día y una hora para purgar el historial y los registros de salida:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager\|output.history.purgeperiod` | Especifique el número de días después de los cuales se depura el historial de salida junto con los registros de salida. Si desea deshabilitar esta función, establezca esta propiedad en 0.Everyday a la hora especificada en que se ejecute el proceso de depuración en las salidas generadas antes del número de días especificado en esta propiedad. | **Valor predeterminado**: 5 |
| `output.history.purgetime` | Especifique la hora en la que se inicia el proceso de depuración. | **Valor predeterminado**: 0:00 \(o 12:00 medianoche\) |

>[!TAB Local]

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.config.ConfigManager**.

1. En la propiedad **Periodo de purga del historial de salida**, especifique el número de días después de los cuales se purgará el historial de salida junto con los registros de salida. De forma predeterminada, se establece en 5 días. Si desea deshabilitar esta función, establezca esta propiedad en 0.

1. En la propiedad **Hora de purga del historial de salida**, especifique la hora a la que se inicia el proceso de purga. De forma predeterminada, se establece en 0:00 \(o 12:00 medianoche\). Todos los días en este momento, el proceso de depuración se ejecuta en las salidas generadas antes del número de días especificado en la propiedad **Periodo de purga del historial de salida**.

   >[!NOTE]
   >
   > De forma predeterminada, la función de depuración se ejecuta cada medianoche en salidas de más de 5 días.

1. Haga clic en **Guardar**.

>[!ENDTABS]

## Cambiar el límite de lista de resultados generados recientemente {#id1679JH0H0O2}

Se puede cambiar el número máximo de salidas generadas que se muestran en la ficha Salidas para un mapa DITA.

>[!BEGINTABS]

>[!TAB Cloud Service]

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para cambiar el número de salidas que se mostrarán en la lista:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `output.historylimit` | Valor entero.<br> **Valor predeterminado**: 25 |

>[!TAB Local]

De forma predeterminada, se muestra una lista de las últimas 25 salidas generadas. Para cambiar el número de salidas que se mostrarán en la lista, actualice la configuración **Límite de lista de salidas** en el paquete `com.adobe.fmdita.config.ConfigManager`.

>[!ENDTABS]

>[!TIP]
>
> Consulte la sección *Historial de resultados* en la [Guía de prácticas recomendadas](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-mar-22/Adobe-Experience-Manager-Guides_Best-Practices_EN.pdf) para conocer las prácticas recomendadas sobre cómo trabajar con el historial de resultados.

## Optimización del rendimiento de generación de resultados (solo para local) {#id176LB050VUI}

AEM Guides permite configurar el tamaño del grupo de procesos de generación de salida que controla el número de procesos de generación de salida que se ejecutan simultáneamente. De forma predeterminada, el tamaño del grupo de procesos está establecido en el número de núcleos de procesamiento disponibles en el sistema más uno. Puede que desee cambiar este valor a 1 si desea una publicación secuencial. En este caso, se ejecuta la primera tarea de publicación y la siguiente tarea de publicación se almacena en la cola de publicación.

Para cambiar el tamaño del grupo de procesamiento de generación de salida, actualice el valor **Tamaño del grupo de generación** en el paquete `com.adobe.fmdita.publish.manager.PublishThreadManagerImpl`.

## Configuración de FrameMaker Publishing Server (solo para local) {#id1678G0Z0TN6}

Puede utilizar FrameMaker Publishing Server \(FMPS\) para generar resultados para el contenido DITA. La configuración de FMPS le permite generar salidas en varios formatos compatibles con FMPS.

>[!NOTE]
>
> Para generar resultados mediante FMPS, debe tener configurado el servidor FMPS. Para obtener detalles de instalación y configuración, consulte la Guía del usuario de FrameMaker Publishing Server.

Para configurar AEM Guides para que utilice FMPS, actualice las siguientes propiedades del paquete `com.adobe.fmdita.config.ConfigManager` en la consola web.

>[!NOTE]
>
> Acceda a la URL http://&lt;server name\>:&lt;port\>/system/console/configMgr para abrir la consola web.

| Propiedad | Descripción |
|--------|-----------|
| Dominio de inicio de sesión de FrameMaker Publishing Server | Especifique el nombre de dominio o el nombre del grupo de trabajo en el que está alojado FrameMaker Publishing Server. Según la versión de FMPS, proporcione el nombre de dominio como :-   **FMPS 2020**: la dirección IP 192.168.1.101 <br>- **FMPS 2019 y anteriores**: la dirección IP o el nombre de dominio |
| URL de FrameMaker Publishing Server | Especifique la URL de FrameMaker Publishing Server. Según la versión de FMPS, proporcione la URL de FMPS como:<br>- **FMPS 2020**: `http://<fmps_ip>:<port>` \(http://192.168.1.101:7000\) <br> - **FMPS 2019 y anteriores**: `http://<fmps_ip>:<port>/fmserver/v1/` |
| Versión de FMPS | Especifique el número de versión de FrameMaker Publishing Server. Según la versión de FMPS, proporcione la información de la versión como: <br>- **FMPS 2020**: 2020 <br> - **FMPS 2019 y anteriores**: 2019 o 2017 |
| Usuario y contraseña de FrameMaker Publishing Server | Especifique el nombre de usuario y la contraseña para acceder a FrameMaker Publishing Server. |
| Tiempo de espera de FMPS | \(*Opcional*\) Especifique el tiempo \(en segundos\) durante el cual AEM Guides espera una respuesta de FrameMaker Publishing Server. Si no se recibe ninguna respuesta en el tiempo especificado, AEM Guides finaliza la tarea de publicación y la tarea se marca como fallida. <br> Valor predeterminado: 300 segundos \(5 minutos\) |
| URL de AEM externo | *\(Opcional\)* La URL de AEM donde FrameMaker Publishing Server colocará los archivos de salida generados. Por ejemplo, `http://<server-name>:<port>/`. |
| Usuario y contraseña de administrador de AEM | *\(Opcional\)* El nombre de usuario y la contraseña de un administrador de la configuración de AEM. FrameMaker Publishing Server lo utilizará para comunicarse con AEM. |
| Tiempo de espera de ejecución de tarea FMPS | Esta configuración solo es aplicable a FMPS 2020. Especifique el tiempo \(en segundos\) después del cual FMPS dejará de esperar a que se ejecute este proceso. |


