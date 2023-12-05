---
title: Configurar plantilla de tema DITA personalizada
description: Obtenga información sobre cómo configurar una plantilla de tema DITA personalizada
exl-id: 5a2f4897-9697-4c5c-b5be-8fdb3a211948
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 2%

---

# Configurar plantilla de tema DITA personalizada {#id16A7G0O02TD}

AEM Las guías de la aplicación incluyen las siguientes plantillas de temas DITA:

- Tema

- Tarea

- Concepto

- Referencia

- Glosario

- Solución de problemas

- En blanco


Puede utilizar cualquiera de estas plantillas para crear temas o plantillas según sus necesidades de creación. La plantilla DITA en blanco no contiene estructura ni elementos como las demás plantillas. Se puede utilizar la plantilla en blanco como base si la plantilla está altamente personalizada y no se basa en ninguna plantilla de tema DITA normal.

Para personalizar la plantilla de tema DITA y utilizarla para la creación, se deben realizar las tres tareas principales siguientes:

1. *\(Opcional\)* [Configurar la ruta de carpeta de la plantilla DITA personalizada](#id191LCF0095Z)

1. [Crear una plantilla de creación personalizada](conf-folder-level.md#id1917D0EG0HJ)

1. Añada una plantilla personalizada al perfil global o de nivel de carpeta como se explica en la [Configuración de plantillas de creación](conf-folder-level.md#id1889D0IL0Y4) sección


## Configurar la ruta de carpeta de la plantilla DITA personalizada {#id191LCF0095Z}

AEM Guías de le permite configurar una carpeta para almacenar el mapa y las plantillas DITA personalizados. De forma predeterminada, los archivos de plantilla se almacenan en la siguiente carpeta de DAM:

`/content/dam/dita-templates/`

Para administrar archivos de tema y plantilla de asignación, hay carpetas dedicadas para almacenar el tema y las plantillas de asignación. De forma predeterminada, todas las plantillas de temas se almacenan en la variable `/content/dam/dita-templates/topics`

carpeta. Todas las plantillas de mapa se almacenan en `/content/dam/dita-templates/maps` carpeta.

Como administrador, puede elegir crear plantillas de temas o mapas personalizadas en la carpeta predeterminada o crear su propia carpeta para almacenar plantillas personalizadas. Si planea utilizar la carpeta predeterminada, puede omitir este proceso.

Siga las instrucciones que se indican en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el fichero de configuración, proporcione los siguientes detalles \(property\) para configurar una carpeta para las plantillas de temas DITA personalizadas:

>[!IMPORTANT]
>
> Puede omitir este proceso si desea utilizar la carpeta predeterminada para almacenar plantillas personalizadas.

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `topic.templates` | Especifique una ubicación para almacenar plantillas personalizadas.<br> Si la ubicación especificada existe en DAM, todas las plantillas predeterminadas de temas y asignaciones se copian en esa carpeta. Si la ubicación no existe, la carpeta se creará con todas las plantillas predeterminadas de asignación y tema. |

**Tema principal:**[ Configuración de plantillas de temas y mapas](conf-template-tags.md)
