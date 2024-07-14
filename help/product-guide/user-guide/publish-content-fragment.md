---
title: Publish de un tema a un fragmento de contenido
description: Publish un tema o los elementos dentro de un tema a un fragmento de contenido en AEM Guides.  Obtenga información sobre cómo ver los fragmentos de contenido presentes en un tema y volver a publicarlos.
exl-id: b1769e48-d721-4e93-b10f-04b385272be7
feature: Publishing
role: User
source-git-commit: 7c7e3dcddf733793a5d6db50205ba60d24702451
workflow-type: tm+mt
source-wordcount: '925'
ht-degree: 0%

---

# Fragmentos de contenido de Publish

Los fragmentos de contenido son fragmentos de contenido discretos en Adobe Experience Manager. Son contenidos estructurados basados en un modelo de contenido. Los fragmentos de contenido son contenido puro sin información de diseño. Se pueden crear y administrar independientemente de los canales compatibles con Experience Manager para el Adobe. Los fragmentos de contenido son modulares, donde el contenido se desglosa en componentes más pequeños.

Adobe Experience Manager Guides permite publicar un tema o los elementos dentro de un tema en un fragmento de contenido. Puede crear una asignación basada en JSON entre un tema y un modelo de fragmento de contenido. Utilice esta asignación para publicar un tema o los elementos dentro de un tema en un fragmento de contenido. A continuación, puede utilizar fragmentos de contenido en cualquier sitio de Adobe Experience Manager o extraer los detalles mediante las API admitidas por los fragmentos de contenido.


Para crear un fragmento de contenido, realice los siguientes pasos:

1. Crear un [modelo de fragmento de contenido](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=es) en Adobe Experience Manager Assets.
1. Cree una carpeta en la que desee guardar los fragmentos de contenido que cree en función del modelo de fragmento de contenido. Por ejemplo, &quot;stock-content-fragments&quot;.
1. Edite las propiedades de la carpeta (por ejemplo, &quot;stock-content-fragments&quot;) y agregue la ruta de la carpeta, que contiene el modelo de fragmento de contenido en la configuración de la nube.
Por ejemplo, agregue `/conf/we-retail` en la configuración de nube. Esta configuración conecta todos los modelos de fragmento de contenido con la carpeta.\
   ![agregar detalles de configuración de nube en las propiedades de la carpeta](images/fragment-folder-cloud-configuration.png){width="650" align="left"}
   *Agregue la configuración de nube en las propiedades de la carpeta para conectarla con los modelos de fragmento.*

1. Para generar un fragmento de contenido, seleccione **Nueva salida** ![nuevo icono de salida](./images/Add_icon.svg) de la sección **Salidas** en las **Propiedades de archivo** de un tema.
1. Seleccione **Fragmento de contenido**.\
   ![ficha de opciones de propiedades de archivo](./images/file-properties-outputs-tab.png){width="300" align="left"}

   *Agregar un nuevo fragmento de contenido desde las propiedades de archivo de un tema*.

1. En el cuadro de diálogo **Generar fragmento de contenido**, rellene los siguientes detalles:
   ![Agregue el modelo de fragmento y los detalles de asignación en el cuadro de diálogo Publish como fragmento de contenido](images/content-fragment-publish.png){width="500" align="left"}
   *Agregue la ruta, el modelo y los detalles de asignación para publicar un tema o sus elementos como fragmento de contenido. Puede sobrescribir un fragmento de contenido existente.*

   >[!NOTE]
   >
   >También puede publicar un fragmento de contenido desde la **vista de repositorio**. Seleccione el tema que desea publicar como fragmento de contenido. A continuación, en el menú **Opciones**, seleccione **Publish As** > **Fragmento de contenido**.

   * **Ruta**: busque y seleccione la ruta de la carpeta donde desea publicar el fragmento de contenido. Si selecciona un fragmento de contenido existente, se sobrescribe el contenido de los campos asignados.
   * **Título**: escriba el título del fragmento de contenido. De forma predeterminada, el título se rellena con el título del tema. Puede editarlo. Este título se utiliza para generar el nombre del fragmento de contenido.
   * **Nombre**: escriba el nombre del fragmento de contenido. De forma predeterminada, el nombre se rellena con el título del tema y los espacios se sustituyen por &quot;_&quot;. Por ejemplo, *sample_content_fragment*. Puede editarlo.  Este nombre se utiliza para generar la dirección URL del fragmento de contenido.
   * **Modelo**: Seleccione el modelo de fragmento de contenido que desee usar para crear el fragmento de contenido. Los modelos se seleccionan de la carpeta, que ha configurado en los servicios en la nube.
   * **Asignación**: seleccione una asignación en la lista desplegable. Selecciona las asignaciones del archivo *contentFragmentMapping.json*.



     El administrador puede agregar las asignaciones en el archivo *contentFragmentMapping.json*. Obtenga más información acerca de cómo [crear una asignación entre un tema y un fragmento de contenido](../cs-install-guide/conf-content-fragment-mapping-cs.md) en la Guía de instalación y configuración.

   * También puede seleccionar diferentes condiciones para publicar el contenido.  Seleccione una de las siguientes opciones:


      * **Ninguno**: seleccione esta opción si no desea aplicar ninguna condición en la salida publicada.
      * **Utilizando DITAVAL**: seleccione el archivo DITAVAL para generar la salida, que incluye contenido específico. Puede seleccionar el fichero DITAVAL mediante el cuadro de diálogo de exploración o escribiendo la ruta del fichero.
      * **Utilizar atributos**: puede definir atributos de condición en los temas DITA. A continuación, seleccione el atributo de condición para publicar el contenido relevante.
     >[!NOTE]
     > 
     >Las condiciones solo se activan si los atributos de condición se definen en el tema.



   * Seleccione **Sobrescribir contenido existente** si el fragmento de contenido ya existe y desea sobrescribirlo. Experience Manager Guides muestra un error si no selecciona la casilla de verificación y el fragmento de contenido ya existe.
1. Haga clic en **Generar** para publicar el fragmento de contenido.

1. Puede ver los fragmentos de contenido de un tema en la sección **Salidas** de **Propiedades del archivo**.

   ![Ver los fragmentos de contenido de un tema](images/outputs-options-menu.png){width="300" align="left"}

   *Vea los fragmentos de contenido presentes en un tema y vuelva a publicarlos.*


Una vez publicados los fragmentos de contenido, también puede utilizarlos en cualquier sitio de Adobe Experience Manager.




## Menú Opciones para un fragmento de contenido

También puede realizar las siguientes acciones para un fragmento de contenido desde el menú **Opciones**:

* **Generar**: vuelva a publicar el fragmento de contenido para actualizarlo con el contenido más reciente del tema DITA. Al regenerar la salida, no se puede cambiar la ruta, el nombre, el título, el modelo y la asignación del fragmento de contenido. Sin embargo, se pueden seleccionar condiciones diferentes al regenerar la salida.

* **Duplicado**: Duplique un fragmento de contenido. Puede cambiar la ruta, el nombre, el título, el modelo y la asignación. También puede seleccionar condiciones diferentes al duplicar un fragmento de contenido.

* **Quitar**: quita un fragmento de contenido de la lista de resultados. Aparecerá un mensaje de confirmación. Una vez confirmado, el fragmento de contenido se eliminará de la lista **Salidas**.

  >[!NOTE]
  >
  > Esta acción no elimina contenido del fragmento de contenido.

* **Ver**: vea el editor de fragmentos de contenido. También puede realizar cambios y guardarlos.


