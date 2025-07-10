---
title: AEM Sites
description: Cree y configure el ajuste preestablecido de AEM Sites en la consola Mapa mediante la asignación de componentes compuestos y la asignación de componentes heredados.
feature: Publishing
role: User
exl-id: f3657268-9dee-43af-b643-499dbc3ca948
source-git-commit: 8f2658bd3a724ff375d6d1a9b4474a5cdd8ce270
workflow-type: tm+mt
source-wordcount: '3534'
ht-degree: 0%

---

# Ajuste preestablecido de AEM Sites en la consola Mapa

Puede crear ajustes preestablecidos de AEM Sites desde la consola Mapa y configurarlos para generar la salida de AEM Sites. Existen dos formas de crear la salida de AEM Sites:

- [Usar asignación de componentes compuestos](#use-composite-component-mapping)
- [Usar asignación de componentes heredados](#use-legacy-component-mapping)

>[!TIP]
>
> Se recomienda utilizar la asignación de componentes compuestos, disponible en la versión de Experience Manager Guides 2502, y en versiones más recientes, para un rendimiento mejorado.

## Usar asignación de componentes compuestos

La asignación de componentes compuestos ofrece una publicación más rápida y escalable en AEM Sites en comparación con la asignación de componentes heredados. Incluye plantillas editables integradas que se pueden personalizar según sus necesidades con el editor de plantillas de AEM. Las plantillas utilizan una combinación de componentes principales de WCM y `guides-components` especializados para garantizar que los usuarios finales obtengan la mejor experiencia en las páginas de AEM Sites. También puede personalizar las plantillas existentes mediante el método de asignación de componentes compuestos.

Experience Manager Guides proporciona plantillas predefinidas para crear AEM Sites. Estas plantillas le ayudan a garantizar la coherencia en el diseño y la estructura del contenido.
- [Crear páginas principales](../cs-install-guide/download-install-aem-sites-templates-cs.md#create-a-home-page-using-the-template) basadas en estas plantillas predefinidas.
- Puede [editar plantillas de temas](../cs-install-guide/download-install-aem-sites-templates-cs.md#package-installation) y aplicar estilos según sus necesidades.
- También puede [personalizar plantillas de AEM Sites existentes](../cs-install-guide/download-install-aem-sites-templates-cs.md#customize-existing-aem-sites-templates).


**Crear ajuste preestablecido de AEM Sites**

Realice los siguientes pasos para crear el ajuste preestablecido de AEM Sites mediante la asignación de componentes compuestos:

1. [Abra el archivo de mapa DITA en la consola de mapas](./open-files-map-console.md).
1. En el panel **Ajustes preestablecidos de salida**, seleccione el icono + para crear uno de salida.
1. Seleccione **AEM Sites** de la lista desplegable **Type** en el cuadro de diálogo **Nuevo ajuste preestablecido de salida**.
1. Anule la selección de la opción **Usar asignación de componentes heredados**.
1. Seleccione la opción **Agregar al perfil de carpeta actual** para crear un ajuste preestablecido de salida dentro del perfil de carpeta actual. El ![icono de perfil de carpeta](images/global-preset-icon.svg) indica un ajuste preestablecido de nivel de perfil de carpeta.

   Obtenga más información sobre [Administrar ajustes preestablecidos de salida de perfil global y de carpeta](./web-editor-manage-output-presets.md).

1. Seleccione **Añadir**.

   Se crea el ajuste preestablecido de AEM Sites.


   ![Nuevo ](images/new-aem-sites-dialog-box.png){width="300" align="left"}

<!-----------------------
### Generate the AEM Sites output using the templates

Once, the preset is created, you can configure the various options available for AEM Sites output generation. Experience Manager Guides allows you to use the out of the box templates or add your own AEM Sites templates.

You can configure the Out-of-the-box Sites template  in two ways:

- In the **Sites** field, select the AEM sites where you want to publish your output.  For example, `AEMG Docs`.

    The **Publish path** and the **Topic page template** options are automatically set in the dropdown.  For example,  `AEMG-Docs-Site/en/docs/product1` and `Topic page` are set respectively. You can also choose the other options from the dropdown.

- Or, Select the **Use Sites path** option to select the complete Sites path, and then select a **Map page template**. 

    You can browse a predefined Sites path or specify a custom path even if the specified path has not been pre-created within the AEM Sites structure. In such cases, the system creates the necessary structure during the publishing process by using the selected map homepage template.

   For example, you can specify the path `/content/AEMG-Docs-Site/en/docs/product4` where the `product4`does not exist in the strcuture. In this case, the system automatically creates `product4` using the selected **Map page template** and publish the output within this newly created page. 
   
   The **Topic page template** is automatically set as `Topic Page`. However, you can choose to select other available options in the dropdown.

--->

### Configuración preestablecida de AEM Sites para la asignación de componentes compuestos

>[!NOTE]
>
> Antes de configurar el ajuste preestablecido de AEM Sites para Experience Manager Guides, el administrador debe crear una estructura de AEM Sites con las plantillas.

- **Software On-Premise**: Obtenga más información acerca de cómo [descargar e instalar plantillas de AEM Sites](../install-guide/download-install-aem-sites-templates.md) para software On-Premise.
- **Cloud Service**: Más información sobre cómo [descargar e instalar plantillas de AEM Sites](../cs-install-guide/download-install-aem-sites-templates-cs.md) para Cloud Service.

En la consola Mapa, las opciones de configuración preestablecidas para la asignación de componentes compuestos se organizan en las siguientes pestañas:

- General
- Contenido
- Lista de temas
- Referencias entre mapas

![Nuevo ](images/aem-sites-new-config.png){width="650" align="left"}

**General**

La ficha **General** contiene las siguientes opciones de configuración:

| Opciones de AEM Sites | Descripción |
| --- | --- |
| Usar ruta del sitio | Utilice esta opción para publicar el contenido en un sitio de Experience Manager. |
| Ruta del sitio | **Esta opción aparece si selecciona** Usar ruta de acceso al sitio **opción**. Explore la ruta predefinida del sitio de Experience Manager o especifique una ruta personalizada en la que desee publicar el resultado. La opción **Usar sitios** le permite especificar la ruta de publicación completa aunque la ruta especificada no se haya creado previamente en la estructura de AEM Sites. En estos casos, el sistema crea la estructura necesaria durante el proceso de publicación utilizando la plantilla de página principal de mapa seleccionada. |
| Plantilla de página de mapa | **Esta opción aparece si selecciona** Usar ruta de acceso al sitio **opción**. Seleccione una plantilla que desee aplicar para las páginas principales de mapas. |
| Sitio | Nombre de la Experience Manager Sites en la que desea publicar el contenido. Las opciones del menú desplegable se rellenan en función de la lista de sitios disponibles en AEM Sites. <br>Seleccione **Actualizar** ![icono de actualización](images/navtitle-refresh-icon.svg) para obtener una lista nueva de opciones y reflejar los datos actualizados. |
| Ruta de publicación | La ruta dentro del repositorio de AEM donde se almacena el resultado. La ruta de publicación se rellena con todas las rutas que contienen páginas creadas a partir de la plantilla de la página de inicio. La salida AEM Sites del mapa DITA se genera en esta ruta.  Por ejemplo, si especifica el sitio como `AEMG-Docs` y la ruta de publicación como `aemg-docs-en/docs/product-abc.`, la salida de AEM Sites se generará en el nodo `aemg-docs-en/docs/product-abc/` en `crx/de`. |
| Plantilla de página de tema | Seleccione la plantilla que desee aplicar a todos los temas de salida. |
| Generar nombres de página basados en | **Nombre de archivo del tema**: Utiliza el nombre de archivo del tema DITA para crear la dirección URL del sitio. <br> **Título del tema**: Utiliza el título del tema DITA para crear los nombres de los sitios Experience Manager. |
| Limpieza de páginas generadas anteriormente | - **Eliminar las páginas generadas anteriormente para el tema eliminado del mapa**: si la estructura del mapa DTIA cambia, puede utilizar esta opción para quitar las páginas generadas anteriormente para los temas eliminados. Esta función solo está disponible para la publicación de mapas completa.<br><br>Supongamos que ha publicado un mapa DITA, que contiene los temas a.dita, b.dita y c.dita. Antes de volver a publicar el mapa, ha eliminado el tema b.dita del mapa. Ahora, si ha seleccionado esta opción, todo el contenido relacionado con b.dita se elimina de la salida de AEM Sites y solo se publican a.dita y c.dita.<br><br>**Nota**: la información sobre las páginas eliminadas también se captura en los registros de generación de salida. Para obtener más información acerca del acceso a los archivos de registro, [vea y compruebe el archivo de registro](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). <br><br>**Precaución**: al eliminar los temas, las páginas dejarán de estar disponibles en el sitio publicado. Por lo tanto, antes de eliminar los temas, aparece una advertencia. Debe confirmar que desea eliminarlos.<br><br>- **Eliminar todas las páginas creadas por otras fuentes en esta ruta**: Si selecciona esta opción, se eliminarán todas las páginas publicadas en esta ruta desde otros mapas, temas individuales o cualquier otro origen. Las páginas tampoco estarán disponibles desde el sitio publicado. Por lo tanto, antes de eliminar los temas, aparece una advertencia. Debe confirmar que desea eliminarlos. |
| Flujo de trabajo de generación posterior | Al elegir esta opción, se muestra una nueva lista desplegable Flujo de trabajo de generación posterior que contiene todos los flujos de trabajo configurados en AEM. Debe seleccionar un flujo de trabajo que desee ejecutar después de completar el flujo de trabajo de generación de resultados. |

**Contenido**

La pestaña **Content** contiene las siguientes opciones de configuración:

| Opciones de AEM Sites | Descripción |
| --- | --- |
| Usar línea base | Si ha creado una Línea base para el mapa DITA seleccionado, seleccione esta opción para especificar la versión que desea publicar.<br><br>Ver [Trabajar con línea de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obtener más detalles. |
| Filtrado condicional | Seleccione una de las siguientes opciones:<br><br>**None**: Seleccione esta opción si no desea aplicar ninguna condición en la salida publicada.<br>**Usando DITAVAL**: seleccione los archivos DITAVal para generar contenido condicionado. Puede seleccionar varios archivos DITAVal mediante el cuadro de diálogo de exploración o escribiendo la ruta del archivo. Utilice el icono en forma de cruz situado cerca del nombre del archivo para eliminarlo. Los archivos DITAVal se evalúan en el orden especificado, por lo que las condiciones especificadas en el primer archivo tienen prioridad sobre las condiciones coincidentes especificadas en archivos posteriores. Puede mantener el orden de los archivos añadiendo o eliminando archivos. Si el archivo DITAVal se mueve a otra ubicación o se elimina, no se elimina automáticamente del panel de asignaciones. Debe actualizar la ubicación en caso de que los archivos se muevan o eliminen. Puede pasar el ratón sobre el nombre del archivo para ver la ruta en el repositorio de AEM donde está almacenado el archivo. Solo puede seleccionar archivos DITAVal y se muestra un error si selecciona cualquier otro tipo de archivo.<br>**Ajuste preestablecido de condición**: seleccione un ajuste preestablecido de condición en la lista desplegable para aplicar una condición al publicar la salida. Esta opción está visible si se ha añadido una condición para el fichero de mapa DITA. La configuración condicional está disponible en la ficha Ajustes preestablecidos de condición de la consola de mapas DITA. Para obtener más información acerca de los ajustes preestablecidos de condición, vea [Usar ajustes preestablecidos de condición](generate-output-use-condition-presets.md#id1825FL004PN). |
| Argumentos adicionales de la línea de comandos de DITA-OT | Especifique los argumentos adicionales que desea que DITA-OT procese durante la generación de resultados. Para obtener más información acerca de los argumentos de línea de comandos admitidos en DITA-OT, vea [documentación de DITA-OT](https://www.dita-ot.org/). |
| Metadatos <br> <br>Propiedades de archivo (Assets) | Seleccione las propiedades que desee procesar como metadatos. Estas propiedades se definen desde la página Propiedades del fichero de mapa DITA o de mapa de libros. Las propiedades que seleccione en la lista desplegable aparecerán en el campo **Propiedades del archivo**. Seleccione el icono en forma de cruz situado junto a la propiedad para eliminarla. <br><br>**Nota**: las propiedades de metadatos distinguen entre mayúsculas y minúsculas.<br><br>*Si ha seleccionado una Línea base, los valores de las propiedades se basan en la versión de la Línea base seleccionada.<br>* Si no ha seleccionado una Línea de base, los valores de las propiedades se basan en la versión más reciente.<br><br>También puede pasar los metadatos a la salida mediante la publicación DITA-OT. Para obtener más información, [Pase los metadatos a la salida mediante DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Nota**: si no ha definido `cq:tags` en la opción Propiedades, los valores de `cq:tags` se seleccionarán de la copia de trabajo actual aunque haya seleccionado una Línea de base para la publicación. |
| Metadatos <br> <br>Usar propiedades de mapa como alternativa | Si se selecciona, las propiedades definidas para el fichero de mapa también se copian en los temas en los que no se definen dichas propiedades. Tenga en cuenta los siguientes puntos al utilizar esta opción:<br><br>*Solo las propiedades String, Date o Long (únicas y de varios valores) se pueden pasar a las páginas del sitio de AEM.<br>* Los valores de metadatos de una propiedad de tipo cadena no admiten ningún carácter especial (como `@, #, " "`).<br>* Esta opción debe usarse junto con la opción `Properties`. |

**Lista de temas**

La ficha **Lista de temas** muestra la lista de temas presentes en la copia de trabajo actual del mapa DITA. De forma predeterminada, se incluyen todos los temas. Puede seleccionar temas específicos y generar la salida de AEM Sites solo para ellos. Por ejemplo, se han actualizado algunos temas para poder publicar sólo esos temas en lugar de publicar todo el mapa DITA.

![lista de temas de aem sites](images/aem-presets-topic-list.png) {align="left"}


>[!NOTE]
>
> Cuando se selecciona una Línea de base en la ficha **Contenido**, la lista Tema muestra los temas y sus versiones de la Línea de base adjunta. Además, la publicación incremental de la lista Temas debe utilizarse únicamente cuando no haya cambios en la estructura del mapa. Si se produce un cambio en la estructura del mapa/índice, todo el mapa debe publicarse una vez para actualizar el índice.

**Referencias de mapas cruzados**

Esta lista contiene temas que contienen referencias entre mapas con `scope ="peer"`. Puede especificar el contexto de publicación para una lista de referencias de mapas cruzados con `scope="peer"` a temas disponibles en otras asignaciones DITA. Esta pestaña aparece si utiliza la versión de Experience Manager Guides (UUID).

Para obtener más información, consulte la sección [Trabajar con temas vinculados](#working-with-linked-topics) a continuación.

Una vez configurado, guarde los cambios realizados en el ajuste preestablecido y seleccione **Generate** para generar AEM Sites para el mapa correspondiente.

>[!NOTE]
>
> Si publica contenido en sitios de AEM por primera vez, se recomienda publicar las páginas en el nivel de sitio. Esto garantiza que la salida se muestre correctamente en la instancia **Publish** sin interrupciones en el CSS.

## Usar asignación de componentes heredados

Los pasos para crear el ajuste preestablecido de AEM Sites mediante la asignación de componentes heredados son los mismos que se describen en la sección [Asignación de componentes compuestos](#use-composite-component-mapping) anterior. Sin embargo, al crear el ajuste preestablecido, asegúrese de seleccionar la opción **Usar asignación de componentes heredados** en el cuadro de diálogo **Nuevo ajuste preestablecido de salida**.

![](images/aem-sites-output-legacy.png) {width="300" align="left"}

En la consola Mapa, las opciones de configuración preestablecidas para la asignación de componentes heredados se organizan en las siguientes pestañas:

- General
- Contenido
- Referencias entre mapas

![Nuevo ](images/aem-sites-preset-legacy-config.png){width="500" align="left"}

**General**

La ficha **General** contiene las siguientes opciones de configuración:

| Opciones de AEM Sites | Descripción |
| --- | --- |
| Nombre del sitio | Un nombre de sitio donde la salida se almacena en el repositorio de AEM.<br><br>Se crea un nodo en el repositorio de AEM con el nombre especificado aquí. Si no se especifica el Nombre del sitio (Site Name), se creará el nodo de sitio con el nombre de fichero de mapa DITA.<br><br>El nombre de sitio que especifique aquí también se utiliza como título en la ficha del explorador.<br><br>También puede utilizar variables al establecer el Nombre del sitio. |
| Ruta de salida | La ruta dentro del repositorio de AEM donde se almacena el resultado. Al generar la salida final, se combinan el nombre del sitio y la ruta de salida. Por ejemplo, si especifica el nombre del sitio como `user-guide` y la ruta de acceso de salida como `/content/output/aem-guides`, el resultado final se generará en el nodo `/content/output/aem-guides/user-guide`.<br><br>También puede utilizar variables al establecer la ruta de acceso de salida. |
| Páginas de salida existentes | Seleccione la opción **Sobrescribir contenido** para sobrescribir contenido en las páginas existentes. Esta opción solo sobrescribe el contenido presente en los nodos de contenido y encabezado de la página. Esta opción habilita la publicación combinada de contenido. Al seleccionar esta opción, se proporciona una opción para seleccionar la eliminación de páginas huérfanas de la salida publicada. Esta es también la opción *default* para crear la salida de AEM Sites.<br><br>Seleccione la opción **Eliminar y crear** para forzar la eliminación de las páginas existentes durante la publicación. Esta opción elimina el nodo de página junto con su contenido y todas las páginas secundarias debajo de él. Utilice esta opción si ha cambiado la plantilla de diseño del ajuste preestablecido de salida o si desea que se eliminen las páginas adicionales ya presentes en el destino. |
| Eliminar páginas generadas anteriormente para temas eliminados del mapa | Si la estructura del mapa DTIA cambia, puede utilizar esta opción para quitar las páginas generadas anteriormente para los temas eliminados. Esta función solo está disponible para la publicación de mapas completa.<br><br>Supongamos que ha publicado un mapa DITA, que contiene los temas a.dita, b.dita y c.dita. Antes de volver a publicar el mapa, ha eliminado el tema b.dita del mapa. Ahora, si ha seleccionado esta opción, todo el contenido relacionado con b.dita se elimina de la salida de AEM Sites y solo se publican a.dita y c.dita.<br><br>**Nota**: la información sobre las páginas eliminadas también se captura en los registros de generación de salida. Para obtener más información acerca del acceso a los archivos de registro, [vea y compruebe el archivo de registro](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). <br><br>**Precaución**: al eliminar los temas, las páginas dejarán de estar disponibles en el sitio publicado. Por lo tanto, antes de eliminar los temas, aparece una advertencia. Debe confirmar que desea eliminarlos. |
| Diseño | Seleccione la plantilla de diseño que desee utilizar para generar el resultado.<br><br>Para obtener más información acerca de cómo usar plantillas de diseño personalizadas para generar resultados, póngase en contacto con el administrador de publicaciones. |
| Flujo de trabajo de generación posterior | Al elegir esta opción, se muestra una nueva lista desplegable Flujo de trabajo de generación posterior que contiene todos los flujos de trabajo configurados en AEM. Debe seleccionar un flujo de trabajo que desee ejecutar después de completar el flujo de trabajo de generación de resultados. |
| Conservar archivos temporales | Seleccione esta opción para conservar los ficheros temporales generados por DITA-OT. Si se producen errores al generar la salida mediante DITA-OT, seleccione esta opción para conservar los ficheros temporales. Puede utilizar esos archivos para solucionar errores de generación de resultados.<br> <br> Después de generar la salida, seleccione el icono **Descargar archivos temporales** ![descargar archivos temporales](images/download-temp-files-icon.svg) para descargar la carpeta ZIP que contiene los archivos temporales. <br><br> **Nota**: Si las propiedades de archivo se agregan durante la generación, los archivos temporales de salida también incluyen un archivo *metadata.xml* que contiene esas propiedades. |

**Contenido**

![Nuevo ](images/aem-sites-content-tab.png){width="650" align="left"}

La pestaña **Content** contiene las siguientes opciones de configuración:

| Opciones de AEM Sites | Descripción |
| --- | --- |
| Usar línea base | Si ha creado una Línea base para el mapa DITA seleccionado, seleccione esta opción para especificar la versión que desea publicar.<br><br>Ver [Trabajar con línea de base](./web-editor-baseline.md) para obtener más detalles. |
| Filtrado condicional | Seleccione una de las siguientes opciones:<br><br>**None**: Seleccione esta opción si no desea aplicar ninguna condición en la salida publicada.<br>**Usando DITAVAL**: seleccione los archivos DITAVal para generar contenido condicionado. Puede seleccionar varios archivos DITAVal mediante el cuadro de diálogo de exploración o escribiendo la ruta del archivo. Utilice el icono en forma de cruz situado cerca del nombre del archivo para eliminarlo. Los archivos DITAVal se evalúan en el orden especificado, por lo que las condiciones especificadas en el primer archivo tienen prioridad sobre las condiciones coincidentes especificadas en archivos posteriores. Puede mantener el orden de los archivos añadiendo o eliminando archivos. Si el archivo DITAVal se mueve a otra ubicación o se elimina, no se elimina automáticamente del panel de asignaciones. Debe actualizar la ubicación en caso de que los archivos se muevan o eliminen. Puede pasar el ratón sobre el nombre del archivo para ver la ruta en el repositorio de AEM donde está almacenado el archivo. Solo puede seleccionar archivos DITAVal y se muestra un error si selecciona cualquier otro tipo de archivo.<br>**Ajuste preestablecido de condición**: seleccione un ajuste preestablecido de condición en la lista desplegable para aplicar una condición al publicar la salida. Esta opción está visible si se ha añadido una condición para el fichero de mapa DITA. La configuración condicional está disponible en la ficha Ajustes preestablecidos de condición de la consola de mapas DITA. Para obtener más información acerca de los ajustes preestablecidos de condición, vea [Usar ajustes preestablecidos de condición](generate-output-use-condition-presets.md#id1825FL004PN). |
| Metadatos <br> <br>Propiedades de archivo (Assets) | Seleccione las propiedades que desee procesar como metadatos. Estas propiedades se definen desde la página Propiedades del fichero de mapa DITA o de mapa de libros. Las propiedades que seleccione en la lista desplegable aparecerán en el campo **Propiedades del archivo**. Seleccione el icono en forma de cruz situado junto a la propiedad para eliminarla. <br><br>**Nota**: las propiedades de metadatos distinguen entre mayúsculas y minúsculas.<br><br>*Si ha seleccionado una Línea base, los valores de las propiedades se basan en la versión de la Línea base seleccionada.<br>* Si no ha seleccionado una Línea de base, los valores de las propiedades se basan en la versión más reciente.<br><br>También puede pasar los metadatos a la salida mediante la publicación DITA-OT. Para obtener más información, [Pase los metadatos a la salida mediante DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Nota**: si no ha definido `cq:tags` en la opción Propiedades, los valores de `cq:tags` se seleccionarán de la copia de trabajo actual aunque haya seleccionado una Línea de base para la publicación. |
| Metadatos <br> <br>Usar propiedades de mapa como alternativa | Si se selecciona, las propiedades definidas para el fichero de mapa también se copian en los temas en los que no se definen dichas propiedades. Tenga en cuenta los siguientes puntos al utilizar esta opción:<br><br>*Solo las propiedades String, Date o Long (únicas y de varios valores) se pueden pasar a las páginas del sitio de AEM.<br>* Los valores de metadatos de una propiedad de tipo cadena no admiten ningún carácter especial (como `@, #, " "`).<br>* Esta opción debe usarse junto con la opción `Properties`. |

**Referencias de mapas cruzados**

Esta lista contiene temas que contienen referencias entre mapas con `scope ="peer"`. Puede especificar el contexto de publicación para una lista de referencias de mapas cruzados con `scope="peer"` a temas disponibles en otras asignaciones DITA. Esta pestaña aparece si utiliza la versión de Experience Manager Guides (UUID).

Para obtener más información, consulte la sección [Trabajar con temas vinculados](#working-with-linked-topics) a continuación.

## Trabajar con temas vinculados

Experience Manager Guides le permite crear referencias de temas utilizando `peer @scope`. A continuación, puede definir el contexto de publicación de estas referencias desde los ajustes preestablecidos de AEM Sites y, finalmente, generar la salida de los temas vinculados.

Para obtener más información, vea [Generar resultados de temas de vinculación de otros mapas](../user-guide/generate-output-aem-site.md#generate-output-linking-topics-from-other-maps).


Siga estos pasos para especificar el contexto de publicación de los archivos de vínculos cruzados:

1. Abra la ficha **Referencias de mapas cruzados**. Para ver esta ficha, asegúrese de que `<xrefs>` tengan identificadores únicos. Los identificadores únicos de `<xrefs>` se generarán automáticamente al editar o guardar el contenido anterior si el identificador no está presente.

   No podrá ver la vinculación entre mapas cruzados en los casos siguientes:
   - Para los ajustes preestablecidos creados antes de la versión 4.6, la pestaña Referencias cruzadas está deshabilitada y aparece la información del objeto **Consulte el tablero de mapas**.
   - Para los ajustes preestablecidos creados a partir del tablero de mapas, **consulte el tablero de mapas**.
   - Para los ajustes preestablecidos de OOTB, **consulte la información sobre herramientas del tablero de mapas**.
   - Para los ajustes preestablecidos globales, cree una copia local de este ajuste preestablecido global para establecer referencias entre mapas.


1. Se muestra una lista de temas y sus referencias

   >[!NOTE]
   >
   >La ficha **Referencias de mapas cruzados** muestra los temas que están vinculados usando solamente `scope="peer"`. Para los vínculos con `scope="local"`, no es necesario especificar el contexto de publicación.

   Todos los temas vinculados tienen su último ajuste preestablecido de salida y mapa seleccionado de forma predeterminada. El contexto de publicación de todos los temas vinculados está establecido en la asignación `<Most recently generated>` de forma predeterminada.

   ![Referencias de mapas cruzados](images/aem-sites-preset-cross-map-references.png)

1. Si desea utilizar el resultado publicado más recientemente de cada archivo dependiente en el mapa, seleccione **Usar contexto de publicación generado más recientemente** para todos los temas dependientes.
Debe publicar el mapa seleccionado como mapa principal antes de publicar el mapa que contiene los temas vinculados. Si el mapa con temas vinculados no se publica, los vínculos aparecen como texto normal en lugar de como hipervínculos en la salida de AEM Sites.
Debe seleccionar el mismo tipo de ajuste preestablecido de AEM Sites para el tema vinculado. Por ejemplo, si el ajuste preestablecido actual de AEM Sites utiliza la asignación de componentes heredados, seleccione un ajuste preestablecido de AEM Sites similar en el tema vinculado.
1. En la lista desplegable Mapa principal, seleccione el archivo de asignación con cuya salida desee vincular la salida del mapa actual.
Al seleccionar un archivo de asignación, se muestra el UUID del mapa en la columna UUID del mapa principal. Los ajustes preestablecidos de salida asociados con el mapa elegido se enumeran en la lista Ajustes preestablecidos del mapa principal. Por ejemplo, el Tema 1 del Mapa A contiene una referencia al Tema 2. El tema 2 puede estar presente en mapas únicos o múltiples. Puede seleccionar el mapa principal y un ajuste preestablecido específico o la salida publicada más recientemente para cada vínculo.

1. Si se hace referencia al mismo tema más de una vez en un archivo, puede agregar un contexto de publicación diferente para cada instancia. Esto proporciona una mayor flexibilidad y control sobre su contenido. Por ejemplo, el tema 3 está presente tanto en el mapa B como en el mapa C. El tema 1 contiene dos referencias al tema 3. Puede elegir Mapa B como mapa principal para el primer vínculo y Mapa C como mapa principal para el segundo vínculo.

1. En la lista desplegable Ajuste preestablecido del mapa principal, seleccione el ajuste preestablecido de salida con el que desea vincular la salida del mapa actual.
   >[!NOTE]
   >
   > Los diferentes ajustes preestablecidos de AEM Sites del mapa actual aparecen en la lista desplegable. Si no selecciona ningún ajuste preestablecido, aparece un icono de advertencia y la generación de resultados falla.

1. Seleccione la asignación requerida y su ajuste preestablecido de salida para todos los temas de origen y seleccione **Generar**.




**Tema principal:** [Explicación de los ajustes preestablecidos de salida](generate-output-understand-presets.md)