---
title: Pasar los metadatos a la salida utilizando DITA-OT
description: AEM Obtenga información sobre cómo pasar los metadatos a la salida mediante la publicación DITA-OT en las guías del usuario de la aplicación de la publicación en las guías de usuario de la aplicación.
exl-id: 70ca32dc-56c3-45ee-b6b9-0efb8cc79ea1
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# Pasar los metadatos a la salida utilizando DITA-OT {#id21BJ00QD0XA}

Los metadatos son información adicional sobre el resultado. AEM En las guías de la, puede pasar los metadatos existentes o crear etiquetas de metadatos personalizadas. AEM Se pueden transferir metadatos a salidas de formato personalizado, PDF, HTML 5, EPUB y mediante la publicación DITA-OT.

Realice los siguientes pasos para pasar los metadatos a la salida mediante la publicación DITA-OT:

1. En el **IU de Assets**, desplácese hasta el fichero de mapa DITA para el que desea pasar los metadatos al DITA-OT y haga clic en él.
1. Seleccione y edite un ajuste preestablecido de salida al que desee pasar los campos de metadatos. Por ejemplo, seleccione Ajuste preestablecido de salida del PDF.
1. Seleccionar **DITA-OT** en Generar &lt;output> Utilizando en el ajuste preestablecido de salida seleccionado.

   ![](images/custom-meta-data-output-preset.png){width="800" align="left"}

1. En la lista desplegable Propiedades, seleccione los metadatos que desee pasar a la publicación DITA-OT.

   La lista desplegable Propiedades enumera las propiedades personalizadas y las predeterminadas. Por ejemplo, en la captura de pantalla anterior, el autor es la propiedad personalizada mientras que `dc:description`, `dc:language`, `dc:title`, y `docstate` son las propiedades predeterminadas.

   >[!NOTE]
   >
   > Estas propiedades se seleccionan del archivo metadataList disponible en la siguiente ubicación:`/libs/fmdita/config/metadataList`. De forma predeterminada, hay cuatro propiedades enumeradas en este archivo: `dc:description`, `dc:language`, `dc:title`, y `docstate`.

   Este archivo se puede superponer en: `/apps/fmdita/config/metadataList`.

   Para pasar una propiedad personalizada para la que ya ha definido los valores, consulte [AEM Uso de metadatos en la salida del PDF DITA-OT](https://experienceleaguecommunities.adobe.com/t5/xml-documentation-discussions/use-aem-metadata-in-dita-ot-pdf-output/td-p/411880).

1. Desde el **Propiedades** , seleccione las propiedades personalizadas y predeterminadas necesarias. Por ejemplo, seleccione `author`, `dc:title`, y `dc:description`. Estos son los estándares `metadata/properties` que se crea una vez que creamos un archivo. Las propiedades seleccionadas se muestran debajo de la lista desplegable.

   ![](images/selected-metadata-properties.png){width="300" align="left"}

1. Clic **Listo** en la parte superior izquierda para guardar los cambios.
1. Genere la salida.

Las propiedades de metadatos seleccionadas se pasarán a la salida generada mediante DITA-OT.

**Tema principal:**[ Generación de salida](generate-output.md)
