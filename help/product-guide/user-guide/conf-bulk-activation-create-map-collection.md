---
title: Creación de una colección de mapas de activación masiva
description: Obtenga información sobre cómo crear una colección de mapas de activación masiva en las guías de AEM.
exl-id: ea0bd465-a2d9-488f-83e9-62b336233eb1
feature: Publishing, Bulk Activation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---

# Creación de una colección de mapas de activación masiva {#id214GG0E90EV}

Para crear una recopilación de mapas de activación masiva, realice los siguientes pasos:

1. Seleccione el logotipo de Adobe Experience Manager en la parte superior y elija **Herramientas**.

1. En el panel **Herramientas**, seleccione **Guías**.

1. Seleccione el mosaico **Panel de publicación en lotes**.

   Se muestra el tablero Publicación masiva. También puede acceder a este tablero desde el panel izquierdo de [Adobe Experience Manager Guides Home page](intro-home-page.md).

   Por primera vez, se muestra una página de colecciones en blanco. Si ha creado colecciones de activación masiva anteriormente, estas se muestran en esta página.


1. Seleccione **Crear**.

1. Escriba un título para la colección de mapas de activación masiva y seleccione **Crear**.

   Se muestra un mensaje de éxito al crear la colección de mapas de activación masiva.

1. Seleccione **Abrir** en el mensaje de éxito.

1. Seleccione **Editar** y luego **Agregar asignaciones**.

1. Busque y agregue las asignaciones DITA que desee agregar a la colección de asignaciones de activación masiva.

   De forma predeterminada, todos los ajustes preestablecidos y configuraciones regionales asociados con el mapa se añaden automáticamente.

1. Seleccione la salida deseada activando o desactivando el botón deslizante.

   Puede elegir varios ajustes preestablecidos de salida en las configuraciones regionales disponibles.

1. Seleccione **Listo**.

Los ficheros de mapa DITA se añaden a la recopilación de mapas de activación masiva.

![ creó la colección de activación masiva](images/bulk-activation-collection-created.png){align="left"}

## Pestaña Mapas y ajustes preestablecidos

La pestaña **Mapas y ajustes preestablecidos** presenta información en las siguientes columnas:

- **Mapa**: muestra el título del archivo de mapa DITA.
- **Ruta de acceso al mapa**: muestra la ruta de acceso completa del archivo de mapa DITA.

- **UUID**: muestra el identificador único asociado con el archivo.

- **Idioma**: muestra el código de idioma del mapa DITA.
- **Ajuste preestablecido**: muestra el título del ajuste preestablecido de salida configurado en el archivo de asignación. También muestra el icono en función del tipo de ajuste preestablecido de salida.

  >[!NOTE]
  >
  > El icono pequeño ![](images/global-preset-icon.svg) indica un ajuste preestablecido de nivel de perfil de carpeta.

- **Modificado**: indica si el mapa DITA se ha actualizado después de la última publicación. En función de esta información, puede decidir si desea activar o no la salida para este mapa DITA.
- **Generado**: muestra la fecha y la hora del último resultado generado.
- **Publicado**: Muestra la fecha y la hora de la última salida publicada (o activada). Si selecciona el vínculo, se muestra la página **Resultados de la activación**, que contiene los registros con información sobre la ruta raíz en la que se activa el contenido.

## Pestaña Historial de auditoría

La ficha **Historial de auditoría** presenta información sobre los resultados de mapa activados en las siguientes columnas:
- **Mapa**: muestra el título del archivo de mapa DITA.
- **Ruta de acceso al mapa**: muestra la ruta de acceso completa del archivo de mapa DITA.
- **UUID** : Muestra el identificador único asociado con el archivo.
- **Idioma**: muestra el código de idioma del mapa DITA.
- **Ajuste preestablecido**: muestra el título del ajuste preestablecido de salida configurado en el archivo de asignación. También muestra el icono en función del tipo de ajuste preestablecido de salida.
- **Estado**: muestra el estado de activación como correcto o incorrecto.
- **Destino**: si genera la salida en Experience Manager Guides as a Cloud Service, puede ver el destino de la salida como Publicar o Vista previa.

  >[!NOTE]
  >
  > El icono pequeño ![](images/global-preset-icon.svg) indica un ajuste preestablecido de nivel de perfil de carpeta.

- **Modificado**: indica si el mapa DITA se actualizó después de la última publicación. En función de esta información, puede decidir si desea activar la salida para este mapa DITA.
- **Publicado**: Muestra la fecha y la hora de la última salida publicada (o activada). Si selecciona el vínculo, se muestra la página Resultados de la activación, que contiene los registros con información sobre la ruta raíz en la que se activa el contenido.
  ![ creó la pestaña del historial de auditoría de la colección de activación masiva](images/bulk-collection-audit-history.png){align="left"}

  *Vea la información acerca de los resultados del mapa activado en la ficha **Historial de auditoría**.*


  >[!NOTE]
  >
  > Los resultados de la ficha **Historial de auditoría** se ordenan según la columna **Publicado**.



## Panel izquierdo

Las siguientes opciones de filtrado están disponibles en el panel izquierdo:

- **Modificado**: Puede seleccionar Sí o No. Si selecciona Sí, sólo se mostrarán los mapas DITA modificados. Un mapa modificado es un mapa que se ha generado desde la última vez que se publicó.
- **Ajuste preestablecido**: seleccione un ajuste preestablecido para el que desee filtrar los archivos de asignación. Esta columna muestra el título del ajuste preestablecido de salida configurado en el archivo de asignación. Por ejemplo, si elige el ajuste preestablecido *AEM Site*, solo se mostrarán los mapas que tengan configurado el ajuste preestablecido de salida *AEM Site*.
- **Idioma**: puede seleccionar cualquiera de los códigos de idioma disponibles y mostrar solo el idioma seleccionado en la pestaña Mapas y ajustes preestablecidos.

Los filtros se actualizan cuando cambia de la ficha **Mapas y ajustes preestablecidos** a la ficha **Historial de auditoría** y viceversa.

**Tema principal: &#x200B;** [Activación masiva del contenido publicado](conf-bulk-activation.md)
