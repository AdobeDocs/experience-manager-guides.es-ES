---
title: Configuración del número de LimitReads de una consulta
description: Obtenga información sobre cómo configurar el número de LimitReads para una consulta
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 1%

---

# Configure el número de LimitReads para una consulta de local

Para aumentar el número de nodos que una consulta puede leer a la vez, realice los siguientes pasos:

1. Abra la página Adobe Experience Manager Web Console JMX.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/jmx
   ```

1. Busque **QueryEngineSettings** y haga clic en él.

1. Cambie el valor del atributo **LimitReads**.

1. Haga clic en **Guardar**.


Cuando se aumenta este valor de atributo, se ayuda a generar el informe para mapas DITA más grandes.

**Tema principal:**[ Personalizar editor web](customize-overview.md)
