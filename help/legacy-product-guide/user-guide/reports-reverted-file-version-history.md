---
title: Informe de historial de versiones de archivos revertidos
description: Ver los informes del historial de versiones de los archivos revertidos en AEM Guides. Obtenga información sobre cómo acceder a los registros de versiones anteriores desde la interfaz de usuario de Assets, la vista previa de temas y la selección de herramientas de AEM.
feature: Report Generation
role: User
hide: true
exl-id: c787947a-b235-4c12-a9cc-eac5136d31db
source-git-commit: e5d02c6047c3ed74efa1777ce6585efc391af426
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# Informe de historial de versiones de archivos revertidos {#id205BBC00PRK}

Cuando se trabaja en varias versiones simultáneas junto con varios autores, el contenido está destinado a tener varias versiones. Podría haber información común en varias versiones que distintos autores podrían utilizar en su proyecto. Para gestionar estas asignaciones de trabajo, los autores podrían terminar con varias versiones de los archivos. Estas versiones podrían ser simplemente una versión más reciente de un archivo o una versión anterior. Identificar cuándo se revirtió un archivo y por qué es una tarea compleja.

AEM Guides permite generar un informe del historial de versiones para un archivo individual o para todos los archivos de una carpeta. Este historial de versiones le proporciona una vista consolidada de todas las versiones de un archivo que se revirtieron y quién creó esas versiones y el motivo para crearlas.

Puede acceder a este informe desde los siguientes lugares:

- **IU de Assets**: seleccionando un archivo y abriendo **Historial de versiones** desde el carril izquierdo. La vista **Historial de versiones** contiene el vínculo **Revertir registros de versiones** en la parte inferior del panel. Al hacer clic en este vínculo, se muestra el historial de versiones revertidas del archivo seleccionado.

  ![](images/revert-log-from-assets-ui.png){width="300" align="left"}

- **Vista previa del tema**: al obtener una vista previa de un tema, también puede mostrar el panel **Historial de versiones** desde el carril izquierdo. Obtendrá un panel similar a la interfaz de usuario de Assets desde donde puede hacer clic en el vínculo **Revertir registros de versión** para acceder al historial de versiones revertidas del documento activo.

- **Sección de herramientas de AEM**: también puede obtener acceso a este informe desde la sección de herramientas de AEM. El siguiente procedimiento explica cómo puede acceder al historial de versiones de reversión desde la sección Herramientas de AEM.


Siga estos pasos para acceder al informe Revertir historial:

1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.

1. Seleccione **Guías** de la lista de herramientas.

1. Haga clic en el mosaico **Historial de reversión de versión**.

   Se muestra una página Revertir historial de versiones en blanco en la que debe buscar y seleccionar un archivo o carpeta para generar el informe.

1. Haga clic en **Mostrar registros** para generar el informe del archivo o la carpeta seleccionados.

   ![](images/revert-version-history-report.png){width="800" align="left"}

   El informe contiene los siguientes detalles:

   - **Nombre de archivo**: El título del tema. Al hacer clic en el vínculo del título del tema, se abre la vista previa del tema.

   - **Marca de tiempo**: La fecha y hora en que se revirtió el tema a una versión anterior.

   - **Usuario**: Nombre del usuario que revirtió a una versión anterior.

   - **Revertir de**: El número de versión original del archivo desde el que se revirtió.

   - **Revertir a**: La versión a la que se revirtió el archivo.

   - **Comentario**: Cualquier comentario dado por el usuario que revirtió el archivo.

{{test}}

**Tema principal:**[ Informes](reports-intro.md)
