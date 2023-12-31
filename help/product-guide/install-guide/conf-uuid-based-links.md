---
title: Configurar la visualización de vínculos basados en UUID
description: Obtenga información sobre cómo configurar la visualización de vínculos basados en UUID
exl-id: ab1b0ecf-cb50-4fcd-b36e-d16a8c396054
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Configurar la visualización de vínculos basados en UUID {#id2035G20M0QN}

De forma predeterminada, cuando se crea un vínculo con la opción Insertar referencia o Insertar contenido reutilizado del Editor Web, el vínculo se crea con el UUID del contenido al que se hace referencia. El **Vínculo** la propiedad \(en el panel Propiedades\) del contenido al que se hace referencia se puede configurar para mostrar la ruta de archivo relativa del contenido al que se hace referencia o el UUID. Esta pantalla está controlada por el **Habilitar UUID** en configMgr. De forma predeterminada, está activado, lo que implica que el UUID del contenido al que se hace referencia se muestra en el panel Propiedades.

Realice los siguientes pasos para mostrar la ruta relativa o el UUID del contenido al que se hace referencia en el editor web:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** paquete.

1. En el *XmlEditorConfig* configuración, la variable **Habilitar UUID** está activada de forma predeterminada. Esto implica que el UUID del contenido al que se hace referencia se muestra en la variable **Vínculo** en el panel Propiedades.

   Si desea mostrar la ruta relativa del contenido vinculado, anule la selección del **Habilitar UUID** opción.

1. Haga clic en **Guardar**.


**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
