---
title: Informe de reutilización de contenido
description: Obtenga información sobre cómo ver el informe de reutilización de contenido en AEM Guides. Genere el informe para buscar el porcentaje de reutilización de contenido.
exl-id: ccae4303-75b1-4077-829a-7ef6a14fd8ad
feature: Report Generation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# Informe de reutilización de contenido {#id205BB900OQD}

Otro informe útil que puede generar es el Informe de reutilización de contenido. Este informe calcula el porcentaje de uso de contenido promedio, lo que resulta muy útil para que los jefes de proyecto y los propietarios de empresa vean la cantidad de contenido que se está reutilizando.

>[!TIP]
>
> Para garantizar el correcto funcionamiento del informe de reutilización de contenido, debe habilitar el flujo de trabajo de posprocesamiento. Póngase en contacto con el administrador del sistema para habilitar flujos de trabajo posteriores al procesamiento.

Siga estos pasos para ver el informe de reutilización de contenido:

1. Seleccione el logotipo de Adobe Experience Manager en la parte superior y elija **Herramientas**.

1. Seleccione **Guías** de la lista de herramientas.

1. Seleccione el mosaico **Informe de reutilización de contenido**.

1. Seleccione **Examinar** para elegir una ruta de acceso donde residan los temas o ingrese la ruta manualmente.

   El informe se genera analizando el contenido de las carpetas principal y todas las secundarias.

1. Seleccione **Generar informe** para obtener el informe de reutilización de contenido.

   ![](images/content-reuse-uuid.png){align="left"}

   La página del informe se divide en dos partes:

   - **Resumen del informe:**

     Muestra la reutilización media del contenido, que se calcula como instancias de reutilización de contenido/recuento total de temas. Este informe tiene en cuenta todas las referencias de contenido directo de primer nivel y las referencias de temas para el cálculo. Las instancias de reutilización de contenido se calculan como la suma total de los valores del campo Número de veces reutilizado. El tema que se reutiliza más ampliamente también se enumera en el Resumen del informe. Al seleccionar el vínculo del tema en el tema más reutilizado, se abre la vista previa del tema.

   - **Detalles:**

     La sección Detalles contiene las siguientes columnas:

      - **Título**: título del tema. Al seleccionar el vínculo del título del tema, se abre la vista previa del tema.

      - **UUID**: El identificador único universal \(UUID\) del archivo.

      - **Tamaño**: tamaño de los archivos en bytes.

      - **Estado**: el estado actual del documento: Borrador, En revisión o Revisado.

      - **Número de veces que se reutilizó**: Número de veces que se reutilizó el tema correspondiente. Esto se calcula como la suma total de las entradas de las columnas Referenciado por menos 1.

      - **Referido por**: Temas en los que se ha hecho referencia al tema correspondiente. Aquí, solo se tienen en cuenta las referencias directas \(primer nivel\). Los temas múltiples se separan con comas. El UUID del archivo al que se hace referencia también se menciona entre corchetes. Al seleccionar en el vínculo del título del tema, se abre la vista previa del tema.


>[!NOTE]
>
> También puede exportar el informe de reutilización de contenido en formato CSV. Para ello, seleccione Exportar a CSV en la esquina superior izquierda de la pantalla y elija una ubicación para guardar el archivo CSV. A continuación, puede abrir este archivo CSV en cualquier editor CSV.

**Tema principal:**&#x200B;[ Introducción a los informes](reports-intro.md)
