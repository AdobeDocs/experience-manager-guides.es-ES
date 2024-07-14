---
title: Etiquetado masivo de contenido DITA
description: Utilice el etiquetado masivo de contenido en AEM Guides para mejorar la capacidad de detección de contenido DITA. Obtenga información sobre cómo aplicar, quitar, mostrar u ocultar etiquetas masivas en un solo tema o en varios.
exl-id: 4c6639a3-333b-44ad-9aec-735a327c3320
feature: Metadata Management
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 0%

---

# Etiquetado masivo de contenido DITA {#id179SG0TN05Z}

Las etiquetas permiten agrupar o clasificar contenido dentro del repositorio de contenido y también en la salida publicada. Si ha aplicado etiquetas a su contenido, puede encontrar fácilmente temas relacionados dentro de un mapa DITA que puede ayudarle a crear contenido. Con el resultado publicado, los usuarios finales podrán localizar el contenido correcto más rápido con las etiquetas adecuadas.

AEM Guides le permite etiquetar contenido DITA en unos pocos clics. Puede utilizar la función de etiquetado por lotes para aplicar varias etiquetas en varios temas, en un mapa DITA o en un submapa. O bien, también puede aplicar etiquetas a un tema individual. AEM AEM El etiquetado es la característica nativa de la documentación de, por lo que puede encontrar más detalles sobre la creación y administración de etiquetas en la sección [Administración de etiquetas](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=en) de la documentación de la.

De forma predeterminada, AEM Guides AEM no concede acceso de lectura a ningún usuario de la carpeta en la que se almacenen todas las etiquetas del repositorio de la. AEM Para utilizar etiquetas definidas en el repositorio de la, debe solicitar al administrador del sistema que conceda acceso a la carpeta donde se almacenan las etiquetas.

## Aplicación de etiquetas masivas

Utilice la función de etiquetado masivo para aplicar varias etiquetas a la vez. Siga estos pasos para aplicar etiquetas a los temas de un mapa DITA:

1. En la interfaz de usuario de Assets, vaya al fichero de mapa DITA y haga clic en él.

   Aparecerá la consola de mapas DITA con la lista de ajustes preestablecidos de salida disponibles para generar resultados.

1. Haga clic en **Temas**.

   Se mostrará una lista de los temas disponibles en el mapa DITA. Los UUID de &quot;temas&quot; se muestran debajo del título del tema.

1. Seleccione los temas o el submapa al que desee aplicar las etiquetas.

   ![](images/apply-tags-uuid.png){width="650" align="left"}


   >[!NOTE]
   >
   > La captura de pantalla anterior muestra un submapa seleccionado y expandido. Al seleccionar el submapa, también se seleccionan todos los temas del submapa.

1. Haga clic en **Aplicar etiquetas**.

   Aparecerá el cuadro de diálogo Seleccionar etiquetas.

1. Seleccione una o varias etiquetas que desee aplicar a los temas seleccionados.

1. Confirme la selección.

   Las etiquetas seleccionadas se aplican a los temas y se muestran junto al título del tema.

   >[!NOTE]
   >
   > Después de agregar etiquetas a los temas, si mueve o elimina un tema, también se quitan las etiquetas de esos temas. Sin embargo, ese tema permanece en el mapa hasta que lo elimine.


## Aplicación de etiquetas en un tema individual

Siga estos pasos para aplicar etiquetas a un tema individual:

1. En la interfaz de usuario de Assets, vaya y seleccione el archivo de tema en el que desea aplicar las etiquetas.

1. En la barra de herramientas, haga clic en **Propiedades**.

   Aparecerá la página de propiedades del tema.

1. En la pestaña Básico, haga clic en el icono Examinar junto al campo **Etiquetas**.

1. Seleccione una o varias etiquetas que desee aplicar al tema seleccionado.

1. Confirme la selección.

1. Haga clic en **Aplicar etiquetas**.

   Las etiquetas seleccionadas se aplican al tema y se muestran en el campo Etiquetas.

1. Haga clic en **Guardar y cerrar**.


## Eliminar etiquetas

Según sus necesidades comerciales, puede cambiar la información de etiquetado para cualquier tema de DITA. Puede quitar fácilmente todas las etiquetas a la vez o quitar solo las que no sean válidas en el tema.

Siga estos pasos para quitar todas las etiquetas de uno o varios temas:

1. En la interfaz de usuario de Assets, vaya al fichero de mapa DITA y haga clic en él.

   Aparecerá la consola de mapas DITA con la lista de ajustes preestablecidos de salida disponibles para generar resultados.

1. Haga clic en **Temas**.

   Se mostrará una lista de los temas disponibles en el mapa DITA.

1. Seleccione los temas de los que desea quitar etiquetas.

1. Haga clic en **Quitar etiquetas**.

   >[!NOTE]
   >
   > Si el icono Eliminar etiquetas no está visible, asegúrese de que no ha habilitado la función Ocultar etiquetas.

1. En el cuadro de diálogo Confirmar eliminación, haga clic en **Aceptar** para quitar las etiquetas de los temas seleccionados.


## Mostrar u ocultar etiquetas

Si tiene una larga lista de etiquetas aplicadas a los temas, puede que le resulte un poco engorroso navegar. Puede ocultar etiquetas fácilmente desde la vista de la consola de mapas DITA haciendo clic en el icono Ocultar etiquetas. Del mismo modo, cuando las etiquetas no están visibles, al hacer clic en Mostrar etiquetas se muestran todas las etiquetas.

**Tema principal:**[ Administrar metadatos](manage-metadata.md)
