---
title: Configurar la solicitud para proteger un archivo al cerrar
description: Obtenga información sobre cómo configurar el mensaje para proteger un archivo al cerrar
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 1%

---

# Configurar la solicitud para proteger un archivo al cerrar {#id222HC040PE8}

Cuando el usuario intenta cerrar un archivo que está abierto en el Editor Web con el botón **Cerrar** de la ficha del archivo o con la opción **Cerrar** del menú Opciones, aparece un cuadro de diálogo si el archivo tiene datos sin guardar o una versión sin guardar. Se solicitará al usuario que desbloquee el archivo si está bloqueado.

Las siguientes pestañas proporcionan instrucciones para configurar el indicador para proteger un archivo en la opción de cierre de forma predeterminada en el Editor web en función de la configuración de Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar una solicitud de protección de un archivo al cerrar:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.checkin` | Booleano \( true/ false\).<br> **Valor predeterminado**: false |

Cuando esta configuración está habilitada, la casilla de verificación **Desbloquear el archivo** está seleccionada de forma predeterminada en el cuadro de diálogo.

Para obtener más información, consulte la sección *Cerrar archivo y guardar escenarios* en la guía Usar Adobe Experience Manager Guides as a Cloud Service.

>[!TAB Local]

>[!NOTE]
>
>La casilla de verificación **Desbloquear el archivo** no está habilitada de manera predeterminada y debe habilitarla desde configMgr. Realice los siguientes pasos para habilitar la opción de forma predeterminada en el Editor web:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Seleccione la opción **Pedir protección al cerrar**.

1. Haga clic en **Guardar**.


Cuando esta configuración está habilitada, la casilla de verificación **Desbloquear el archivo** está seleccionada de forma predeterminada en el cuadro de diálogo.

Para obtener más información, consulte la sección *Cerrar archivo y guardar escenarios* en la guía Usar Adobe Experience Manager Guides as a Cloud Service.

>[!ENDTABS]

**Tema principal:**[ Personalizar editor web](customize-overview.md)
