---
title: Configuración de la generación de salida
description: Obtenga información sobre cómo configurar los ajustes de generación de resultados
exl-id: 6df31e3c-683c-4188-b917-9c1855d9b95b
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '5762'
ht-degree: 0%

---

# Configuración de la generación de salida {#id181AI0B0E30}

AEM Guías de la viene con un montón de opciones de configuración para que usted personalice el proceso de generación de salida. Este tema cubre todas las configuraciones y personalizaciones que le ayudarán a configurar su proceso de generación de resultados.

## Configure la ficha Línea base en el tablero de mandos de asignación DITA {#id223MD0D0YRM}

Puede configurar y ocultar la pestaña Línea base disponible en el panel de mapas.

El **Ocultar ficha Línea base** La opción no está activada de forma predeterminada y debe activarla desde configMgr. Realice los siguientes pasos para habilitar la opción de forma predeterminada en el Editor web:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en **com.adobe.fmdita.config.ConfigManager** paquete.

1. Seleccione el **Ocultar ficha Línea base** opción.

1. Haga clic en **Guardar**.

   >[!NOTE]
   >
   > Esta configuración está desactivada de forma predeterminada y la pestaña Línea base está disponible en el panel de asignaciones.


## Configuración del FrameMaker Publishing Server {#id1678G0Z0TN6}

Puede utilizar el FrameMaker Publishing Server \(FMPS\) para generar resultados para el contenido DITA. La configuración de FMPS le permite generar salidas en varios formatos compatibles con FMPS.

>[!NOTE]
>
> Para generar resultados mediante FMPS, debe tener configurado el servidor FMPS. Para obtener detalles de instalación y configuración, consulte la Guía del usuario de FrameMaker Publishing Server.

AEM Para configurar las guías de la para que utilicen FMPS, actualice las siguientes propiedades del `com.adobe.fmdita.config.ConfigManager` paquete en la consola web.

>[!NOTE]
>
> Acceda a http://&lt;server name=&quot;&quot;>:&lt;port>/system/console/configMgr URL para abrir la consola web.

