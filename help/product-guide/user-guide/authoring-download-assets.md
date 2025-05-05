---
title: Descargar archivos
description: Obtenga información sobre cómo descargar archivos desde la consola de mapas DITA en AEM Guides y exportar un archivo de mapa DITA en el repositorio de AEM.
exl-id: ae9eb355-d3ac-446a-958b-5f2da43f5533
feature: Content Management
role: User
source-git-commit: 632b253a36822b4b5b93766153f0fc3a1116b616
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%

---

# Descargar archivos {#id216MC0H0BE8}

Puede descargar recursos, incluidos archivos DITA y no DITA. Existen varias formas de descargar recursos, algunos son nativos de Adobe Experience Manager y otros son compatibles con Adobe Experience Manager Guides. Para obtener información de descarga de recursos nativos de Adobe Experience Manager, vea [Descargar recursos de Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/download-assets-from-aem.html?lang=es) en la documentación de Adobe Experience Manager. En la siguiente sección se explica el mecanismo de descarga de archivos mediante la consola de mapas DITA en Experience Manager Guides.

## Exportación de un fichero de mapa DITA

Una vez que tenga el fichero de mapa DITA en el repositorio de Adobe Experience Manager, podrá descargar el fichero de mapa junto con sus dependientes. Esto le proporciona la flexibilidad para compartir el archivo de asignación completo para la edición, validación, revisión o simplemente la creación de una copia de seguridad sin conexión.

Realice los siguientes pasos para descargar un archivo de asignación DITA junto con sus archivos dependientes:

1. En la interfaz de usuario de Assets, vaya al mapa DITA que desee descargar.

1. Seleccione el mapa DITA para abrirlo en la consola de mapas DITA.

1. Seleccione la ficha **Temas** para ver la lista de temas disponibles en el mapa DITA.

1. En la barra de herramientas principal, seleccione **Descargar mapa**.

   Aparecerá el cuadro de diálogo Descargar mapa.

   ![](images/download-map.png){width="300" align="left"}

1. Seleccione **Descargar**. En el cuadro de diálogo Descargar mapa, puede elegir las siguientes opciones:

   - **Usar Línea Base**: Seleccione esta opción para obtener una lista de Líneas Base creadas para el mapa DITA. Si desea descargar el archivo de asignación y su contenido en función de una Línea base específica, seleccione la Línea base en la lista desplegable. Para obtener más información acerca de cómo trabajar con líneas de base, vea [Trabajar con línea de base](generate-output-use-baseline-for-publishing.md#).

   - **Acoplar jerarquía de archivos**: seleccione esta opción para guardar todos los temas a los que se hace referencia y los archivos multimedia en una sola carpeta.


   >[!NOTE]
   >
   > También puede descargar el archivo de asignación sin seleccionar ninguna opción. En ese caso, se descarga la última versión persistente de los temas a los que se hace referencia y los archivos multimedia.

1. Después de seleccionar el botón **Descargar**, la solicitud de descarga del mapa se pone en cola. Recibirá la siguiente notificación una vez que el mapa esté listo para descargarse.

   ![](images/download-map-prompt.png){width="550" align="left"}

   - Seleccione **Descargar** para descargar el archivo de asignación en formato .zip.

   - Seleccione **Descargar más tarde** para descargar el archivo de asignación más adelante. Se puede acceder al vínculo de descarga desde la bandeja de entrada de notificaciones de Adobe Experience Manager. Seleccione la notificación de asignación generada en la bandeja de entrada para descargar la asignación en formato .zip.

   >[!NOTE]
   >
   > De forma predeterminada, las asignaciones descargadas permanecen durante cinco días en la Bandeja de entrada de notificaciones de Adobe Experience Manager.

![](images/download-map-inbox.png){width="300" align="left"}

Una vez descargado el mapa, puede seleccionarlo y utilizar el icono Abrir de la parte superior para abrir el informe seleccionado.

**Tema principal:**&#x200B;[ Administrar contenido](authoring.md)
