---
title: Establecer el Editor de mapas avanzado como predeterminado
description: Aprenda a establecer el Editor de mapas avanzado como predeterminado
exl-id: 365264ab-f990-42c1-ab79-61a40ecea42f
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---

# Establecer el Editor de mapas avanzado como predeterminado {#id181AI0003PN}

AEM Guides viene con un editor de mapas básico y un editor de mapas avanzado. El editor de mapas básico le ofrece todas las funciones necesarias para crear su archivo de mapa. El editor de mapas avanzado es mucho más rico en funciones y está integrado dentro del editor web. El Editor de mapas avanzado permite a los autores crear y editar ficheros de mapa DITA con una interfaz fácil de usar.

De forma predeterminada, cada vez que se crea un nuevo archivo de asignación, se abre en el Editor de mapas básico. Puede cambiar este comportamiento si habilita la configuración para abrir el Editor de mapas avanzado de forma predeterminada.

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para habilitar el Editor de mapas básico:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | ``fmdita.hide.oldmapeditor`` | Boolean \(true/false\). Si desea usar el Editor de mapas avanzado de forma predeterminada, establezca esta propiedad en true.<br> **Valor predeterminado**: false |

>[!NOTE]
>
> De forma predeterminada, cuando un autor crea un archivo de mapa y elige abrirlo para editarlo, se inicia el Editor de mapas básico. Cuando se selecciona la opción Editar para un archivo de mapa desde la interfaz de usuario de Assets, también se abre en el Editor de mapas básico.

**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
