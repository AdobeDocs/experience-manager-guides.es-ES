---
title: Abrir un tema DITA o archivos de asignación en la misma ficha
description: Obtenga información sobre cómo abrir un tema o asignar archivos DITA en la misma pestaña
exl-id: 81ad2e18-3ea7-4cc1-8387-d703d1038a18
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# Abrir un tema DITA o archivos de asignación en la misma ficha {#id223HI0P202H}

En algunos flujos de trabajo, al hacer clic en un vínculo de un tema o de un archivo de mapa, se abre en una nueva pestaña. Esto podría generar muchas pestañas abiertas en el explorador, lo que podría afectar a la productividad. Puede cambiar este comportamiento al abrir un tema o un archivo de asignación en una nueva pestaña y forzarlo a abrirse en la propia pestaña actual. Para ello, realice los siguientes cambios de configuración:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** paquete.

1. Seleccione el **Abrir tema/mapa DITA en la misma ficha** opción.

1. Haga clic en **Guardar**.


Esta configuración afecta a los siguientes lugares desde donde puede acceder a los archivos de tema o asignación:

- Crear tema DITA \(al final del flujo de trabajo, al hacer clic en el **Abrir tema** button\)

- Crear mapa DITA \(al final del flujo de trabajo, al hacer clic en el icono **Abrir mapa** button\)

- Pestaña Temas de la consola de mapas DITA

- Pestaña Líneas bases de la consola de mapas DITA

- Pestaña Informes de la consola de mapas DITA


**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
