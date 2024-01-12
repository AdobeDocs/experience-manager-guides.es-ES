---
title: Descargar archivos
description: AEM AEM Obtenga información sobre cómo descargar archivos desde la consola de mapas de DITA en Guías de y exportar un archivo de mapa de DITA en el repositorio de datos de la aplicación de mapas de DITA.
exl-id: ae9eb355-d3ac-446a-958b-5f2da43f5533
feature: Content Management
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 0%

---

# Descargar archivos {#id216MC0H0BE8}

Puede descargar recursos, incluidos archivos DITA y no DITA. AEM AEM Existen varias formas de descargar recursos, algunos métodos son nativos de los recursos y otros son compatibles con las guías de los recursos de los que dispone el usuario para la descarga de recursos de la manera más rápida y eficaz. En la práctica, los métodos son nativos de los recursos y los métodos son compatibles con las guías de los recursos de la. AEM Para obtener información sobre la descarga de recursos nativos de la, consulte [Descarga de recursos desde Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/download-assets-from-aem.html) AEM en la documentación de. AEM En la siguiente sección se explica el mecanismo de descarga de archivos mediante la consola de mapas DITA en las guías de la aplicación de la aplicación de la.

## Exportación de un fichero de mapa DITA

AEM Una vez que tenga el fichero de mapa DITA en el repositorio de la, podrá descargar el fichero de mapa junto con sus dependientes. Esto le proporciona la flexibilidad para compartir el archivo de asignación completo para la edición, validación, revisión o simplemente la creación de una copia de seguridad sin conexión.

Realice los siguientes pasos para descargar un archivo de asignación DITA junto con sus archivos dependientes:

1. En la interfaz de usuario de Assets, vaya al mapa DITA que desee descargar.

1. Haga clic en el mapa DITA para abrirlo en la consola de mapas DITA.

1. Seleccione el **Temas** para ver una lista de los temas disponibles en el mapa DITA.

1. En la barra de herramientas principal, haga clic en **Descargar mapa**.

   Aparecerá el cuadro de diálogo Descargar mapa.

   ![](images/download-map.png){width="300" align="left"}

1. Haga clic en **Descargar**. En el cuadro de diálogo Descargar mapa, puede elegir las siguientes opciones:

   - **Usar línea base**: seleccione esta opción para obtener una lista de las líneas base creadas para el mapa DITA. Si desea descargar el archivo de asignación y su contenido en función de una Línea base específica, seleccione la Línea base en la lista desplegable. Para obtener más información sobre cómo trabajar con líneas de base, consulte [Trabajar con línea base](generate-output-use-baseline-for-publishing.md#).
   - **Acoplar jerarquía de archivos**: seleccione esta opción para guardar todos los temas a los que se hace referencia y los archivos multimedia en una sola carpeta.
   >[!NOTE]
   >
   > También puede descargar el archivo de asignación sin seleccionar ninguna opción. En ese caso, se descarga la última versión persistente de los temas a los que se hace referencia y los archivos multimedia.

1. Después de hacer clic en **Descargar** botón, la solicitud de descarga de mapa se pone en cola. Recibirá la siguiente notificación una vez que el mapa esté listo para descargarse.

   ![](images/download-map-prompt.png){width="550" align="left"}

   - Clic **Descargar** para descargar el archivo de mapa en formato .zip.

   - Clic **Descargar más tarde** para descargar el archivo de asignación más adelante. AEM Se puede acceder al vínculo de descarga desde la bandeja de entrada de notificaciones de la. Haga clic en la notificación de asignación generada en la bandeja de entrada para descargar la asignación en formato .zip.

   >[!NOTE]
   >
   > AEM De forma predeterminada, las asignaciones descargadas permanecen durante cinco días en la Bandeja de entrada de notificaciones de la.

![](images/download-map-inbox.png){width="300" align="left"}

Una vez descargado el mapa, puede seleccionarlo y utilizar el icono Abrir de la parte superior para abrir el informe seleccionado.

**Tema principal:**[ Administrar contenido](authoring.md)
