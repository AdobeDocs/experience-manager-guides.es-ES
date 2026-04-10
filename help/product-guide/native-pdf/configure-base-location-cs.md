---
title: PDF nativo | Configuración de la ubicación de salida base para la publicación de PDF para Cloud Services
description: Configuración de la ubicación de salida base para la publicación de PDF para Cloud Services
feature: Output Generation
role: Admin
level: Experienced
exl-id: d79085d6-938a-4e80-84a2-03562e6b76e0
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 2%

---

# Configurar la ubicación de salida base para publicar la salida para Cloud Services

Para configurar la ubicación de salida base, realice los siguientes pasos:

1. Siga las instrucciones indicadas en [Anulaciones de configuración](../cs-install-guide/download-install-additional-config-override.md) para crear el archivo de configuración.

1. En el archivo de configuración, proporcione los siguientes detalles (propiedad) para configurar la ubicación de salida base:

   | PID | Clave de propiedad | Valor de propiedad |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `base.output.path` | **Valor predeterminado:** &quot;/content/dam/fmdita-output&quot; |
