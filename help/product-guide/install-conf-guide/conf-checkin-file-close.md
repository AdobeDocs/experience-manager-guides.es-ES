---
title: Configurar la solicitud para proteger un archivo al cerrar
description: Obtenga información sobre cómo configurar el mensaje para proteger un archivo al cerrar
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 6b1b5894-0d55-4230-83cf-6b219e969116
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%
---
# Configurar la solicitud para proteger un archivo al cerrar {#id222HC040PE8}

Cuando el usuario intenta cerrar un archivo que está abierto en el Editor con el botón **Cerrar** de la ficha del archivo o con la opción **Cerrar** del menú Opciones, aparece un cuadro de diálogo si el archivo tiene datos sin guardar o una versión sin guardar. Se solicitará al usuario que desbloquee el archivo si está bloqueado.

Las siguientes pestañas proporcionan instrucciones para configurar el indicador para proteger un archivo al cerrarlo de forma predeterminada en el Editor en función de la configuración de Experience Manager Guides: Cloud Service o On-Premise.

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
>La casilla de verificación **Desbloquear el archivo** no está habilitada de manera predeterminada y debe habilitarla desde configMgr. Realice los siguientes pasos para habilitar la opción de forma predeterminada en el Editor:

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

**Tema principal:**&#x200B;[&#x200B; Editor personalizado](customize-overview.md)