| Propiedad | Descripción |
|--------|-----------|
| Dominio de inicio de sesión de FrameMaker Publishing Server | Especifique el nombre de dominio o el nombre del grupo de trabajo en el que está alojado el FrameMaker Publishing Server. En función de la versión de FMPS, proporcione el nombre de dominio como:   **FMPS 2020**: Dirección IP 192.168.1.101 <br>- **FMPS 2019 y anteriores**: dirección IP o nombre de dominio |
| URL de FrameMaker Publishing Server | Especifique la dirección URL del FrameMaker Publishing Server. En función de la versión de FMPS, proporcione la URL de FMPS como:<br>- **FMPS 2020**: `http://<fmps_ip>:<port>` \(http://192.168.1.101:7000\) <br> - **FMPS 2019 y anteriores**: `http://<fmps_ip>:<port>/fmserver/v1/` |
| Versión de FMPS | Especifique el número de versión del FrameMaker Publishing Server. En función de la versión de FMPS, proporcione la información de la versión como: <br>- **FMPS 2020**: 2020 <br> - **FMPS 2019 y anteriores**: 2019 o 2017 |
| Nombre de usuario y contraseña de FrameMaker Publishing Server | Especifique el nombre de usuario y la contraseña para acceder al FrameMaker Publishing Server. |
| Tiempo de espera de FMPS | \(*Opcional* AEM \) Especifique el tiempo \(en segundos\) durante el que Guías de la aplicación espera una respuesta del FrameMaker Publishing Server. AEM Si no se recibe ninguna respuesta en el tiempo especificado, Guías de publicación finaliza la tarea de publicación y la tarea se marca como fallida. <br> Valor predeterminado: 300 segundos \(5 minutos\) |
| AEM Dirección URL externa | *\(Opcional\)* AEM Dirección URL donde el FrameMaker Publishing Server colocará los archivos de salida generados. Por ejemplo, `http://<server-name>:<port>/`. |
| AEM Nombre de usuario y contraseña de administrador | *\(Opcional\)* AEM El nombre de usuario y la contraseña de un administrador de la configuración de su. El FrameMaker Publishing Server AEM utilizará esto para comunicarse con los usuarios de la red de área de trabajo de la red de área de trabajo. |
| Tiempo de espera de ejecución de tarea FMPS | Esta configuración solo es aplicable a FMPS 2020. Especifique el tiempo \(en segundos\) después del cual FMPS dejará de esperar a que se ejecute este proceso. |

## AEM Configuración de la publicación combinada en un sitio de existente {#id1691I0V0MGR}

AEM AEM Si dispone de un sitio de que contiene contenido DITA, puede configurar la salida del sitio de la aplicación para que publique contenido DITA en una ubicación predefinida dentro del sitio. AEM Por ejemplo, en la siguiente captura de pantalla de una página del sitio de la, la variable `ditacontent` El nodo está reservado para almacenar contenido DITA:

![](assets/publish-in-aem-site.png){width="300" align="left"}

AEM Los nodos restantes de la página se crean directamente desde el editor del sitio de la. AEM La configuración de publicación para publicar contenido DITA en una ubicación predefinida garantiza que el proceso de publicación de guías de usuario no modifique ningún contenido que no sea DITA.

Es necesario realizar las siguientes configuraciones en el sitio existente para permitir la publicación de contenido DITA en un nodo predefinido:

- Configurar las propiedades de la plantilla del sitio

- Añadir nodos en el sitio para publicar contenido DITA


Realice los siguientes pasos para configurar las propiedades de plantilla del sitio existente:

1. AEM Inicie sesión en la aplicación y abra el modo CRXDE Lite.

1. Vaya al nodo de configuración de la plantilla del sitio. AEM Por ejemplo, Guías de almacena las configuraciones de plantilla predeterminadas en el siguiente nodo:

   `/libs/fmdita/config/templates/default`

   >[!NOTE]
   >
   > No realice ninguna personalización en los archivos de configuración predeterminados disponibles en el `libs` nodo. Debe crear una superposición de `libs` nodo en el `apps` y actualice los archivos necesarios en la `apps` solo nodo.

1. Añada las siguientes propiedades:

   | Nombre de la propiedad | Tipo | Valor  |
   |-------------|----|-----|
   | `topicContentNode` | Cadena | Especifique el nombre del nodo donde desea publicar el contenido DITA. AEM Por ejemplo, el nodo predeterminado en el que Guías de la aplicación publica contenido DITA es el siguiente: <br>`jcr:content/contentnode` |
   | `topicHeadNode` | Cadena | Especifique el nombre del nodo donde desea almacenar la información de metadatos del contenido DITA. AEM Por ejemplo, el nodo predeterminado en el que Guías de recursos almacena información de metadatos es: <br>`jcr:content/headnode` |


AEM La siguiente captura de pantalla muestra las propiedades agregadas en el nodo de plantilla predeterminado de las guías de:

![](assets/add-content-node.png){width="800" align="left"}

La próxima vez que publique contenido DITA con las configuraciones de plantilla del sitio, el contenido se publicará en los nodos especificados en la `topicContentNode` y `topicHeadNode` propiedades.

Sin embargo, para los sitios existentes, debe agregar manualmente la variable `topicContentNode` y `topicHeadNode` nodos.

Realice los siguientes pasos para agregar los nodos necesarios al sitio existente:

1. AEM Inicie sesión en la aplicación y abra el modo CRXDE Lite.

1. Localizar `jcr:content` dentro del nodo del sitio.

1. Añadir `topicContentNode` y `topicHeadNode` nodos con el mismo nombre especificado en las configuraciones de plantilla del sitio.


## AEM Personalizar salida del sitio {#id166TG0B30WR}

AEM Las guías de la aplicación admiten la creación de salidas en los siguientes formatos:

- AEM Sitio web de

- PDF

- HTML5
- EPUB
- Salida personalizada mediante DITA-OT

AEM Para la salida del sitio de la, puede asignar diferentes plantillas de diseño con diferentes tareas de salida. Estas plantillas de diseño pueden representar el contenido DITA en diferentes diseños. Por ejemplo, puede especificar distintas plantillas de diseño para audiencias internas y externas.

AEM También se pueden utilizar complementos personalizados DITA Open Toolkit \(DITA-OT\) con guías de la aplicación de la interfaz de usuario de DITAs (DITA Open Toolkit). Puede cargar estos complementos DITA-OT personalizados para generar salidas de PDF de una forma específica.

>[!TIP]
>
> Consulte la *AEM Publicación de sitios de* de la guía de prácticas recomendadas[apendice.md\#](appendix.md#) AEM para conocer las prácticas recomendadas sobre la creación de salida del sitio de.

### Personalizar la plantilla de diseño para generar resultados {#customize_xml-add-on}

AEM AEM Guías de diseño utiliza un conjunto de plantillas de diseño predefinidas para generar la salida del sitio de la. AEM Puede personalizar las plantillas de diseño de las guías de la compañía para generar el resultado que se ajuste a su marca corporativa. Una plantilla de diseño es una colección de varios estilos \(CSS\), secuencias de comandos \(del lado del servidor y del lado del cliente\), recursos \(imágenes, logotipos y otros recursos\) y nodos JCR que unen todos estos recursos. Una plantilla de diseño puede ser tan sencilla como un único script del lado del servidor con solo un par de nodos JCR o una combinación compleja de estilos, recursos y nodos JCR. AEM AEM Las plantillas de diseño son utilizadas por el subsistema de publicación Guías de diseño mientras se genera la salida del sitio de la página web y se controla la estructura, el aspecto y la presentación de la salida generada.

No hay restricciones en cuanto a la ubicación de los recursos de la plantilla de diseño en el servidor, pero suelen estar organizados lógicamente según su función. Por ejemplo, la plantilla predeterminada tiene todos sus archivos JavaScript y CSS almacenados en `/etc/designs/fmdita/clientlibs/siteoutput/default` carpeta. Dondequiera que se encuentren estos archivos, se vinculan entre sí mediante una colección de nodos JCR. Juntos, estos nodos JCR y los archivos constituyen la plantilla de diseño completa.

AEM La plantilla de diseño predeterminada enviada con las guías del usuario le permite personalizar los componentes de página de aterrizaje, tema y búsqueda. Se puede realizar una copia del diseño por defecto y de las plantillas de referencia correspondientes, así como especificar diferentes componentes para generar la salida deseada.

AEM Realice los siguientes pasos para especificar su propia plantilla de diseño para utilizarla en la generación de resultados del sitio de la red de distribución de contenido ():

1. AEM Inicie sesión en la aplicación y abra el modo CRXDE Lite.

1. Vaya al nodo de plantilla de diseño predeterminado. La ubicación del nodo de plantilla de diseño predeterminado es:

   `/libs/fmdita/config/templates/`

   ![](assets/templates-node.png){width="300" align="left"}

   >[!NOTE]
   >
   > Realice una copia de las plantillas de diseño predeterminadas desde el `libs` a la carpeta `apps` y realice cambios en la carpeta `apps` carpeta. También debe realizar cambios en las plantillas a las que se hace referencia desde el nodo de plantilla predeterminado. Las plantillas a las que se hace referencia se colocan debajo de `/libs/fmdita/templates/default/cqtemplates` nodo. Realice una copia de las plantillas a las que se hace referencia en la `apps` antes de realizar cambios.

1. Haga clic en *predeterminado* componente en la *templates* para acceder a sus propiedades.

   AEM En la tabla siguiente se describen las propiedades de la plantilla de diseño de las guías.

   | Propiedad | Descripción |
   |--------|-----------|
   | `landingPageTemplate`, `searchPageTemplate`, `topicPageTemplate`, `shadowPageTemplate` | Especifique el `cq:Template` nodo para estas páginas correspondientes \(aterrizaje, búsqueda y tema\). De forma predeterminada, la variable `cq:Template` El nodo para estas páginas se encuentra en `/libs/fmdita/templates/default/cqtemplates` nodo. Este nodo define la estructura y las propiedades de las páginas de aterrizaje, búsqueda y tema. <br>El `shadowPageTemplate` se utiliza para optimizar el contenido fragmentado. Debe establecer el valor de esta propiedad en: <br> `fmdita/templates/default/cqtemplates/shadowpage` <br> **Nota** Debe especificar un valor para `topicPageTemplate`. El `landingPageTemplate` y `searchPageTemplate` son propiedades opcionales. Si no desea que se generen las páginas de búsqueda y de aterrizaje, no especifique estas propiedades. |
   | `title` | Un nombre descriptivo de la plantilla de diseño. |
   | `topicContentNode` | Ubicación del nodo que contendrá el contenido DITA en una página de tema. La ruta es relativa a la página del tema. |
   | `topicHeadNode` | Ubicación del nodo que contendrá los valores \(o metadatos\) del encabezado derivados del contenido DITA. La ruta es relativa a la página del tema. |
   | `tocNode` | Ubicación del nodo que contendrá la TDC. La ruta es relativa a la página de aterrizaje o a la ruta de destino. |
   | `basePathProp` | Nombre de propiedad para almacenar la ruta de acceso de la raíz del sitio publicado. |
   | `indexPathProp` | Nombre de propiedad para almacenar la ruta de la página de aterrizaje/índice del sitio publicado. |
   | `pdfPathProp` | Nombre de propiedad para almacenar la ruta del PDF del tema, si la generación del PDF del tema está habilitada. |
   | `pdfTypeProp` | Nombre de propiedad para almacenar el tipo de generación de PDF. Actualmente, esta propiedad siempre contiene &quot;Tema&quot;. |
   | `searchPathProp` | Nombre de propiedad para almacenar la ruta de la página de búsqueda, si la plantilla incluye una página de búsqueda. |
   | `siteTitleProp` | Nombre de propiedad para almacenar el título del sitio que se está publicando. Este título suele ser el mismo que el título del mapa que se está publicando. |
   | `sourcePathProp` | Nombre de propiedad para almacenar la ruta del tema DITA de origen de la página actual. |
   | `tocPathProp` | Nombre de propiedad para almacenar la ruta de la raíz del índice del sitio publicado. |


>[!NOTE]
>
> AEM Después de crear un nodo de plantilla de diseño personalizado, debe actualizar la opción Diseño en los ajustes preestablecidos de salida del sitio de la para utilizar el nodo de plantilla de diseño personalizado.

Para obtener más información, consulte [Creación del primer sitio web de Adobe Experience Manager 6.3](https://helpx.adobe.com/experience-manager/using/first_aem63_website.html) y [Conceptos básicos](https://helpx.adobe.com/experience-manager/6-3/sites/developing/using/the-basics.html) AEM de desarrollar su propio sitio web en el que se puede acceder a la.

### AEM Utilizar el título del documento para generar la salida del sitio de

AEM Al generar la salida del sitio de, la forma en que se generan las direcciones URL desempeña un papel importante en la capacidad de detección del contenido. Si utiliza nombres de archivo basados en UUID, la generación de direcciones URL basadas en el UUID de sus archivos no sería fácil de buscar. AEM Como administrador o editor, tiene el control sobre cómo desea generar las direcciones URL para la salida del sitio de la. AEM AEM Guías le proporciona una configuración a través de la cual puede optar por generar las direcciones URL de salida del sitio mediante el título del archivo en lugar de utilizar nombres de archivo basados en UUID. De forma predeterminada, para sistemas de archivos basados en UUID, esta opción está activada. AEM Esto implica que, cuando se genera la salida del sitio de la aplicación para sistemas de archivos basados en UUID, los títulos del archivo se utilizan para generar las direcciones URL y no los UUID de los archivos.

AEM Al generar la salida del sitio de, la forma en que se generan las direcciones URL desempeña un papel importante en la capacidad de detección del contenido. AEM En el caso de los sistemas de archivos no basados en UUID, la salida del sitio de la se genera utilizando los nombres de archivo y no los títulos del archivo. AEM Como administrador o editor, tiene el control sobre cómo desea generar las direcciones URL para la salida del sitio de la. AEM AEM Guías le proporciona una configuración a través de la cual puede optar por generar las direcciones URL de salida del sitio mediante el título del archivo en lugar de utilizar los nombres de archivo de, según el caso, el nombre de la dirección URL. Esta opción está desactivada de forma predeterminada. AEM Esto implica que, cuando se genera la salida del sitio de la página, los nombres de archivo se utilizan para generar las direcciones URL y no para generar el título del archivo. Puede optar por generar las direcciones URL basadas en los títulos del archivo activando esta opción.

>[!NOTE]
>
> AEM Además, puede configurar reglas para permitir solo un conjunto de caracteres en las direcciones URL de la salida de un sitio de. Para obtener más información, consulte [AEM Configure las reglas de saneamiento de nombres de archivo para crear temas y publicar resultados del sitio de la](#id2164D0KD0XA).

AEM Para configurar la generación de direcciones URL en la salida de sitio de la aplicación, realice los siguientes pasos:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en **com.adobe.fmdita.config.ConfigManager** paquete.

1. Seleccione el **AEM Utilizar título para nombres de páginas de sitios de** opción.

   >[!NOTE]
   >
   > Si desea generar una salida con los nombres de archivo, anule la selección de esta opción.

1. Haga clic en **Guardar**.


### AEM Configure las reglas de saneamiento de nombres de archivo para crear temas y publicar resultados del sitio de la {#id2164D0KD0XA}

AEM Como administrador, puede definir una lista de caracteres especiales válidos permitidos en los nombres de archivo, que finalmente forman la dirección URL de la salida de un sitio de. En versiones anteriores, los usuarios podían definir nombres de archivo que contenían caracteres especiales como `@`, `$`, `>`, y más. AEM Estos caracteres especiales daban como resultado una dirección URL codificada en la generación de páginas del sitio de la.

A partir de la versión 3.8, se han añadido configuraciones para definir una lista de caracteres especiales permitidos en los nombres de archivo. De forma predeterminada, la configuración de nombre de archivo válida contiene &quot;`a-z A-Z 0-9 - _`&quot;. Esto implica que, al crear un archivo, puede tener cualquier carácter especial en el título del archivo, pero internamente se reemplazará con un guion \(`-`\) en el nombre de archivo. Por ejemplo, puede tener el título del archivo como Introducción 1 o Introduction@1, el nombre de archivo correspondiente generado para ambos casos sería Introducción-1.

Cuando defina una lista de caracteres válidos, recuerde que estos caracteres &quot;`*/:[\]|#%{}?&<>"/+`&quot; y `a space` se reemplazará siempre con un guión \(`-`\).

>[!NOTE]
>
> Si no configura la lista de caracteres especiales válidos, el proceso de creación de archivos podría dar algunos resultados inesperados.

AEM Para configurar los caracteres especiales válidos en los nombres de archivo y en la salida del sitio de la, realice los siguientes pasos:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en *com.adobe.fmdita.common.SanitizeNodeNameImpl* paquete.

1. En el **Conjunto de caracteres no permitido para la publicación en AEM Sites** , asegúrese de que la propiedad está configurada en ```'<>`@$```. Puede agregar más caracteres especiales a esta lista, pero debe tener estos caracteres especiales necesarios.

   >[!NOTE]
   >
   > También puede configurar las demás propiedades, como **Usar minúsculas** en nombres de archivo, **Separador** para gestionar caracteres no válidos, y **Número máximo de caracteres** permitido en los nombres de archivo.

1. Haga clic en **Guardar**.

1. Busque y haga clic en **com.adobe.fmdita.config.ConfigManager** paquete.

1. En el **Regex para caracteres válidos** , asegúrese de que la propiedad está configurada en `[-a-zA-Z0-9_]`. Puede agregar más caracteres a esta lista, pero debe tener estos caracteres básicos y la lista debe comenzar con un guión \(`-`\).

   >[!NOTE]
   >
   > Esta propiedad define la lista de caracteres válidos utilizados para crear un nuevo archivo.

1. Haga clic en **Guardar**.


### AEM Configuración del acoplamiento de la estructura de nodos del sitio de la

AEM Cuando se genera la salida del sitio de, se crea internamente un nodo para cada elemento de los temas. Para un mapa DITA con miles de temas, esta estructura de nodos puede llegar a ser demasiado profunda. Este tipo de estructura de nodos profundamente anidados puede tener problemas de rendimiento para sitios más grandes. AEM La siguiente instantánea muestra la estructura de nodos profundamente anidados para una salida de sitio de la:

![](assets/deep-nested-aem-site-node-structure.png){width="300" align="left"}

En la instantánea anterior, observe que hay un nodo creado para cada `p` y sus subelementos subsiguientes, y se crea una estructura similar para todos los demás elementos utilizados en el tema.

AEM AEM Guías de le permite configurar cómo se crea internamente la estructura de nodos de la salida del sitio de la aplicación. Puede aplanar la estructura del nodo en elementos especificados, lo que significa que puede definir un elemento que se considerará como el elemento principal y todos los subelementos dentro de él se combinarán con el elemento principal. Por ejemplo, si decide acoplar la variable `p` , entonces cualquier elemento que aparezca dentro de `p` se combinará con el elemento principal `p` Elemento. No se crearía una nota independiente para ningún subelemento dentro de `p` Elemento. La siguiente instantánea muestra la estructura de nodos aplanada en `p` elemento:

![](assets/flattened-aem-site-node-structure.png){width="300" align="left"}

AEM Para acoplar la estructura de nodos del sitio de la, realice los siguientes pasos:

1. Especifique el elemento en el que desea acoplar la estructura del nodo.

   1. Superposición de la `libs` nodo en el `apps` y abra el archivo elementmapping.xml.

   1. Añada el `<flatten>true</flatten>` en la definición del elemento en el que desea acoplar la estructura del nodo. Por ejemplo, si desea acoplar la estructura del nodo en la `p` , luego añada el atributo flatten en la definición de `p` como se muestra a continuación:

      ```XML
      <ditaelement>
          <name>p</name>
          <class>- topic/p</class>
          <componentpath>fmdita/components/dita/wrapper</componentpath>
          <type>COMPOSITE</type>
          <target>para</target>
          <flatten>true</flatten>
          <wrapelement>div</wrapelement>
      </ditaelement>
      ```

      >[!NOTE]
      >
      > De forma predeterminada, la propiedad acoplar nodo se ha configurado en `p` Elemento.

1. Habilite la configuración de acoplamiento del nodo de sitio en configMgr.

   1. Abra la página Configuración de la consola web de Adobe Experience Manager.

      La URL predeterminada para acceder a la página de configuración es:

      ```http
      http://<server name>:<port>/system/console/configMgr
      ```

   1. Busque y haga clic en *com.adobe.dxml.flattening.FlateningConfigurationService* paquete.

   1. Seleccione el **Propiedad flattening.enabled** opción.

   1. Haga clic en **Guardar**.


>[!IMPORTANT]
>
> Si ha realizado algún cambio en el archivo elementmapping.xml, asegúrese de abrir configMgr y guardar cualquier paquete para que los cambios entren en vigor.

AEM Ahora, cuando genere la salida del sitio de la, los nodos dentro de la variable `p` se aplanan y almacenan dentro de la variable `p` elemento en sí. Se pueden encontrar las nuevas propiedades de acoplamiento para la variable `p` en CRXDE.

![](assets/flatten-aem-site-note-props-crxde.png){width="650" align="left"}

**AEM Evitar el acoplamiento de la estructura de notas del sitio de la**

AEM De forma similar a especificar el nodo que se va a acoplar en la salida del sitio de la aplicación, también se puede especificar un elemento que desee excluir de esta configuración. Por ejemplo, si desea acoplar nodos en `body` , pero no desea ningún elemento `table` elemento dentro de `body` para acoplar, puede añadir la propiedad exclude dentro de la variable `table` definición del elemento.

Para excluir el `table` del acoplamiento, agregue la siguiente propiedad al `table` definición del elemento:

`<preventancestorflattening>true|false</preventancestorflattening>`

### AEM Configurar el control de versiones de las páginas eliminadas en la salida del sitio de

AEM Cuando se genera la salida del sitio de con **Eliminar y** Crear ****opción seleccionada para la configuración Páginas de salida existentes, se crea una versión para la página\(s\) que se está eliminando. Puede configurar el sistema para que detenga la creación de una versión antes de la eliminación.

Realice los siguientes pasos para detener la creación de una versión para la página que se está eliminando:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en *com.adobe.fmdita.config.ConfigManager* paquete.

1. Seleccionar **No crear versión para páginas eliminadas** opción.

   >[!NOTE]
   >
   > Con esta opción seleccionada, los usuarios podrán eliminar directamente cualquier página sin crear ninguna versión para ellos. Si la opción no está seleccionada, se crea una versión antes de que se eliminen las páginas.

1. Haga clic en **Guardar**.

## Usar metadatos en la salida de publicación mediante DITA-OT {#id191LF0U0TY4}

AEM Las guías de la aplicación proporcionan una forma de pasar metadatos personalizados mientras se publica la salida mediante DITA-OT. Como administrador y publicador, deberá realizar las siguientes tareas para configurar y utilizar metadatos personalizados en el resultado publicado:

- Como administrador, añada los metadatos requeridos en el sistema para que estén disponibles en la página Propiedades del mapa DITA.

- Como administrador, añada los metadatos personalizados a la lista de metadatos para que aparezcan en la consola de mapas DITA.

- Como editor, configure y añada los metadatos personalizados con el mapa DITA y genere la salida requerida.


Para añadir los metadatos necesarios en el sistema, realice los siguientes pasos:

1. Inicie sesión en Adobe Experience Manager como administrador.

1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.

1. Seleccionar **Assets** de la lista de herramientas.

1. Haga clic en **Esquemas de metadatos** mosaico.

   Se muestra la página Forms del esquema de metadatos.

1. Seleccione el **predeterminado** de la lista.

   >[!NOTE]
   >
   > Las propiedades mostradas en la página Propiedades de un mapa DITA se toman de este formulario.

1. Clic **Editar**.

1. Añada los metadatos personalizados que desee utilizar en las salidas publicadas. Por ejemplo, agregaremos metadatos de audiencia siguiendo los pasos siguientes:

   1. Desde el **Generar formulario** lista de componentes, arrastrar y soltar **Texto de línea única** en el formulario.

   1. Seleccione el nuevo campo para abrir **Configuración** del campo.

   1. En el **Etiqueta de campo**, introduzca el nombre del metadato— Audiencia.

   1. En el **Asignar a la propiedad** , especifique ./jcr:content/metadata/&lt;name of=&quot;&quot; the=&quot;&quot; metadata=&quot;&quot;>. Para nuestro ejemplo, lo estableceremos en ./jcr:content/metadata/audience.

   Siga estos pasos para agregar todos los parámetros de metadatos necesarios.

1. Haga clic en **Guardar**.


El nuevo parámetro aparece ahora en la página Propiedades para todos los mapas DITA.

![](assets/properties-page-custom-metadata.PNG){width="650" align="left"}

A continuación, es necesario que los metadatos personalizados estén disponibles en la consola de mapas DITA. Realice los siguientes pasos para que los metadatos personalizados estén disponibles en el tablero de mandos de mapa DITA:

1. AEM Inicie sesión en la aplicación y abra el modo CRXDE Lite.

1. Acceda al archivo metadataList disponible en la siguiente ubicación:

   /libs/fmdita/config/metadataList

   >[!NOTE]
   >
   > El archivo metadataList contiene una lista de propiedades que se muestran en la **Propiedades** lista desplegable de un mapa DITA en el tablero de mandos de mapas. De forma predeterminada, hay cuatro propiedades enumeradas en este archivo: docstate, dc:language, dc:description y dc:title.

1. Añada los metadatos personalizados que ha añadido en la página de Forms del esquema de metadatos. Para nuestro ejemplo, añada el parámetro de audiencia al final de la lista predeterminada.

1. Haga clic en **Guardar todo**.


Ahora los metadatos personalizados se mostrarán en la consola de mapas DITA **Propiedades** lista desplegable.

Por último, como editor, debe incluir los metadatos personalizados en el resultado publicado. Para procesar los metadatos personalizados mientras se genera la salida, realice los siguientes pasos:

1. En la interfaz de usuario de Assets, vaya al mapa DITA que desee publicar.

1. Seleccione el fichero de mapa DITA y abra su página de propiedades.

1. En la página Propiedades, especifique el valor de los metadatos personalizados. Para nuestro ejemplo, hemos especificado un valor de External para el parámetro audience.

   ![](assets/properties-page-custom-metadata-value.png){width="650" align="left"}

1. Haga clic en **Guardar y cerrar**.

1. Pulse en el fichero de mapa DITA para abrir la consola de mapas DITA.

1. En el **Valores de salida** , seleccione el ajuste preestablecido de salida que desee utilizar para generar la salida.

1. Clic **Editar**.

1. Desde el **Propiedades** , seleccione las propiedades que desee pasar al proceso de publicación.

   ![](assets/props-in-publish-output.PNG){width="650" align="left"}


Las propiedades/metadatos seleccionados se pasan al proceso de publicación y están disponibles en la salida final.

## AEM Personalización de la asignación de elementos DITA con componentes de {#id1679J600HEL}

AEM AEM Los elementos DITA de las Guías de se asignan a sus correspondientes componentes de. AEM AEM Guías de utiliza esta asignación en flujos de trabajo como publicación y revisión para convertir un elemento DITA en un componente de la aplicación correspondiente. La asignación se define en la variable `elementmapping.xml` , a la que se puede acceder desde el modo CRXDE Lite. Acceda a la siguiente URL en el modo CRXDE Lite:

`/libs/fmdita/config/elementmapping.xml`

>[!NOTE]
>
> No realice ninguna personalización en los archivos de configuración predeterminados disponibles en el ``libs`` nodo. Debe crear una superposición de ``libs`` nodo en el ``apps`` y actualice los archivos necesarios en la ``apps`` solo nodo.

AEM Se pueden utilizar las asignaciones de elementos DITA predefinidas o se pueden asignar elementos DITA a los componentes personalizados de la aplicación de la aplicación de la aplicación de la aplicación de la aplicación de la aplicación de la aplicación de la. AEM Para utilizar los componentes de la personalizada, debe comprender la estructura del `elementmapping.xml` archivo.

### estructura de elementmapping.xml

Una visión general de alto nivel del `elementmapping.xml` La estructura de se explica a continuación:

1. En cada elemento DITA se busca primero una asignación de componentes correspondiente basada en el nombre del elemento. Por ejemplo:

   ```XML
   <ditaelement>     
      <name>**substeps**</name>  
      <class>- topic/ol task/substeps</class>  
      <componentpath>dita/components/ditaolist</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>
   </ditaelement>
   ```

   En el ejemplo anterior, todas las `substeps` Los elementos DITA se representan con la variable `dita/components/ditaolist` componente.

1. Si un elemento DITA no encuentra una coincidencia basada en el nombre, entonces una coincidencia basada en el `class` ha finalizado. Por ejemplo:

   ```XML
   <ditaelement>  
      <name>topic</name>  
      <class>**- topic/topic**</class>  
      <componentpath>fmdita/components/dita/topic</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>  
      <attributemap> 
         <attribute from="id" to="id" />  
      </attributemap>
   </ditaelement>
   ```

   En el ejemplo anterior, si no hay ninguna asignación definida para la variable `task` , luego el elemento `task` está asignado al componente anterior porque `task` se hereda de `topic` componente.

1. Cuando un elemento tiene una asignación de componentes correspondiente, el procesamiento posterior de sus elementos secundarios viene determinado por `type`. Por ejemplo:

   ```XML
   <ditaelement>  
      <name>title</name>  
      <class>- topic/title</class>  
      <componentpath>foundation/components/title</componentpath>  
      <type>**STANDALONE**</type>  
      <target>para</target>  
      <textprop>jcr:title</textprop>
   </ditaelement>
   ```

   `type` toma los siguientes valores:

   - COMPUESTO: elemento a componente *la asignación continúa para elementos secundarios* y también.

   - INDEPENDIENTE: los elementos secundarios del elemento actual son *sin asignar más*.

   En el ejemplo anterior, si la variable `<title>` tiene cualquier elemento secundario, no se asignarán a ningún otro componente. El componente para `<title>` es responsable de procesar todos los elementos secundarios dentro de `<title>` Elemento.

1. Si hay varios componentes asignados a un único elemento DITA, se selecciona la mejor coincidencia para el elemento. Para seleccionar el componente que mejor se ajuste, se tiene en cuenta la especialización estructural y de dominio de los elementos DITA.

   Si hay elementos DITA con especialización de dominio y un componente está asignado para la especialización de dominio, se le asigna una prioridad alta a ese componente.

   Del mismo modo, si hay elementos DITA con especialización estructural y se asigna un componente para la especialización estructural, se le asigna una alta prioridad a dicho componente.

1. Puede utilizar `<attributemap>` en la asignación de elementos para asignar valores de atributo a las propiedades del nodo correspondiente.

1. `textprop` se puede utilizar para serializar el contenido de texto de un elemento DITA en una propiedad de nodo. Además, se puede utilizar varias veces en una etiqueta de elemento para serializar el contenido de texto en varias ubicaciones de la jerarquía publicada. También puede personalizar la ubicación y el nombre de la propiedad de destino. Por ejemplo:

   ```XML
   <ditaelement> 
       <name>title</name> 
       <class>- topic/title</class> 
       <componentpath>foundation/components/title</componentpath> 
       <type>STANDALONE</type> 
       <target>para</target> 
       <textprop>**jcr:title**</textprop>
   </ditaelement>
   ```

   La asignación de elementos anterior especifica que el contenido de texto de `<title>` se guardará como valor de una propiedad denominada `jcr:title` en el nodo de salida.

1. `xmlprop` se puede utilizar para serializar todo el XML de un elemento determinado en una propiedad de nodo. A continuación, el componente puede leer esta propiedad de nodo y realizar una representación personalizada. Por ejemplo:

   ```XML
   <ditaelement> 
       <name>svg-container</name> 
       <class>+ topic/foreign svg-d/svg-container</class> 
       <componentpath>fmdita/components/dita/svg</componentpath> 
       <type>STANDALONE</type> 
       <target>para</target> 
       <xmlprop>**data**</xmlprop>
   </ditaelement>
   ```

   La asignación de elementos anterior especifica que el marcado XML completo del elemento `<svg-container>` se guardará como valor de una propiedad denominada `data` en el nodo de salida.

1. Hay una asignación de atributo especial para controlar la resolución de la ruta en el proceso de generación de resultados. Por ejemplo:

   ```XML
   <attributemap> 
       <attribute from="href" to="fileReference" ispath="true" rel="source" /> 
       <attribute from="height" to="height" /> 
       <attribute from="width" to="width" />
   </attributemap>
   ```

   Para lo anterior `attributemap`, el `href` en el elemento DITA se asignará a una propiedad de nodo denominada `fileReference`. Ahora desde `ispath` se establece en `true`, el proceso de generación de resultados resuelve esta ruta y la establece en `fileReference` propiedad del nodo.

   El modo en que se produce esta resolución se determina en función del valor de la variable `rel` en la asignación de atributos.

   - If `rel=source`, entonces el valor de `href` se resuelve con respecto al fichero de origen DITA que se está procesando en ese momento. El valor de `href` se resuelve y se coloca en el valor de `fileReference` propiedad.

   - If `rel=target`, entonces el valor de `href` se resuelve con respecto a la ubicación de publicación raíz. El valor de `href` se resuelve y se coloca en el valor de `fileReference` propiedad.

   Si no desea que se produzca ningún procesamiento previo o resolución en los atributos de ruta, no necesita especificar la `ispath` atributo. El valor se copia tal cual y el componente puede realizar la resolución necesaria.


### Esquema de elemento DITA

A continuación se muestra un ejemplo del esquema de elementos DITA en `elementmapping.xml` archivo:

```XML
<ditaelement>         
    <name>element_name</name>     
    <class>element_class</class>     
    <componentpath>fmdita/components/dita/component_name</componentpath>     
    <type>COMPOSITE|STANDALONE</type>      
    <attributeprop>propname_a</attributeprop>       
    <textprop>propname_t</textprop>     
    <xmlprop>propname_x</xmlprop>      
    <xpath>xpath expression string</xpath>      
    <target>head|para</target>      
    <wrapelement>div</wrapelement>      
    <wrapclass>class_name</wrapclass>      
    <attributemap>           
    <attribute from="attrname" to="propname" ispath="true|false" rel="source|target" />     
    </attributemap>     
    <skip>true|false</skip> 
</ditaelement>
```

En la tabla siguiente se describen los elementos del esquema de elementos DITA:

| Elemento | Descripción |
|-------|-----------|
| `<ditaelement>` | Nodo de nivel superior para cada elemento de asignación. |
| `<class>` | Atributo de clase del elemento DITA de destino para el que se está escribiendo el componente. <br>Por ejemplo, el atributo de clase para el tema DITA es: <br>`topic/topic` |
| `<componentpath>` | AEM La ruta CRXDE del componente de asignado. |
| `<type>` | Valores posibles: <br>- **COMPUESTO**: Procesar también elementos secundarios <br>- **INDEPENDIENTE**: omite el procesamiento de elementos secundarios |
| `<attributeprop>` | AEM Se utiliza para asignar atributos y valores DITA serializados a nodos como propiedad de la propiedad de la propiedad de la propiedad de datos de. Por ejemplo, si tiene `<note type="Caution">` y el componente asignado para este elemento tiene `<attributeprop>attr_t</ attributeprop>`, el atributo y valor del nodo se serializa en `attr_t` AEM de la propiedad correspondiente del nodo de \( `attr_t->type="caution"`\). |
| `<textprop>propname_t</textprop>` | Guarde el `getTextContent()` salida a propiedad definida por `propname_t.` **Nota:**  Esta es una propiedad optimizada. |
| `<xmlprop>propname_x </xmlprop>` | Guardar XML serializado de este nodo en la propiedad definida por `propname_x.` **Nota:** Esta es una propiedad optimizada. |
| `<xpath>` | Si se proporciona un elemento XPath en la asignación de elementos, junto con el nombre del elemento y la clase, la condición XPath también debe cumplirse para que se utilice la asignación de componentes. |
| `<target>` | Coloque el elemento DITA en el repositorio CRX en la ubicación especificada. <br>Valores posibles:<br>- **dirigir**: bajo el nodo principal <br>- **texto**: en el nodo de párrafo |
| `<wrapelement>` | El elemento HTML dentro del que se envolverá el contenido. |
| `<wrapclass>` | El valor del elemento de la propiedad `wrapclass.` |
| `<attributemap>` | Nodo de contenedor que contiene uno o más `<attribute>` nodos. |
| `<attribute from="attrname" to="propname" ispath="true|false" rel="source|target" />` | AEM Asigna los atributos DITA a las propiedades de la:<br>- **`from`**: Nombre de atributo DITA<br>- **`to`** AEM : nombre de propiedad del componente <br>- **`ispath`**: Si el atributo es un valor de ruta \(por ejemplo: *imagen*\)<br>- **`rel`**: Si la ruta es el origen o el destino <br>**Nota:** If `attrname` empieza por `%`y, a continuación, asignar `attrname minus '%'` a prop &#39; `propname`&#39;. |

**Notas adicionales**

- Si planea anular la asignación de elementos predeterminada, se recomienda no realizar los cambios en el valor predeterminado `elementmapping.xml` archivo. Debe crear un nuevo archivo XML de asignación y colocar el archivo en otra ubicación, preferiblemente dentro de la carpeta de aplicaciones personalizadas que cree.

- En el `elementmapping.xml` , hay muchas entradas de asignación que hacen referencia al componente fmedia/components/dita/wrapper. Wrapper es un componente genérico que procesa construcciones DITA relativamente sencillas utilizando propiedades en su nodo de sitio para generar un HTML relevante. Utiliza el `wrapelement` para generar etiquetas envolventes y delega el procesamiento secundario en los componentes correspondientes. Esto resulta útil en casos en los que solo desea un componente contenedor. En lugar de crear un nuevo componente que procese una etiqueta contenedora específica como `div` o `p`, puede utilizar el componente Envolvente con el `wrapelement` y `wrapclass` para lograr el mismo efecto.

- No se recomienda guardar grandes cantidades de texto en las propiedades JCR de la cadena. El cálculo del tipo de propiedad optimizada en la generación de salida garantiza que el contenido de texto grande no se guarde como tipo de cadena. En su lugar, cuando es necesario guardar contenido que supera un determinado umbral, el tipo de la propiedad se cambia a binario. De forma predeterminada, este umbral está configurado a 512 bytes, pero se puede cambiar en el Administrador de configuración \(*com.adobe.fmdita.config.ConfigManager*\) cambiando el **Guardar como umbral binario** configuración.

- Si planea anular algunas \(y no todas\) de las asignaciones de elementos, no tiene que replicar todo el `elementmapping.xml` archivo. Debe crear un nuevo archivo de asignación XML y definir sólo los elementos que va a anular.

- Después de crear el archivo XML en la ubicación personalizada, actualice el `Override Element Mapping` configuración en la `com.adobe.fmdita.config.ConfigManager` paquete.


## Personalizar la consola de mapas DITA {#id188HC08M0CZ}

AEM Guías le ofrece la flexibilidad de ampliar las capacidades de la consola de mapas DITA. AEM Por ejemplo, si tiene un conjunto de informes que son diferentes de los que están disponibles en las guías de la aplicación, puede agregar dichos informes a la consola de mapas. AEM Para personalizar la consola de asignaciones, debe crear una biblioteca de cliente de la biblioteca \(o ClientLib\) que contenga el código para realizar la funcionalidad que necesita.

>[!NOTE]
>
> No se recomienda la modificación directa a los componentes de la página, ya que se sobrescribirá con las nuevas versiones del producto.

AEM Guías de proporciona la `apps.fmdita.dashboard-extn` categoría para personalizar la consola de mapas. Siempre que se carga la consola de mapas, la funcionalidad creada en la variable `apps.fmdita.dashboard-extn` la categoría se ejecuta y carga.

>[!NOTE]
>
> AEM Para obtener más información sobre la creación de la biblioteca de cliente de, consulte [Uso de bibliotecas del lado del cliente](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/clientlibs.html).

## Controlar la representación de imágenes durante la generación de salida {#id177BF0G0VY4}

AEM viene con un conjunto de flujos de trabajo predeterminados y controladores de medios para procesar recursos. AEM En la práctica, hay flujos de trabajo predefinidos para gestionar el procesamiento de recursos para los tipos MIME más comunes. AEM Normalmente, para cada imagen que carga, se crean varias representaciones de la misma en formato binario, lo que hace que la imagen se cree más de una vez. Estas representaciones pueden tener un tamaño diferente, con una resolución diferente, con una marca de agua agregada o cualquier otra característica modificada. AEM Para obtener más información sobre cómo gestiona los recursos los recursos, consulte [Procesamiento de recursos mediante controladores de medios y flujos de trabajo](https://helpx.adobe.com/experience-manager/6-5/assets/using/media-handlers.html) AEM en la documentación de.

AEM Guías de le permite configurar qué representación de imagen utilizar en el momento de generar la salida para los documentos. Por ejemplo, puede elegir una de las representaciones de imágenes predeterminadas o crear una y utilizar la misma para publicar los documentos. La asignación de representación de imágenes para publicar los documentos se almacena en `/libs/fmdita/config/ **renditionmap.xml**` archivo. Un fragmento de `renditionmap.xml` es el siguiente:

>[!NOTE]
>
> Se recomienda crear una copia del `renditionmap.xml` archivo en el `apps` para todas las personalizaciones.

```XML
<renditionmap>
   <mapelement>
      <mimetype>image/png</mimetype>
      <rendition output="AEMSITE">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="PDF">original</rendition>
      <rendition output="HTML5">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="EPUB">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="CUSTOM">cq5dam.web.1280.1280.jpeg</rendition>
   </mapelement>
...
</renditionmap>
```

El `mimetype` especifica el tipo MIME del formato de archivo. El `rendition output` especifica el tipo de formato de salida y el nombre de la representación \(por ejemplo, `cq5dam.web.1280.1280.jpeg`\) que deben utilizarse para publicar el resultado especificado. Puede especificar las representaciones de imágenes que se utilizarán para todos los formatos de salida admitidos: AEMSITE, PDF, HTML5, EPUB y PERSONALIZADO.

AEM Si la representación especificada no está presente, el proceso de publicación de Guías de la guía busca primero la representación web de la imagen dada. Si no se encuentra ni siquiera la representación web, se utiliza la representación original de la imagen.

>[!NOTE]
>
> Estas representaciones de imágenes controlan únicamente la generación de salida. La representación web de una imagen se utiliza al abrir un documento para previsualizarlo o revisarlo.

## Configurar el período de depuración automática para el historial de salida {#id19AAI070V8Q}

Cuando se genera una salida, esta se crea junto con los registros de salida. Para mapas DITA grandes, estos registros pueden ocupar una gran cantidad de espacio en el repositorio. De forma predeterminada, los registros se almacenan en la siguiente ubicación del repositorio:

/var/dxml/metadata/outputHistory/

Durante un período de tiempo, el tamaño colectivo de todos los archivos de registro podría alcanzar los GB. AEM Guías de le permite configurar un período de tiempo para mantener estos archivos de registro en el repositorio. Después del período de tiempo especificado, los registros junto con el historial de generación de salida se eliminan del repositorio.

>[!NOTE]
>
> El historial de generación de resultados es la entrada de registro de la lista Salidas generadas de la pestaña Salidas.

La configuración de la función de depuración del historial afecta a la generación de resultados para todas las asignaciones DITA del repositorio. En la ficha Salidas de un mapa DITA, el historial se depura después del número de días especificado y a la hora especificada en la configuración.

>[!NOTE]
>
> La eliminación de los archivos de registro y del historial de generación de resultados no afecta a la salida generada.

Realice los siguientes pasos para establecer un día y una hora para purgar el historial y los registros de salida:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en **com.adobe.fmdita.config.ConfigManager** paquete.

1. En el **Período de depuración del historial de salida** , especifique el número de días después de los cuales se depura el historial de salida junto con los registros de salida. De forma predeterminada, se establece en 5 días. Si desea deshabilitar esta función, establezca esta propiedad en 0.

1. En el **Tiempo de purga del historial de salida** , especifique la hora a la que se inicia el proceso de depuración. De forma predeterminada, se establece en 0:00 \(o 12:00 medianoche\). Todos los días en este momento, el proceso de depuración se ejecuta en las salidas generadas antes del número de días especificado en la **Período de depuración del historial de salida** propiedad.

   >[!NOTE]
   >
   > De forma predeterminada, la función de depuración se ejecuta cada medianoche en salidas de más de 5 días.

1. Haga clic en **Guardar**.


## Cambiar el límite de lista de resultados generados recientemente {#id1679JH0H0O2}

Se puede cambiar el número máximo de salidas generadas que se muestran en la ficha Salidas para un mapa DITA. De forma predeterminada, se muestra una lista de las últimas 25 salidas generadas. Para cambiar el número de salidas que se mostrarán en la lista, actualice el **Límite de lista de salidas** configuración en la `com.adobe.fmdita.config.ConfigManager` paquete.

>[!TIP]
>
> Consulte la *Historial de salida* de la guía de prácticas recomendadas[apendice.md\#](appendix.md#) para conocer las prácticas recomendadas sobre cómo trabajar con el historial de resultados.

## Optimización del rendimiento de generación de salida {#id176LB050VUI}

AEM Guías de le permite configurar el tamaño del grupo de procesos de generación de salida que controla el número de procesos de generación de salida que se ejecutan simultáneamente. De forma predeterminada, el tamaño del grupo de procesos está establecido en el número de núcleos de procesamiento disponibles en el sistema más uno. Puede que desee cambiar este valor a 1 si desea una publicación secuencial. En este caso, se ejecuta la primera tarea de publicación y la siguiente tarea de publicación se almacena en la cola de publicación.

Para cambiar el tamaño del grupo de procesamiento de generación de salida, actualice el **Tamaño del grupo de generación** configuración en la `com.adobe.fmdita.publish.manager.PublishThreadManagerImpl` paquete.
