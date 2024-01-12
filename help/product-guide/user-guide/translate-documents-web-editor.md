---
title: Traducir documentos desde el editor web
description: Traduzca el contenido a varios idiomas desde el editor web. AEM Obtenga información sobre cómo crear un proyecto de traducción, agregar reglas, ver versiones y descartar archivos no sincronizados en las guías del usuario.
exl-id: 321c5442-92eb-4662-ab61-d4d4f05eeb39
feature: Authoring, Features of Web Editor, Translation
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '1907'
ht-degree: 0%

---

# Traducir documentos desde el editor web {#id21BKF0Z0YZF}

>[!TIP]
>
> AEM Se recomienda utilizar esta función de traducción del Editor web si ha actualizado a las Guías de traducción as a Cloud Service para febrero de 2022 o posteriores.

AEM Guías de incluye una potente función en el editor web que le permite traducir el contenido a varios idiomas. Puede crear un nuevo proyecto de traducción y posteriormente agregar los trabajos de traducción al proyecto de traducción existente. También puede crear un proyecto de traducción multilingüe que incluya trabajos de traducción para todos los idiomas seleccionados.

>[!NOTE]
>
> El administrador puede configurar la pestaña Administrar \(utilizada para la traducción\) en el Editor web. Para obtener más información, consulte *Configurar la función de traducción en el editor web* de la sección Instalar y configurar las guías de Adobe Experience Manager as a Cloud Service.

## Antes de empezar

Antes de realizar los pasos de este procedimiento, asegúrese de haber creado las carpetas raíz y destino del idioma necesarias

1. Cree una carpeta raíz para almacenar el contenido de origen. La carpeta raíz debe crearse con el nombre de idioma \(como inglés\) o el código de idioma \(en\).
1. Cree las carpetas de destino a las que desea traducir el contenido. Por ejemplo, si desea traducir el contenido al alemán o al francés, debe crear una carpeta denominada como -de \(para alemán\) o -fr \(para francés\).

>[!NOTE]
>
> La carpeta raíz y las carpetas de destino deben crearse en el mismo nivel.

## Crear un proyecto de traducción

1. En el panel Repositorio, abra el fichero de mapa DITA en la vista de mapa.
1. Haga clic en **Administrar** pestaña. El panel Traducción muestra el título de hipervínculo del mapa DITA junto con el **Idiomas** lista.
1. Desde el **Idiomas** , seleccione la configuración regional a la que desea traducir el proyecto. Puede seleccionar **Todo** para traducir el proyecto a todos los idiomas disponibles.

   >[!NOTE]
   >
   > La lista contiene las carpetas de idioma junto con sus códigos de idioma. Por ejemplo, francés \(fr\) y alemán \(de\).

   >[!IMPORTANT]
   >
   > Idioma muestra solo aquellos idiomas para los que se crea una carpeta de idioma paralela al idioma de origen. Tampoco se muestra una carpeta de idioma creada en cualquier otro nivel, como un nivel por debajo de la carpeta de idioma de origen. Asegúrese de crear todas las carpetas de idioma de destino en el mismo nivel que la carpeta de idioma de origen.

   ![](images/translation-languages.png){width="350" align="left"}

