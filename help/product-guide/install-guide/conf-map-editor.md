---
title: Establecer el Editor de mapas avanzado como predeterminado
description: Aprenda a establecer el Editor de mapas avanzado como predeterminado
exl-id: ecc023f6-48eb-4afd-97a2-4b3cdd5a8991
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 126cecdaa481b9da1add4ba3664c26c2bc5da068
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 0%

---

# Establecer el Editor de mapas avanzado como predeterminado {#id181AI0003PN}

>[!NOTE]
>
> El Editor de mapas básico, disponible anteriormente en Experience Manager Guides, ha quedado obsoleto a partir de la versión 4.3 y 2307. No se puede acceder al Editor de mapas básico para crear y gestionar mapas DITA.
>Se recomienda utilizar el Editor de mapas avanzado. El editor de mapas avanzado ofrece funciones mejoradas y mejores opciones de personalización. Más información sobre cómo usar el [Editor de mapas avanzado](../user-guide/map-editor-advanced-map-editor.md).

Para las versiones anteriores a la 4.3 y 2307, Experience Manager Guides viene con un Editor de mapas básico y un Editor de mapas avanzado. El editor de mapas básico le ofrece todas las funciones necesarias para crear su archivo de mapa. El editor de mapas avanzado es mucho más rico en funciones y está integrado dentro del editor web. El Editor de mapas avanzado permite a los autores crear y editar ficheros de mapa DITA con una interfaz fácil de usar.

De forma predeterminada, cada vez que se crea un nuevo archivo de asignación, se abre en el Editor de mapas básico. Puede cambiar este comportamiento si habilita la configuración para abrir el Editor de mapas avanzado de forma predeterminada.

Realice los siguientes pasos para hacer que el Editor de Mapas Avanzado sea el editor predeterminado para los archivos de asignación:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Seleccione la opción **Ocultar editor de mapas básico**.

   Con esta opción seleccionada, los usuarios no verán el vínculo Editor de mapas básico en ninguna parte de la interfaz de usuario. De forma predeterminada, los archivos de asignación se abrirán en el Editor de mapas avanzado.
