---
title: Publish de un tema a una página de AEM Sites
description: Publish un tema o los elementos dentro de un tema a una salida de Adobe Experience Manager Sites.  Obtenga información sobre cómo ver la página de Experience Manager Sites presente para un tema y volver a publicarla.
feature: Publishing
role: User
source-git-commit: 05c3e5e6f3c6aea4b3e3f3a52af5810307f1f29b
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 0%

---

# Páginas de Publish Adobe Experience Manager Sites


La página de Experience Manager Sites hace referencia al contenido publicado en el sitio web de Adobe Experience Manager. Experience Manager Guides le permite publicar un tema independiente en una página de Sites.

Esta función permite publicar un tema y sus elementos sin crear un mapa DITA ni los ajustes preestablecidos de salida. Puede actualizar fácilmente el tema, volver a publicar la página de Sites y reutilizarla en diferentes páginas web. Con esta función, puede publicar fácilmente artículos independientes o contenido de marketing.





Para generar una página de Sites, realice los siguientes pasos:




1. Seleccione **Nueva salida** ![nuevo icono de salida](./images/Add_icon.svg) de la sección **Salidas** en las **Propiedades de archivo** de un tema.
1. Seleccionar **página de sitios**.


1. En el cuadro de diálogo **Generar página de sitios**, rellene los siguientes detalles:
   ![Agregue la ruta y los detalles de la plantilla en la página Generar sitios](images/aem-sites-page-generate.png){width="500" align="left"}

   * Añada la ruta, el título, el nombre y los detalles de plantilla para publicar un tema o sus elementos como una página de Sites. *

   * **Ruta**: busque y seleccione la ruta de la carpeta donde desea publicar la página de Sites.
   * **Título**: escriba el título de la página de Sites. De forma predeterminada, el título se rellena con el título del tema. Puede editarlo. Este título se utiliza para generar el nombre de la página de Sites.
   * **Nombre**: escriba el nombre de la página de Sites. De forma predeterminada, el nombre se rellena con el título del tema y los caracteres no permitidos, como espacios y caracteres especiales, se sustituyen por &quot;_&quot;. Por ejemplo, *sample_sites_page*. Puede editarlo. Este nombre se utiliza para generar la dirección URL de la página de Sites.
   * **Plantilla de página**: seleccione la plantilla de página Sitios para crear su página Sitios. Puede ver las plantillas en la carpeta en la ruta que seleccione. El administrador también puede cargar plantillas personalizadas.


   * También puede seleccionar diferentes condiciones para publicar el contenido.  Seleccione una de las siguientes opciones:


      * **Ninguno**: seleccione esta opción si no desea aplicar ninguna condición en la salida publicada.
      * **Utilizando DITAVAL**: seleccione el archivo DITAVAL para generar contenido personalizado. Puede seleccionar el fichero DITAVAL mediante el cuadro de diálogo de exploración o escribiendo la ruta del fichero.
      * **Utilizar atributos**: puede definir atributos de condición en los temas DITA. A continuación, seleccione el atributo de condición para publicar el contenido relevante.

     >[!NOTE]
     > 
     >Las condiciones solo se activan si los atributos de condición se definen en el tema.



1. Haga clic en **Generar** para publicar la página de Sites.
1. Puede ver la página Sitios de un tema en la sección **Resultados** de las **propiedades de archivo**. Las páginas de Sites aparecen según la fecha y la hora de su publicación, con la última como la primera.

   ![Ver la página de Sites de un tema](images/aem-sites-outputs.png){width=300 align=&quot;left&quot;}

   *Vea la página de Sites presente para un tema y vuelva a publicarla.*




Una vez publicada la página de Sites, también puede utilizarla en cualquier sitio de Adobe Experience Manager.


## Menú Opciones de un Experience Manager Sites

También puede realizar las siguientes acciones para un Experience Manager Sites desde el menú **Opciones**:

* **Generar**: vuelva a publicar la página de Sites para actualizarla con el contenido más reciente del tema DITA. Cuando vuelva a generar la salida sin cambiar la ruta, el nombre, el título, la plantilla y las condiciones, la página de Sites simplemente se actualiza con el contenido más reciente.

* **Duplicado**: duplicar una página de Sites. Puede cambiar la ruta, el nombre, el título y la plantilla. También puede seleccionar condiciones diferentes al duplicar una página de Sites.

* **Quitar**: elimine una página de Sites de la lista de resultados. Aparecerá un mensaje de confirmación. Una vez confirmada, la página Sitios se eliminará de la lista **Resultados**. Sin embargo, la página de Sites no se elimina de forma permanente.

* **Ver**: vea el editor de páginas de Sites. También puede realizar cambios y guardarlos.
