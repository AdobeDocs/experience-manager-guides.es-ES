---
title: Configurar plantilla de tema DITA personalizada
description: Obtenga información sobre cómo configurar una plantilla de tema DITA personalizada
exl-id: 5a2f4897-9697-4c5c-b5be-8fdb3a211948
feature: Template Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '354'
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
| `com.adobe.fmdita.config.ConfigManager` | `topic.templates` | Especifique una ubicación para almacenar plantillas personalizadas.<br> Si la ubicación especificada existe en DAM, todas las plantillas predeterminadas de asignación y tema se copian en esa carpeta. Si la ubicación no existe, la carpeta se creará con todas las plantillas predeterminadas de asignación y tema. |

**Tema principal:**[ Configurar plantillas de temas y asignaciones](conf-template-tags.md)
