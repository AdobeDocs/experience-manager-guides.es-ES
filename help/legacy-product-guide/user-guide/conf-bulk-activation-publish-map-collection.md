---
title: Activar salida
description: Activar la salida de mapas DITA en AEM Guides. Obtenga información sobre cómo activar el contenido en la instancia de publicación.
feature: Publishing, Bulk Activation
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 1%

---

# Activar salida {#id214GGF00V5U}

Una vez creada una colección de mapas para la activación masiva, el siguiente paso es activar el contenido en la instancia de publicación. Para activar el contenido, realice los siguientes pasos:

1. Seleccione **Guías** de la lista de herramientas.

1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.

1. Haga clic en el mosaico **Tablero de Publish en lotes**.

   Se muestra una lista de colecciones de mapas de activación masiva.

1. Seleccione la colección que desea publicar y haga clic en **Abrir**.

   ![](images/bulk-activation-collection-open.png){width="800" align="left"}

1. \(*Opcional*\) Aplique los filtros necesarios del carril izquierdo para filtrar el mapa en función de su \(estado\), ajuste preestablecido de salida o idioma modificado.

   >[!NOTE]
   >
   >Genere la salida para el mapa utilizando el ajuste preestablecido de salida antes de activarlos en la colección de mapas.


Vea las diferentes formas de activar la colección en función de su configuración.

<details>
<summary> Cloud Services </summary>

![publicación-colección-masiva en el servicio en la nube](images/bulk-activation-collection-quick-publish-CS.png){width="650" align="left"}

Puede activar el resultado en las instancias **Preview** o **Publish**.

**Previsualizar**

* Para activar la salida de los mapas seleccionados, seleccione la salida de mapa pregenerada y seleccione **Publish to** > **Preview**.
* Para activar la salida de todas las asignaciones DITA con sus ajustes preestablecidos configurados, seleccione la casilla de verificación situada junto a la columna **Map** y, a continuación, seleccione **Publish to** > **Publish**.


**Publish**

* Para activar la salida de los mapas seleccionados, seleccione la salida de mapa pregenerada y seleccione **Publish to** > **Publish**.

* Para activar la salida de todas las asignaciones DITA con sus ajustes preestablecidos configurados, seleccione la casilla de verificación situada junto al mapa (columna) y, a continuación, seleccione **Publish to** > **Publish**.


>[!NOTE]
> 
> La casilla de verificación para una salida de mapa solo está activada si se ha generado la salida para un mapa.

Se muestra un mensaje de éxito cuando el resultado del mapa está en la cola para su publicación.

Una vez que se activa la salida para los archivos de mapa seleccionados, se actualiza la pestaña Historial de auditoría y aparece la última salida activada en la parte superior. La columna **Publicado** se ha actualizado con la fecha y la hora de publicación.

</details>

<details>    
<summary>  Software On-Premise </summary>


Realice una de las siguientes acciones:

* Para activar la salida de los mapas seleccionados, seleccione la salida de mapa pregenerada y seleccione **Quick Publish**.
* Para activar la salida de todos los mapas DITA con sus ajustes preestablecidos configurados, active la casilla de verificación situada junto al mapa (columna) y, a continuación, seleccione **Quick Publish.**
  ![publicación-colección-en-lotes](images/bulk-activation-collection-quick-publish.png){width="650" align="left"}

  >[!NOTE]
  > 
  >La casilla de verificación para una salida de mapa solo está activada si se ha generado la salida para un mapa.


Se muestra un mensaje de éxito cuando el resultado del mapa está en la cola para su publicación.

Una vez que se activa la salida para los archivos de mapa seleccionados, se actualiza la pestaña Historial de auditoría y aparece la última salida activada en la parte superior. La columna **Publicado** se ha actualizado con la fecha y la hora de publicación.

**Tema principal: **[Activación masiva del contenido publicado](conf-bulk-activation.md)
