---
title: Uso de etiquetas
description: Descubra el uso de etiquetas para diferentes versiones de un archivo en Adobe Experience Manager Guides. Obtenga información sobre cómo agregar o eliminar una etiqueta a una versión de un tema.
exl-id: d116906d-b469-4a97-b0af-4fadbe15222b
feature: Authoring, Features of Web Editor, Publishing
role: User
TQID: https://experienceleague.adobe.com/sOFJReXzhdWNvsDCcM-s5c5gN-YzV7juLkbGWxbz4bw
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 535
ht-degree: 0%

---

# Uso de etiquetas {#id164JBG0M0T1}

Adobe Experience Manager Guides permite agregar etiquetas a diferentes versiones de un archivo. Puede utilizar estas etiquetas para especificar la versión que desea incluir en una línea de base para la publicación. Para obtener más información acerca del uso de etiquetas para crear una línea de base, vea [Trabajar con línea de base](generate-output-use-baseline-for-publishing.md#).

Por ejemplo, si desea utilizar la *versión 1.0* de un tema en la *versión 1.0* y la *versión 1.1* del mismo tema en la *versión 2.0*, puede agregar la etiqueta *versión 1.0* en la etiqueta *versión 1.0* y *versión 2.0* en la *versión 1.1*.

Una vez agregadas las etiquetas, puede crear una línea de base y especificar qué versión del tema debe incluirse para la publicación mediante esa línea de base. Para ver qué versión se debe incluir o excluir en una línea base, se puede utilizar la opción Historial de Versiones.

## Añadir una etiqueta desde el editor

Siga estos pasos para agregar una etiqueta al tema desde el Editor:

1. En el panel Repositorio, vaya a un tema y ábralo en el Editor.
1. Seleccione **Etiqueta de versión** del menú desplegable **Menú**.

   Se muestra el cuadro de diálogo **Administración de etiquetas de versión**.

1. En el cuadro de diálogo **Administración de etiquetas de versión**, seleccione una versión a la que desee agregar una etiqueta.
1. Seleccione una etiqueta para la versión seleccionada y seleccione **Agregar etiqueta**.

   ![](images/version-label-management-dialog-new.png){width="650"}

   >[!NOTE]
   >
   > No se puede agregar la misma etiqueta a las distintas versiones de un tema. Sin embargo, puede agregar varias etiquetas a la misma versión de un tema.
1. Confirme para aplicar las etiquetas en el mensaje de confirmación.

   Las etiquetas se muestran en el Historial de versiones del tema seleccionado.

   ![](images/label-comparison-version-history.png){width="650"}

   >[!NOTE]
   >
   > Con una línea de base, puede agregar una etiqueta a varios temas. Para obtener más información acerca de cómo agregar etiquetas mediante línea de base, vea [Agregar etiquetas a una línea de base](generate-output-use-baseline-for-publishing.md#id184KD0T305Z).

Para eliminar una etiqueta de versión de un tema, use el icono **Quitar** proporcionado con cada etiqueta agregada en el cuadro de diálogo Administración de etiquetas de versión.

![](images/remove-version-label.png)


## Uso de etiquetas desde la interfaz de usuario de Assets

También puede agregar etiquetas a un tema y eliminarlas según sea necesario en la interfaz de usuario de Assets.

Siga estos pasos para agregar una etiqueta al tema desde la interfaz de usuario de Assets:

1. En la interfaz de usuario de Assets, seleccione un tema y ábralo.
1. Seleccione el icono del selector del carril izquierdo y seleccione **Historial de versiones**.
1. En el menú desplegable Historial de versiones, seleccione la versión a la que desee agregar una etiqueta.
1. Introduzca una etiqueta para la versión seleccionada y pulse Intro. Por ejemplo, *Versión 2.6*.

   >[!NOTE]
   >
   > No se puede agregar la misma etiqueta a las distintas versiones de un tema. Sin embargo, puede agregar varias etiquetas a la misma versión de un tema.

   Las etiquetas se muestran en el Historial de versiones del tema seleccionado. La captura de pantalla siguiente muestra las etiquetas *x.x Release* y *User Guide* agregadas a la versión resaltada del tema.

   ![](images/labels.png){width="300"}

>[!NOTE]
>
> Con una línea de base, puede agregar una etiqueta a varios temas. Para obtener más información acerca de cómo agregar etiquetas mediante línea de base, vea [Agregar etiquetas a una línea de base](generate-output-use-baseline-for-publishing.md#id184KD0T305Z).

Para eliminar una etiqueta de versión de un tema, use el botón **Eliminar** proporcionado con cada etiqueta en el panel Historial de versiones.

![](images/delete-labels.png){width="300"}


**Tema principal:**[ Introducción al editor](web-editor.md)
