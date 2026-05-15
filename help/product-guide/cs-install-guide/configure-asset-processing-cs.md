---
title: Configurar el procesamiento de recursos para Cloud Service
description: Obtenga información sobre cómo configurar el procesamiento de recursos para Cloud Service
feature: Output Generation
role: Admin
level: Experienced
exl-id: 219a096f-4087-489f-9b3b-104864817198
TQID: https://experienceleague.adobe.com/pwwaOoH35wROxMMw4ZWNTwCmXWUBxR6y23UWvPiqTR4
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 58
ht-degree: 3%

---

# Configurar la función de procesamiento de recursos

Para configurar la función de procesamiento de recursos, realice los siguientes pasos:

1. Siga las instrucciones indicadas en [Anulaciones de configuración](../cs-install-guide/download-install-additional-config-override.md) para crear el archivo de configuración.

1. En el archivo de configuración, proporcione los siguientes detalles (propiedad):

   | PID | Clave de propiedad | Valor de propiedad |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `enable.asset.processing.scheduler` | **Valor predeterminado:** &quot;true&quot; |
