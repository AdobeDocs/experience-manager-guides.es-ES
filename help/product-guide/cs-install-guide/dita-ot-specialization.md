---
title: Utilizar la especialización personalizada DITA-OT y DITA
description: Aprenda a utilizar la especialización personalizada DITA-OT y DITA
exl-id: 4d3e0fc1-b684-44f9-ab0d-411033024019
feature: DITA-OT Configuration
role: Admin
level: Experienced
source-git-commit: 3119ef32a753afac9405af31a241ae508f922ea7
workflow-type: tm+mt
source-wordcount: '1701'
ht-degree: 0%

---

# Utilizar la especialización personalizada DITA-OT y DITA {#id181GAJ0005Z}

DITA Open Toolkit \(DITA-OT\) es un conjunto de herramientas de código abierto basadas en Java que proporcionan procesamiento para mapas DITA y contenido de temas. AEM Guides permite importar y utilizar fácilmente complementos DITA-OT personalizados. Una vez importado, AEM Guides puede configurarse para que utilice el complemento DITA-OT personalizado para generar resultados en cualquier formato. En el momento de generar la salida, simplemente seleccione la opción DITA-OT y AEM Guides utilizará el complemento DITA-OT personalizado para generar la salida requerida.

Si desea procesar parámetros Ant al publicar cualquier salida, AEM Guides le ofrece una forma sencilla de hacerlo. Puede especificar qué parámetros Ant desea utilizar y los mismos que procesará el proceso de publicación.

