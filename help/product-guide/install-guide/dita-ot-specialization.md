---
title: Utilizar la especialización personalizada DITA-OT y DITA
description: Aprenda a utilizar la especialización personalizada DITA-OT y DITA
exl-id: ddc1393b-b269-40e5-9627-96dad82b42e9
source-git-commit: 8e8e64ad1105b0546856cb82b47547ceacd405b9
workflow-type: tm+mt
source-wordcount: '2093'
ht-degree: 0%

---

# Utilizar la especialización personalizada DITA-OT y DITA {#id181GAJ0005Z}

DITA Open Toolkit \(DITA-OT\) es un conjunto de herramientas de código abierto basadas en Java que proporcionan procesamiento para mapas DITA y contenido de temas. AEM Las guías de la aplicación le permiten importar y utilizar fácilmente complementos DITA-OT personalizados. AEM Una vez importadas, se pueden configurar las guías de la aplicación para que utilicen el complemento DITA-OT personalizado para generar resultados en cualquier formato. AEM En el momento de generar la salida, simplemente seleccione la opción DITA-OT y Guías utiliza el complemento DITA-OT personalizado para generar la salida requerida.

AEM Si desea procesar los parámetros Ant al publicar cualquier salida, Guías de le ofrece una forma sencilla de hacerlo. Puede especificar qué parámetros Ant desea utilizar y los mismos que procesará el proceso de publicación.

