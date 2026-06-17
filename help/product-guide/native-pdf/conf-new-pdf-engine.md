---
title: Activar el nuevo motor de PDF
description: Obtenga información sobre cómo habilitar el nuevo motor de PDF en Experience Manager Guides
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: f3f30400f776f746427e257e2c937ff3413aa9ac
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 2%

---


# Configuración del motor de PDF nativo v2

El nuevo motor de publicación para PDF nativo, es decir _Native PDF engine v2_, proporciona funciones actualizadas de procesamiento de PDF y correcciones para los problemas de _Native PDF engine v1_.

Siga las instrucciones indicadas en [Anulaciones de configuración](../install-conf-guide/download-install-config-override.md) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles (propiedad):

| PID | Clave de propiedad | Valor de propiedad |
|-----|--------------|----------------|
| `com.adobe.fmdita.publish.config.GuidesPublishConfiguratorService` | `guides.publish.config` | `{"PDF_ENGINE": "v2"}` <br> Valor predeterminado: `v1` |