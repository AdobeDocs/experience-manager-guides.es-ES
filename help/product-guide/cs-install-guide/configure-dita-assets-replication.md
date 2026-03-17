---
title: Configuración de la replicación de DITA Assets para Cloud Service
description: Obtenga información sobre cómo configurar la replicación de recursos de datos para Cloud Service
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 356ea6edd5e688fb1f77e737c705ed0bd4d2e7f0
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
