---
title: AEM Sites
description: Cree y configure el ajuste preestablecido de AEM Sites en el editor web y genere la salida de AEM Sites para el mapa DITA, los temas seleccionados y los temas vinculados.
feature: Publishing
role: User
hide: true
exl-id: 9a9ae44f-8fed-4a4e-812c-451bcf138d0a
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '2755'
ht-degree: 0%

---

# Ajustes preestablecidos de AEM Sites en el editor web


Puede crear ajustes preestablecidos de AEM Sites desde el editor web y configurarlos para generar la salida de AEM Sites. El resultado de AEM Sites se basa en la asignación de componentes compuestos junto con `guides-components`, lo que facilita la creación y administración eficientes del contenido.

Experience Manager Guides proporciona plantillas predefinidas para crear AEM Sites. Estos ajustes preestablecidos le ayudan a garantizar la coherencia en el diseño y la estructura del contenido.
- [Crear páginas principales](/help/product-guide/cs-install-guide/download-install-aem-sites-templates-cs.md#create-a-home-page-using-the-template) basadas en estas plantillas predefinidas.
- Puede [editar plantillas de temas](/help/product-guide/cs-install-guide/download-install-aem-sites-templates-cs.md#package-installation) y aplicar estilos según sus necesidades.
- También puede [personalizar plantillas de AEM Sites existentes](/help/product-guide/cs-install-guide/download-install-aem-sites-templates-cs.md#customize-existing-aem-sites-templates).



## Crear ajustes preestablecidos de AEM Sites

Siga estos pasos para crear los ajustes preestablecidos de AEM Sites desde el Editor web:

1. En el panel Repositorio, abra el fichero de mapa DITA en la vista Mapa.
1. En la ficha **Output**, seleccione el icono + para crear un ajuste preestablecido de salida.
1. Seleccione **AEM Sites** de la lista desplegable **Type** en el cuadro de diálogo **Nuevo ajuste preestablecido de salida**.
1. Anule la selección de la opción **Usar asignación de componentes heredados** del cuadro de diálogo **Nuevo ajuste preestablecido de salida**.

![Nuevo &#x200B;](images/new-aem-sites-dialog-box.png)





>[!NOTE]
>
>Antes de configurar los ajustes preestablecidos de AEM Sites para Experience Manager Guides, el administrador debe crear una estructura de AEM Sites con las plantillas.
>- **Software On-Premise**: Obtenga más información acerca de cómo [descargar e instalar plantillas de AEM Sites](/help/product-guide/install-guide/download-install-aem-sites-templates.md) para software On-Premise.
>- **Cloud Service**: Más información sobre cómo [descargar e instalar plantillas de AEM Sites](/help/product-guide/cs-install-guide/download-install-aem-sites-templates-cs.md) para Cloud Service.




### Añadir ajustes preestablecidos al perfil de carpeta actual

Como administrador, Experience Manager Guides le permite crear y administrar ajustes preestablecidos de salida para los Perfiles global y de carpeta. Seleccione la opción **Agregar al perfil de carpeta actual** en el cuadro de diálogo **Nuevo ajuste preestablecido de salida** para crear un ajuste preestablecido de salida para el perfil de carpeta actual. El icono ![icono de perfil de carpeta](images/global-preset-icon.svg) indica un ajuste preestablecido de nivel de perfil de carpeta.  Obtenga más información acerca de [Administrar ajustes preestablecidos de salida de perfil global y de carpeta](./web-editor-manage-output-presets.md).

### Ajustes preestablecidos de AEM Sites basados en asignación de componentes heredados

También puede crear los ajustes preestablecidos de AEM Sites mediante la asignación de componentes heredados. Para crear los ajustes preestablecidos de AEM Sites basados en la asignación de componentes heredados, seleccione la opción **Usar asignación de componentes heredados** en el cuadro de diálogo **Nuevo ajuste preestablecido de salida**.

Algunas opciones pueden diferir para los ajustes preestablecidos que utilizan la asignación de componentes heredados.



## Configuración de los ajustes preestablecidos de AEM Sites

Las configuraciones están organizadas bajo las pestañas **General**, **Contenido**, **Lista de temas** y **Referencias de mapas cruzados**.

![ajustes preestablecidos de aem sites](images/aem-sites-new-config.png)
**General**

La ficha **General** contiene las siguientes configuraciones relacionadas con la generación de resultados:

- Usar ruta del sitio
- Ruta del sitio
- Sitio
- Ruta de publicación
- Plantilla de página de tema
- Generar nombres de página basados en
   - Nombre de archivo del tema
   - Título del tema
- Limpieza de páginas generadas anteriormente
   - Eliminar páginas generadas anteriormente para temas eliminados del mapa
   - Elimine todas las páginas creadas por otras fuentes en esta ruta:
- Flujo de trabajo de generación posterior



**Contenido**

La ficha **Contenido** contiene las siguientes configuraciones:

- Usar línea base
- Filtro de condición
- Argumentos adicionales de la línea de comandos de DITA-OT
- Metadatos
   - Propiedades de archivo (Assets)
   - Use map properties as fallback


For details, refer to [AEM Sites configuration](#aem_sites_config).

**Topic List**

The **Topic List** displays the list of topics present in the current working copy of the DITA map. By default, all topics are included. You can select specific topics and generate the AEM Sites output only for them. For example, you have updated some topics so you can publish only those topics instead of publish the entire DITA map.

**Topic List** tab is present in the AEM presets that are not created based on legacy mapping.

**Cross-map references**
This list contains topics containing cross-map references with `scope ="peer"`. You can specify the publishing context for a list of cross map references with `scope="peer"` to topics available in other DITA maps. This tab appears if you use the Experience Manager Guides (UUID) version.



Learn more about how to [publish linked topics](#publish-linked-topics).





## AEM Sites configuration {#aem_sites_config}

The following options are available for the AEM Sites output:

| AEM Sites options | Descripción |
| --- | --- |
| Use site path | Use this option to publish your content to an Experience Manager Site. Select this option if you know the exact site path where you want the output to be published. Also, mention the full path in the Site path field. |
| Site path | This option appears if you select **Use site path** option. Browse the exact Experience Manager Site path where you want the output to be published. |
| Sitio | Name of the Experience Manager Sites to which you want to publish your content. The options in the dropdown are populated based on the list of sites available in AEM Sites. <br>Select **Refresh** ![refreseh icon](images/navtitle-refresh-icon.svg) to fetch a fresh list of options and reflect the udpated data. |
| Publish Path | The path within your AEM repository where the output is stored. The Publish Path is populated with all the paths that contain pages created based on the Home Page template. The AEM Sites output of the DITA map is generated under this path.  For example, if you specify the Site as `AEMG-Docs` and the Publish Path as `aemg-docs-en/docs/product-abc.`, then the AEM Sites output is generated under the `aemg-docs-en/docs/product-abc/` node in `crx/de`. |
| Topic page template | The structural components that you can use to organize content consistently across multiple documents. These templates are predefined in the Adobe Experience Manager Site template. The options are populated with all the topic page templates available for the selected Site. Select the template you want to apply to all the output topics. |
| Generate page names based on | **Topic filename**: Uses the DITA topic&#39;s file name to create the Site URL. <br> **Topic title**: Uses the DITA topic&#39;s title to create the Experience Manager Site names. |
| Cleanup previously generated pages | -  **Delete previously generated pages for topic removed from the map**: If the structure of the DTIA map changes, you can use this option to remove the previously generated pages for the removed topics. This feature is available only for full map publishing.<br><br>Let&#39;s say you have published a DITA map, which contains topics a.dita, b.dita, and c.dita. Before publishing the map again, you removed b.dita topic from the map. Now, if you have selected this option, then all content related to b.dita is removed from the AEM Sites output and only a.dita and c.dita are published.<br><br>**Note**: Information about deleted pages is also captured in the output generation logs. For more information about accessing the log files, [View and check the log file](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). <br><br>**Caution**: On deleting the topics, the pages become unavailable from the published site. So, before the topics are deleted, a warning appears. You must confirm to delete them.<br><br>- **Delete all pages created by other sources at this path**: If you select this option, all pages published on this path from other maps, individual topics, or any other source are deleted. The pages also become unavailable from the published site. So, before the topics are deleted, a warning appears. Debe confirmar que desea eliminarlos. |
| Flujo de trabajo de generación posterior | Al elegir esta opción, se muestra una nueva lista desplegable Flujo de trabajo de generación posterior que contiene todos los flujos de trabajo configurados en AEM. Debe seleccionar un flujo de trabajo que desee ejecutar después de completar el flujo de trabajo de generación de resultados. |
| Usar línea base | Si ha creado una Línea de base para el mapa DITA seleccionado, seleccione esta opción para especificar la versión que desea publicar.<br><br>**Importante**: Cuando esté generando resultados incrementales para el sitio de AEM, el resultado se creará utilizando la versión actual de los archivos y no la Línea de base adjunta.<br><br>Ver [Trabajar con Línea de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obtener más información. |
| Filtrado condicional | Seleccione una de las siguientes opciones:<br><br>**None**: Seleccione esta opción si no desea aplicar ninguna condición en la salida publicada.<br>**Usando DITAVAL**: seleccione los archivos DITAVal para generar contenido condicionado. Puede seleccionar varios archivos DITAVal mediante el cuadro de diálogo de exploración o escribiendo la ruta del archivo. Utilice el icono en forma de cruz situado cerca del nombre del archivo para eliminarlo. Los archivos DITAVal se evalúan en el orden especificado, por lo que las condiciones especificadas en el primer archivo tienen prioridad sobre las condiciones coincidentes especificadas en archivos posteriores. Puede mantener el orden de los archivos añadiendo o eliminando archivos. Si el archivo DITAVal se mueve a otra ubicación o se elimina, no se elimina automáticamente del panel de asignaciones. Debe actualizar la ubicación en caso de que los archivos se muevan o eliminen. Puede pasar el ratón sobre el nombre del archivo para ver la ruta en el repositorio de AEM donde está almacenado el archivo. Solo puede seleccionar archivos DITAVal y se muestra un error si selecciona cualquier otro tipo de archivo.<br>**Ajuste preestablecido de condición**: seleccione un ajuste preestablecido de condición en la lista desplegable para aplicar una condición al publicar la salida. Esta opción está visible si se ha añadido una condición para el fichero de mapa DITA. La configuración condicional está disponible en la ficha Ajustes preestablecidos de condición de la consola de mapas DITA. Para obtener más información acerca de los ajustes preestablecidos de condición, vea [Usar ajustes preestablecidos de condición](generate-output-use-condition-presets.md#id1825FL004PN). |
| Argumentos adicionales de la línea de comandos de DITA-OT | Especifique los argumentos adicionales que desea que DITA-OT procese durante la generación de resultados. Para obtener más información acerca de los argumentos de línea de comandos admitidos en DITA-OT, vea [documentación de DITA-OT](https://www.dita-ot.org/). |
| Metadatos <br> <br>Propiedades de archivo (Assets) | Seleccione las propiedades que desee procesar como metadatos. Estas propiedades se definen desde la página Propiedades del fichero de mapa DITA o de mapa de libros. Las propiedades que seleccione en la lista desplegable aparecerán en el campo **Propiedades del archivo**. Seleccione el icono en forma de cruz situado junto a la propiedad para eliminarla. <br><br>**Nota**: las propiedades de metadatos distinguen entre mayúsculas y minúsculas.<br><br>*Si ha seleccionado una Línea de base, los valores de las propiedades se basan en la versión de la Línea de base seleccionada.<br>* Si no ha seleccionado una Línea base, los valores de las propiedades se basan en la versión más reciente.<br><br>También puede pasar los metadatos a la salida mediante la publicación DITA-OT. Para obtener más información, [Pase los metadatos a la salida mediante DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Nota**: si no ha definido `cq:tags` en la opción Propiedades, los valores de `cq:tags` se seleccionarán de la copia de trabajo actual, incluso si ha seleccionado una Línea de base para la publicación. |
| Metadatos <br> <br>Usar propiedades de mapa como alternativa | Si se selecciona, las propiedades definidas para el fichero de mapa también se copian en los temas en los que no se definen dichas propiedades. Tenga en cuenta los siguientes puntos al utilizar esta opción:<br><br>*Solo las propiedades String, Date o Long (únicas y de varios valores) se pueden pasar a las páginas del sitio de AEM.<br>* Los valores de metadatos de una propiedad de tipo String no admiten ningún carácter especial (como `@, #, " "`).<br>* Esta opción debe utilizarse junto con la opción `Properties`. |
| Conservar archivos temporales | Seleccione esta opción para conservar los ficheros temporales generados por DITA-OT. Si se producen errores al generar la salida mediante DITA-OT, seleccione esta opción para conservar los ficheros temporales. Puede utilizar esos archivos para solucionar errores de generación de resultados.<br> <br> Después de generar la salida, seleccione el icono **Descargar archivos temporales** ![descargar archivos temporales](images/download-temp-files-icon.png) para descargar la carpeta ZIP que contiene los archivos temporales. <br><br> **Nota**: Si las propiedades de archivo se agregan durante la generación, los archivos temporales de salida también incluyen un archivo *metadata.xml* que contiene esas propiedades. |


### Genere la salida de AEM Sites con las plantillas

Experience Manager Guides le permite utilizar las plantillas predeterminadas o agregar sus propias plantillas de AEM Sites.

Antes de configurar los ajustes preestablecidos de AEM Sites, asegúrese de crear una estructura de AEM Sites con las plantillas.\
Para obtener más información, vea [Descargar e instalar plantillas de AEM Sites](/help/product-guide/install-guide/download-install-aem-sites-templates.md).



Siga estos pasos para crear y configurar un ajuste preestablecido de AEM Sites:
1. Abra la ficha **Ajustes preestablecidos de salida** del mapa DITA que desee publicar.
1. Seleccione el ajuste preestablecido de salida **AEM Sites**.
1. (Opcional) Desmarque la opción **Usar asignación de componentes heredados** para crear un ajuste preestablecido de AEM Sites no heredado
1. Haga clic en **Agregar**. Se crea el ajuste preestablecido de AEM Sites.
1. Puede configurar la plantilla de sitios predeterminada de dos formas:
   1. Seleccione **Sitio** y, a continuación, elija la ruta de publicación y las plantillas de página del tema entre las opciones rellenadas:
      1. Seleccione el sitio.
      1. Seleccione **Sitio**. Por ejemplo, `AEMG Docs`.
      1. Las opciones **Publish path** y **Topic page template** se establecen automáticamente en el menú desplegable. También puede elegir las opciones. Por ejemplo, `AEMG-Docs-Site/en/docs/product1` y `Topic page` se establecen respectivamente.
   1. Seleccione la ruta completa del sitio:
      1. Seleccione la opción **Usar ruta del sitio**.
      1. Seleccione la ruta completa del sitio. Por ejemplo, `/content/AEMG-Docs-Site/en/docs/product1`.
      1. La &quot;Plantilla de página de tema&quot; se establece automáticamente como `Topic Page`.


1. Guarde los cambios realizados en el ajuste preestablecido.
1. Seleccione la opción **Generate**.
1. Genere AEM Sites para el mapa correspondiente. Por ejemplo, `/content/AEMG-Docs-Site/en/docs/product`.


   >[!NOTE]
   >
   > Si publica contenido en un sitio de AEM por primera vez, se recomienda publicar las páginas en el nivel de sitio. Esto garantiza que la salida se muestre correctamente en la instancia **Publish** sin interrupciones en el CSS.



### Publicar temas vinculados

Experience Manager Guides simplifica la publicación de documentos complejos al permitirle crear referencias de temas utilizando `peer @scope`. A continuación, puede definir el contexto de publicación de estas referencias desde los ajustes preestablecidos de AEM Sites y, finalmente, generar la salida de los temas vinculados.
Para obtener más información, vea [Generar resultados de temas de vinculación de otros mapas](../user-guide/generate-output-aem-site.md#generate-output-linking-topics-from-other-maps).




Siga estos pasos para especificar el contexto de publicación de los archivos de vínculos cruzados:
1. Abra la ficha **Ajustes preestablecidos de salida** del mapa DITA que desee publicar.
1. Seleccione el ajuste preestablecido de salida **AEM Sites**.

   Puede ver las fichas **General**, **Contenido**, **Lista de temas** y **Referencias de mapas cruzados**. **Referencias de mapas cruzados** ficha aparece si utiliza la versión de Experience Manager Guides (UUID).

   No podrá ver la vinculación entre mapas cruzados en los casos siguientes:
   - Para los ajustes preestablecidos creados antes de la versión 4.6. La pestaña Referencias cruzadas está desactivada y aparece la información del objeto, Consulte Asignación del tablero de mandos.
   - Para ajustes preestablecidos creados a partir del tablero de mapas. Consulte Asignación de información sobre herramientas del tablero.
   - Para ajustes preestablecidos de OOTB, consulte Cómo aparece la información del panel de mapas.
   - Para los ajustes preestablecidos globales, cree una copia local de este ajuste preestablecido global para establecer referencias entre mapas.
Si desea utilizar ajustes preestablecidos de AEM Sites del editor web, cree un nuevo ajuste preestablecido o duplique el existente.

1. Abra la ficha **Referencias de mapas cruzados**.

   Se le mostrará una lista de temas y sus referencias. Puede especificar el contexto de publicación para una lista de referencias de mapas cruzados a temas disponibles en otras asignaciones DITA con `scope="peer"`.

   Para usar el panel de referencia de mapas cruzados del Editor Web, `<xrefs>` debe tener identificadores únicos. Los identificadores únicos de `<xrefs>` se generarán automáticamente al editar o guardar el contenido anterior si el identificador no está presente.

   >[!NOTE]
   >
   >La ficha **Referencias de mapas cruzados** muestra los temas que están vinculados usando solamente `scope="peer"`. Para los vínculos con `scope="local"`, no es necesario especificar el contexto de publicación.

   Todos los temas vinculados tienen su último ajuste preestablecido de salida y mapa seleccionado de forma predeterminada. El contexto de publicación de todos los temas vinculados está establecido en la asignación `<Most recently generated>` de forma predeterminada.

   ![Referencias de mapas cruzados](images/aem-sites-cross-map-references.png)

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
