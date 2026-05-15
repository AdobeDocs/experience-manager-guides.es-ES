---
title: Configurar la visualización de vínculos basados en UUID
description: Obtenga información sobre cómo configurar la visualización de vínculos basados en UUID
exl-id: 2ae6a27f-983b-4aa0-be29-166899aeb4ff
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/--RdjezGIsplCdBLF8u-3LvR92rVBcgGmPo8a7GbQys
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 162
ht-degree: 1%

---

# Configurar la visualización de vínculos basados en UUID {#id2035G20M0QN}

De forma predeterminada, cuando se crea un vínculo con la opción Insertar referencia o Insertar contenido reutilizado del Editor Web, el vínculo se crea con el UUID del contenido al que se hace referencia. La propiedad **Link** \(en el panel Propiedades\) del contenido al que se hace referencia se puede configurar para mostrar la ruta de archivo relativa del contenido al que se hace referencia o el UUID. De forma predeterminada, el UUID del contenido al que se hace referencia se muestra en el panel Propiedades.

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para mostrar la ruta relativa o el UUID del contenido al que se hace referencia en el Editor web:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uuid` | Boolean \(true/false\). Si desea mostrar la ruta relativa del contenido vinculado, establezca esta propiedad en false. <br> **Valor predeterminado**: true |

**Tema principal:**&#x200B;[&#x200B; Personalizar editor web](conf-web-editor.md)
