---
title: Uso del editor DITAVAL
description: AEM Obtenga información sobre cómo crear y editar archivos DITAVAL con el Editor DIVATAL en Guías de la. Descubra cómo el editor DITAVAL admite archivos DITAVAL en las vistas de autor y origen.
exl-id: f3901a4f-1925-42aa-b773-0d6f18175ce8
feature: Authoring, DITAVAL Editor
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---

# editor DITAVAL {#ditaval-editor}

Los archivos DITAVAL se utilizan para generar una salida condicional. En un solo tema, puede añadir condiciones utilizando atributos de elemento para condicionar el contenido. A continuación, se crea un archivo DITAVAL en el que se especifican las condiciones que deben recopilarse para generar contenido y qué condición debe excluirse de la salida final.

AEM Guías de le permite crear y editar fácilmente archivos DITAVAL utilizando el editor DITAVAL. El editor DITAVAL recupera los atributos \(o etiquetas\) definidos en su sistema y puede utilizarlos para crear o editar archivos DITAVAL. AEM Para obtener más información acerca de la creación y administración de etiquetas en la documentación de, consulte la sección sobre la creación y administración de etiquetas en la documentación de la documentación de [Administración de etiquetas](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=en) AEM en la documentación de la.

## Crear archivo DITAVAL

Siga estos pasos para crear un archivo DITAVAL:

1. En la interfaz de usuario de Assets, vaya a la ubicación en la que desea crear el archivo DITAVAL.

1. Clic **Crear** \> **Tema DITA**.

1. En la página Modelo, seleccione Plantilla de archivo DITAVAL y haga clic en **Siguiente**.

1. En la página Propiedades, especifique el **Título** y **Nombre** para el archivo DITAVAL.

   >[!NOTE]
   >
   > El nombre se sugiere automáticamente en función del Título del archivo. Si desea especificar manualmente el nombre del archivo, asegúrese de que el nombre no contenga espacios, apóstrofos ni llaves, y termine con .ditaval.

1. Haga clic en **Crear**. Aparecerá el mensaje Tema creado.

   AEM Puede elegir abrir el archivo DITAVAL para editarlo en el editor DITAVAL o guardar el archivo del tema en el repositorio de la.


## Editar archivo DITAVAL

Siga estos pasos para editar un archivo DITAVAL:

1. En la interfaz de usuario de Assets, vaya al archivo DITAVAL que desee editar.

1. Para bloquear el archivo de forma exclusiva, selecciónelo y haga clic en **Desproteger**.

1. Seleccione el archivo y haga clic en **Editar** AEM para abrir el archivo en el editor DITAVAL de Guías de.

   El editor DITAVAL permite realizar las siguientes tareas:

   A: Alternar panel izquierdo Alternar la vista del panel izquierdo. Si ha abierto el fichero DITAVAL a través de un mapa DITA, el mapa y el repositorio se mostrarán en este panel. Para obtener más información acerca de cómo abrir un archivo mediante DITA map, consulte [Edición de temas mediante el mapa DITA](map-editor-advanced-map-editor.md#id17ACJ0F0FHS).

   B: Guardar . Guarda los cambios realizados en el archivo. Todos los cambios se guardan en la versión actual del archivo.

   C: Agregar propiedad Agregue una sola propiedad en el archivo DITAVAL.

   ![](images/ditaval-editor-props.png)

   En la primera lista desplegable se enumeran los atributos DITA permitidos que se pueden utilizar en el fichero DITAVAL. Se admiten cinco atributos: `audience`, `platform`, `product`, `props`, y `otherprops`.

   La segunda lista desplegable muestra los valores configurados para el atributo seleccionado. A continuación, la siguiente lista desplegable muestra las acciones que se pueden configurar en el atributo seleccionado. Los valores permitidos en la lista desplegable de acción son: `include`, `exclude`, `passthrough`, y `flag`. Para obtener más información sobre estos valores, consulte la definición de [prop](http://docs.oasis-open.org/dita/dita/v1.3/errata01/os/complete/part3-all-inclusive/langRef/ditaval/ditaval-prop.html#ditaval-prop) en la documentación de OASIS DITA

   D: Agregar todas las propiedades Si desea agregar todas las propiedades o atributos condicionales definidos en el sistema con un solo clic, utilice la función Agregar todas las propiedades.

   >[!NOTE]
   >
   > Si ya existen todas las propiedades condicionales definidas en el fichero DITAVAL, no se pueden añadir más propiedades. Aparece un mensaje de error en este escenario.

   ![](images/ditaval-all-props.png)

1. Cuando haya terminado de editar el archivo DITAVAL, haga clic en **Guardar**.

   >[!NOTE]
   >
   > Si cierra el archivo sin guardarlo, se perderán los cambios. AEM Si no desea confirmar los cambios en el repositorio de la, haga clic en **Cerrar** y haga clic en **Cerrar sin guardar** en el **Cambios sin guardar** diálogo.


## Vistas del editor DITAVAL

AEM El editor DITAVAL de Guides admite la visualización de archivos DITAVAL en dos modos o vistas diferentes:

**Autor**: Esta es una vista típica de Lo que ve es lo que obtiene \(WYSISYG\) del editor DITAVAL. Puede agregar o quitar propiedades mediante la interfaz de usuario simple, que presenta las propiedades, sus valores y las acciones en la lista desplegable. En la vista Autor, tiene las opciones para insertar una propiedad individual e insertar todas las propiedades con un solo clic.

También puede encontrar la versión del archivo DITAVAL en la que está trabajando pasando el puntero sobre el nombre del archivo.

**Origen**: la vista Código fuente muestra el XML subyacente que conforma el archivo DITAVAL. Además de realizar ediciones de texto normales en esta vista, un autor también puede agregar o editar propiedades mediante el Catálogo inteligente.

Para invocar el catálogo inteligente, coloque el cursor al final de cualquier definición de propiedad y escriba &quot;&lt;&quot;. El editor mostrará una lista de todos los elementos XML válidos que puede insertar en esa ubicación.

![](images/ditaval-source-view.png)
