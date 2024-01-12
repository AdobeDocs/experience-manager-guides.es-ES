---
title: Utilizar la especialización personalizada DITA-OT y DITA
description: Aprenda a utilizar la especialización personalizada DITA-OT y DITA
exl-id: 4d3e0fc1-b684-44f9-ab0d-411033024019
feature: DITA-OT Configuration
role: Admin
level: Experienced
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '1697'
ht-degree: 0%

---

# Utilizar la especialización personalizada DITA-OT y DITA {#id181GAJ0005Z}

DITA Open Toolkit \(DITA-OT\) es un conjunto de herramientas de código abierto basadas en Java que proporcionan procesamiento para mapas DITA y contenido de temas. AEM Las guías de la aplicación le permiten importar y utilizar fácilmente complementos DITA-OT personalizados. AEM Una vez importadas, se pueden configurar las guías de la aplicación para que utilicen el complemento DITA-OT personalizado para generar resultados en cualquier formato. AEM En el momento de generar la salida, simplemente seleccione la opción DITA-OT y las Guías de usuario utilizan el complemento DITA-OT personalizado para generar la salida requerida.

AEM Si desea procesar los parámetros Ant al publicar cualquier salida, Guías de le ofrece una forma sencilla de hacerlo. Puede especificar qué parámetros Ant desea utilizar y los mismos que procesará el proceso de publicación.

