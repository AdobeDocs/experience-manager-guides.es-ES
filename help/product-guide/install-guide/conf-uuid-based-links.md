---
title: Configurar la visualización de vínculos basados en UUID
description: Obtenga información sobre cómo configurar la visualización de vínculos basados en UUID
exl-id: ab1b0ecf-cb50-4fcd-b36e-d16a8c396054
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Configurar la visualización de vínculos basados en UUID {#id2035G20M0QN}

De forma predeterminada, cuando se crea un vínculo con la opción Insertar referencia o Insertar contenido reutilizado del Editor Web, el vínculo se crea con el UUID del contenido al que se hace referencia. La propiedad **Link** \(en el panel Propiedades\) del contenido al que se hace referencia se puede configurar para mostrar la ruta de archivo relativa del contenido al que se hace referencia o el UUID. Esta pantalla está controlada por la opción **Enable UUIDs** de configMgr. De forma predeterminada, está activado, lo que implica que el UUID del contenido al que se hace referencia se muestra en el panel Propiedades.

Realice los siguientes pasos para mostrar la ruta relativa o el UUID del contenido al que se hace referencia en el editor web:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. En la configuración de *XmlEditorConfig*, la opción **Habilitar UUIDs** está habilitada de manera predeterminada. Esto implica que el UUID del contenido al que se hace referencia se muestra en la propiedad **Link** del panel Propiedades.

   Si desea mostrar la ruta relativa del contenido vinculado, anule la selección de la opción **Habilitar UUID**.

1. Haga clic en **Guardar**.


**Tema principal:**&#x200B;[&#x200B; Personalizar editor web](conf-web-editor.md)
