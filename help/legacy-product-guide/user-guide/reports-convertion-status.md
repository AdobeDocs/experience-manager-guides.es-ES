---
title: Informe de estado de conversión
description: Convierta documentos de diferentes formatos en DITA en AEM Guides. Obtenga información sobre cómo añadir filtros y ver un informe de estado de conversión.
feature: Report Generation
role: User
hide: true
exl-id: f6bf1033-9c2f-42c7-9ad5-e1060e2c9770
TQID: https://experienceleague.adobe.com/TBeg61eVmHydID-z3dGoQcHJtAY0EzwhuJD9SHpuhwI
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: cdab8659-8d50-4417-b6fd-762f347c13ee
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 318
ht-degree: 0%

---

# Informe de estado de conversión {#id205BBA00WZZ}

AEM Guides proporciona una función de conversión sólida para convertir documentos de diversos formatos a DITA. El informe de estado de conversión proporciona una vista consolidada de todas las tareas de conversión ejecutadas por AEM Guides.

Siga estos pasos para ver el informe de estado de conversión:

1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.

1. Seleccione **Guías** de la lista de herramientas.

1. Haga clic en el mosaico **Informe de estado de conversión**.

   El informe de estado de conversión se muestra para todas las tareas de conversión ejecutadas en el sistema.

   ![](images/conversion-status-report.png){width="800"}

1. La página del informe se divide en dos partes:

   - **Filtro:**

     Puede filtrar los datos del informe en función del Tipo de archivo y el Estado de conversión. En Tipo de archivo, puede elegir ver los datos del informe de los documentos de Word, HTML estructurado, XML y DocBook. En Estado, puede elegir ver los datos del informe de las tareas que se han ejecutado correctamente, con error, activas o en cola.

     La siguiente captura de pantalla muestra los datos del informe de las tareas de conversión que tienen los estados Error, Activo y En cola.

     ![](images/conversion-report-failed-active-queued.png){width="800"}

   - **Datos del informe:**

     Los datos del informe contienen las columnas siguientes:

      - **Nombre de archivo**: Nombre del archivo de origen en el que se ejecutó el proceso de conversión. Al hacer clic en el vínculo Nombre de archivo, se le redirige a la ubicación del documento de origen.

      - **Tipo de archivo**: tipo de documento de origen, que puede ser Word, HTML estructurado, XML y DocBook.

      - **Agregado por**: nombre del usuario que ejecutó la tarea de conversión.

      - **Fecha de incorporación**: Fecha en la que se ejecutó la tarea. Al hacer clic en el vínculo Fecha de incorporación, se descarga el archivo de registro.

      - **Ruta**: Ruta de acceso completa del documento de origen.

      - **Estado**: estado de las tareas de conversión: correcto, fallido, activo o en cola.

      - **Salida**: ruta del documento convertido correctamente. Al hacer clic en el vínculo Output, se le lleva a la ubicación en la que se guarda la salida.


**Tema principal:**&#x200B;[&#x200B; Informes](reports-intro.md)
