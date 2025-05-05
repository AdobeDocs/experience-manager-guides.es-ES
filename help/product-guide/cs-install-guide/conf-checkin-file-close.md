---
title: Configurar la solicitud para proteger un archivo al cerrar
description: Obtenga información sobre cómo configurar el mensaje para proteger un archivo al cerrar
exl-id: 5b09ec46-aea4-4a3f-8bab-42414e31e37d
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 1%

---

# Configurar la solicitud para proteger un archivo al cerrar {#id222HC040PE8}

Cuando el usuario intenta cerrar un archivo que está abierto en el Editor Web con el botón **Cerrar** de la ficha del archivo o con la opción **Cerrar** del menú Opciones, aparece un cuadro de diálogo si el archivo tiene datos sin guardar o una versión sin guardar. Se solicitará al usuario que desbloquee el archivo si está bloqueado.

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar una solicitud de protección de un archivo al cerrar:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.checkin` | Booleano \( true/ false\).<br> **Valor predeterminado**: false |

Cuando esta configuración está habilitada, la casilla de verificación **Desbloquear el archivo** está seleccionada de forma predeterminada en el cuadro de diálogo.

Para obtener más información, consulte la sección *Cerrar archivo y guardar escenarios* en la guía as a Cloud Service sobre el uso de Adobe Experience Manager Guides.

**Tema principal:**&#x200B;[ Personalizar editor web](conf-web-editor.md)
