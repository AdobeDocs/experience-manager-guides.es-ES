---
title: Perfiles de atributos condicionales
description: Obtenga información sobre cómo crear atributos condicionales en AEM Guides. Utilice atributos condicionales en la carpeta y perfiles globales para condicionalizar el contenido.
exl-id: 5ec7666e-df6b-4b0d-b6c2-cdc395fcccc5
feature: Publishing
role: User
TQID: https://experienceleague.adobe.com/23vd2pqUR6yXPQvq5xxj31JxkoWgkQaqtKhu7l9XxOs
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2: id: f9dbea21-a714-40dd-bc90-080d8046c93fid: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 479
ht-degree: 0%

---

# Perfiles de atributos condicionales {#id1843I0HN0Y4}

En el nivel empresarial, es extremadamente importante asegurarse de que dispone de un sistema de etiquetado estándar. Las etiquetas o los atributos condicionales se pueden asociar a recursos digitales en el repositorio, lo que ayuda a publicar los resultados en función de las condiciones seleccionadas. Por ejemplo, puede crear un atributo condicional para el contenido de Windows y Mac. A continuación, agregue estos atributos al contenido relevante en los temas. En el momento de publicar el contenido, puede elegir si desea publicar sólo contenido de Windows o de Mac.

Adobe Experience Manager Guides permite crear y asociar fácilmente atributos condicionales utilizando los atributos DITA relevantes. Puede definir atributos condicionales en el nivel global o de carpeta. Las condiciones definidas globalmente son visibles en todos los proyectos y las condiciones específicas de la carpeta solo son visibles en proyectos creados dentro de la carpeta especificada. Los autores de contenido pueden utilizar estos atributos condicionales para condicionar el contenido de sus temas o mapas DITA que crean o utilizan. El editor puede utilizar estas condiciones para crear ajustes preestablecidos condicionales. Mediante los ajustes preestablecidos condicionales, el editor puede decidir qué condición incluir y excluir de la salida publicada.

>[!NOTE]
>
> Puede crear o editar los atributos condicionales en un perfil de carpeta al que tenga acceso. Si el administrador del sistema no le ha dado acceso a un perfil de carpeta, no puede crear ni editar los atributos condicionales en el perfil de carpeta.

Para definir atributos condicionales, realice los siguientes pasos:

1. Seleccione el logotipo de Adobe Experience Manager en la parte superior y elija **Herramientas**.

1. En el panel Herramientas, seleccione **Guías**.

1. Seleccione el mosaico **Perfiles de carpeta** y elija un Perfil de carpeta.

   >[!NOTE]
   >
   > No se puede editar el perfil global.

1. Seleccione la ficha **Atributos condicionales** y, a continuación, seleccione **Editar**.

   Se muestra la tabla Atributos condicionales.

1. Seleccione **Añadir**.

1. Escriba **Name**, **Value** y **Label** para el atributo.

   Puede guardar un perfil con solo el nombre del atributo. Sin embargo, un atributo solo se puede utilizar cuando tiene un valor especificado. Si especifica - valor y etiqueta para un atributo, el editor web seguirá mostrando solo el valor del atributo. La etiqueta se muestra al administrador de publicación en el momento de crear el ajuste preestablecido condicional.

   La siguiente captura de pantalla muestra la definición del atributo `platform` con el valor `unix` y una etiqueta de `Red Hat Linux`.

   ![](images/add-profile-new.png)

1. Si desea agregar más valores para el mismo atributo, seleccione el icono **+** e introduzca un valor y una etiqueta adicionales.

1. Si desea agregar más atributos, seleccione **Agregar**.

1. Seleccione **Guardar** para guardar los cambios.


El atributo `platform` está almacenado en el sistema. Cada vez que un autor decide utilizar el atributo `platform` en un tema DITA de una carpeta, puede ver los valores en la pestaña Propiedades del Editor.

![](images/properties-tab.png){width="350"}

**Tema principal:**[ Generación de resultados](generate-output.md)
