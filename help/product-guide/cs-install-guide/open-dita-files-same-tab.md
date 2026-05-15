---
title: Abrir un tema DITA o archivos de asignación en la misma ficha
description: Obtenga información sobre cómo abrir un tema o asignar archivos DITA en la misma pestaña
exl-id: 466cbea4-c75a-488e-bde2-465cf2c184d5
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/futODy2B62sg-Epb4bnmxHVAOUVoGDoKg5WJWV-7bpM
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0eid: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 207
ht-degree: 0%

---

# Abrir un tema DITA o archivos de asignación en la misma ficha {#id223HH0301J3}

En algunos flujos de trabajo, al hacer clic en un vínculo de un tema o de un archivo de mapa, se abre en una nueva pestaña. Esto podría generar muchas pestañas abiertas en el explorador, lo que podría afectar a la productividad. Puede cambiar este comportamiento al abrir un tema o un archivo de asignación en una nueva pestaña y forzarlo a abrirse en la propia pestaña actual.

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para abrir un tema o archivo de asignación en una nueva pestaña:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinsametab` | Booleano \(true/false\). <br> **Valor predeterminado**: `false` |

Esta configuración afecta a los siguientes lugares desde donde puede acceder a los archivos de tema o asignación:

- Crear tema DITA \(al final del flujo de trabajo, al hacer clic en el botón **Abrir tema**\)

- Crear mapa DITA \(al final del flujo de trabajo, al hacer clic en el botón **Abrir mapa**\)

- Pestaña Temas de la consola de mapas DITA

- Pestaña Líneas bases de la consola de mapas DITA

- Pestaña Informes de la consola de mapas DITA


**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
