---
title: Generar automáticamente ID de elementos
description: Obtenga información sobre cómo generar automáticamente ID de elementos
exl-id: 8d09ab89-4be5-49f1-9831-9f01c92dc472
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Generar automáticamente ID de elementos {#id20CIL40016I}

AEM Guides genera un ID de documento para cualquier documento nuevo que cree. Por ejemplo, al crear un mapa DITA, se asigna un identificador como `map.ditamap_random_digits` al identificador del mapa. También puede definir elementos en los que se genera y asigna automáticamente un ID.

AEM Guides proporciona ajustes de configuración sencillos en los que debe definir los elementos en los que se genera automáticamente un ID y un patrón para el ID. De manera predeterminada, algunos elementos como `section`, `table`, `ul`, `ol`, están configurados para la generación automática del identificador. Puede añadir otros elementos a esta lista para que, cada vez que se inserten en un documento, AEM Guides genere y asigne un ID basado en el patrón determinado

Realice los siguientes pasos para configurar los elementos para que tengan un ID generado automáticamente:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. En la configuración de *XmlEditorConfig*, especifique uno o más elementos en el campo **Generar ID automáticamente para etiquetas de elementos**.

   >[!NOTE]
   >
   > Las etiquetas de elementos son los nombres de elementos DITA como `body`, `title`, `codeblock`, etc. Para especificar varios elementos, separe los nombres de los elementos con una coma.

1. En el campo **Patrón para generar identificadores**, especifique un patrón para generar un identificador.

   El valor predeterminado de este campo está establecido en `${elementName}_${id}`. El valor `${elementName}` se reemplaza con el nombre del elemento. La variable `${id}` genera un número secuencial para el elemento. Por ejemplo, si asigna al elemento de párrafo ID generados automáticamente, el primer párrafo del tema o documento obtendrá un ID como p\_1, el siguiente párrafo obtendrá p\_2, y así sucesivamente. Sin embargo, en otro documento, se reinicia el proceso de generación de ID. Esto significa que en un documento diferente, ID como p\_1 y p\_2 se pueden asignar a elementos de párrafo.

   Si el documento ya contiene ID en el patrón especificado, el proceso de generación automática no asigna esos ID a nuevos elementos.

1. Haga clic en **Guardar**.


**Tema principal:**&#x200B;[&#x200B; Personalizar editor web](conf-web-editor.md)
