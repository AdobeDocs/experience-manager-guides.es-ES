---
title: Configurar la opción de edición en Oxígeno
description: Aprenda a configurar la opción de edición en el complemento Conector de oxígeno.
exl-id: 96081a6d-39cf-4697-8b43-6494543ea187
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/cBWLIunbSxmmPxc5JTFc7z45xhLwWo7EEQj8zR-DpaY
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
source-wordcount: 103
ht-degree: 1%

---

# Configurar la opción de edición en Oxígeno

AEM Guides también permite a los usuarios editar sus temas DITA y mapas DITA en el complemento Conector de oxígeno.

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles (propiedad) para configurar la opción **Editar en oxígeno**:



| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.editinoxygen` | Boolean \(true/false\). **Valor predeterminado**: false |

>[!NOTE]
>
> Esta configuración está deshabilitada de forma predeterminada y la opción no está disponible en el Editor web.

**Tema principal:**&#x200B;[&#x200B; Personalizar editor web](conf-web-editor.md)
