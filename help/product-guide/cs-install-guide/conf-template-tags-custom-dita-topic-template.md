---
title: Configurar plantilla de tema DITA personalizada
description: Obtenga información sobre cómo configurar una plantilla de tema DITA personalizada
exl-id: 5a2f4897-9697-4c5c-b5be-8fdb3a211948
feature: Template Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/PX1v2yPqLErAIST8JPr-vUwV81HH6EeFQ4LqKES9gkI
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0id: df6fa66f-4542-4a6d-90ca-9f146eb5d494
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 354
ht-degree: 2%

---

# Configurar plantilla de tema DITA personalizada {#id16A7G0O02TD}

AEM Guides incluye las siguientes plantillas de temas DITA:

- Tema

- Tarea

- Concepto

- Referencia

- Glosario

- Resolución de problemas

- En blanco


Puede utilizar cualquiera de estas plantillas para crear temas o plantillas según sus necesidades de creación. La plantilla DITA en blanco no contiene estructura ni elementos como las demás plantillas. Se puede utilizar la plantilla en blanco como base si la plantilla está altamente personalizada y no se basa en ninguna plantilla de tema DITA normal.

Para personalizar la plantilla de tema DITA y utilizarla para la creación, se deben realizar las tres tareas principales siguientes:

1. *\(Opcional\)* [Configurar ruta de carpeta de plantilla DITA personalizada](#id191LCF0095Z)

1. [Crear una plantilla de creación personalizada](conf-folder-level.md#id1917D0EG0HJ)

1. Agregue una plantilla personalizada al perfil global o de nivel de carpeta como se explica en la sección [Configurar las plantillas de creación](conf-folder-level.md#id1889D0IL0Y4)


## Configurar la ruta de carpeta de la plantilla DITA personalizada {#id191LCF0095Z}

AEM Guides permite configurar una carpeta para almacenar el mapa y las plantillas DITA personalizadas. De forma predeterminada, los archivos de plantilla se almacenan en la siguiente carpeta de DAM:

`/content/dam/dita-templates/`

Para administrar archivos de tema y plantilla de asignación, hay carpetas dedicadas para almacenar el tema y las plantillas de asignación. De manera predeterminada, todas las plantillas de temas se almacenan en `/content/dam/dita-templates/topics`

carpeta. Todas las plantillas de asignación se almacenan en la carpeta `/content/dam/dita-templates/maps`.

Como administrador, puede elegir crear plantillas de temas o mapas personalizadas en la carpeta predeterminada o crear su propia carpeta para almacenar plantillas personalizadas. Si planea utilizar la carpeta predeterminada, puede omitir este proceso.

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el fichero de configuración, proporcione los siguientes detalles \(property\) para configurar una carpeta para las plantillas de temas DITA personalizadas:

>[!IMPORTANT]
>
> Puede omitir este proceso si desea utilizar la carpeta predeterminada para almacenar plantillas personalizadas.

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `topic.templates` | Especifique una ubicación para almacenar plantillas personalizadas.<br> Si la ubicación especificada existe en DAM, todas las plantillas predeterminadas de temas y asignaciones se copian en esa carpeta. Si la ubicación no existe, la carpeta se creará con todas las plantillas predeterminadas de asignación y tema. |

**Tema principal:**[ Configurar plantillas de temas y asignaciones](conf-template-tags.md)
