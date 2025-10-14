---
title: Configurar mensaje para guardar como nueva versión al cerrar
description: Obtenga información sobre cómo configurar el mensaje para guardar como una nueva versión al cerrar
exl-id: 9029b671-8ff8-45eb-b27e-ab89bd09e7ed
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 1%

---

# Configurar mensaje para guardar como nueva versión al cerrar {#id222HBI00XXA}

Cuando el usuario intenta cerrar un archivo que está abierto en el Editor Web con el botón **Cerrar** de la ficha del archivo o con la opción **Cerrar** del menú Opciones, aparece un cuadro de diálogo si el archivo tiene datos sin guardar o una versión sin guardar. Se solicitará al usuario que guarde el archivo como una nueva versión si la versión no está guardada.

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar una solicitud de que se guarde como una nueva versión al cerrar:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.savenewversion` | Booleano \( true/ false\). <br>  **Valor predeterminado**: true |

Cuando esta configuración está habilitada, la casilla de verificación **Guardar como nueva versión** está seleccionada de forma predeterminada en el cuadro de diálogo.

Para obtener más información, consulte la sección *Cerrar archivo y guardar escenarios* en la guía as a Cloud Service sobre el uso de Adobe Experience Manager Guides.

**Tema principal:**&#x200B;[&#x200B; Personalizar editor web](conf-web-editor.md)
