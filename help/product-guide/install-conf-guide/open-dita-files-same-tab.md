---
title: Abrir un tema DITA o archivos de asignación en la misma ficha
description: Obtenga información sobre cómo abrir un tema o asignar archivos DITA en la misma pestaña
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 13f7eab1-2235-4537-9520-69d1df04e921
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
source-wordcount: '276'
ht-degree: 1%
---
# Abrir un tema DITA o archivos de asignación en la misma ficha {#id223HI0P202H}

En algunos flujos de trabajo, al hacer clic en un vínculo de un tema o de un archivo de mapa, se abre en una nueva pestaña. Esto podría generar muchas pestañas abiertas en el explorador, lo que podría afectar a la productividad. Puede cambiar este comportamiento al abrir un tema o un archivo de asignación en una nueva pestaña y forzarlo a abrirse en la propia pestaña actual.

Las siguientes pestañas proporcionan instrucciones para abrir un tema o archivo de asignación DITA en la misma pestaña en función de la configuración de Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para abrir un tema o archivo de asignación en una nueva pestaña:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinsametab` | Booleano \(true/false\). <br> **Valor predeterminado**: `false` |

>[!TAB Local]

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Seleccione la opción **Abrir tema/mapa DITA en la misma ficha**.

1. Haga clic en **Guardar**.

>[!ENDTABS]

Esta configuración afecta a los siguientes lugares desde donde puede acceder a los archivos de tema o asignación:

- Crear tema DITA \(al final del flujo de trabajo, al hacer clic en el botón **Abrir tema**\)

- Crear mapa DITA \(al final del flujo de trabajo, al hacer clic en el botón **Abrir mapa**\)

- Pestaña Temas de la consola de mapas DITA

- Pestaña Líneas bases de la consola de mapas DITA

- Pestaña Informes de la consola de mapas DITA

**Tema principal:**&#x200B;[&#x200B; Editor personalizado](customize-overview.md)
