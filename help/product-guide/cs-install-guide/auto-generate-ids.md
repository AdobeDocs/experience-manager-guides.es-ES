---
title: Generar automáticamente ID de elementos
description: Obtenga información sobre cómo generar automáticamente ID de elementos
exl-id: a651db7f-228e-4de5-b569-3f1b4f86c418
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 1%

---

# Generar automáticamente ID de elementos {#id20CIL40016I}

AEM Guías de documentos genera un ID de documento para cualquier documento nuevo que cree. Por ejemplo, al crear un mapa DITA, un ID como `map.ditamap_random_digits` se asigna al ID del mapa. También puede definir elementos en los que se genera y asigna automáticamente un ID.

AEM Guías de proporciona una configuración sencilla en la que debe definir los elementos en los que se genera automáticamente un ID y un patrón para el ID. De forma predeterminada, algunos elementos como `section`, `table`, `ul`, `ol`, están configuradas para la generación automática de ID. AEM Puede añadir otros elementos a esta lista para que, cada vez que estos elementos se inserten en un documento, las Guías de generen y asignen un ID basado en el patrón determinado

Siga las instrucciones que se indican en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar los ID de elementos generados automáticamente:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.classes` | Especifique una lista de elementos separados por comas. <br> **Valor predeterminado**: `"topic, section, table, simpletable, fig, image, ul, ol"` |

Para configurar un patrón para un ID generado automáticamente, cree un archivo de configuración con las siguientes propiedades:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.pattern` | El valor predeterminado de este campo es `${elementName}_${id}`. El `${elementName}` El valor se reemplaza con el nombre del elemento. El `${id}` genera un número secuencial para el elemento. Por ejemplo, si asigna al elemento de párrafo ID generados automáticamente, el primer párrafo del tema o documento obtendrá un ID como p\_1, el siguiente párrafo obtendrá p\_2, y así sucesivamente. Sin embargo, en otro documento, se reinicia el proceso de generación de ID. Esto significa que en un documento diferente, ID como p\_1 y p\_2 se pueden asignar a elementos de párrafo. **Valor predeterminado**: ``${elementName}_${id}`` |

**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
