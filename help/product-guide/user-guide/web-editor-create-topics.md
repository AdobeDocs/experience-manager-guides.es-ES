---
title: Crear temas
description: Aprenda a crear tipos de temas DITA con plantillas personalizadas en Adobe Experience Manager Guides.
exl-id: 84e9cfdf-e188-487f-9181-68708029c101
feature: Authoring
role: User
source-git-commit: c6709ffb8e415c88931e732456e2f2a5e6b63729
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 0%

---

# Crear temas {#id2056AL00O5Z}

Adobe Experience Manager Guides permite crear temas DITA de tipo: tema, tarea, concepto, referencia, glosario, DITAVAL, Markdown, etc. Además de crear temas basados en las plantillas predeterminadas, también puede definir las plantillas personalizadas. Estas plantillas deben añadirse al perfil de carpeta para que se muestren en la selección de plantillas de modelo y editor.

>[!NOTE]
>
> La configuración del perfil Global y Carpeta solo está disponible para los usuarios administrativos de nivel de carpeta. Para obtener más información sobre la configuración de perfiles globales y de nivel de carpeta, consulta *Configuración de plantillas de creación* en Instalar y configurar Adobe Experience Manager Guides para tu configuración.


Existen dos formas de crear temas en Experience Manager Guides:

- [Crear temas desde el editor](#create-topics-from-the-editor)
- [Creación de temas desde la interfaz de usuario de Assets](#create-topics-from-the-assets-ui)

## Crear temas desde el editor

Siga estos pasos para crear un tema desde el Editor:

1. En el panel Repositorio, seleccione el icono **Nuevo archivo** y, a continuación, seleccione **Tema** en el menú desplegable.

   ![](images/create-topic-option.png){width="500" align="left"}

   También puede acceder a esta opción desde la [página principal de Experience Manager Guides](./intro-home-page.md) y desde el menú de opciones de una carpeta en la vista Repositorio.

2. Se muestra el cuadro de diálogo **Nuevo tema**.

3. En el cuadro de diálogo **Nuevo tema**, proporcione los siguientes detalles:
   - Título del tema.
   - \(Opcional\)* El nombre de archivo del tema. El nombre del archivo se sugiere automáticamente en función del tema Título. Si el administrador ha habilitado nombres de archivo automáticos basados en la configuración de UUID, no verá el campo Nombre.
   - Una plantilla en la que se basará el tema. Por ejemplo, para una configuración predeterminada, puede elegir entre las plantillas en blanco, Concepto, DITAVAL, Referencia, Tarea, Tema, Markdown, Glosario y Solución de problemas. Si la carpeta tiene un perfil de carpeta configurado, solo verá las plantillas de temas que estén configuradas en el perfil de carpeta.
   - Ruta de acceso donde desea guardar el archivo de tema. De forma predeterminada, la ruta de la carpeta seleccionada actualmente en el repositorio se muestra en el campo Ruta.

4. Seleccione **Crear**.

   ![](images/create-topic-dialog-new.png){width="300" align="left"}

El tema se crea en la ruta de acceso especificada. Además, el tema se abre en el Editor para editarlo.

![](images/new-topic-editor.png){align="left"}

## Creación de temas desde la interfaz de usuario de Assets

Siga estos pasos para crear un tema desde la interfaz de usuario de Assets:

1. En la interfaz de usuario de Assets, vaya a la ubicación en la que desea crear el tema.

1. Para crear un tema nuevo, seleccione **Crear** \> **Tema DITA**.

1. En la página Modelo, seleccione el tipo de documento DITA que desea crear y seleccione **Siguiente**.

   ![](images/create_dita_topic.png){align="left"}

   De forma predeterminada, Experience Manager Guides proporciona las plantillas de temas DITA más utilizadas. Puede configurar más plantillas de temas según sus requisitos organizativos, ver *Configuración de plantillas de creación* en Instalar y configurar Adobe Experience Manager Guides para su configuración.

   >[!NOTE]
   >
   > En la vista de lista de la IU de Assets, el tipo de tema DITA se muestra en la columna Tipo como Tema, Tarea, Concepto, Referencia, Glossentry, Markdown o DITAVAL. El mapa DITA se muestra como Mapa.

1. En la página Propiedades, especifique el documento **Título**.

1. \(Opcional\) Especifique el archivo **Nombre**.

   Si el administrador ha configurado un nombre de archivo automático basado en la configuración de UUID, no verá la opción para especificar el nombre de archivo. Se asigna automáticamente un nombre de archivo basado en UUID al archivo.

   Si la opción de nomenclatura de archivos está disponible, también se sugiere automáticamente el nombre en función del **Título** del documento. Si desea especificar manualmente el nombre del documento, asegúrese de que **Name** no contenga espacios, apóstrofos ni llaves y termine con .xml o .dita. De forma predeterminada, Experience Manager Guides reemplaza todos los caracteres especiales por guiones. Consulte la sección Nombres de archivo en la Guía de recomendaciones para conocer las prácticas recomendadas sobre la asignación de nombres a archivos DITA.

1. Seleccione **Crear**. Aparecerá el mensaje Tema creado.

   Puede elegir abrir el tema para editarlo en el Editor o guardar el archivo del tema en el repositorio de Adobe Experience Manager.

**Información adicional**

1. A cada tema nuevo que cree desde la interfaz de usuario de Assets **Create** \> **DITA Topic** o el editor se le asigna un ID de tema único. El valor de este ID es el propio nombre de archivo. Además, un nuevo documento se guarda como la última copia de trabajo del tema en DAM. Hasta que guarde una revisión de un tema recién creado, no verá ningún número de versión en el Historial de versiones. Si abre el tema para editarlo, la información de la versión se muestra en la esquina superior derecha de la barra de herramientas:

   ![](images/topic-version-none_cs.png){width="550" align="left"}

2. La información de versión de un tema recién creado se muestra como *none*. Al guardar una nueva versión, se le asigna un número de versión como 1.0.

3. Si el administrador ha configurado el Editor para que bloquee los archivos antes de editarlos, no podrá editar un archivo hasta que lo bloquee. Del mismo modo, si se configura, se le pedirá que desbloquee cualquier archivo bloqueado antes de cerrarlo.

4. Una vez creado el tema DITA, siga guardando los cambios en la copia de trabajo y cree una nueva versión una vez que haya completado las actualizaciones del tema.

**Tema principal:**&#x200B;[&#x200B; Crear y previsualizar temas](create-preview-topics.md)
