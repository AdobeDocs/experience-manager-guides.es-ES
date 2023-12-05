---
title: Generar automáticamente ID de elementos
description: Obtenga información sobre cómo generar automáticamente ID de elementos
exl-id: 8d09ab89-4be5-49f1-9831-9f01c92dc472
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Generar automáticamente ID de elementos {#id20CIL40016I}

AEM Guías de documentos genera un ID de documento para cualquier documento nuevo que cree. Por ejemplo, al crear un mapa DITA, un ID como `map.ditamap_random_digits` se asigna al ID del mapa. También puede definir elementos en los que se genera y asigna automáticamente un ID.

AEM Guías de proporciona una configuración sencilla en la que debe definir los elementos en los que se genera automáticamente un ID y un patrón para el ID. De forma predeterminada, algunos elementos como `section`, `table`, `ul`, `ol`, están configuradas para la generación automática de ID. AEM Puede añadir otros elementos a esta lista para que, cada vez que estos elementos se inserten en un documento, las Guías de generen y asignen un ID basado en el patrón determinado

Realice los siguientes pasos para configurar los elementos para que tengan un ID generado automáticamente:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** paquete.

1. En el *XmlEditorConfig* configuración, especifique uno o varios elementos en la **Generación automática de ID para etiquetas de elementos** field.

   >[!NOTE]
   >
   > Las etiquetas de elementos son los nombres de elementos DITA, como `body`, `title`, `codeblock`, etc. Para especificar varios elementos, separe los nombres de los elementos con una coma.

1. En el **Patrón para generar ID** , especifique un patrón para generar un ID.

   El valor predeterminado de este campo es `${elementName}_${id}`. El `${elementName}` El valor se reemplaza con el nombre del elemento. El `${id}` genera un número secuencial para el elemento. Por ejemplo, si asigna al elemento de párrafo ID generados automáticamente, el primer párrafo del tema o documento obtendrá un ID como p\_1, el siguiente párrafo obtendrá p\_2, y así sucesivamente. Sin embargo, en otro documento, se reinicia el proceso de generación de ID. Esto significa que en un documento diferente, ID como p\_1 y p\_2 se pueden asignar a elementos de párrafo.

   Si el documento ya contiene ID en el patrón especificado, el proceso de generación automática no asigna esos ID a nuevos elementos.

1. Haga clic en **Guardar**.


**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
