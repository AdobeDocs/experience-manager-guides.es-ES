---
title: Configuración del número de LimitReads de una consulta
description: Obtenga información sobre cómo configurar el número de LimitReads para una consulta
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 53748636-f3d1-4b3b-a772-2730b78741cb
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 2%

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

**Tema principal:**&#x200B;[&#x200B; Editor personalizado](customize-overview.md)
