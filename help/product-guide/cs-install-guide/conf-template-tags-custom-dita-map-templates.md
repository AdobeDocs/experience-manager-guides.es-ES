---
title: Configuración de una plantilla de mapa DITA personalizada
description: Obtenga información sobre cómo configurar una plantilla de mapa DITA personalizada
exl-id: a0eeb43c-06e4-4922-a005-704e8929063f
feature: Template Configuration
role: Admin
level: Experienced
source-git-commit: 83971ee35a19cf0146ddd034b1ae7a345f587663
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 1%

---

# Configuración de una plantilla de mapa DITA personalizada {#id1774F04F05Z}

AEM Guides incluye dos plantillas de mapas predeterminadas: DITA map y Bookmap. Puede crear mapas basados en estas plantillas; o bien, puede definir sus propias plantillas de mapas que se pueden utilizar para crear nuevos mapas.

Siga estos pasos para agregar las plantillas de asignación personalizadas:

1. Inicie sesión en Adobe Experience Manager como administrador.

1. En la interfaz de usuario de Assets, vaya a la carpeta configurada para almacenar los archivos de plantilla de asignación. De forma predeterminada, todas las plantillas de asignación se almacenan en la carpeta /content/dam/dita-templates/maps.

   >[!NOTE]
   >
   > Para configurar una ubicación personalizada para almacenar plantillas de temas o asignaciones, consulte [Configurar la ruta de la carpeta de plantillas DITA personalizada](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z)

1. Haga clic en **Crear** \> **Plantilla DITA**.

1. En la página Modelo, seleccione el tipo de plantilla de mapa que desea crear.

   >[!NOTE]
   >
   > Puede utilizar la plantilla Mapa o Mapa de libro como base para la nueva plantilla.

1. Haga clic en **Siguiente**.

1. En la nueva página Propiedades de plantilla, escriba un **Título** y un **Nombre** para la plantilla.

   >[!NOTE]
   >
   > El nombre se sugiere automáticamente en función del Título de la plantilla. Si desea especificar manualmente el nombre, asegúrese de que el nombre no contiene espacios, apóstrofos ni llaves y termina con .ditamap.

1. Haga clic en **Crear**.

   Aparecerá el mensaje Crear mapa.

   Puede elegir abrir la plantilla para editarla en el Editor de mapas o guardar el archivo de plantilla en la ubicación del almacén de plantillas. Una vez creada la plantilla, puede utilizar el Editor de mapas para personalizarla según sus necesidades de creación. Una vez preparada una plantilla, asegúrese de asociarla con un perfil global o de nivel de carpeta.


La próxima vez que cree un nuevo mapa, la plantilla se mostrará en la página Modelo. Para obtener más información sobre la creación de un mapa DITA, consulte la Guía as a Cloud Service de uso de Adobe Experience Manager Guides.

>[!TIP]
>
> Consulte *la sección Plantillas personalizadas* en la guía de prácticas recomendadas para conocer las prácticas recomendadas sobre el uso de plantillas de mapas personalizadas.


## Personalización del número de referencias en un mapa DITA

Se puede configurar el umbral para el procesamiento asincrónico en función del número de referencias del mapa DITA. De forma predeterminada, las asignaciones con más de 5 referencias se crearán mediante operaciones asincrónicas, mientras que las asignaciones con menos referencias seguirán utilizando operaciones sincrónicas.


Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el fichero de configuración, proporcione los siguientes detalles (propiedad) para especificar el número de referencias en la plantilla de mapa DITA para mantener el proceso síncrono:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| com.adobe.fmdita.xmleditor.config.XmlEditorConfig | xmleditor.asyncmapcreation | > 0 <br> **Valor predeterminado**: 5 |

Al crear un mapa DITA con referencias de temas grandes mediante una plantilla personalizada, la creación del mapa fallaría en el servidor de la nube si el tiempo total de procesamiento supera los 60 segundos.

Para evitarlo, configure la **creación asincrónica de asignaciones de datos** en XmlEditorConfig, que permite que las tareas se ejecuten en paralelo y reduzca los tiempos de procesamiento para asignaciones DITA más grandes.

**Tema principal:** [Configurar plantillas de temas y asignaciones](conf-template-tags.md)
