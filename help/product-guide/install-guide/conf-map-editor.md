---
title: Establecer el Editor de mapas avanzado como predeterminado
description: Aprenda a establecer el Editor de mapas avanzado como predeterminado
exl-id: ecc023f6-48eb-4afd-97a2-4b3cdd5a8991
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# Establecer el Editor de mapas avanzado como predeterminado {#id181AI0003PN}

AEM Las guías de la aplicación incluyen un Editor de Mapas Básico y un Editor de Mapas Avanzado. El editor de mapas básico le ofrece todas las funciones necesarias para crear su archivo de mapa. El editor de mapas avanzado es mucho más rico en funciones y está integrado dentro del editor web. El Editor de mapas avanzado permite a los autores crear y editar ficheros de mapa DITA con una interfaz fácil de usar.

De forma predeterminada, cada vez que se crea un nuevo archivo de asignación, se abre en el Editor de mapas básico. Puede cambiar este comportamiento si habilita la configuración para abrir el Editor de mapas avanzado de forma predeterminada.

Realice los siguientes pasos para hacer que el Editor de Mapas Avanzado sea el editor predeterminado para los archivos de asignación:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** paquete.

1. Seleccione el **Ocultar editor de mapas básico** opción.

   Con esta opción seleccionada, los usuarios no verán el vínculo Editor de mapas básico en ninguna parte de la interfaz de usuario. De forma predeterminada, los archivos de asignación se abrirán en el Editor de mapas avanzado.
