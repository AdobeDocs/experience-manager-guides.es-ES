---
title: Sitio de AEM
description: Cree y configure los ajustes preestablecidos de sitios de AEM en AEM Guides desde el panel de mapas. Utilice la compatibilidad con sitios de AEM para generar resultados basados en artículos, publicar temas vinculados , conref y buscar una cadena dentro del contenido.
feature: Publishing
role: User
exl-id: 641c98ca-b815-4176-abf5-a12c31ff4496
source-git-commit: 558cc1a724a483353eb5d912354e1ab37dab348a
workflow-type: tm+mt
source-wordcount: '2404'
ht-degree: 0%

---

# Ajustes preestablecidos de AEM Sites en el tablero de mapas {#id205BE3008SW}

Puede crear ajustes preestablecidos de AEM Sites desde el panel de asignaciones y configurarlos para generar la salida de AEM Sites.


Las siguientes opciones están disponibles para la salida de AEM Sites:

| Opciones de AEM Sites | Descripción |
| --- | --- |
| Tipo de salida | El tipo de salida que desea generar. Para generar una salida de AEM Sites adaptable, elija la opción AEM Sites. |
| Nombre de configuración | Asigne un nombre descriptivo a la configuración de AEM Sites que está creando. Por ejemplo, puede especificar *salida de clientes internos* o *salida de usuarios finales*. |
| Nombre del sitio | Un nombre de sitio donde la salida se almacena en el repositorio de AEM.<br><br>Se crea un nodo en el repositorio de AEM con el nombre especificado aquí. Si no se especifica el Nombre del sitio (Site Name), se creará el nodo de sitio con el nombre de fichero de mapa DITA.<br><br>El nombre de sitio que especifique aquí también se utiliza como título en la ficha del explorador.<br><br>También puede utilizar variables al establecer el Nombre del sitio. Para obtener más información acerca del uso de variables, vea [Usar variables para establecer las opciones Ruta de destino, Nombre de sitio o Nombre de archivo](generate-output-use-variables.md#id18BUG70K05Z). |
| Diseño | Seleccione la plantilla de diseño que desee utilizar para generar el resultado.<br><br>Para obtener más información acerca de cómo usar plantillas de diseño personalizadas para generar resultados, póngase en contacto con el administrador de publicaciones. |
| Ruta de destino | La ruta dentro del repositorio de AEM donde se almacena el resultado. Al generar la salida final, se combinan el Nombre del sitio y la Ruta de destino. Por ejemplo, si especifica el Nombre del sitio como `user-guide` y la Ruta de destino como `/content/output/aem-guides`, el resultado final se generará en el nodo `/content/output/aem-guides/user-guide`.<br><br>También puede utilizar variables al establecer la ruta de destino. Para obtener más información acerca del uso de variables, vea [Usar variables para establecer las opciones Ruta de destino, Nombre de sitio o Nombre de archivo](generate-output-use-variables.md#id18BUG70K05Z). |
| Aplicar condiciones usando | Seleccione una de las siguientes opciones:<br><br>**Ninguna aplicada**: seleccione esta opción si no desea aplicar ninguna condición en la salida publicada.<br>**archivo DITAVal**: seleccione los archivos DITAVal para generar contenido condicionado. Puede seleccionar varios archivos DITAVal mediante el cuadro de diálogo de exploración o escribiendo la ruta del archivo. Utilice el icono en forma de cruz situado cerca del nombre del archivo para eliminarlo. Los archivos DITAVal se evalúan en el orden especificado, por lo que las condiciones especificadas en el primer archivo tienen prioridad sobre las condiciones coincidentes especificadas en archivos posteriores. Puede mantener el orden de los archivos añadiendo o eliminando archivos. Si el archivo DITAVal se mueve a otra ubicación o se elimina, no se elimina automáticamente del panel de asignaciones. Debe actualizar la ubicación en caso de que los archivos se muevan o eliminen. Puede pasar el ratón sobre el nombre del archivo para ver la ruta en el repositorio de AEM donde está almacenado el archivo. Solo puede seleccionar archivos DITAVal y se muestra un error si selecciona cualquier otro tipo de archivo.<br>**Ajuste preestablecido de condición**: seleccione un ajuste preestablecido de condición en la lista desplegable para aplicar una condición al publicar la salida. Esta opción está visible si se ha añadido una condición para el fichero de mapa DITA. La configuración condicional está disponible en la ficha Ajustes preestablecidos de condición de la consola de mapas DITA. Para obtener más información sobre los ajustes preestablecidos de condición, consulte [Usar ajustes preestablecidos de condición](generate-output-use-condition-presets.md#id1825FL004PN). |
| Páginas de salida existentes | Seleccione la opción **Sobrescribir contenido** para sobrescribir contenido en las páginas existentes. Esta opción solo sobrescribe el contenido presente en los nodos de contenido y encabezado de la página. Esta opción habilita la publicación combinada de contenido. Al seleccionar esta opción, se proporciona una opción para seleccionar la eliminación de páginas huérfanas de la salida publicada. Esta es también la opción *default* para crear la salida de AEM Sites.<br><br>Seleccione la opción **Eliminar y crear** para forzar la eliminación de las páginas existentes durante la publicación. Esta opción elimina el nodo de página junto con su contenido y todas las páginas secundarias debajo de él. Utilice esta opción si ha cambiado la plantilla de diseño del ajuste preestablecido de salida o si desea que se eliminen las páginas adicionales ya presentes en el destino. |
| Eliminar páginas de sitio huérfanas | Si se selecciona **Sobrescribir contenido** en la configuración de **Páginas de salida existentes**, se presenta esta opción. Si selecciona esta opción, se eliminarán todas las páginas huérfanas del sitio de AEM publicado. Para que esta función se ejecute correctamente, debe publicar todo el mapa DITA y no utilizar la publicación incremental.<br><br>Supongamos que ha publicado un mapa DITA, que contiene los temas a.dita, b.dita y c.dita. Antes de volver a publicar el mapa, ha eliminado el tema b.dita del mapa. Ahora, si ha seleccionado esta opción, todo el contenido relacionado con b.dita se elimina de la salida de AEM Sites y solo se publican a.dita y c.dita.<br><br>Esta característica no quita ningún mapa secundario publicado. Por ejemplo, si el mapa principal contiene un mapa secundario y se elimina todo el mapa secundario, el contenido del mapa secundario no se elimina de la salida publicada. Sin embargo, si quita cualquier tema de un mapa secundario y vuelve a publicar, el contenido del tema eliminado se elimina de la salida del sitio.<br><br>Además, si hay contenido referenciado y ese contenido se quita antes de volver a publicar, los datos del contenido referenciado no se quitan.<br><br>**Nota**: la información sobre las páginas huérfanas eliminadas también se captura en los registros de generación de salida. Para obtener más información acerca del acceso a los archivos de registro, vea [Ver y comprobar el archivo de registro](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). |
| Conservar archivos temporales | Seleccione esta opción para conservar los ficheros temporales generados por DITA-OT. Si se producen errores al generar la salida mediante DITA-OT, seleccione esta opción para conservar los ficheros temporales. Puede utilizar esos archivos para solucionar errores de generación de resultados.<br> <br> Después de generar la salida, seleccione el icono **Descargar archivos temporales** ![descargar archivos temporales](images/download-temp-files-icon.png) para descargar la carpeta ZIP que contiene los archivos temporales. <br><br> **Nota**: Si las propiedades de archivo se agregan durante la generación, los archivos temporales de salida también incluyen un archivo *metadata.xml* que contiene esas propiedades. |
| Generar PDF independiente para cada tema | Si se selecciona, también se crea una PDF para cada tema del mapa DITA. Al elegir esta opción, se muestra una nueva opción Dividir ruta de PDF.<br><br>En el campo Dividir ruta de PDF, especifique la ruta para almacenar los archivos PDF generados para cada tema.<br><br>**Nota**: AEM Guides usa el complemento DITA-OT llamado pdfx para generar PDF para cada tema. Este complemento se incluye con el paquete DITA-OT que se suministra listo para usar. Puede personalizar este complemento para que genere PDF según sus necesidades. Si utiliza un complemento DITA-OT personalizado, asegúrese de integrar el complemento pdfx para tener la capacidad de generación de PDF de nivel de tema. |
| Ejecutar flujo de trabajo posterior a generación | Al elegir esta opción, se muestra una nueva lista desplegable Flujo de trabajo de generación posterior que contiene todos los flujos de trabajo configurados en AEM. Debe seleccionar un flujo de trabajo que desee ejecutar después de completar el flujo de trabajo de generación de resultados. |
| Usar línea base | Si ha creado una Línea base para el mapa DITA seleccionado, seleccione esta opción para especificar la versión que desea publicar.<br><br>**Importante**: cuando se genera un resultado incremental para el sitio de AEM, el resultado se crea utilizando la versión actual de los archivos y no la línea de base adjunta.<br><br>Vea [Trabajar con línea de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obtener más detalles. |
| Propiedades | Seleccione las propiedades que desee procesar como metadatos. Estas propiedades se definen desde la página Propiedades del fichero de mapa DITA o de mapa de libros. Las propiedades que seleccione en la lista desplegable aparecerán en el campo **Propiedades del archivo**. Seleccione el icono en forma de cruz situado junto a la propiedad para eliminarla. <br><br>**Nota**: las propiedades de metadatos distinguen entre mayúsculas y minúsculas.<br><br>*Si ha seleccionado una Línea base, los valores de las propiedades se basan en la versión de la Línea base seleccionada.<br>* Si no ha seleccionado una Línea de base, los valores de las propiedades se basan en la versión más reciente.<br><br>También puede pasar los metadatos a la salida mediante la publicación DITA-OT. Para obtener más información, consulte [Pasar los metadatos a la salida mediante DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Nota**: si no ha definido `cq:tags` en la opción Propiedades, los valores de `cq:tags` se seleccionarán de la copia de trabajo actual aunque haya seleccionado una Línea de base para la publicación. |
| Usar las propiedades de mapa como predeterminadas | Si se selecciona, las propiedades definidas para el fichero de mapa también se copian en los temas en los que no se definen dichas propiedades. Tenga en cuenta los siguientes puntos al utilizar esta opción:<br><br>*Solo las propiedades String, Date o Long (únicas y de varios valores) se pueden pasar a las páginas de AEM Sites.<br>* Los valores de metadatos de una propiedad de tipo cadena no admiten ningún carácter especial (como `@, #, " "`).<br>* Esta opción debe usarse junto con la opción `Properties`. |

## Nota adicional sobre AEM Sites

### Generar resultados basados en artículos desde la consola Mapa

Se puede generar la salida de AEM Sites para uno o más temas o todo el mapa DITA desde la consola Mapa. Debe crear ajustes preestablecidos de salida para el mapa DITA y, a continuación, puede generar fácilmente la salida AEM Sites para el mapa. Si ha actualizado algunos temas en el mapa, también puede generar la salida de AEM Sites solo para esos temas desde la consola Mapa. Para obtener más información, vea [Generar salida de la base de conocimiento](web-editor-article-publishing.md#id218CK0U019I).

### Generar resultados de temas de vinculación de otros mapas

Es muy común tener un gran conjunto de documentación distribuida en varias carpetas y mapas DITA. Publicar contenido vinculado desde varios lugares se vuelve extremadamente complejo. De manera predeterminada, todos los vínculos `<xref>` se crean con `local` `@scope`. La publicación de estos temas no implica ningún desafío, ya que utiliza un vínculo directo al tema. Si el tema se encuentra fuera del mapa DITA actual, el vínculo no muestra el contenido enlazado.

Otra forma de vincular contenido es crear un vínculo con `peer` `@scope`. Para dicho contenido, el vínculo se resuelve en tiempo de ejecución seleccionando el título del archivo y el contexto configurado para el tema vinculado desde el contexto de publicación del mapa DITA. La siguiente captura de pantalla muestra el panel Propiedades de un vínculo que tiene `peer` `@scope`:

![](images/peer-link-scope-link-new.png){width="800" align="left"}

Para simplificar la publicación de mapas complejos y temas que vinculan a otros temas en otros mapas, Adobe Experience Manager Guides permite establecer el contexto de publicación para cada ajuste preestablecido de salida.

El contexto de publicación permite especificar qué tema se debe utilizar desde qué mapa para publicar una salida específica. Entendámoslo con la ayuda de un ejemplo. Digamos que tenemos cuatro carpetas: muestra a, muestra b, muestra c, y muestra d. Cada carpeta contiene un mapa DITA: el mapa DITA A, el mapa DITA B, el mapa DITA C y el mapa DITA D. La vinculación entre mapas se producirá cuando un tema del mapa DITA A se vincule a un tema del mapa DITA B, C o D. En la siguiente captura de pantalla, un tema de concepto de ejemplo contiene vínculos \(o referencias\) a archivos que forman parte de otros mapas DITA.

![](images/sample-concept-link-to-other.png){width="350" align="left"}

Ahora, al establecer la configuración de publicación de AEM Sites para el archivo de asignación que contiene este tema, puede seleccionar qué contexto de publicación para el contenido vinculado se utiliza durante la publicación. Un contexto de publicación es una combinación de un mapa DITA y su ajuste preestablecido de salida. El ajuste preestablecido de salida, a su vez, contiene una versión específica del contenido y ajustes preestablecidos condicionales. Toda esta combinación del mapa DITA, el ajuste preestablecido de salida, la versión \(archivos\) y las condiciones definen el contexto de publicación para un mapa enlazado.

Siga estos pasos para especificar el contexto de publicación de los archivos de vínculos cruzados:

1. Abra la ficha **Ajustes preestablecidos de salida** del mapa DITA que desee publicar.

1. Seleccione el ajuste preestablecido de salida **AEM Site**.

   Obtendrá las pestañas Configuración de ajustes preestablecidos de AEM y Contexto de publicación.

   ![](images/aem-site-publish-settings.png){width="800" align="left"}

1. Abra la ficha **Contexto de publicación**.

   Se le mostrará una lista de temas dependientes. Estos son los temas vinculados a partir de algún tema del mapa actual, pero están disponibles en otros mapas DITA.

   >[!NOTE]
   >
   > La pestaña Publicar contexto muestra los temas que están vinculados usando solamente `peer` `@scope`. Para los vínculos con `local` `@scope`, no es necesario especificar el contexto de publicación.

   De forma predeterminada, todos los temas vinculados tienen seleccionados su último ajuste preestablecido de salida y su asignación.

   ![](images/default-publish-context.png){width="800" align="left"}

1. Para cambiar la selección predeterminada del mapa DITA y el ajuste preestablecido, seleccione **Editar** \(en la barra de herramientas principal\).

1. Si desea utilizar el resultado publicado más recientemente de cada archivo dependiente en el mapa, seleccione **Usar contexto de publicación generado más recientemente para todos los temas dependientes**.

1. En la lista desplegable **Mapa principal**, seleccione el archivo de mapa con cuya salida desee vincular la salida del mapa actual.

   Al seleccionar un archivo de asignación, el UUID del mapa se muestra en la columna UUID del mapa principal. Los ajustes preestablecidos de salida asociados con el mapa seleccionado se enumeran en la lista Ajustes preestablecidos del mapa principal.

1. En la lista desplegable **Ajuste preestablecido del mapa principal**, seleccione el ajuste preestablecido de salida con el que desea vincular la salida del mapa actual.

1. Seleccione la asignación requerida y su ajuste preestablecido de salida para todos los temas dependientes y seleccione **Listo**.

   El contexto de los temas dependientes ya está definido. Puede generar la salida para el mapa actual. Para obtener más información acerca de la generación de resultados, vea [Generar resultados para un mapa DITA desde la consola de mapas](generate-output-for-a-dita-map.md#).

### Publicación combinada

AEM Guides admite la publicación de contenido DITA en el sitio de AEM existente. Por ejemplo, si tiene un sitio existente, puede utilizar la salida de AEM Sites para publicar sólo el contenido DITA en ese sitio. En este proceso, el proceso de publicación no modifica el contenido no DITA existente. Para obtener más información acerca de cómo configurar el sitio para que publique únicamente contenido DITA, póngase en contacto con el administrador de publicación.

### Publicación `conref`

Si usa `conref` en el contenido, este se publica como contenido normal o incrustado junto con el contenido del tema de origen \(o referencia\). El contenido de `conref` se procesa junto con el contenido principal y no se crea ninguna página de sitio independiente para el mismo. Cuando busca el contenido al que se hace referencia en `conref`, solo se muestra en los resultados de la búsqueda el tema principal o la página que contiene el contenido de `conref`.

>[!NOTE]
>
>Si ha generado páginas independientes para el contenido de `conref` mediante AEM Guides versión 3.5 o anterior, se recomienda limpiar o eliminar esas páginas mediante la opción [Eliminar páginas de sitios huérfanos](#delete-orphan-page-aem-site).


### Buscar una cadena dentro del contenido

Puede buscar una cadena en la salida de AEM Sites. De forma predeterminada, solo puede buscar la cadena en los títulos. Para buscar la cadena en el contenido o en el cuerpo de la salida de AEM Sites, póngase en contacto con el administrador del sistema para habilitar la propiedad flattening.enabled.

![Buscar resultados de AEM Sites](images/aem-output-search.png){width="650" align="left"}

Para obtener más información, consulte la sección *Configuración del acoplamiento de la estructura del nodo del sitio de AEM* en la guía Instalar y configurar Adobe Experience Manager Guides.

**Tema principal:**[ Explicación de los ajustes preestablecidos de salida](generate-output-understand-presets.md)
