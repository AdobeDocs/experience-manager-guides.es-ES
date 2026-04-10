---
title: Configuración de la replicación de DITA Assets para Cloud Service
description: Obtenga información sobre cómo configurar la replicación de recursos de datos para Cloud Service
feature: Output Generation
role: Admin
level: Experienced
exl-id: 1eafc6b2-2b85-486a-bb2c-0038fae1fef9
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 3%

---

# Configuración de la replicación de recursos DITA

Para configurar la función de procesamiento de recursos, realice los siguientes pasos:

1. Siga las instrucciones indicadas en [Anulaciones de configuración](../cs-install-guide/download-install-additional-config-override.md) para crear el archivo de configuración.

1. En el archivo de configuración, proporcione los siguientes detalles (propiedad):

   | PID | Clave de propiedad | Valor de propiedad |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `publish.replicate` | **Valor predeterminado:** &quot;true&quot; |
