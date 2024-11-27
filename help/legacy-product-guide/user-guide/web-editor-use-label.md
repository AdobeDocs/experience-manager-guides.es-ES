---
title: Uso de etiquetas
description: Descubra el uso de etiquetas para diferentes versiones de un archivo en AEM Guides. Obtenga información sobre cómo agregar o eliminar una etiqueta a una versión de un tema.
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---

# Uso de etiquetas {#id164JBG0M0T1}

AEM Guides permite agregar etiquetas a diferentes versiones de un archivo. Puede utilizar estas etiquetas para especificar la versión que desea incluir en una línea de base para la publicación. Para obtener más información acerca del uso de etiquetas para crear una línea de base, vea [Trabajar con línea de base](generate-output-use-baseline-for-publishing.md#).

Por ejemplo, si desea utilizar la *versión 1.0* de un tema en la *versión 1.0* y la *versión 1.1* del mismo tema en la *versión 2.0*, puede agregar la etiqueta *versión 1.0* en la etiqueta *versión 1.0* y *versión 2.0* en la *versión 1.1*.

Una vez agregadas las etiquetas, puede crear una línea de base y especificar qué versión del tema debe incluirse para la publicación mediante esa línea de base. Para ver qué versión se debe incluir o excluir en una línea base, puede utilizar la opción Historial de versiones.

## Añadir una etiqueta

Siga estos pasos para agregar una etiqueta al tema:

1. En la IU de Assets, seleccione un tema
1. Haga clic en el icono del selector de carril izquierdo y seleccione **Historial de versiones**.
1. En el Historial de versiones, haga clic en la versión a la que desee agregar una etiqueta.

1. Introduzca una etiqueta para la versión seleccionada y pulse Intro. Por ejemplo, *Versión 2.6*.

   >[!NOTE]
   >
   > No se puede agregar la misma etiqueta a las distintas versiones de un tema. Sin embargo, puede agregar varias etiquetas a la misma versión de un tema.

   Las etiquetas se muestran en el Historial de versiones del tema seleccionado. La captura de pantalla siguiente muestra las etiquetas *x.x Release* y *User Guide* agregadas a la versión resaltada del tema.

   ![](images/labels.png){width="300" align="left"}

>[!NOTE]
>
> Con una línea de base, puede agregar una etiqueta a varios temas. Para obtener más información acerca de cómo agregar etiquetas mediante línea de base, vea [Agregar etiquetas a una línea de base](generate-output-use-baseline-for-publishing.md#id184KD0T305Z).

## Eliminación de una etiqueta

Siga estos pasos para eliminar una etiqueta:

1. En la interfaz de usuario de Assets, seleccione un tema que tenga una etiqueta añadida.
1. Haga clic en el icono del selector de carril izquierdo y seleccione **Historial de versiones**.

   En el Historial de versiones, verá todas las versiones de un tema y las etiquetas adjuntas a ellas. La siguiente imagen muestra un ejemplo de diferentes versiones de un tema y una versión tiene etiquetas agregadas.

   ![](images/labels.png){width="300" align="left"}

1. Haga clic en el botón Eliminar \(**X**\) para eliminar la etiqueta.

   ![](images/delete-labels.png){width="300" align="left"}


**Tema principal:**[ Trabajar con el editor web](web-editor.md)
