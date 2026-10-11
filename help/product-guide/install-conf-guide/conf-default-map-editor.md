---
title: Establecer el Editor de mapas avanzado como predeterminado
description: Aprenda a establecer el Editor de mapas avanzado como predeterminado
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 60205ca4-518f-49fa-b63b-f1a56d70fc01
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
source-wordcount: '391'
ht-degree: 0%
---
# Establecer el Editor de mapas avanzado como predeterminado {#id181AI0003PN}

>[!NOTE]
>
> El Editor de mapas básico, disponible anteriormente en Experience Manager Guides, ha quedado obsoleto a partir de la versión 4.3 y 2307. No se puede acceder al Editor de mapas básico para crear y gestionar mapas DITA.
>Se recomienda utilizar el Editor de mapas avanzado. El editor de mapas avanzado ofrece funciones mejoradas y mejores opciones de personalización. Más información sobre cómo usar el [Editor de mapas avanzado](../user-guide/map-editor-advanced-map-editor.md).

Para las versiones anteriores a la 4.3 y 2307, Experience Manager Guides viene con un Editor de mapas básico y un Editor de mapas avanzado. El editor de mapas básico le ofrece todas las funciones necesarias para crear su archivo de mapa. El editor de mapas avanzado es mucho más rico en funciones y está integrado dentro del editor. El Editor de mapas avanzado permite a los autores crear y editar ficheros de mapa DITA con una interfaz fácil de usar.

De forma predeterminada, cada vez que se crea un nuevo archivo de asignación, se abre en el Editor de mapas básico. Puede cambiar este comportamiento si habilita la configuración para abrir el Editor de mapas avanzado de forma predeterminada.

Las siguientes pestañas proporcionan instrucciones para hacer que el Editor de mapas avanzado sea el editor predeterminado para los archivos de mapa en función de la configuración de Experience Manager Guides: Cloud Service o On-Premise.


>[!BEGINTABS]

>[!TAB Cloud Service]

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para habilitar el Editor de mapas básico:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | ``fmdita.hide.oldmapeditor`` | Boolean \(true/false\). Si desea usar el Editor de mapas avanzado de forma predeterminada, establezca esta propiedad en true.<br> **Valor predeterminado**: false |

>[!NOTE]
>
> De forma predeterminada, cuando un autor crea un archivo de mapa y elige abrirlo para editarlo, se inicia el Editor de mapas básico. Cuando se selecciona la opción Editar para un archivo de mapa desde la interfaz de usuario de Assets, también se abre en el Editor de mapas básico.

>[!TAB Local]

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Seleccione la opción **Ocultar editor de mapas básico**.

   Con esta opción seleccionada, los usuarios no verán el vínculo Editor de mapas básico en ninguna parte de la interfaz de usuario. De forma predeterminada, los archivos de asignación se abrirán en el Editor de mapas avanzado.

>[!ENDTABS]

**Tema principal:**&#x200B;[&#x200B; Editor personalizado](customize-overview.md)
