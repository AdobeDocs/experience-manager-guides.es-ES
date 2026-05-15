---
title: Abrir un tema DITA o archivos de asignación en la misma ficha
description: Obtenga información sobre cómo abrir un tema o asignar archivos DITA en la misma pestaña
exl-id: 81ad2e18-3ea7-4cc1-8387-d703d1038a18
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/-QYM6xoQCkvRcpxpsWtnJb5le7-4RirhgOZk94UvzIg
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0eid: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 211
ht-degree: 0%

---

# Abrir un tema DITA o archivos de asignación en la misma ficha {#id223HI0P202H}

En algunos flujos de trabajo, al hacer clic en un vínculo de un tema o de un archivo de mapa, se abre en una nueva pestaña. Esto podría generar muchas pestañas abiertas en el explorador, lo que podría afectar a la productividad. Puede cambiar este comportamiento al abrir un tema o un archivo de asignación en una nueva pestaña y forzarlo a abrirse en la propia pestaña actual. Para ello, realice los siguientes cambios de configuración:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Seleccione la opción **Abrir tema/mapa DITA en la misma ficha**.

1. Haga clic en **Guardar**.


Esta configuración afecta a los siguientes lugares desde donde puede acceder a los archivos de tema o asignación:

- Crear tema DITA \(al final del flujo de trabajo, al hacer clic en el botón **Abrir tema**\)

- Crear mapa DITA \(al final del flujo de trabajo, al hacer clic en el botón **Abrir mapa**\)

- Pestaña Temas de la consola de mapas DITA

- Pestaña Líneas bases de la consola de mapas DITA

- Pestaña Informes de la consola de mapas DITA


**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
