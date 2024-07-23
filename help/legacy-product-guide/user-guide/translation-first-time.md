---
title: Prácticas recomendadas para la traducción de contenido
description: Conozca las prácticas recomendadas para la traducción de contenido en AEM Guides. Obtenga información sobre cómo configurar el servicio de traducción, crear un nuevo proyecto de traducción e iniciar el trabajo de traducción.
feature: Translation
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '1295'
ht-degree: 1%

---

# Prácticas recomendadas para la traducción de contenido {#id1678G0S702F}

Tenga en cuenta el siguiente punto para traducir contenido:

- Los nombres de carpeta y archivo deben cumplir con los estándares de nomenclatura de archivos como: no debe haber espacios, apóstrofos, llaves, signo igual, caracteres especiales o no ASCII.

- Si traduce contenido a distintos idiomas, debe crear las carpetas correspondientes a cada idioma. Cada una de estas carpetas de idioma contendrá el contenido correspondiente a ese idioma. Por ejemplo, puede crear carpetas utilizando el designador de idioma como `de` para alemán, `fr` para francés, etc. O bien, puede crear carpetas utilizando los designadores de idioma y región como `fr-FR` para francés tal como se usa en Francia o `fr-CA` para francés tal como se usa en Canadá.
- El idioma de destino también debe tener las configuraciones regionales reales seleccionadas según las carpetas de idioma de destino de su instancia.
- La configuración de nube debe ser la misma que la de la carpeta de origen y solo debe haber una configuración de nube en una carpeta. Puede crear varias carpetas en /conf si desea utilizar varios conectores de traducción.
- Una carpeta no debe contener más de 1000 archivos.
- Asegúrese de que el usuario encargado de iniciar el proceso de traducción tenga permisos de lectura, modificación, creación y eliminación en las carpetas de idioma de origen y destino.
- AEM Como la traducción de contenido requiere la creación de un proyecto de traducción, el usuario debe tener acceso para crear un proyecto en la.
- Si desea utilizar ajustes preestablecidos condicionales con el mapa, debe crearlos antes de iniciar el proceso de traducción. Como los ajustes preestablecidos condicionales también se incluyen en la versión traducida del mapa, la creación de los ajustes preestablecidos antes de iniciar el proceso de traducción garantiza que estén disponibles en la versión traducida.
- El proceso de traducción de contenido debe iniciarse desde la consola de mapas DITA y no desde la interfaz de usuario de AEM Assets.
- El flujo de trabajo de traducción DITA basado en componentes no debe utilizarse si se está traduciendo contenido mediante traducción humana. Sin embargo, esta opción debe utilizarse para la traducción automática.
- El contenido y los medios utilizados globalmente que no requieran localización deben mantenerse fuera de las copias de idioma.
- Todo el contenido común que debe localizarse debe mantenerse en una carpeta común bajo la carpeta de idioma.

AEM En la siguiente ilustración se muestra un ejemplo de una estructura de carpetas en las que se ha utilizado de forma global contenido y tres copias de idioma.

![](images/aem-directory_structure.png){width="800" align="left"}

## Configuración del servicio de traducción

Realice los siguientes pasos para configurar el servicio de traducción humana o automática que se va a utilizar:

1. En la interfaz de usuario de Assets, seleccione la carpeta de idioma de origen.

1. Abra las propiedades de la carpeta y vaya a la ficha **Cloud Service**.

1. En la ficha **Cloud Service**, configure el servicio de traducción que desee usar.

   Puede configurar la traducción automática o humana.

   Asegúrese de que solo haya una configuración para el conector de traducción en una carpeta. Se pueden crear varias carpetas en /conf si hay varios conectores de traducción. La carpeta de idioma de origen debe tener una configuración de nube seleccionada antes de iniciar el proceso de traducción.

   >[!NOTE]
   >
   > AEM Consulte [Configuración del marco de trabajo de integración de traducciones](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) en documentación de para obtener más información sobre la integración con servicios de traducción de terceros.

1. Haga clic en **Guardar y cerrar** para guardar las propiedades actualizadas de la carpeta.


>[!TIP]
>
> Consulte la sección *Traducción* en la guía de prácticas recomendadas para conocer las prácticas recomendadas sobre la traducción de contenido.

## Crear un nuevo proyecto de traducción

Siga estos pasos para crear un proyecto de traducción:

