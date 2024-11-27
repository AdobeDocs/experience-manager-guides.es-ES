---
title: Perfiles de atributos condicionales
description: Obtenga información sobre cómo crear atributos condicionales en AEM Guides. Utilice atributos condicionales en la carpeta y perfiles globales para condicionalizar el contenido.
feature: Publishing
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 0%

---

# Perfiles de atributos condicionales {#id1843I0HN0Y4}

En el nivel empresarial, es extremadamente importante asegurarse de que dispone de un sistema de etiquetado estándar. Las etiquetas o los atributos condicionales se pueden asociar a recursos digitales en el repositorio, lo que ayuda a publicar los resultados en función de las condiciones seleccionadas. Por ejemplo, puede crear un atributo condicional para el contenido de Windows y Mac. A continuación, agregue estos atributos al contenido relevante en los temas. En el momento de publicar el contenido, puede elegir si desea publicar sólo contenido de Windows o de Mac.

AEM Guides permite crear y asociar fácilmente atributos condicionales utilizando los atributos DITA relevantes. Puede definir atributos condicionales en el nivel global o de carpeta. Las condiciones definidas globalmente son visibles en todos los proyectos y las condiciones específicas de la carpeta solo son visibles en proyectos creados dentro de la carpeta especificada. Los autores de contenido pueden utilizar estos atributos condicionales para condicionar el contenido de sus temas o mapas DITA que crean o utilizan. El editor puede utilizar estas condiciones para crear ajustes preestablecidos condicionales. Mediante los ajustes preestablecidos condicionales, el editor puede decidir qué condición incluir y excluir de la salida publicada.

>[!NOTE]
>
> Puede crear o editar los atributos condicionales en un perfil de carpeta al que tenga acceso. Si el administrador del sistema no le ha dado acceso a un perfil de carpeta, no puede crear ni editar los atributos condicionales en el perfil de carpeta.

Para definir atributos condicionales, realice los siguientes pasos:

1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.

1. Seleccione **Guías** de la lista de herramientas.

1. Haga clic en el mosaico **Perfiles de carpeta** y seleccione un Perfil de carpeta.

   >[!NOTE]
   >
   > No se puede editar el perfil global.

1. Haga clic en la ficha **Atributos condicionales** y luego en **Editar**.

   Se muestra la tabla Atributos condicionales.

1. Haga clic en **Agregar**.

1. Escriba **Name**, **Value** y **Label** para el atributo.

   Puede guardar un perfil con solo el nombre del atributo. Sin embargo, un atributo solo se puede utilizar cuando tiene un valor especificado. Si especifica - valor y etiqueta para un atributo, el editor web seguirá mostrando solo el valor del atributo. La etiqueta se muestra al administrador de publicación en el momento de crear el ajuste preestablecido condicional.

   La siguiente captura de pantalla muestra la definición del atributo `platform` con el valor `unix` y una etiqueta de `Red Hat Linux`.

   ![](images/add-profile.png){width="800" align="left"}

1. Si desea agregar más valores para el mismo atributo, haga clic en el icono **+** e introduzca un valor y una etiqueta adicionales.

1. Si desea agregar más atributos, haga clic en **Agregar**.

1. Haga clic en **Guardar** para guardar los cambios.


El atributo `platform` está almacenado en el sistema. Siempre que un autor decida utilizar el atributo `platform` en un tema DITA de una carpeta, verá los valores en la pestaña Propiedades del Editor Web.

![](images/properties-tab.png){width="350" align="left"}

**Tema principal:**[ Generación de resultados](generate-output.md)
