---
title: Configuración de filtros de texto
description: Obtenga información sobre cómo configurar filtros de texto
exl-id: 0963606c-010e-4a72-b7bf-850b86b34a84
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/kni90T4QnDideo-hhxJZRje3H4WTEvBfwEaLa2zOzcg
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9baid: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 389
ht-degree: 0%

---

# Configuración de filtros de texto {#id21BPD0FK0XA}

AEM Guides proporciona la función para buscar texto en los archivos presentes en la ruta seleccionada del repositorio de AEM. Puede utilizar el filtro para buscar archivos desde el panel del repositorio o para examinar archivos. Mientras trabaja en el Editor Web, debe utilizar el cuadro de diálogo de exploración de archivos para insertar elementos como imagen, referencia o referencia de clave.

De forma predeterminada, puede utilizar algunos filtros mejorados para buscar los archivos en el repositorio de AEM. Puede filtrar todos los ficheros DITA o no DITA presentes en la ruta seleccionada. También se pueden buscar valores específicos en los atributos de elementos DITA. También puede buscar archivos que el usuario especificado haya desprotegido.

>[!NOTE]
>
> También puede configurar el perfil global y añadir más filtros para la búsqueda.

Siga estos pasos para configurar los filtros de texto:

1. Inicie sesión en Adobe Experience Manager como administrador.
1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.
1. Seleccione **Guías** de la lista de herramientas y haga clic en **Perfiles de carpeta**.
1. Haga clic en el mosaico **Perfil global**.
1. Haga clic en **Configuración del editor XML**.
1. Haz clic en el icono **Editar** de la parte superior.
1. Haga clic en el icono **Descargar** para descargar el archivo ui\_config.json en su sistema local. A continuación, puede realizar cambios en el archivo y luego cargarlo.
   1. Configure los filtros en el archivo. También puede añadir filtros personalizados como se muestra en el ejemplo siguiente:

      En el siguiente fragmento de código se muestra cómo añadir opciones de filtrado Archivos DITA, Elementos DITA, Elementos DITA y Extraído por archivos. También contiene un filtro personalizado: Etiquetas.

      ```
       "operation":"like"
                                      },
                                      {
                                      "title":"Checked out by",
                                      "property":"jcr:content/cq:drivelock",
                                      "operation":"like",
                                      "itemConfig":{
                                      "component":"textfield",
                                      "placeholder":"Checked out by"
                                      },
                                      "children":[
                                      {
                                      "title":"Check out"
                                      }
                                      ]
                                      },
                                      {
                                      "title":"Tags",
                                      "property":"jcr:content/metadata/cq:tags",
                                      "itemConfig":{
                                      "component":"textfield",
                                      "placeholder":"Enter Tag"
                                      },
                                      "children":[
                                      {
                                      "title":"Tags"
                                      }
                                      ]
                                      }
                                      ]
      ```

      En el fragmento de código anterior, el primer filtro es para archivos DITA. La definición del filtro toma los siguientes parámetros:

      ****Título****: El nombre para mostrar del filtro. Este título aparece como la opción de filtrado en el cuadro de diálogo de exploración de archivos.

      ****Propiedad****: La propiedad que debe coincidir en los metadatos del archivo. Por ejemplo, para permitir solo los archivos que tienen los metadatos dita\_class en su propiedad, el filtro de propiedad toma &quot;jcr:content/metadata/dita\_class&quot; como su valor.

      ****Operación **:**Especifique &quot;exists&quot; para que coincida con la existencia del valor especificado en el parámetro de propiedad

1. Cargue el archivo ui\_config.json actualizado que contiene los filtros agregados.

Los filtros configurados están disponibles en el panel Filtros.

**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
