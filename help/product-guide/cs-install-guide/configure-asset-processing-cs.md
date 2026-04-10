---
title: Configurar el procesamiento de recursos para Cloud Service
description: Obtenga información sobre cómo configurar el procesamiento de recursos para Cloud Service
feature: Output Generation
role: Admin
level: Experienced
exl-id: 219a096f-4087-489f-9b3b-104864817198
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 3%

---

# Configurar la función de procesamiento de recursos

Para configurar la función de procesamiento de recursos, realice los siguientes pasos:

1. Siga las instrucciones indicadas en [Anulaciones de configuración](../cs-install-guide/download-install-additional-config-override.md) para crear el archivo de configuración.

1. En el archivo de configuración, proporcione los siguientes detalles (propiedad):

   | PID | Clave de propiedad | Valor de propiedad |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `enable.asset.processing.scheduler` | **Valor predeterminado:** &quot;true&quot; |
