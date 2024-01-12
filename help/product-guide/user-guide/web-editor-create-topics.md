---
title: Crear temas
description: AEM Aprenda a crear tipos de temas DITA utilizando plantillas personalizadas en el editor web de Guías de.
exl-id: 84e9cfdf-e188-487f-9181-68708029c101
feature: Authoring
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 0%

---

# Crear temas {#id2056AL00O5Z}

AEM Guías de permite crear temas DITA de tipo: tema, tarea, concepto, referencia, glosario, DITAVAL, etc. Además de crear temas basados en las plantillas predeterminadas, también puede definir las plantillas personalizadas. Estas plantillas deben añadirse al perfil de carpeta para que se muestren en la selección de plantillas de modelo y en el editor web.

Tenga en cuenta que la configuración de Perfil global y de carpeta solo está disponible para los usuarios administrativos de nivel de carpeta. Para obtener más información sobre la configuración de perfiles globales y de nivel de carpeta, consulte *Configuración de plantillas de creación* en Instalar y configurar las guías de Adobe Experience Manager para su configuración.

Siga estos pasos para crear un tema:

1. En la interfaz de usuario de Assets, vaya a la ubicación en la que desea crear el tema.

1. Para crear un nuevo tema, haga clic en **Crear** \> **Tema DITA**.

1. En la página Modelo, seleccione el tipo de documento DITA que desea crear y haga clic en **Siguiente**.

   ![](images/create_dita_topic.png){width="800" align="left"}

   AEM De forma predeterminada, Guías de proporciona las plantillas de temas DITA más utilizadas. Puede configurar más plantillas de temas según sus necesidades organizativas, consulte *Configuración de plantillas de creación* en Instalar y configurar las guías de Adobe Experience Manager para su configuración.

   >[!NOTE]
   >
   > En la vista de lista de la IU de Assets, el tipo de tema DITA se muestra en la columna Tipo como Tema, Tarea, Concepto, Referencia, Glossentry o DITAVAL. El mapa DITA se muestra como Mapa.

1. En la página Propiedades, especifique el documento **Título**.

1. \(Opcional\) Especifique el archivo **Nombre**.

   Si el administrador ha configurado un nombre de archivo automático basado en la configuración de UUID, no verá la opción para especificar el nombre del archivo. Se asigna automáticamente un nombre de archivo basado en UUID al archivo.

   Si la opción de nomenclatura de archivos está disponible, el nombre también se sugiere automáticamente en función de la variable **Título** del documento. Si desea especificar manualmente el nombre del documento, asegúrese de que la variable **Nombre** no contiene espacios, apóstrofos ni llaves, y termina con .xml o .dita. AEM De forma predeterminada, Guías de reemplaza todos los caracteres especiales por guiones. Consulte la sección Nombres de archivo en la Guía de prácticas recomendadas para conocer las prácticas recomendadas sobre la nomenclatura de archivos DITA.

1. Haga clic en **Crear**. Aparecerá el mensaje Tema creado.

   AEM Puede elegir abrir el tema para editarlo en el Editor Web o guardar el archivo de tema en el repositorio de la aplicación de la aplicación de la aplicación de la aplicación de la aplicación de la aplicación de la aplicación de la aplicación de la aplicación de la aplicación de la aplicación de la aplicación de la aplicación de la aplicación de la aplicación de la aplicación.

   Todos los temas nuevos que cree desde la interfaz de usuario de Assets **Crear** \> **Tema DITA** o al editor web se le asigna un ID de tema único. El valor de este ID es el propio nombre de archivo. Además, un nuevo documento se guarda como la última copia de trabajo del tema en DAM. Hasta que guarde una revisión de un tema recién creado, no verá ningún número de versión en el Historial de versiones. Si abre el tema para editarlo, la información de la versión se muestra en la esquina superior derecha de la pestaña del archivo de tema:

   ![](images/topic-version-none_cs.png){width="550" align="left"}

   La información de versión de un tema recién creado se muestra como *ninguno*. Al guardar una nueva versión, se le asigna un número de versión como 1.0. Para obtener más información sobre cómo guardar una nueva versión, consulte [Guardar como nueva versión](web-editor-features.md#save-as-new-version-id209ME400GXA).


>[!NOTE]
>
> Si el administrador ha configurado el Editor Web para que desproteja los archivos antes de editarlos, no podrá editar un archivo hasta que lo desproteja. Del mismo modo, si está configurado, se le pedirá que proteja cualquier archivo desprotegido antes de cerrarlo.

>[!IMPORTANT]
>
> Una vez creado el tema DITA, siga guardando los cambios en la copia de trabajo y cree una nueva versión una vez que haya completado las actualizaciones del tema.

**Tema principal:**[ Crear y previsualizar temas](create-preview-topics.md)
