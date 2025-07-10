---
title: Generación incremental de resultados
description: Descubra cómo funciona la generación de resultados incrementales para AEM Sites en AEM Guides.
exl-id: 019d9fbf-2f23-4669-8022-d693be75c1c3
feature: Publishing
role: User
source-git-commit: 05d3246bd8b1e1b1d870b494aa09f6acff8a0f1d
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 0%

---


# Generación incremental de resultados

>[!NOTE]
>
> La generación de resultados incrementales solo es aplicable a la salida de AEM Sites. Además, sólo se pueden regenerar temas DITA \(.dita/.xml\) desde un mapa o submapas DITA. Si selecciona un mapa DITA, submapa, grupo de temas o un tema con `@processing-role="resource-only"`, la opción de regeneración no estará disponible.

Podría haber varias instancias en las que se actualizaran sólo unos pocos temas del mapa DITA y sólo se insertaran en directo esos temas actualizados. Para gestionar estos escenarios, Experience Manager Guides le permite crear salidas incrementales. Si se han actualizado algunos temas, no es necesario volver a generar todo el mapa DITA. Solo puede seleccionar los temas actualizados y volver a generarlos.

Si el mapa está fragmentado y ha actualizado un solo tema en ese mapa, debe volver a generar todo el mapa para que el tema o el contenido actualizado se refleje en la salida. No obtendrá la opción de regeneración de salida en un nivel de tema, solo está disponible en el nivel de asignación \(fragmentado\). Esto se aplica al mapa principal y a todos los submapas.

Realice los siguientes pasos para volver a generar los resultados de un tema específico o un grupo de temas:

## Generar resultados incrementales desde la consola de mapas (para sitios de AEM que utilizan la asignación de componentes compuestos)

Siga estos pasos para generar resultados incrementales para AEM Sites mediante la consola Mapa:

1. [Abra el archivo de mapa DITA en la consola de mapas](./open-files-map-console.md).
1. Seleccione el ajuste preestablecido de AEM Sites para el que desea generar una salida incremental.
1. En la ficha **Temas**, seleccione los temas que desee publicar.

   - Sin línea base

     ![lista de temas de aem sites](images/aem-presets-topic-list.png) {align="left"}

   - Con línea base

     ![lista de temas de aem sites con línea de base](images/aem-presets-topic-list-new.png) {align="left"}

   >[!NOTE]
   >
   > Cuando se selecciona una Línea de base en la ficha **Contenido**, la lista Tema muestra los temas y sus versiones de la Línea de base adjunta.<br><br>
   > La publicación incremental de la lista Temas debe utilizarse únicamente cuando no haya cambios en la estructura del mapa. Si se produce un cambio en la estructura del mapa/índice, todo el mapa debe publicarse una vez para actualizar el índice.

1. Seleccione **Guardar** para guardar los cambios.
1. Seleccione **Generar salida** para generar la salida.


## Generar resultados incrementales desde el panel de mapas (para sitios de AEM que utilizan la asignación de componentes heredados)

Siga estos pasos para generar una salida incremental para AEM Sites mediante el panel de asignaciones:

1. En la interfaz de usuario de Assets, desplácese hasta el fichero de mapa DITA y selecciónelo.

   Aparecerá la consola de mapas DITA con la lista de Ajustes preestablecidos de salida disponibles para generar la salida.

1. Seleccione la ficha **Temas**.

   Se mostrará una lista de los temas disponibles en el mapa DITA.

1. Seleccione los temas que desee volver a generar.

   >[!NOTE]
   >
   > Si ha añadido nuevos temas al mapa DITA, no podrá generar esos nuevos temas desde aquí. En primer lugar, debe publicar los temas recién añadidos mediante la función de publicación de mapa DITA.

   ![](images/regenerate-topics.png){align="left"}

1. Seleccione **Regenerar**.

   Aparecerá la página **Regenerar temas seleccionados**.

1. Seleccione el ajuste preestablecido de salida que desee utilizar para regenerar los temas seleccionados.

   Para el ajuste preestablecido de salida de AEM Sites que utiliza la asignación de componentes heredados, si se selecciona una línea de base, las versiones de tema incluidas en la línea de base seleccionada se utilizan para la generación de resultados. Además, la publicación incremental de la lista Temas debe utilizarse únicamente cuando no haya cambios en la estructura del mapa. Si se produce un cambio en la estructura del mapa/índice, todo el mapa debe publicarse una vez para actualizar el índice. Para obtener más información sobre cómo usar los ajustes preestablecidos del sitio de AEM, vea [Ajustes preestablecidos de AEM Sites en el tablero de mapas](./generate-output-aem-site-map-dashboard.md).


1. Seleccione **Regenerar** para iniciar el proceso de generación de resultados.


>[!IMPORTANT]
>
> Si se cambia el nombre de un título de tema y se vuelve a generar el tema, el título actualizado no se refleja en la tabla de contenido del mapa DITA. Para actualizar el título del tema en el índice, se debe generar todo el mapa DITA.

Puede ver el estado actual de la solicitud de generación de resultados en la ficha **Salidas**. Para obtener más información, vea [Ver el estado de la tarea de generación de resultados](#view-the-status-of-the-output-generation-task).



**Tema principal:** [Explicación de los ajustes preestablecidos de salida](generate-output-understand-presets.md)