>[!NOTE]
>
> AEM Las guías se envían con DITA-OT versión 3.3.2. AEM Sin embargo, las guías de la aplicación de la versión de DITA-OT 1.7 y posteriores. Para obtener la lista completa de las versiones de DITA-OT, consulte [Versiones DITA-OT](http://www.dita-ot.org/download).

>[!TIP]
>
> Consulte la *Configuración de perfiles DITA-OT* y *Uso de DITA-OT personalizado* secciones en la Guía de prácticas recomendadas para prácticas recomendadas sobre el uso de complementos DITA-OT personalizados.

## Uso de complementos DITA-OT personalizados {#id181NH1020L7}

AEM Puede utilizar el complemento DITA-OT personalizado para la publicación cargando el complemento DITA-OT personalizado en el repositorio de la. AEM De forma predeterminada, las guías de la aplicación incluyen un perfil preconfigurado que contiene las configuraciones de las plantillas predeterminadas que se utilizan para editar y publicar contenido. Puede crear perfiles personalizados con plantillas personalizadas para utilizarlas al editar documentos y complementos DITA-OT personalizados para publicar contenido.

AEM El paquete DITA-OT predeterminado disponible con Guías de viene con el procesador Apache FOP XSL-FO, que no admite la representación de ecuaciones MathML. Si utiliza ecuaciones de MathML en el contenido, asegúrese de haber integrado un complemento del motor de renderización de MathML para Apache FOP o utilice un procesador XSL-FO diferente.

AEM Realice los siguientes pasos para cargar el complemento DITA-OT personalizado en el repositorio de:

1. Descargue el archivo DITA-OT.zip desde el vínculo compartido en el correo electrónico de bienvenida.

1. Extraiga el contenido del archivo zip en su sistema.

1. Utilice un mecanismo de integrador de plugins DITA-OT para integrar la nueva versión de DITA-OT con su plugin DITA-OT personalizado.

1. Vuelva a crear el archivo ZIP manteniendo el mismo nombre \(`DITA-OT.ZIP`\) y la estructura de carpetas.

1. AEM Cargue el archivo ZIP actualizado de nuevo en el repositorio de.

   Asegúrese de realizar las siguientes comprobaciones antes de cargar el archivo ZIP:

   - Ejecute el integrador \(para instalar el complemento personalizado\) en un sistema operativo Mac/Linux para evitar problemas con los separadores de archivos: como los sistemas operativos Windows y Linux tienen diferentes separadores de archivos, el complemento integrado en el sistema operativo Mac/Linux es compatible con la configuración de Windows y Linux.
   - Asegúrese de que la variable `DITA-OT.ZIP` contiene una carpeta denominada &quot;DITA-OT&quot; que contiene todos los plugins y archivos relevantes.
   - Compruebe que `DITA-OT.ZIP` AEM el archivo que cree es del tipo mime: &quot;nt:file&quot; \(corresponde al tipo principal de archivo ZIP cuando se carga en el servidor de correo electrónico al cargar el archivo en el servidor de correo electrónico). AEM Utilice una herramienta WebDAV o una implementación de código para cargar este archivo ZIP en la ruta deseada en la. AEM AEM \(No utilice el administrador de paquetes de la aplicación para implementar este archivo ZIP, ya que este ZIP no es un paquete de contenido de la aplicación, sino solo un archivo de almacenamiento.\)

   >[!NOTE]
   >
   > Se recomienda no sobrescribir el paquete DITA-OT predeterminado. Debe cargar el paquete DITA-OT personalizado que contiene la carpeta del complemento /var/xml/dita\_resources/dita-ot. También puede hacerlo utilizando la canalización de Cloud Manager, consulte [AEM Implementación en el as a Cloud Service de](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=es) AEM en la documentación de la para obtener más información.

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
   | Ruta de extracción de perfil | *\(Opcional\)* Especifique la ruta en la que DITA-OT se guarda en el disco. AEM De forma predeterminada, Guías de la aplicación agrupa un paquete DITA-OT en su repositorio y se extrae en el disco en esta ruta. <br> **NOTA** Puede definir esta ruta utilizando cualquier variable o propiedad del sistema existente. Consulte la descripción de [Variables de entorno DITA-OT](#id181NH0YN0AX) para obtener más información. |
   | Ruta asignada | \(*Opcional*\) Especifique la ruta en el repositorio de contenido para la que se aplica este perfil. Puede especificar varias ubicaciones. |
   | **Propiedades de DITA-OT** |
   | Tiempo de espera DITA-OT | \(*Opcional* AEM \) Especifique el tiempo \(en segundos\) durante el que las guías de la aplicación de la aplicación esperan una respuesta del complemento DITA-OT. AEM Si no se recibe ninguna respuesta en el tiempo especificado, Guías de publicación finaliza la tarea de publicación y la tarea se marca como fallida. Además, los registros de errores están disponibles en el archivo de registro de generación de resultados. <br> Valor predeterminado: 300 segundos \(5 minutos\) |
   | Argumentos del PDF DITA-OT | Especifique los argumentos de línea de comandos que procesa el complemento DITA-OT personalizado para generar la salida del PDF. Para todos los perfiles DITA-OT personalizados, especifique el siguiente argumento de línea de comandos:`-lib plugins/org.dita.pdf2.fop/lib/` |
   | AEM Argumentos de DITA-OT | \(*Opcional* AEM \) Especifique los argumentos de línea de comandos personalizados que procesa el complemento DITA-OT personalizado para generar la salida del sitio de la página de comandos de la página de comandos de la página de inicio de sesión (SITE) de la página de salida de la página de la página de. |
   | Rutas de biblioteca DITA-OT | \(*Opcional*\) Especifique las rutas de biblioteca adicionales del complemento DITA-OT. |
   | XML de compilación DITA-OT | \(*Opcional*\) Especifique la ruta del script de Ant build personalizado incorporado al complemento DITA-OT personalizado. Esta ruta es relativa al directorio DITA-OT del sistema de archivos. |
   | Carpeta de script DITA-OT Ant | \(Opcional\) Especifique la ruta de la carpeta de scripts DITA-OT Ant. Esta ruta es relativa al directorio DITA-OT del sistema de archivos. |
   | Variables de entorno DITA-OT | *\(Opcional\)* Especificar variables de entorno para pasar al proceso DITA-OT. AEM De forma predeterminada, las Guías de añaden cuatro variables: `ANT_OPTS`, `ANT_HOME`, `PATH`, y `CLASSPATH`. <br> Puede reutilizar cualquiera de las variables o propiedades de entorno del sistema existentes para crear nuevas variables de entorno. Por ejemplo, si tiene `JAVA_HOME` definida en el sistema y desea definir una nueva variable de entorno llamada `JAVA_BIN` que se crea mediante `JAVA_HOME`. A continuación, puede agregar la definición de `JAVA_BIN` como:`JAVA_BIN= ${JAVA_HOME}/bin` <br> **Nota:** También puede utilizar las propiedades del sistema Java para crear variables de entorno. AEM Por ejemplo, si la secuencia de comandos de inicio define una propiedad del sistema JavaScript, `java.io.tmpdir` a un directorio temporal, puede utilizar esta propiedad para definir una nueva variable como: `${java.io.tmpdir}/fmdita/dita_ot`. <br> **Importante:** Para reutilizar cualquier variable o propiedad del sistema existente, debe incluirse dentro de `${}`. |
   | Sobrescribir salida DITA-OT | Elija si la salida DITA-OT debe sobrescribirse. Mantenga esta opción seleccionada. |
   | AEM Ruta de código postal de DITA-OT | AEM Especifique la ruta de acceso completa en la que se almacena el archivo DITA-OT.zip personalizado en el repositorio de. |
   | Ruta de complemento de DITA-OT | Ruta del complemento personalizado. Este complemento se integra automáticamente con el paquete DITA-OT principal. |
   | Integrar catálogos | \(*Opcional* AEM \) Ruta de los archivos DTD y XSD catalog.xml personalizados en el repositorio de. Esto sólo debe proporcionarse cuando falten catálogos en el paquete DITA-OT. Estos catálogos se integran automáticamente con el DITA-OT principal como complemento. |
   | Agregar catálogo de ID de sistema | \(*Opcional*\) Seleccione esta opción sólo si faltan entradas de Id. público en el catálogo o si los archivos DITA utilizan sólo los Id. de sistema relativos a la ruta del servidor desde la que se cargan. |
   | Ruta temporal DITA-OT | Ubicación temporal en la que se copian los ficheros DITA para su procesamiento. Antes de que DITA-OT procese los archivos, se copian en esta ubicación temporal. De forma predeterminada, la ubicación de almacenamiento temporal es: <br> `<*AEM-Install*>/crx-quickstart/profiles/ditamaps` <br> **Importante:** No debe cambiar la ruta predeterminada. |

   >[!NOTE]
   >
   > AEM El programa de instalación de guías de la aplicación crea dos variables de entorno que se pueden utilizar para especificar la ruta de los archivos de complemento DITA-OT personalizados. Estas variables de entorno son: `DITAOT\_DIR`, que contiene la ruta del directorio DITA-OT en el sistema de archivos; y `DITAMAP\_DIR`, que contiene la ruta en la que se extrae el contenido del mapa DITA en el sistema de archivos.

1. Clic **Listo** para guardar el perfil.


## Integración de la especialización DITA {#id211MB0E00XA}

La especialización DITA es el proceso de creación de nuevas estructuras DITA mediante la adición de nuevos elementos o la eliminación de elementos existentes. Para crear un nuevo elemento DITA, se puede tomar un elemento DITA existente como base y modificarlo según sus necesidades de creación. En esencia, la especialización DITA le permite crear modelos de información personalizados que cumplan con los requisitos de su empresa, conservando al mismo tiempo las ventajas de la arquitectura DITA existente.

La función Perfil (Profile) se puede utilizar para almacenar ajustes de especialización DITA personalizados. Esta configuración se puede utilizar en el momento de crear y publicar contenido DITA personalizado. AEM Guías de le permiten utilizar un ID público y un ID del sistema en sus DTD/XSD personalizados.

>[!NOTE]
>
> AEM El Editor web de guías no es compatible con XSD.

AEM Realice los siguientes pasos para crear un nuevo perfil y configurarlo para utilizar DTD y XSD especializados en las guías de la:

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

   `/var/dxml/dita_resources`

1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.

1. Seleccionar **Guías** de la lista de herramientas.

1. Haga clic en **Perfiles DITA** mosaico.

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
