---
title: Configurar mensaje para guardar como nueva versión al cerrar
description: Obtenga información sobre cómo configurar el mensaje para guardar como una nueva versión al cerrar
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 1%

---

# Configurar mensaje para guardar como nueva versión al cerrar {#id222HBI00XXA}

Cuando el usuario intenta cerrar un archivo que está abierto en el Editor Web con el botón **Cerrar** de la ficha del archivo o con la opción **Cerrar** del menú Opciones, aparece un cuadro de diálogo si el archivo tiene datos sin guardar o una versión sin guardar. Se solicitará al usuario que guarde el archivo como una nueva versión si la versión no está guardada.

Las siguientes pestañas proporcionan instrucciones basadas en la configuración de Experience Manager Guides: Cloud Service o Local.

>[!BEGINTABS]

>[!TAB Cloud Service]

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar una solicitud de que se guarde como una nueva versión al cerrar:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.savenewversion` | Booleano \( true/ false\). <br>  **Valor predeterminado**: true |

Cuando esta configuración está habilitada, la casilla de verificación **Guardar como nueva versión** está seleccionada de forma predeterminada en el cuadro de diálogo.

Para obtener más información, consulte la sección *Cerrar archivo y guardar escenarios* en la guía Usar Adobe Experience Manager Guides as a Cloud Service.

>[!TAB Local]

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Seleccione la opción **Pedir nueva versión al cerrar**.

1. Haga clic en **Guardar**.


La casilla de verificación **Guardar como nueva versión** no está habilitada de forma predeterminada y debe habilitarla desde configMgr.

Cuando se selecciona esta opción, la casilla de verificación **Guardar como nueva versión** está seleccionada de forma predeterminada en el cuadro de diálogo.

Para obtener más información, consulte la sección *Cerrar archivo y guardar escenarios* en la guía Usar Adobe Experience Manager Guides as a Cloud Service.

>[!ENDTABS]