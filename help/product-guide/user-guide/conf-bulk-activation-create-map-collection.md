---
title: Creación de una colección de mapas de activación masiva
description: AEM Obtenga información sobre cómo crear una colección de mapas de activación masiva en las guías de.
exl-id: ea0bd465-a2d9-488f-83e9-62b336233eb1
feature: Publishing, Bulk Activation
role: User
source-git-commit: 1be8cddcbf58696a53bfccf887a04e5807f2198e
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 0%

---

# Creación de una colección de mapas de activación masiva {#id214GG0E90EV}

Para crear una recopilación de mapas de activación masiva, realice los siguientes pasos:

1. Seleccionar **Guías** de la lista de herramientas.

1. Seleccione el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.

1. Seleccione el **Tablero de publicación masiva** mosaico.

   Por primera vez, se muestra una página de colecciones en blanco. Si ha creado colecciones de activación masiva anteriormente, estas se muestran en esta página.

1. Haga clic en **Crear**.

1. Escriba un título para la colección de mapas de activación masiva y haga clic en **Crear**.

   Se muestra un mensaje de éxito al crear la colección de mapas de activación masiva.

1. Clic **Abrir** en el mensaje de éxito.

1. Seleccionar **Editar** y luego seleccione **Agregar asignaciones**.

1. Busque y agregue las asignaciones DITA que desee agregar a la colección de asignaciones de activación masiva.

   De forma predeterminada, todos los ajustes preestablecidos y configuraciones regionales asociados con el mapa se añaden automáticamente.

1. Seleccione la salida deseada activando o desactivando el botón deslizante.

   Puede elegir varios ajustes preestablecidos de salida en las configuraciones regionales disponibles.

1. Haga clic en **Listo**.

Los ficheros de mapa DITA se añaden a la recopilación de mapas de activación masiva.

![ colección de activación masiva creada](images/bulk-activation-collection-created.png){width="800" align="left"}

## Pestaña Mapas y ajustes preestablecidos

El **Mapas y ajustes preestablecidos** presenta información en las columnas siguientes:

- **Mapa**: muestra el título del fichero de mapa DITA.
- **Ruta de mapa**: muestra la ruta completa del fichero de mapa DITA.

- **UUID**: Muestra el identificador único asociado al archivo.

- **Idioma**: muestra el código de idioma del mapa DITA.
- **Preestablecido**: Muestra el título del ajuste preestablecido de salida configurado en el archivo de asignación. También muestra el icono en función del tipo de ajuste preestablecido de salida.

  >[!NOTE]
  >
  > La pequeña ![](images/global-preset-icon.svg) El icono indica un ajuste preestablecido de nivel de perfil de carpeta.

- **Modificado**: indica si el mapa DITA se actualiza después de la última publicación. En función de esta información, puede decidir si desea activar o no la salida para este mapa DITA.
- **Generado**: Muestra la fecha y la hora de la última salida generada.
- **Publicado**: Muestra la fecha y la hora de la última salida publicada (o activada). Si selecciona el vínculo, la variable **Resultados de activación** , que contiene los registros con información sobre la ruta raíz en la que se activa el contenido.

## Pestaña Historial de auditoría

El **Historial de auditoría** presenta información sobre las salidas de mapa activadas en las siguientes columnas:
- **Mapa**: muestra el título del fichero de mapa DITA.
- **Ruta de mapa**: muestra la ruta completa del fichero de mapa DITA.
- **UUID** : Muestra el identificador único asociado al archivo.
- **Idioma**: muestra el código de idioma del mapa DITA.
- **Preestablecido**: Muestra el título del ajuste preestablecido de salida configurado en el archivo de asignación. También muestra el icono en función del tipo de ajuste preestablecido de salida.
- **Estado**: muestra el estado de la activación como correcta o incorrecta.
- **Destino**: si genera la salida en Guías del Experience Manager as a Cloud Service, puede ver el destino de la salida como Publicar o Vista previa.

  >[!NOTE]
  >
  > La pequeña ![](images/global-preset-icon.svg) El icono indica un ajuste preestablecido de nivel de perfil de carpeta.

- **Modificado**: indica si el mapa DITA se actualizó después de la última publicación. En función de esta información, puede decidir si desea activar la salida para este mapa DITA.
- **Publicado**: Muestra la fecha y la hora de la última salida publicada (o activada). Si selecciona el vínculo, se muestra la página Resultados de la activación, que contiene los registros con información sobre la ruta raíz en la que se activa el contenido.
  ![ ficha historial de auditoría de recopilación de activación masiva creada](images/bulk-collection-audit-history.png){width="800" align="left"}

  *Vea la información sobre las salidas de mapa activadas en la **Historial de auditoría**pestaña.*


  >[!NOTE]
  >
  > Los resultados en la **Historial de auditoría** Las pestañas se ordenan según el **Publicado** columna.



## Panel izquierdo

Las siguientes opciones de filtrado están disponibles en el panel izquierdo:

- **Modificado**: puede seleccionar Sí o No. Si selecciona Sí, sólo se mostrarán los mapas DITA modificados. Un mapa modificado es un mapa que se ha generado desde la última vez que se publicó.
- **Preestablecido**: seleccione un ajuste preestablecido para el que desee filtrar los archivos de asignación. Esta columna muestra el título del ajuste preestablecido de salida configurado en el archivo de asignación. Por ejemplo, si elige *AEM Sitio web de* preestablecido, solo se muestran las asignaciones que tienen el *AEM Sitio web de* Ajuste preestablecido de salida configurado en ellos.
- **Idioma**: Puede seleccionar cualquiera de los códigos de idioma disponibles y mostrar solo el idioma seleccionado en la pestaña Mapas y ajustes preestablecidos.

Los filtros se actualizan cuando se cambia del **Mapas y ajustes preestablecidos** a la pestaña **Historial de auditoría** y viceversa.

**Tema principal: **[Activación masiva de contenido publicado](conf-bulk-activation.md)
