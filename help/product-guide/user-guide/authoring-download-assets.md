---
title: Descargar archivos
description: Obtenga información sobre cómo descargar archivos desde la consola de mapas DITA en AEM Guides y exportar un archivo de mapa DITA en el repositorio de AEM.
exl-id: ae9eb355-d3ac-446a-958b-5f2da43f5533
feature: Content Management
role: User
TQID: https://experienceleague.adobe.com/xwz0wuugvwPsmIX78kuwv5te2NGcNTik-qoJvijRzzg
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: a7bba4a6-624b-4427-a9b8-dd411a1bfd41
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 864
ht-degree: 0%

---

# Descargar archivos {#id216MC0H0BE8}

Puede descargar recursos, incluidos archivos DITA y no DITA. Existen varias formas de descargar recursos, algunos son nativos de Adobe Experience Manager y otros son compatibles con Adobe Experience Manager Guides. Para obtener información de descarga de recursos nativos de Adobe Experience Manager, vea [Descargar recursos de Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/download-assets-from-aem.html?lang=es) en la documentación de Adobe Experience Manager. En la siguiente sección se explica el mecanismo de descarga de archivos en Experience Manager Guides.

## Descargar un archivo de mapa DITA desde el Editor

Siga estos pasos para descargar un archivo de mapa DITA desde el Editor:

1. Desplácese hasta el mapa DITA que desee descargar.
1. Seleccione el mapa DITA para abrirlo en el Editor.

1. En la vista Mapa, selecciona el icono **Opciones** y elige **Descargar mapa** de la lista.

   ![](images/download-map-option-editor.png)

   Se muestra el cuadro de diálogo **Descargar mapa**.

   ![](images/download-map-dialog-new.png){width="300"}

1. En el cuadro de diálogo Descargar mapa, puede elegir las siguientes opciones:

   - **Usar línea base**: seleccione esta opción para obtener una lista de líneas base creadas para el mapa DITA. Si desea descargar el archivo de asignación y su contenido en función de una Línea base específica, seleccione la Línea base en la lista desplegable. Para obtener más información acerca de cómo trabajar con líneas de base, vea [Trabajar con línea de base](generate-output-use-baseline-for-publishing.md#).

   - **Opciones de jerarquía de archivos**: también puede usar la lista desplegable de jerarquía de archivos para elegir cómo se administra la estructura de carpetas para los archivos de mapa descargados. Las opciones disponibles son:

      - **Conservar jerarquía de archivos**: seleccione esta opción en la lista desplegable para conservar la estructura de carpetas existente para los archivos descargados.
      - **Acoplar jerarquía de archivos**: seleccione esta opción en la lista desplegable para descargar todos los temas a los que se hace referencia y los archivos multimedia en una sola carpeta.

     Para cada opción, puede especificar cómo se gestionan los nombres de archivo de los archivos descargados. Están disponibles las siguientes opciones de nombre de archivo:

      - **Usar nombre de archivo GUID**: descarga el archivo de asignación con GUID como nombre de archivo.
      - **Usar nombre de archivo real**: descarga el archivo de asignación con su nombre de archivo original. Cuando se utiliza esta opción con Acoplar jerarquía de archivos, los nombres de archivo duplicados en el mapa se resuelven automáticamente añadiendo sufijos numéricos (_2, _3, etc.) para garantizar nombres de archivo únicos.

   >[!NOTE]
   >
   > También puede descargar el archivo de asignación sin seleccionar ninguna opción. En ese caso, se descarga la última versión persistente de los temas a los que se hace referencia y los archivos multimedia.


1. Seleccione **Descargar**.

   La solicitud de descarga del mapa está en cola.

   ![](images/download-map-notification.png)

   Recibirá la siguiente notificación una vez que el mapa esté listo para descargarse.

   ![](images/download-map-success-message.png){width="550"}

1. Seleccione **Descargar** para descargar el archivo de asignación en formato `.zip`. O bien, descárguelo más tarde desde la bandeja de entrada de AEM.

   >[!NOTE]
   >
   > De forma predeterminada, las asignaciones descargadas permanecen durante cinco días en la Bandeja de entrada de notificaciones de Adobe Experience Manager.

Una vez descargado el mapa, puede seleccionarlo y utilizar el icono Abrir de la parte superior para abrir el contenido descargado. Para ver los metadatos asociados del mapa descargado, abra el archivo `metdata.json` incluido en el contenido descargado. Este archivo está disponible para las opciones *Jerarquía de archivos*: Acoplar jerarquía de archivos y Conservar jerarquía de archivos.

## Descargar un fichero de mapa DITA desde el tablero de mandos Mapa

Una vez que tenga el fichero de mapa DITA en el repositorio de Adobe Experience Manager, podrá descargar el fichero de mapa junto con sus dependientes. Esto le proporciona la flexibilidad para compartir el archivo de asignación completo para la edición, validación, revisión o simplemente la creación de una copia de seguridad sin conexión.

Realice los siguientes pasos para descargar un archivo de asignación DITA junto con sus archivos dependientes:

1. En la interfaz de usuario de Assets, vaya al mapa DITA que desee descargar.

1. Seleccione el mapa DITA para abrirlo en la consola de mapas DITA.

1. Seleccione la ficha **Temas** para ver la lista de temas disponibles en el mapa DITA.

1. En la barra de herramientas principal, seleccione **Descargar mapa**.

   Aparecerá el cuadro de diálogo Descargar mapa.

   ![](images/download-map.png){width="300"}

1. Seleccione **Descargar**. En el cuadro de diálogo Descargar mapa, puede elegir las siguientes opciones:

   - **Usar Línea Base**: Seleccione esta opción para obtener una lista de Líneas Base creadas para el mapa DITA. Si desea descargar el archivo de asignación y su contenido en función de una Línea base específica, seleccione la Línea base en la lista desplegable. Para obtener más información acerca de cómo trabajar con líneas de base, vea [Trabajar con línea de base](generate-output-use-baseline-for-publishing.md#).

   - **Acoplar jerarquía de archivos**: seleccione esta opción para guardar todos los temas a los que se hace referencia y los archivos multimedia en una sola carpeta.


   >[!NOTE]
   >
   > También puede descargar el archivo de asignación sin seleccionar ninguna opción. En ese caso, se descarga la última versión persistente de los temas a los que se hace referencia y los archivos multimedia.

1. Después de seleccionar el botón **Descargar**, la solicitud de descarga del mapa se pone en cola. Recibirá la siguiente notificación una vez que el mapa esté listo para descargarse.

   ![](images/download-map-prompt.png){width="550"}

   - Seleccione **Descargar** para descargar el archivo de asignación en formato .zip.

   - Seleccione **Descargar más tarde** para descargar el archivo de asignación más adelante. Se puede acceder al vínculo de descarga desde la bandeja de entrada de notificaciones de Adobe Experience Manager. Seleccione la notificación de asignación generada en la bandeja de entrada para descargar la asignación en formato .zip.

   >[!NOTE]
   >
   > De forma predeterminada, las asignaciones descargadas permanecen durante cinco días en la Bandeja de entrada de notificaciones de Adobe Experience Manager.

![](images/download-map-inbox.png){width="300"}

Una vez descargado el mapa, puede seleccionarlo y utilizar el icono Abrir de la parte superior para abrir el contenido descargado.

**Tema principal:**&#x200B;[&#x200B; Administrar contenido](authoring.md)