>[!NOTE]
>
> Antes de realizar los pasos de este procedimiento, asegúrese de haber creado las carpetas raíz y de destino del idioma necesarias tal como se describe en las [prácticas recomendadas para la traducción de contenido](#id1678G0S702F).

1. En la interfaz de usuario de Assets, haga clic en el fichero de mapa DITA.

1. Haga clic en la ficha **Traducción**.

1. En la lista **Idiomas de destino**, seleccione la configuración regional a la que desea traducir el proyecto y haga clic en **Listo**.

   Se muestra un resumen y detalles de los temas y los recursos asociados.

   >[!IMPORTANT]
   >
   > Los **idiomas de destino** solo muestran los idiomas para los que se crea una carpeta de idioma paralela al idioma de origen. Tampoco se muestra una carpeta de idioma creada en cualquier otro nivel, como un nivel por debajo de la carpeta de idioma de origen. Asegúrese de crear todas las carpetas de idioma de destino en el mismo nivel que la carpeta de idioma de origen.

1. Seleccione los temas que desee enviar para su traducción.

   También puede utilizar las siguientes opciones de filtrado de temas:

   >[!NOTE]
   >
   > Después de aplicar el filtro requerido, haga clic en **Listo** en el panel Filtro para filtrar los temas según su selección.

   - **Estado de traducción**: elija filtrar los temas según su estado de traducción. Las opciones disponibles son: Fuera de sincronización, Falta de copia, En curso y Sincronizado.
   - **Buscar**: escriba uno o varios términos para buscar en los títulos de los temas.
   - **Tipo de Source**: elija filtrar los temas según sus tipos de archivo. Las opciones disponibles son: Todos, DITA, Mapa DITA, Recurso.
   - **Versión de Source modificada después de**: elija filtrar el tema en función de su fecha y hora de modificación. En la lista se muestran todos los temas modificados después de la fecha y hora especificadas.
   - **Línea de base**: Haga clic en Usar línea de base y elija una línea de base creada en el mapa. Todos los archivos que forman parte de la Línea base seleccionada se muestran en la página Traducción. Puede elegir los archivos deseados de la línea base y continuar con el proceso de traducción. Una vez traducido el contenido, puede exportar la línea de base traducida. Para obtener más información sobre cómo exportar la línea de base traducida, consulte [Exportar línea de base traducida](generate-output-use-baseline-for-publishing.md#id196SE600GHS).
1. Haga clic en **Crear/actualizar copias de idioma** en la parte inferior del panel Filtro.

1. En la lista **Proyecto**, seleccione **Crear un nuevo proyecto de traducción**.

   >[!NOTE]
   >
   > Si ya tiene un proyecto de traducción, puede agregarle temas. Seleccione la opción **Agregar a proyecto de traducción existente** de la lista **Proyecto** y elija un proyecto de la lista **Proyecto de traducción existente**.

1. En el campo **Título del proyecto**, introduzca un título.

1. Seleccione la opción **Incluir mapa DITA** para enviar el mapa para su traducción.
1. Haga clic en **Iniciar** para crear un nuevo proyecto de traducción.

   Se crea un nuevo proyecto de traducción con la versión seleccionada de los temas. En este momento, se muestra un mensaje emergente que confirma que se ha creado el proyecto de traducción. Una vez que todas las copias de idioma de destino estén disponibles en el proyecto de traducción, recibirá una notificación en la bandeja de entrada. Una vez que las copias de idioma de destino estén disponibles en el proyecto de traducción, puede continuar e iniciar el trabajo de traducción.

   ![](images/status-translation-uuid.png){width="800" align="left"}


La pestaña Traducción tiene las siguientes secciones:

- **Resumen**: muestra el número de temas a los que se hace referencia y el idioma de origen junto con su código.
- **Detalles**: muestra el título del tema, el tipo de tema, el código de idioma del tema, el idioma de origen, la versión del tema de origen, la etiqueta agregada al tema y el estado de traducción.




## Iniciar el trabajo de traducción {#id225IK030OE8}

Siga estos pasos para iniciar el trabajo de traducción:

1. En la consola **Proyectos**, vaya a la carpeta del proyecto que creó para la localización.

1. Haga clic en el proyecto de localización para abrir la página de detalles.

1. Haga clic en la flecha del mosaico **Trabajo de traducción** y seleccione **Iniciar** en la lista para iniciar el flujo de trabajo de traducción.

   >[!NOTE]
   >
   > Si utiliza el servicio de traducción humana, debe exportar el contenido para su traducción. Una vez que tenga el contenido traducido, debe importarlo de nuevo en el proyecto de traducción.

1. Para ver el estado del trabajo de traducción, haga clic en los puntos suspensivos en la parte inferior del mosaico **Trabajo de traducción**.


Una vez finalizada la traducción, el estado del trabajo de traducción cambia a *Listo para revisión*. Para completar el proceso de traducción, debe aceptar la copia traducida y los metadatos de recursos del mosaico Trabajo de traducción en la consola Proyecto.

>[!NOTE]
>
> Si rechaza la traducción de uno o más temas de un trabajo de traducción, el estado de traducción de **En curso** de todos los temas rechazados vuelve a su estado original. El estado de los temas referidos se comprueba y revierte según el estado de traducción más reciente. Además, los archivos de traducción creados en el proyecto de destino no se eliminan aunque la traducción se rechace para ellos.

**Tema principal:**[ Traducir contenido](translation.md)
