---
title: Configuración de una plantilla de mapa DITA personalizada
description: Obtenga información sobre cómo configurar una plantilla de mapa DITA personalizada
exl-id: a0eeb43c-06e4-4922-a005-704e8929063f
feature: Template Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 1%

---

# Configuración de una plantilla de mapa DITA personalizada {#id1774F04F05Z}

AEM Las guías de la aplicación incluyen dos plantillas de mapa integradas: DITA map y Bookmap. Puede crear mapas basados en estas plantillas; o bien, puede definir sus propias plantillas de mapas que se pueden utilizar para crear nuevos mapas.

Siga estos pasos para agregar las plantillas de asignación personalizadas:

1. Inicie sesión en Adobe Experience Manager como administrador.

1. En la interfaz de usuario de Assets, vaya a la carpeta configurada para almacenar los archivos de plantilla de asignación. De forma predeterminada, todas las plantillas de asignación se almacenan en la carpeta /content/dam/dita-templates/maps.

   >[!NOTE]
   >
   > Para configurar una ubicación personalizada para almacenar plantillas de temas o mapas, consulte [Configurar la ruta de carpeta de la plantilla DITA personalizada](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z)

1. Clic **Crear** \> **Plantilla DITA**.

1. En la página Modelo, seleccione el tipo de plantilla de mapa que desea crear.

   >[!NOTE]
   >
   > Puede utilizar la plantilla Mapa o Mapa de libro como base para la nueva plantilla.

1. Haga clic en **Siguiente**.

1. En la nueva página Propiedades de plantilla, introduzca un **Título** y **Nombre** para la plantilla.

   >[!NOTE]
   >
   > El nombre se sugiere automáticamente en función del Título de la plantilla. Si desea especificar manualmente el nombre, asegúrese de que el nombre no contiene espacios, apóstrofos ni llaves y termina con .ditamap.

1. Haga clic en **Crear**.

   Aparecerá el mensaje Crear mapa.

   Puede elegir abrir la plantilla para editarla en el Editor de mapas o guardar el archivo de plantilla en la ubicación del almacén de plantillas. Una vez creada la plantilla, puede utilizar el Editor de mapas para personalizarla según sus necesidades de creación. Una vez preparada una plantilla, asegúrese de asociarla con un perfil global o de nivel de carpeta.


La próxima vez que cree un nuevo mapa, la plantilla se mostrará en la página Modelo. Para obtener más información sobre la creación de un mapa DITA, consulte la guía as a Cloud Service Using Adobe Experience Manager Guides.

>[!TIP]
>
> Consulte *las plantillas personalizadas* de la guía de prácticas recomendadas para conocer las prácticas recomendadas sobre el uso de plantillas de mapas personalizadas.

**Tema principal:**[ Configuración de plantillas de temas y mapas](conf-template-tags.md)
