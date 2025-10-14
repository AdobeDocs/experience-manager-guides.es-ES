---
title: Informe de mapa DITA del tablero de mapas
description: Genere informes de mapas DITA desde el tablero de mapas de AEM Guides. Obtenga información sobre cómo generar el CSV de un informe de mapa DITA.
exl-id: 7fe52ee0-e940-467b-9b8d-3d2371de7a84
feature: Report Generation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 0%

---

# Informe de mapa DITA del tablero de mapas {#id205BB800EEN}

Adobe Experience Manager Guides proporciona a sus administradores las funciones de creación de informes para comprobar la integridad general de la documentación antes de que se publique o se ponga a disposición de los usuarios finales. El informe de mapa DITA del tablero de mapas de Experience Manager Guides proporciona información valiosa, como los temas que faltan, los temas con elementos que faltan, el UUID de los temas a los que se hace referencia y los archivos multimedia, así como el estado de revisión de cada tema. Un informe detallado a nivel de tema individual también proporciona información relacionada con el contenido DITA, como referencias de contenido e imágenes que faltan o referencias cruzadas.

>[!NOTE]
>
>Experience Manager Guides actualiza este informe en todos los eventos que producen un cambio en el archivo de asignación o cuando se actualiza cualquier referencia del archivo de tema.

Siga estos pasos para ver el informe de mapa DITA:

1. En la interfaz de usuario de Assets, desplácese hasta el fichero de mapa DITA para el que desee ver el informe y selecciónelo.

1. Seleccionar **Informes**.

   ![](images/reports-page-uuid-new.png){align="left"}

   La página Informes está dividida en dos partes:

   - **Resumen del tema:**

     Muestra el resumen general del fichero de mapa seleccionado. Al consultar el Resumen, puede conocer rápidamente la cantidad total de temas en el mapa, los temas que faltan, la cantidad de temas que tienen elementos que faltan, el estado de los temas: en estado Borrador, En revisión o Revisado.

   - **Detalles:**

     Al seleccionar un tema, se muestra un informe detallado del tema seleccionado.

     ![](images/detailed-report-uuid-new.png){align="left"}

     A continuación se describen los elementos resaltados bajo **A**, **B**, **C** y **D**:

      - **Tema**: título del tema especificado en el mapa DITA. Al pasar el puntero del mouse (ratón) sobre el título del tema, se muestra la ruta de acceso completa del tema. Si hay problemas en el tema, como referencias o imágenes que faltan, se muestra un punto rojo antes del título del tema.

      - **Nombre de archivo**: Nombre del archivo.

      - **UUID**: El identificador único universal \(UUID\) del archivo.

      - **Autor**: Usuario que trabajó por última vez en este tema.

      - **Estado del documento**: El estado actual del documento: Borrador, En revisión o Revisado.

      - **Elementos que faltan**: Enumera el número de imágenes que faltan o referencias cruzadas rotas, si las hay.

      - **Temas que faltan \(B\)**: Si hay temas con referencias rotas, esos temas se enumeran en la lista Temas que faltan.

      - **Abrir en Framemaker \(C\)**: Indica el número de imágenes que faltan o referencias cruzadas rotas, si las hay.

      - **Abrir en el editor \(D\)**: al seleccionar este icono, se abre el tema en el editor.


   A continuación se describen los elementos resaltados bajo **E**:

   - **Multimedia**: la ruta de las imágenes utilizadas en el tema se muestra junto con su UUID. Si selecciona la ruta de la imagen, la imagen correspondiente se abrirá en una ventana emergente. Los vínculos de imagen rotos aparecen en color rojo.

   - **Referencias de contenido**: la ruta del contenido al que se hace referencia en el tema se muestra junto con su UUID. Si selecciona el título del contenido al que se hace referencia, el tema correspondiente se abre en el modo de vista previa.

   - **Referencia cruzada**: la ruta del contenido de referencia cruzada se muestra junto con su UUID. Si selecciona el título del contenido al que se hace referencia, el tema correspondiente se abre en el modo de vista previa. Las referencias cruzadas rotas se muestran en color rojo.

   - **Revisar**: muestra el estado de la tarea de revisión del tema. Puede ver el estado \(abrir o cerrar\), la fecha de vencimiento y el usuario asignado del tema que se está revisando. Si selecciona el vínculo del tema, se abre el tema en modo de revisión.

   - **Utilizado en**: muestra una lista de otros temas o asignaciones en los que se usa el tema. También se enumera el UUID de todos estos temas y mapas.

Además del informe para cada tema individual, los administradores también tienen acceso a información como el historial de publicación de un mapa DITA. Para obtener más información sobre el historial de resultados generados, consulte [Ver el estado de la tarea de generación de resultados](generate-output-for-a-dita-map.md#viewing_output_history).

## Generar el informe CSV del mapa DITA

Se puede descargar y exportar el CSV de un informe de mapa DITA. El archivo CSV contiene el informe de mapa DITA detallado.

Siga estos pasos para generar el CSV de un informe de mapa DITA:

1. Seleccione **Generar informe** en la parte superior izquierda para generar el informe de asignación DITA.

   ![](images/generate-DITA-map-report-new.png){align="left"}

1. Recibirá una notificación una vez que el informe esté listo para descargarse. Seleccione **Descargar** para descargar el CSV del informe generado.

   ![](images/download-report-dialog-new.png){width="550" align="left"}


   También puede descargar el CSV del informe generado más adelante desde la bandeja de entrada de notificaciones de Experience Manager.

   Seleccione el informe generado en la bandeja de entrada para descargar el informe.

   ![](images/report-inbox--notification.png){width="300" align="left"}

Una vez descargado el informe en la bandeja de entrada, también puede seleccionarlo y utilizar el icono Abrir de la parte superior para abrir el informe seleccionado.

**Tema principal:**&#x200B;[&#x200B; Introducción a los informes](reports-intro.md)