>[!NOTE]
>
> AEM Las guías se envían con DITA-OT versión 3.3.2. AEM Sin embargo, las guías de la aplicación de la versión de DITA-OT 1.7 y posteriores. Para obtener la lista completa de las versiones de DITA-OT, consulte [Versiones DITA-OT](http://www.dita-ot.org/download).

>[!TIP]
>
> Consulte la *Configuración de perfiles DITA-OT* y *Uso de DITA-OT personalizado* secciones en la Guía de prácticas recomendadas para prácticas recomendadas sobre el uso de complementos DITA-OT personalizados.

## Uso de complementos DITA-OT personalizados {#id181NH1020L7}

Existen dos maneras de utilizar el complemento DITA-OT personalizado para la publicación. AEM El primer método consiste en cargar el complemento DITA-OT personalizado en el repositorio de la. El otro método es guardar el complemento DITA-OT personalizado en el servidor, crear un perfil y proporcionar la ubicación del complemento DITA-OT personalizado en el perfil.

AEM De forma predeterminada, las guías de la aplicación incluyen un perfil preconfigurado que contiene las configuraciones de las plantillas predeterminadas que se utilizan para editar y publicar contenido. Puede crear perfiles personalizados con plantillas personalizadas para utilizarlas al editar documentos y complementos DITA-OT personalizados para publicar contenido.

AEM El paquete DITA-OT predeterminado disponible con Guías de viene con el procesador Apache FOP XSL-FO, que no admite la representación de ecuaciones MathML. Si utiliza ecuaciones de MathML en el contenido, asegúrese de haber integrado un complemento del motor de renderización de MathML para Apache FOP o utilice un procesador XSL-FO diferente.

>[!IMPORTANT]
>
> AEM Si ha actualizado las guías de la versión de 2.2 a 2.5.1 o 2.6, todos los cambios realizados a través del administrador de configuración se seleccionan automáticamente y se almacenan en el perfil predeterminado.

AEM Realice los siguientes pasos para cargar el complemento DITA-OT personalizado en el repositorio de:

1. AEM Inicie sesión en la aplicación y abra el modo CRXDE Lite.

1. Descargue la `DITA-OT.ZIP` archivo.

   La ubicación del `DITA-OT.ZIP` el archivo es `/libs/fmdita/dita_resources/DITA-OT.zip`.

   ![](assets/dita-ot-zip-in-crx.png)

1. Extraiga el contenido del archivo zip en el servidor.

1. Utilice un mecanismo de integrador de plugins DITA-OT para integrar la nueva versión de DITA-OT con su plugin DITA-OT personalizado.

   >[!NOTE]
   >
   > El separador de rutas de clase del archivo ZIP del complemento depende del sistema operativo, lo que significa que si el servidor está alojado en Windows, el separador de rutas de clase será diferente del utilizado en Linux. Para obtener más información sobre la integración manual de complementos, consulte la *Instalación manual de complementos* tema en la documentación de DITA-OT.

1. Vuelva a crear el archivo ZIP manteniendo el mismo nombre \(`DITA-OT.ZIP`\) y la estructura de carpetas.

1. AEM Cargue el archivo ZIP actualizado de nuevo en el repositorio de.

   Asegúrese de realizar las siguientes comprobaciones antes de cargar el archivo ZIP:

   - Ejecute el integrador \(para instalar el complemento personalizado\) en un sistema operativo Mac/Linux para evitar problemas con los separadores de archivos: como los sistemas operativos Windows y Linux tienen diferentes separadores de archivos, el complemento integrado en el sistema operativo Mac/Linux es compatible con la configuración de Windows y Linux.
   - Asegúrese de que la variable `DITA-OT.ZIP` contiene una carpeta denominada &quot;DITA-OT&quot; que contiene todos los plugins y archivos relevantes.
   - Compruebe que `DITA-OT.ZIP` AEM el archivo que cree es del tipo mime: &quot;nt:file&quot; \(corresponde al tipo principal de archivo ZIP cuando se carga en el servidor de correo electrónico al cargar el archivo en el servidor de correo electrónico). AEM Utilice una herramienta WebDAV o una implementación de código para cargar este archivo ZIP en la ruta deseada en la. AEM AEM \(No utilice el administrador de paquetes de la aplicación para implementar este archivo ZIP, ya que este ZIP no es un paquete de contenido de la aplicación, sino solo un archivo de almacenamiento.\)
   >[!NOTE]
   >
   > Se recomienda no sobrescribir el paquete DITA-OT predeterminado. Debe cargar el paquete DITA-OT personalizado que contiene el complemento en alguna otra ubicación de la `apps` carpeta.

1. Abra el perfil DITA predeterminado para editarlo y guárdelo \(sin realizar ninguna actualización\) para que los cambios surtan efecto.


Realice los siguientes pasos para crear un nuevo perfil y configurarlo para utilizar el complemento DITA-OT personalizado almacenado en el servidor:

1. Almacene el complemento DITA-OT personalizado en el servidor.

   >[!NOTE]
   >
   > La estructura de carpetas para almacenar el complemento DITA-OT personalizado debe ser la siguiente: `\*<parent-folder\>*\DITA-OT`.

1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.

1. Seleccionar **Guías** de la lista de herramientas.

1. Haga clic en **Perfiles DITA** mosaico.

   >[!NOTE]
   >
   > La información de Perfil predeterminado se muestra en la página Perfiles. AEM Si ha actualizado las guías de la versión de 2.2 a 2.5.1 o 2.6, todos los cambios realizados a través del administrador de configuración se seleccionan automáticamente y se almacenan en el perfil predeterminado.

1. Puede elegir editar el perfil predeterminado, crear un nuevo perfil o duplicar la configuración del perfil predeterminado para crear un nuevo perfil.

   >[!NOTE]
   >
   > Puede actualizar el perfil predeterminado, pero no puede eliminarlo. Sin embargo, todos los perfiles nuevos que cree se pueden editar y eliminar.

1. Configure las siguientes propiedades para utilizar el complemento DITA-OT personalizado:

   | Nombre de la propiedad | Descripción |
   |-------------|-----------|
   | **Propiedades de perfil** |
   | Nombre de perfil | Proporcione un nombre único para este perfil. |
   | Reutilizar salida | *\(Opcional\)* Si el perfil se basa en un perfil existente, seleccione esta opción. AEM Al seleccionar esta opción, se asegura de que Guías de no vuelva a extraer el contenido del paquete DITA-OT y vuelva a utilizar el paquete DITA-OT existente. |
   | Ruta de extracción de perfil | *\(Opcional\)* Especifique la ruta en la que DITA-OT se guarda en el disco. AEM De forma predeterminada, Guías de la aplicación agrupa un paquete DITA-OT en su repositorio y se extrae en el disco en esta ruta.<br>**Nota** Puede definir esta ruta utilizando cualquier variable o propiedad del sistema existente. Consulte la descripción de [Variables de entorno DITA-OT](#id181NH0YN0AX) para obtener más información. |
   | Ruta asignada | \(*Opcional*\) Especifique la ruta en el repositorio de contenido para la que se aplica este perfil. Puede especificar varias ubicaciones. |
   | **Propiedades de DITA-OT** |
   | Tiempo de espera DITA-OT | \(*Opcional* AEM \) Especifique el tiempo \(en segundos\) durante el que Guías de la aplicación espera una respuesta del complemento DITA-OT. AEM Si no se recibe ninguna respuesta en el tiempo especificado, Guías de publicación finaliza la tarea de publicación y la tarea se marca como fallida. Además, los registros de errores están disponibles en el archivo de registro de generación de resultados. <br>Valor predeterminado: 300 segundos \(5 minutos\) |
   | Argumentos del PDF DITA-OT | Especifique los argumentos de línea de comandos que procesa el complemento DITA-OT personalizado para generar la salida del PDF. Para todos los perfiles DITA-OT personalizados, especifique el siguiente argumento de línea de comandos:`-lib plugins/org.dita.pdf2.fop/lib/` |
   | AEM Argumentos de DITA-OT | \(*Opcional* AEM \) Especifique los argumentos de línea de comandos personalizados que procesa el complemento DITA-OT personalizado para generar la salida del sitio de la página de comandos de la página de comandos de la página de inicio de sesión (SITE) de la página de salida de la página de la página de. |
   | Rutas de biblioteca DITA-OT | \(*Opcional*\) Especifique las rutas de biblioteca adicionales del complemento DITA-OT. |
   | XML de compilación DITA-OT | \(*Opcional*\) Especifique la ruta del script de Ant build personalizado incorporado al complemento DITA-OT personalizado. Esta ruta es relativa al directorio DITA-OT del sistema de archivos. |
   | Carpeta de script DITA-OT Ant | \(Opcional\) Especifique la ruta de la carpeta de scripts DITA-OT Ant. Esta ruta es relativa al directorio DITA-OT del sistema de archivos. |
   | Variables de entorno DITA-OT | *\(Opcional\)* Especificar variables de entorno para pasar al proceso DITA-OT. AEM De forma predeterminada, Guías de agrega cuatro variables: `ANT_OPTS`, `ANT_HOME`, `PATH`, y `CLASSPATH`. <br> Puede reutilizar cualquiera de las variables o propiedades de entorno del sistema existentes para crear nuevas variables de entorno. Por ejemplo, si tiene `JAVA_HOME` definida en el sistema y desea definir una nueva variable de entorno llamada `JAVA_BIN` que se crea mediante `JAVA_HOME`. A continuación, puede agregar la definición de `JAVA_BIN` como:<br> `JAVA_BIN= ${JAVA_HOME}/bin` <br> **Nota** También puede utilizar las propiedades del sistema Java para crear variables de entorno. AEM Por ejemplo, si la secuencia de comandos de inicio define una propiedad del sistema JavaScript, `java.io.tmpdir` a un directorio temporal, puede utilizar esta propiedad para definir una nueva variable como: `${java.io.tmpdir}/fmdita/dita_ot`. <br> **Importante** Para reutilizar cualquier variable o propiedad del sistema existente, debe incluirse dentro de `${}`. |
   | Sobrescribir salida DITA-OT | *\(Opcional\)* Si se selecciona esta opción, se puede especificar el paquete DITA-OT disponible en el sistema local para generar la salida mediante DITA-OT. Esta configuración se establece al activar ConfigManager. <br> AEM Si desea especificar la ruta de un paquete DITA-OT almacenado en el servidor, anule la selección de esta opción. |
   | AEM Ruta de archivo zip de DITA-OT/ Ruta de directorio DITA-OT local | En función de lo que seleccione en Sobrescribir salida DITA-OT, especifique la ruta completa en la que se almacena el fichero DITA-OT.zip personalizado. AEM Podría ser la ruta en su repositorio de o en el sistema local. |
   | Ruta de complemento de DITA-OT | Ruta del complemento personalizado. Este complemento se integra automáticamente con el paquete DITA-OT principal. |
   | Integrar catálogos | \(*Opcional* AEM \) Ruta de los archivos DTD y XSD catalog.xml personalizados en el repositorio de. Esto sólo debe proporcionarse cuando falten catálogos en el paquete DITA-OT. Estos catálogos se integran automáticamente con el DITA-OT principal como complemento. |
   | Agregar catálogo de ID de sistema | \(*Opcional*\) Seleccione esta opción sólo si faltan entradas de Id. público en el catálogo o si los archivos DITA utilizan sólo los Id. de sistema relativos a la ruta del servidor desde la que se cargan. |
   | Ruta temporal DITA-OT | *\(Opcional\)* Especifique una ubicación temporal en la que los ficheros DITA se copien para su procesamiento. Antes de que DITA-OT procese los archivos, se copian en esta ubicación temporal. De forma predeterminada, la ubicación de almacenamiento temporal es: <br> **Nota** Puede definir esta ruta utilizando cualquier variable o propiedad del sistema existente. Consulte la descripción de [Variables de entorno DITA-OT](#id181NH0YN0AX) para obtener más información. |

   >[!NOTE]
   >
   >  AEM El programa de instalación de guías de la aplicación crea dos variables de entorno que se pueden utilizar para especificar la ruta de los archivos de complemento DITA-OT personalizados. Estas variables de entorno son: DITAOT\_DIR, que contiene la ruta del directorio DITA-OT en el sistema de archivos; y DITAMAP\_DIR, que contiene la ruta en la que el contenido del mapa DITA se extrae en el sistema de archivos.

1. Clic **Listo** para guardar el perfil.


>[!NOTE]
>
> AEM Puede exportar el perfil DITA personalizado como paquete y cargarlo en las demás instancias de guías de la aplicación para ahorrar tiempo. Para obtener más información, consulte [Apéndice](appendix.md).

## Integración de la especialización DITA {#id211MB0E00XA}

La especialización DITA es el proceso de creación de nuevas estructuras DITA mediante la adición de nuevos elementos o la eliminación de elementos existentes. Para crear un nuevo elemento DITA, se puede tomar un elemento DITA existente como base y modificarlo según sus necesidades de creación. En esencia, la especialización DITA le permite crear modelos de información personalizados que cumplan con los requisitos de su empresa, conservando al mismo tiempo las ventajas de la arquitectura DITA existente.

La función Perfil (Profile) se puede utilizar para almacenar ajustes de especialización DITA personalizados. Esta configuración se puede utilizar en el momento de crear y publicar contenido DITA personalizado. AEM Guías de le permiten utilizar un ID público y un ID del sistema en sus DTD/XSD personalizados.

>[!NOTE]
>
> AEM El Editor web de guías no es compatible con XSD.

AEM Realice los siguientes pasos para crear un nuevo perfil y configurarlo para utilizar guías de administración de DTD y XSD especializadas:

1. Cree una carpeta de especialización en el equipo local que contenga los DTD y XSD especializados.

1. Especifique los detalles de la DTD en la `catalog.xml` que también debe incluirse en la carpeta de especialización.

   >[!NOTE]
   >
   > En el caso de DITA 1.3, la ubicación por defecto para DTD `catalog.xml` AEM el archivo en el repositorio de es: `/libs/fmdita/dita_resources/DITA-1.3/dtd/catalog.xml`.

1. Especifique los detalles del XSD en la variable `catalog.xml` que también debe incluirse en la carpeta de especialización.

   >[!NOTE]
   >
   > AEM En el caso de DITA 1.3, la ubicación predeterminada para el archivo catalog.xml XSD en el repositorio de es: `/libs/fmdita/dita_resources/DITA-1.3/xsd/catalog.xml`.

1. Cargue la carpeta en la siguiente ubicación:

   `/apps/fmdita/dita_resources`

1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.

1. Seleccionar **Guías** de la lista de herramientas.

1. Haga clic en **Perfiles DITA** mosaico.

   >[!NOTE]
   >
   > La información de Perfil predeterminado se muestra en la página Perfiles. AEM Si ha actualizado las guías de la versión de 2.2 a 2.5.1 o 2.6, todos los cambios realizados a través del administrador de configuración se seleccionan automáticamente y se almacenan en el perfil predeterminado.

1. Puede elegir editar el perfil predeterminado, crear un nuevo perfil o duplicar la configuración del perfil predeterminado para crear un nuevo perfil.

   >[!NOTE]
   >
   > No puede eliminar el perfil predeterminado. Sin embargo, todos los perfiles nuevos que cree se pueden editar y eliminar.

1. En el **Esquema** \> **Catálogo** , especifique la ruta del DTD y XSD personalizados `catalog.xml` AEM archivos en el repositorio de.

1. Seleccione el **Agregar catálogo de ID de sistema** opción.

   >[!NOTE]
   >
   > Seleccione esta opción sólo si faltan entradas de Id. público en el catálogo o si los archivos DITA utilizan sólo los Id. de sistema relativos a la ruta de acceso del archivo local desde la que se cargan.

   Para obtener más información sobre otras propiedades de la página Perfiles, consulte la tabla de propiedades en [Paso 6](#id17A9F0D075Z) de la [Uso de complementos DITA-OT personalizados](#id181NH1020L7) sección.

1. Clic **Listo** para guardar el perfil.


>[!NOTE]
>
> AEM Puede exportar el perfil DITA personalizado como paquete y cargarlo en las demás instancias de guías de la aplicación para ahorrar tiempo. Para obtener más información, consulte [Apéndice.md](appendix.md).
