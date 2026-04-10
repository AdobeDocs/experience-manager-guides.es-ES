---
title: Configuración del número de LimitReads de una consulta
description: Obtenga información sobre cómo configurar el número de LimitReads para una consulta
exl-id: f6010cc3-5fec-4ec7-adf7-5ad3c9bd8879
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 2%

---

# Configuración del número de LimitReads de una consulta {#id231RC0HL0ID}

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

**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