>[!NOTE]
>
> AEM Guides se suministra con la versión 3.3.2 de DITA-OT, pero admite una amplia gama de versiones, desde DITA-OT 1.7 hasta DITA-OT 4.x. Para obtener una lista completa de las versiones de DITA-OT, consulte [Versiones de DITA-OT](http://www.dita-ot.org/download).

>[!TIP]
>
> Consulte las secciones *Configuración de perfiles DITA-OT* y *Uso de DITA-OT personalizado* en la guía de prácticas recomendadas para conocer las prácticas recomendadas sobre el uso de complementos DITA-OT personalizados.

## Uso de complementos DITA-OT personalizados {#id181NH1020L7}

Para publicar un complemento DITA-OT personalizado, cargue el complemento DITA-OT personalizado en el repositorio de AEM. De forma predeterminada, AEM Guides incluye un perfil preconfigurado que contiene las configuraciones de las plantillas predeterminadas que se utilizan para editar y publicar contenido. Puede crear perfiles personalizados con plantillas personalizadas para utilizarlas al editar documentos y complementos DITA-OT personalizados para publicar contenido.

El paquete DITA-OT predeterminado disponible con AEM Guides viene con el procesador Apache FOP XSL-FO, que no admite la representación de ecuaciones de MathML. Si utiliza ecuaciones de MathML en el contenido, asegúrese de haber integrado un complemento del motor de renderización de MathML para Apache FOP o utilice un procesador XSL-FO diferente.

Siga estos pasos para cargar el complemento DITA-OT personalizado en el repositorio de AEM:

1. Descargue el archivo DITA-OT.zip desde el vínculo compartido en el correo electrónico de bienvenida.

1. Extraiga el contenido del archivo zip en su sistema.

1. Utilice un mecanismo de integrador de plugins DITA-OT para integrar la nueva versión de DITA-OT con su plugin DITA-OT personalizado.

1. Vuelva a crear el archivo ZIP manteniendo el mismo nombre \(`DITA-OT.ZIP`\) y la estructura de carpetas.

1. Cargue el archivo ZIP actualizado de nuevo en el repositorio de AEM.

   Asegúrese de realizar las siguientes comprobaciones antes de cargar el archivo ZIP:

   - Ejecute el integrador \(para instalar el complemento personalizado\) en un sistema operativo Mac/Linux para evitar problemas con los separadores de archivos: como los sistemas operativos Windows y Linux tienen diferentes separadores de archivos, el complemento integrado en el sistema operativo Mac/Linux es compatible con la configuración de Windows y Linux.
   - Asegúrese de que el archivo `DITA-OT.ZIP` contenga una carpeta denominada &quot;DITA-OT&quot; que tenga todos los complementos y archivos relevantes.
   - Compruebe que el archivo `DITA-OT.ZIP` que crea sea del tipo mime: &quot;nt:file&quot; \(corresponde al tipo principal de archivo ZIP cuando se carga en AEM\). Utilice una herramienta WebDAV o una implementación de código para cargar este archivo ZIP en la ruta deseada en AEM. \(No utilice el administrador de paquetes de AEM para implementar este archivo ZIP, ya que este ZIP no es un paquete de contenido de AEM, sino solo un archivo.\)

   >[!NOTE]
   >
   > Se recomienda no sobrescribir el paquete DITA-OT predeterminado. Debe cargar el paquete DITA-OT personalizado que contiene la carpeta del complemento /var/xml/dita\_resources/dita-ot. También puede hacerlo mediante la canalización de Cloud Manager. Consulte [Implementación en AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=es) en la documentación de AEM para obtener más información.

1. Puede elegir editar el perfil predeterminado, crear un nuevo perfil o duplicar la configuración del perfil predeterminado para crear un nuevo perfil.

   >[!NOTE]
   >
   > Puede actualizar el perfil predeterminado, pero no puede eliminarlo. Sin embargo, todos los perfiles nuevos que cree se pueden editar y eliminar.

1. Configure las siguientes propiedades para utilizar el complemento DITA-OT personalizado:

   | Nombre de la propiedad | Descripción |
   |-------------|-----------|
   | **Propiedades de perfil** |
   | Nombre de perfil | Proporcione un nombre único para este perfil. |
   | Reutilizar salida | *\(Opcional\)* Si su perfil se basa en un perfil existente, seleccione esta opción. Si selecciona esta opción, AEM Guides no volverá a extraer el contenido del paquete DITA-OT y reutilizará el paquete DITA-OT existente. |
   | Ruta de extracción de perfil | *\(Opcional\)* Especifique la ruta en la que DITA-OT se mantiene en el disco. De forma predeterminada, AEM Guides agrupa un paquete DITA-OT en su repositorio y se extrae en el disco en esta ruta. <br> **NOTA** Puede definir esta ruta usando cualquier variable o propiedad del sistema existente. Consulte la descripción de la propiedad [DITA-OT Environment Variables](#id181NH0YN0AX) para obtener más información. |
   | Ruta asignada | \(*Opcional*\) Especifique la ruta en el repositorio de contenido para el que se aplica este perfil. Puede especificar varias ubicaciones. |
   | **Propiedades DITA-OT** |
   | Tiempo de espera DITA-OT | \(*Opcional*\) Especifique el tiempo \(en segundos\) durante el cual AEM Guides espera una respuesta del complemento DITA-OT. Si no se recibe ninguna respuesta en el tiempo especificado, AEM Guides finaliza la tarea de publicación y la tarea se marca como fallida. Además, los registros de errores están disponibles en el archivo de registro de generación de resultados. <br> Valor predeterminado: 300 segundos \(5 minutos\) |
   | Argumentos de DITA-OT PDF | Especifique los argumentos de línea de comandos que procesa el complemento DITA-OT personalizado para generar la salida de PDF. Para todos los perfiles DITA-OT personalizados, especifique el siguiente argumento de línea de comandos:`-lib plugins/org.dita.pdf2.fop/lib/` |
   | Argumentos de DITA-OT AEM | \(*Opcional*\) Especifique los argumentos de línea de comandos personalizados que procesa el complemento DITA-OT personalizado para generar la salida del sitio de AEM. |
   | Rutas de biblioteca DITA-OT | \(*Opcional*\) Especifique las rutas de biblioteca adicionales del complemento DITA-OT. |
   | XML de compilación DITA-OT | \(*Opcional*\) Especifique la ruta del script de compilación Ant personalizado que se incluye con el complemento DITA-OT personalizado. Esta ruta es relativa al directorio DITA-OT del sistema de archivos. |
   | Carpeta de script DITA-OT Ant | \(Opcional\) Especifique la ruta de la carpeta de scripts DITA-OT Ant. Esta ruta es relativa al directorio DITA-OT del sistema de archivos. |
   | Variables de entorno DITA-OT | *\(Opcional\)* Especifique las variables de entorno que desea pasar al proceso DITA-OT. De manera predeterminada, AEM Guides agrega cuatro variables: `ANT_OPTS`, `ANT_HOME`, `PATH` y `CLASSPATH`. <br> Puede reutilizar cualquiera de las variables o propiedades de entorno del sistema existentes para generar nuevas variables de entorno. Por ejemplo, si tiene `JAVA_HOME` variable de sistema definida en el sistema y desea definir una nueva variable de entorno llamada `JAVA_BIN` que se ha creado con `JAVA_HOME`. A continuación, puede agregar la definición de `JAVA_BIN` como:`JAVA_BIN= ${JAVA_HOME}/bin` <br> **Nota:** También puede usar las propiedades del sistema Java para generar variables de entorno. Por ejemplo, si el script de inicio de AEM define una propiedad del sistema Java `java.io.tmpdir` en un directorio temporal, puede utilizar esta propiedad para definir una nueva variable como: `${java.io.tmpdir}/fmdita/dita_ot`. <br> **Importante:** Para reutilizar cualquier variable o propiedad del sistema existente, debe estar incluida en `${}`. |
   | Sobrescribir salida DITA-OT | Elija si la salida DITA-OT debe sobrescribirse. Mantenga esta opción seleccionada. |
   | Ruta de archivo zip de AEM DITA-OT | Especifique la ruta completa en la que se almacena el archivo DITA-OT.zip personalizado en el repositorio de AEM. |
   | Ruta de complemento de DITA-OT | Ruta del complemento personalizado. Este complemento se integra automáticamente con el paquete DITA-OT principal. |
   | Integrar catálogos | \(*Optional*\) ruta de acceso de los archivos personalizados DTD y XSD catalog.xml en el repositorio de AEM. Esto sólo debe proporcionarse cuando falten catálogos en el paquete DITA-OT. Estos catálogos se integran automáticamente con el DITA-OT principal como complemento. |
   | Agregar catálogo de ID de sistema | \(*Opcional*\) Seleccione esta opción sólo si faltan entradas de Id. público en el catálogo o si los archivos DITA utilizan únicamente los Id. de sistema relativos a la ruta de acceso del servidor desde la que se cargan. |
   | Ruta temporal DITA-OT | Ubicación temporal en la que se copian los ficheros DITA para su procesamiento. Antes de que DITA-OT procese los archivos, se copian en esta ubicación temporal. De manera predeterminada, la ubicación de almacenamiento temporal es: <br> `<*AEM-Install*>/crx-quickstart/profiles/ditamaps` <br> **Importante:** No debe cambiar la ruta de acceso predeterminada. |

   >[!NOTE]
   >
   > El instalador de AEM Guides crea dos variables de entorno que puede utilizar para especificar la ruta de los archivos de complemento DITA-OT personalizados. Estas variables de entorno son: `DITAOT\_DIR`, que contiene la ruta de acceso del directorio DITA-OT en el sistema de archivos; y `DITAMAP\_DIR`, que contiene la ruta de acceso donde se extrae el contenido del mapa DITA en el sistema de archivos.

1. Haga clic en **Listo** para guardar el perfil.


## Integración de la especialización DITA {#id211MB0E00XA}

La especialización DITA es el proceso de creación de nuevas estructuras DITA mediante la adición de nuevos elementos o la eliminación de elementos existentes. Para crear un nuevo elemento DITA, se puede tomar un elemento DITA existente como base y modificarlo según sus necesidades de creación. En esencia, la especialización DITA le permite crear modelos de información personalizados que cumplan con los requisitos de su empresa, conservando al mismo tiempo las ventajas de la arquitectura DITA existente.

La función Perfil (Profile) se puede utilizar para almacenar ajustes de especialización DITA personalizados. Esta configuración se puede utilizar en el momento de crear y publicar contenido DITA personalizado. AEM Guides le permite utilizar un ID público y un ID del sistema en sus DTD/XSD personalizados.

>[!NOTE]
>
> El editor web de AEM Guides no es compatible con XSD.

Realice los siguientes pasos para crear un nuevo perfil y configurarlo para utilizar DTD y XSD especializados en AEM Guides:

1. Cree una carpeta de especialización en el equipo local que contenga los DTD y XSD especializados.

1. Especifique los detalles de DTD en el archivo `catalog.xml` que también se deben incluir en la carpeta de especialización.

   >[!NOTE]
   >
   > En el caso de DITA 1.3, la ubicación predeterminada del archivo DTD `catalog.xml` en el repositorio de AEM es: `/libs/fmdita/dita_resources/DITA-1.3/dtd/catalog.xml`.

1. Especifique los detalles XSD en el archivo `catalog.xml` que también se deben incluir en la carpeta de especialización.

   >[!NOTE]
   >
   > En el caso de DITA 1.3, la ubicación predeterminada del archivo catalog.xml XSD en el repositorio de AEM es: `/libs/fmdita/dita_resources/DITA-1.3/xsd/catalog.xml`.

1. Cargue la carpeta en la siguiente ubicación:

   `/var/dxml/dita_resources`

1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.

1. Seleccione **Guías** de la lista de herramientas.

1. Haga clic en el mosaico **Perfiles DITA**.

1. Puede elegir editar el perfil predeterminado, crear un nuevo perfil o duplicar la configuración del perfil predeterminado para crear un nuevo perfil.

   >[!NOTE]
   >
   > No puede eliminar el perfil predeterminado. Sin embargo, todos los perfiles nuevos que cree se pueden editar y eliminar.

1. En la configuración de **Esquema** \> **Catálogo**, especifique la ruta de los archivos DTD y XSD `catalog.xml` personalizados del repositorio de AEM.

1. Seleccione la opción **Agregar catálogo de ID de sistema**.

   >[!NOTE]
   >
   > Seleccione esta opción sólo si faltan entradas de Id. público en el catálogo o si los archivos DITA utilizan sólo los Id. de sistema relativos a la ruta de acceso del archivo local desde la que se cargan.

   Para obtener más información acerca de otras propiedades de la página Perfiles, vea la tabla de propiedades en [Paso 6](#id17A9F0D075Z) de la sección [Usar complementos DITA-OT personalizados](#id181NH1020L7).

1. Haga clic en **Listo** para guardar el perfil.
