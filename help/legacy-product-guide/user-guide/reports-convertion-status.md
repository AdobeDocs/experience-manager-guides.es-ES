---
title: Informe de estado de conversión
description: Convierta documentos de diferentes formatos en DITA en AEM Guides. Obtenga información sobre cómo añadir filtros y ver un informe de estado de conversión.
feature: Report Generation
role: User
hide: true
exl-id: f6bf1033-9c2f-42c7-9ad5-e1060e2c9770
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# Informe de estado de conversión {#id205BBA00WZZ}

AEM Guides proporciona una función de conversión sólida para convertir documentos de diversos formatos a DITA. El informe de estado de conversión proporciona una vista consolidada de todas las tareas de conversión ejecutadas por AEM Guides.

Siga estos pasos para ver el informe de estado de conversión:

1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.

1. Seleccione **Guías** de la lista de herramientas.

1. Haga clic en el mosaico **Informe de estado de conversión**.

   El informe de estado de conversión se muestra para todas las tareas de conversión ejecutadas en el sistema.

   ![](images/conversion-status-report.png){width="800" align="left"}

1. La página del informe se divide en dos partes:

   - **Filtro:**

     Puede filtrar los datos del informe en función del Tipo de archivo y el Estado de conversión. En Tipo de archivo, puede elegir ver los datos del informe de los documentos de Word, HTML estructurado, XML y DocBook. En Estado, puede elegir ver los datos del informe de las tareas que se han ejecutado correctamente, con error, activas o en cola.

     La siguiente captura de pantalla muestra los datos del informe de las tareas de conversión que tienen los estados Error, Activo y En cola.

     ![](images/conversion-report-failed-active-queued.png){width="800" align="left"}

   - **Datos del informe:**

     Los datos del informe contienen las columnas siguientes:

      - **Nombre de archivo**: Nombre del archivo de origen en el que se ejecutó el proceso de conversión. Al hacer clic en el vínculo Nombre de archivo, se le redirige a la ubicación del documento de origen.

      - **Tipo de archivo**: tipo de documento de origen, que puede ser Word, HTML estructurado, XML y DocBook.

      - **Agregado por**: nombre del usuario que ejecutó la tarea de conversión.

      - **Fecha de incorporación**: Fecha en la que se ejecutó la tarea. Al hacer clic en el vínculo Fecha de incorporación, se descarga el archivo de registro.

      - **Ruta**: Ruta de acceso completa del documento de origen.

      - **Estado**: estado de las tareas de conversión: correcto, fallido, activo o en cola.

      - **Salida**: ruta del documento convertido correctamente. Al hacer clic en el vínculo Output, se le lleva a la ubicación en la que se guarda la salida.


**Tema principal:**&#x200B;[ Informes](reports-intro.md)
