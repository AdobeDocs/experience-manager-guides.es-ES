---
title: Prácticas recomendadas para la traducción de contenido
description: Conozca las prácticas recomendadas para la traducción de contenido en AEM Guides. Obtenga información sobre cómo configurar el servicio de traducción, crear un nuevo proyecto de traducción e iniciar el trabajo de traducción.
exl-id: f2a4df86-bba7-434c-b7f9-3587b8a4f9bc
feature: Translation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 0%

---

# Prácticas recomendadas para la traducción de contenido {#id1678G0S702F}

Tenga en cuenta el siguiente punto para traducir contenido:

- Los nombres de carpeta y archivo deben cumplir con los estándares de nomenclatura de archivos como: no debe haber espacios, apóstrofos, llaves, signo igual, caracteres especiales o no ASCII.

- Si traduce contenido a distintos idiomas, debe crear las carpetas correspondientes a cada idioma. Cada una de estas carpetas de idioma contendrá el contenido correspondiente a ese idioma. Por ejemplo, puede crear carpetas utilizando el designador de idioma como `de` para alemán, `fr` para francés, etc. O bien, puede crear carpetas utilizando los designadores de idioma y región como `fr-FR` para francés tal como se usa en Francia o `fr-CA` para francés tal como se usa en Canadá.
- El idioma de destino también debe tener las configuraciones regionales reales seleccionadas según las carpetas de idioma de destino de su instancia.
- La configuración de nube debe ser la misma que la de la carpeta de origen y solo debe haber una configuración de nube en una carpeta. Puede crear varias carpetas en /conf si desea utilizar varios conectores de traducción.
- Una carpeta no debe contener más de 1000 archivos.
- Asegúrese de que el usuario encargado de iniciar el proceso de traducción tenga permisos de lectura, modificación, creación y eliminación en las carpetas de idioma de origen y destino.
- Como la traducción de contenido requiere la creación de un proyecto de traducción, el usuario debe tener acceso para crear un proyecto en Adobe Experience Manager.
- Si desea utilizar ajustes preestablecidos condicionales con el mapa, debe crearlos antes de iniciar el proceso de traducción. Como los ajustes preestablecidos condicionales también se incluyen en la versión traducida del mapa, la creación de los ajustes preestablecidos antes de iniciar el proceso de traducción garantiza que estén disponibles en la versión traducida.
- El proceso de traducción de contenido debe iniciarse desde la consola de mapas DITA y no desde la interfaz de usuario de Adobe Experience Manager Assets.
- El flujo de trabajo de traducción DITA basado en componentes no debe utilizarse si se está traduciendo contenido mediante traducción humana. Sin embargo, esta opción debe utilizarse para la traducción automática.
- El contenido y los medios utilizados globalmente que no requieran localización deben mantenerse fuera de las copias de idioma.
- Todo el contenido común que debe localizarse debe mantenerse en una carpeta común bajo la carpeta de idioma.

La siguiente ilustración muestra un ejemplo de una estructura de carpetas en Adobe Experience Manager cuando ha utilizado globalmente contenido y tres copias de idioma.

![](images/aem-directory_structure.png){align="left"}

## Configuración del servicio de traducción

Realice los siguientes pasos para configurar el servicio de traducción humana o automática que se va a utilizar:

1. En la interfaz de usuario de Assets, seleccione la carpeta de idioma de origen.

1. Abra las propiedades de la carpeta y vaya a la ficha **Cloud Services**.

1. En la pestaña **Cloud Services**, configure el servicio de traducción que desee usar.

   Puede configurar la traducción automática o humana.

   Asegúrese de que solo haya una configuración para el conector de traducción en una carpeta. Se pueden crear varias carpetas en /conf si hay varios conectores de traducción. La carpeta de idioma de origen debe tener una configuración de nube seleccionada antes de iniciar el proceso de traducción.

   >[!NOTE]
   >
   > Consulte [Configuración del marco de trabajo de integración de traducciones](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=es) en la documentación de Adobe Experience Manager para obtener más información sobre la integración con servicios de traducción de terceros.

1. Seleccione **Guardar y cerrar** para guardar las propiedades actualizadas de la carpeta.


## Iniciar el trabajo de traducción {#id225IK030OE8}

Siga estos pasos para iniciar el trabajo de traducción:

1. En la consola **Proyectos**, vaya a la carpeta del proyecto que creó para la localización.

1. Seleccione el proyecto de localización para abrir la página de detalles.

1. Seleccione la flecha en el mosaico **Trabajo de traducción** y seleccione **Iniciar** de la lista para iniciar el flujo de trabajo de traducción.

   >[!NOTE]
   >
   > Si utiliza el servicio de traducción humana, debe exportar el contenido para su traducción. Una vez que tenga el contenido traducido, debe importarlo de nuevo en el proyecto de traducción.

1. Para ver el estado del trabajo de traducción, seleccione los puntos suspensivos en la parte inferior del mosaico **Trabajo de traducción**.


Una vez finalizada la traducción, el estado del trabajo de traducción cambia a *Listo para revisión*. Para completar el proceso de traducción, debe aceptar la copia traducida y los metadatos de recursos del mosaico Trabajo de traducción en la consola Proyecto. Si desea iniciar un nuevo proyecto de traducción, vea [Crear un proyecto de traducción](translate-documents-web-editor.md#create-a-translation-project).

>[!NOTE]
>
>- Si rechaza la traducción de uno o más temas de un trabajo de traducción, el estado de traducción de **En curso** de todos los temas rechazados vuelve a su estado original. El estado de los temas referidos se comprueba y revierte según el estado de traducción más reciente. Además, los archivos de traducción creados en la carpeta de idioma de destino no se eliminan aunque la traducción se rechace para ellos.
>- Si rechaza, elimina o cancela el trabajo de traducción de un tema presente en varios proyectos (para cualquiera de los proyectos), el estado de traducción **En curso** del tema no se revierte, pero ese proyecto se elimina de la lista de proyectos **En curso** para ese recurso dado.
>- Además, si cancela o elimina el trabajo de traducción o elimina todo el proyecto, el estado de la traducción **En curso** vuelve a su estado original.

**Tema principal:**&#x200B;[&#x200B; Resumen de traducción de contenido](translation.md)
