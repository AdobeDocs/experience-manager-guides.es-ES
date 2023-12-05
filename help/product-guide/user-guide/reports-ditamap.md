---
title: Informe de mapa DITA del tablero de mapas
description: AEM Genere informes de mapas DITA desde el tablero de mapas en las Guías de. Obtenga información sobre cómo generar el CSV de un informe de mapa DITA.
exl-id: 7fe52ee0-e940-467b-9b8d-3d2371de7a84
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 0%

---

# Informe de mapa DITA del tablero de mapas {#id205BB800EEN}

AEM Guías de informes proporciona a los administradores las funciones de creación de informes para comprobar la integridad general de la documentación antes de que se publique o se ponga a disposición de los usuarios finales. AEM El informe de mapa DITA del tablero de mapas de las guías de la aplicación proporciona información valiosa, como los temas que faltan, los temas con elementos que faltan, el UUID de los temas a los que se hace referencia y los archivos multimedia, así como el estado de revisión de cada tema. Un informe detallado a nivel de tema individual también proporciona información relacionada con el contenido DITA, como referencias de contenido e imágenes que faltan o referencias cruzadas.

>[!NOTE]
>
> AEM Guías actualiza este informe en cada evento que produce un cambio en el archivo de asignación o cuando se actualiza cualquier referencia dentro del archivo de tema.

Siga estos pasos para ver el informe de mapa DITA:

1. En la interfaz de usuario de Assets, vaya al archivo de mapa DITA para el que desea ver el informe y haga clic en él.

1. Clic **Informes**.

   ![](images/reports-page-uuid.png){width="800" align="left"}

   La página Informes está dividida en dos partes:

   - **Resumen del tema:**

     Muestra el resumen general del fichero de mapa seleccionado. Al consultar el Resumen, puede conocer rápidamente la cantidad total de temas en el mapa, los temas que faltan, la cantidad de temas que tienen elementos que faltan, el estado de los temas: en estado Borrador, En revisión o Revisado.

   - **Detalles:**

     Al hacer clic en un tema, se muestra un informe detallado del tema seleccionado.

     ![](images/detailed-report-uuid.png){width="800" align="left"}

     Elementos resaltados bajo **A**, **B**, **C** y **D** se describen a continuación:

      - **Tema**: título del tema especificado en el mapa DITA. Al pasar el puntero del mouse (ratón) sobre el título del tema, se muestra la ruta de acceso completa del tema. Si hay problemas en el tema, como referencias o imágenes que faltan, se muestra un punto rojo antes del título del tema.

      - **Nombre de archivo**: Nombre del archivo.

      - **UUID**: el identificador único universal \(UUID\) del archivo.

      - **Autor**: usuario que trabajó por última vez en este tema.

      - **Estado del documento**: el estado actual del documento (borrador, en revisión o revisado).

      - **Faltan temas \(B\)**: si hay temas con referencias rotas, esos temas se enumeran en la lista Temas que faltan.

      - **Elementos faltantes**: Indica el número de imágenes que faltan o referencias cruzadas rotas, si las hay.

      - **Abrir en el editor \(D\)**: Al hacer clic en este icono, se abre el tema en el Editor web.


   Elementos resaltados bajo **E** se describen a continuación:

   - **Multimedia**: la ruta de las imágenes utilizadas en el tema se muestra junto con su UUID. Si hace clic en la ruta de la imagen, la imagen correspondiente se abre en una ventana emergente. Los vínculos de imagen rotos aparecen en color rojo.

   - **Referencias de contenido**: la ruta del contenido al que se hace referencia en el tema se muestra junto con su UUID. Si hace clic en el título del contenido referido, el tema correspondiente se abre en el modo de previsualización.

   - **Referencia cruzada**: la ruta del contenido al que se hace referencia junto con su UUID. Si hace clic en el título del contenido referido, el tema correspondiente se abre en el modo de previsualización. Las referencias cruzadas rotas se muestran en color rojo.

   - **Revisar**: Muestra el estado de la tarea de revisión del tema. Puede ver el estado \(abrir o cerrar\), la fecha de vencimiento y el usuario asignado del tema que se está revisando. Si hace clic en el vínculo del tema, se abre el tema en modo de revisión.

   - **Utilizado en**: Muestra una lista de otros temas o mapas en los que se utiliza el tema. También se enumera el UUID de todos estos temas y mapas.

Además del informe para cada tema individual, los administradores también tienen acceso a información como el historial de publicación de un mapa DITA. Para obtener más información sobre el historial de salidas generadas, consulte [Ver el estado de la tarea de generación de resultados](generate-output-for-a-dita-map.md#viewing_output_history).

## Generar el informe CSV del mapa DITA

Se puede descargar y exportar el CSV de un informe de mapa DITA. El archivo CSV contiene el informe de mapa DITA detallado.

Siga estos pasos para generar el CSV de un informe de mapa DITA:

1. Clic **Generar informe** en la parte superior izquierda para generar el informe de mapa DITA.

   ![](images/generate-DITA-map-report.png){width="800" align="left"}

1. Recibirá una notificación una vez que el informe esté listo para descargarse. Clic **Descargar** para descargar el CSV del informe generado.

   ![](images/download-report-dialog.png){width="550" align="left"}


   AEM También puede descargar el CSV del informe generado más adelante desde la bandeja de entrada de notificaciones de la.

   Haga clic en el informe generado en la bandeja de entrada para descargar el informe.

   ![](images/report-inbox--notification.png){width="300" align="left"}

Una vez descargado el informe en la bandeja de entrada, también puede seleccionarlo y utilizar el icono Abrir de la parte superior para abrir el informe seleccionado.

**Tema principal:**[ Informes](reports-intro.md)
