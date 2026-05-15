---
title: Configurar la visualización de vínculos basados en UUID
description: Obtenga información sobre cómo configurar la visualización de vínculos basados en UUID
exl-id: ab1b0ecf-cb50-4fcd-b36e-d16a8c396054
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/QlYbIRVwAM10wfcu-Fz3CzOkCCUDZHbVzZo3xCxT3wI
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
source-wordcount: 211
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
