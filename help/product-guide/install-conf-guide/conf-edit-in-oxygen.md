---
title: Configurar la opción de edición en Oxígeno
description: Aprenda a configurar la opción de edición en el complemento Conector de oxígeno.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 1%

---

# Configuración de la opción de edición en Oxígeno para Cloud Service

AEM Guides también permite a los usuarios editar sus temas DITA y mapas DITA en el complemento Conector de oxígeno.

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles (propiedad) para configurar la opción **Editar en oxígeno**:



| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.editinoxygen` | Boolean \(true/false\). **Valor predeterminado**: false |

>[!NOTE]
>
> Esta configuración está deshabilitada de forma predeterminada y la opción no está disponible en el Editor web.

**Tema principal:**[ Personalizar editor web](customize-overview.md)
