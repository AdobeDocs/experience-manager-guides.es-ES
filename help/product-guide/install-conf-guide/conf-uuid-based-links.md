---
title: Configurar la visualización de vínculos basados en UUID
description: Obtenga información sobre cómo configurar la visualización de vínculos basados en UUID
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 1%

---

# Configurar la visualización de vínculos basados en UUID {#id2035G20M0QN}

De forma predeterminada, cuando se crea un vínculo con la opción Insertar referencia o Insertar contenido reutilizado en el Editor, el vínculo se crea con el UUID del contenido al que se hace referencia. La propiedad **Link** \(en el panel Propiedades\) del contenido al que se hace referencia se puede configurar para mostrar la ruta de archivo relativa del contenido al que se hace referencia o el UUID. En Cloud Service, de forma predeterminada, el UUID del contenido al que se hace referencia se muestra en el panel Propiedades. En las instalaciones, esta visualización está controlada por la opción **Habilitar UUID** en `configMgr`. De forma predeterminada, está activado, lo que implica que el UUID del contenido al que se hace referencia se muestra en el panel Propiedades.

Las siguientes pestañas proporcionan instrucciones para mostrar la ruta relativa o el UUID del contenido al que se hace referencia en el Editor en función de la configuración de Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para mostrar la ruta relativa o el UUID del contenido al que se hace referencia en el Editor.

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uuid` | Boolean \(true/false\). Si desea mostrar la ruta relativa del contenido vinculado, establezca esta propiedad en false. <br> **Valor predeterminado**: true |


>[!TAB Local]

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. En la configuración de *XmlEditorConfig*, la opción **Habilitar UUIDs** está habilitada de manera predeterminada. Esto implica que el UUID del contenido al que se hace referencia se muestra en la propiedad **Link** del panel Propiedades.

   Si desea mostrar la ruta relativa del contenido vinculado, anule la selección de la opción **Habilitar UUID**.

1. Haga clic en **Guardar**.

>[!ENDTABS]

**Tema principal:**[ Personalizar editor web](customize-overview.md)
