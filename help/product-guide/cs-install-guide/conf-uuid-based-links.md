---
title: Configurar la visualización de vínculos basados en UUID
description: Obtenga información sobre cómo configurar la visualización de vínculos basados en UUID
exl-id: 2ae6a27f-983b-4aa0-be29-166899aeb4ff
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 1%

---

# Configurar la visualización de vínculos basados en UUID {#id2035G20M0QN}

De forma predeterminada, cuando se crea un vínculo con la opción Insertar referencia o Insertar contenido reutilizado del Editor Web, el vínculo se crea con el UUID del contenido al que se hace referencia. La propiedad **Link** \(en el panel Propiedades\) del contenido al que se hace referencia se puede configurar para mostrar la ruta de archivo relativa del contenido al que se hace referencia o el UUID. De forma predeterminada, el UUID del contenido al que se hace referencia se muestra en el panel Propiedades.

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para mostrar la ruta relativa o el UUID del contenido al que se hace referencia en el Editor web:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uuid` | Boolean \(true/false\). Si desea mostrar la ruta relativa del contenido vinculado, establezca esta propiedad en false. <br> **Valor predeterminado**: true |

**Tema principal:**&#x200B;[&#x200B; Personalizar editor web](conf-web-editor.md)