1. También puede utilizar las siguientes opciones:

   **Usar línea base:** Puede seleccionar una línea de base para traducir el proyecto. Haga clic en Utilizar línea base y seleccione una línea base creada en el mapa. Todos los archivos que forman parte de la Línea base seleccionada se muestran en la página Traducción. Una vez traducido el contenido, puede exportar la línea de base traducida. Para obtener más información sobre la exportación de la instantánea traducida, consulte [Exportar línea base traducida](generate-output-use-baseline-for-publishing.md#id196SE600GHS).

   **Usar la última versión como en**: elija filtrar la versión de los temas en función de su fecha y hora de creación. Al seleccionar una fecha y hora, solo se muestra la última versión de los archivos creados en la fecha y la hora seleccionadas o antes.

1. Clic **Aplicar**. Se muestra una lista con detalles de temas y recursos asociados.
1. Seleccione los temas que desee enviar para su traducción. También puede utilizar las opciones de filtrado de temas para las siguientes columnas:

   - **Título**: título del archivo de origen.  Pase el ratón sobre el título del archivo de origen para ver el título del archivo de destino o traducido.
   - **Nombre de archivo**: Nombre del archivo de origen
   - **Tipo de archivo**: tipo del archivo de origen. Las opciones disponibles son Mapa, Tema e Imagen.
   - **Tipo de referencia**: referencias directas o indirectas
   - **Versión**: Número de versión del archivo de origen
   - **Etiqueta de versión**: Etiqueta para la versión seleccionada del archivo de origen
   - **Versión de destino**: Número de versión del archivo de destino
   - **Estado del documento**: estado del archivo de origen. Las opciones disponibles son Borrador, En revisión y Revisado.
   - **Idioma de destino**: el idioma al que desea traducir el archivo de origen
   - **Estado de traducción**: Las opciones disponibles son: Fuera de sincronización, Falta de copia, En curso y Sincronizado.
   - **Etiqueta de destino**: Etiqueta para la versión seleccionada del archivo de destino
1. Clic **Enviar para traducción** en la esquina superior derecha.

   ![](images/translation-send.png){width="800" align="left"}

1. En el menú desplegable, seleccione **Crear un nuevo proyecto de traducción**.

   ![](images/translation-project-types.png){width="350" align="left"}

   Además de un nuevo proyecto de traducción, también puede seleccionar entre las siguientes opciones:

   - Puede elegir entre **Creación de una estructura** solo para el proyecto de traducción.
   - Puede elegir entre **Crear un nuevo proyecto de traducción XLIFF** para convertir el contenido XML al formato de archivo de intercambio de localización XML (XLIFF). XLIFF es un formato abierto basado en XML que se utiliza para estandarizar la transferencia de datos entre varias herramientas utilizadas en el proceso de traducción de contenido. AEM Guías de la admite XLIFF versión 1.2. En un proyecto XLIFF, el contenido se exporta al formato XLIFF estándar del sector, que se puede proporcionar a los proveedores de traducción. El formato XLIFF permite la posible reutilización de segmentos que ya ha traducido durante la fase de traducción.\
     AEM Una vez traducido el contenido XLIFF, se puede importar a las guías de la interfaz de usuario, creando así una versión traducida del proyecto DITA original.

     >[!NOTE]
     >
     > La exportación a XLIFF solo funciona con la configuración de traducción humana.

   - Puede seleccionar **Creación de un nuevo proyecto de traducción multilingüe** que incluirá los trabajos de traducción para todos los idiomas que haya seleccionado para la traducción. Por ejemplo, si ha seleccionado francés, alemán y español, se creará un proyecto que contiene trabajos de traducción para los tres idiomas.
   - Si ya tiene un proyecto de traducción, puede agregarle temas. Seleccione Añadir a **Proyecto de traducción existente** de la lista Proyecto y elija un proyecto de la lista Proyecto de traducción existente. Puede ordenar estos proyectos por orden más reciente, ascendente o descendente.

     >[!NOTE]
     >
     > Si el proyecto existente es un proyecto de ámbito, tiene &#39;\(Ámbito\)&#39; anexado en su nombre.

   - Si necesita crear el ámbito para que se traduzca un proyecto, puede seleccionar **Crear un nuevo proyecto de traducción de ámbito**. Esto no enviará las copias para su traducción y se mantendrá el estado de traducción original de los archivos. No afecta a la copia de idioma de destino de los temas a los que se hace referencia y que se envían para su análisis.
1. En el campo **Título del proyecto**, introduzca un título.
1. Clic **Crear** para crear un nuevo proyecto de traducción.

   Se crea un nuevo proyecto de traducción con la versión seleccionada de los temas. En este momento, se muestra un mensaje emergente que confirma que se ha creado el proyecto de traducción. Una vez que todas las copias de idioma de destino estén disponibles en el proyecto de traducción, recibirá una notificación en la bandeja de entrada. Una vez que las copias de idioma de destino estén disponibles en el proyecto de traducción, puede continuar e iniciar el trabajo de traducción. Para obtener más información, consulte [Iniciar el trabajo de traducción](translation-first-time.md#id225IK030OE8).

   >[!NOTE]
   >
   > Si rechaza la traducción de uno o más temas de un trabajo de traducción, la variable **En curso** el estado de traducción de todos los temas rechazados vuelve a su estado original. El estado de los temas referidos se comprueba y revierte según el estado de traducción más reciente. Además, los archivos de traducción creados en el proyecto de destino no se eliminan aunque la traducción se rechace para ellos.

## Añadir las reglas de traducción

AEM Guías de traducción permite a los administradores configurar las reglas de traducción. El formato SRX (Intercambio de reglas de segmentación) es un estándar para intercambiar reglas de segmentación entre distintos usuarios y entornos de traducción. Puede crear una carpeta y agregarle los archivos SRX personalizados.

Los archivos SRX deben tener el siguiente nombre `<language-code>.srx`. Por ejemplo, en-US o ar-AE.

>[Nota]
>El título no distingue entre mayúsculas y minúsculas, por lo que puede tener &quot;en-US&quot;, &quot;en-us&quot; o &quot;EN-us&quot;. AEM Además, las guías de la pueden resolver &#39;-&#39; (guión) o &#39;_&#39; (guion bajo). Por lo tanto, puede tener &quot;en-US&quot; o &quot;en_US&quot;.

AEM Además, puede colocar estos archivos en cualquier carpeta debajo de la raíz de recursos que se encuentre en la carpeta, que es: `./content/dam`.



Una vez creada la carpeta que contiene los archivos SRX, puede añadir la ruta de la carpeta en la configuración de ubicación de Translation SRX dentro del perfil de carpeta.

Se recomienda que, para un mejor rendimiento, mantenga solo los archivos SRX en la carpeta configurada en el perfil de carpeta.


AEM Guías de traducción elige las reglas SRX según el idioma de origen del proyecto de traducción. Busca un archivo SRX personalizado para un idioma y, si no define un archivo SRX personalizado, selecciona las reglas según las reglas de traducción predeterminadas.


Para obtener más información sobre la configuración de perfiles globales y de nivel de carpeta, consulte *Configuración de plantillas de creación* en Instalar y configurar las guías de Adobe Experience Manager as a Cloud Service.

## Pasar la etiqueta de versión a la versión de destino

AEM Guías de le permite pasar la etiqueta del archivo de origen al archivo de destino. Esto le ayudará a identificar fácilmente la versión de origen del archivo traducido.

Para añadir la etiqueta de versión de origen en la copia de destino, el administrador del sistema debe seleccionar la opción **Propagar etiquetas de versión de origen a la versión de destino** en el **Traducción** pestaña en **Configuración del editor**.

Por ejemplo, si tiene algunos archivos de origen con la etiqueta de versión `Release 1.0` aplicado a ellos, también puede pasar la etiqueta de origen \(`Release 1.0`\) al archivo traducido.

![](images/translation-pass-source-label.png){width="650" align="left"}

>[!NOTE]
>
> La etiqueta de origen solo se adjunta a una versión de destino. Si mueve la etiqueta de origen a otra versión, se reflejará automáticamente en la etiqueta de destino más reciente.

## Ver la diferencia de versión de los archivos sin sincronizar 

AEM Guías de proporciona la función para comprobar las diferencias entre la versión seleccionada y la última versión de origen traducida de los temas. Puede elegir traducir el **Fuera de sincronización** archivos en función de los cambios realizados.

![](images/translation-version-diff.png){width="800" align="left"}

Seleccione el **Mostrar diferencia** icon \(![](images/show-difference-icon.svg)\) para ver las diferencias entre la última versión traducida y la versión actual del archivo seleccionado.

>[!NOTE]
>
> **Mostrar diferencia** icon \(![](images/show-difference-icon.svg)\) sólo aparece para ficheros DITA que tienen el estado de traducción como **Fuera de sincronización**.

El **Diferencia de versión** aparece el cuadro de diálogo. Muestra el **Última versión traducida** y el **Versión seleccionada** número de la izquierda. La ventana de vista previa muestra las diferencias entre la última versión traducida y la versión seleccionada del tema.

![](images/version-diff.png){width="650" align="left"}

## Descartar recursos no sincronizados

Si realiza cambios en algunos de los recursos, estos pasarán a estar Desincronizados. Puede volver a traducir los recursos modificados o elegir descartar el estado Fuera de sincronización. Por ejemplo, si ha realizado algunos cambios muy menores que realmente no necesitan traducción, puede marcar su estado como Sincronizado.

Para descartar el estado Fuera de sincronización, realice los siguientes pasos:

1. Seleccione los recursos sin sincronizar cuyo estado desea cambiar.
1. Seleccione el **Marcar en sincronización** button \(![](images/translation-mark-in-sync-icon.svg)\) en la parte superior El **Marcar en sincronización** aparece el cuadro de diálogo.

   ![](images/translation-mark-in-sync.png){width="550" align="left"}

1. Clic **Forzar sincronización**. Establece el estado en Sincronizado para los recursos sin sincronizar seleccionados.

>[!NOTE]
>
> **Marcar en sincronización** button \(![](images/translation-mark-in-sync-icon.svg)\) solo aparece para los recursos que tienen el estado de traducción Dessincronizado.

## Ver proyectos de traducción en curso de un mapa o un tema

Algunas de las referencias del panel de traducción pueden estar en curso. Estas referencias tienen un **En curso** vínculo en **Estado de traducción** columna. Al hacer clic en el vínculo, la variable **Proyectos en curso** se abre. En el cuadro de diálogo, puede ver la lista de todos los proyectos de traducción en curso \(junto con el idioma de destino\) que contienen la referencia seleccionada.

>[!NOTE]
>
> AEM Puede ver el vínculo En curso para los proyectos traducidos creados en la versión de febrero de 2023 o posterior de las Guías de as a Cloud Service.

Haga clic en el nombre de la referencia en el cuadro de diálogo para abrirla en el modo de vista previa. También puede hacer clic en el proyecto de traducción para iniciar la traducción.

![](images/translation-in-progress.png){width="550" align="left"}

**Tema principal:**[ Trabajar con el editor web](web-editor.md)
