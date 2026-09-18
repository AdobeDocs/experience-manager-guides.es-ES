---
title: PDF nativo | Configuración de indicadores JVM para la publicación nativa de PDF
description: Configuración de indicadores JVM para la publicación nativa de PDF
feature: Output Generation
role: Admin
level: Experienced
exl-id: a2a9f44c-cb17-4423-a66e-499bce921398
source-git-commit: 82c93529b8535532cf50f6428c41a1881b24859e
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 1%
---
# Configuración de indicadores JVM para la publicación nativa de PDF para in situ

La publicación nativa de PDF inicia un proceso JVM independiente para generar un PDF. Es posible que tenga que modificar las configuraciones de esta JVM para que admitan diferentes escenarios. Por ejemplo, para ejecutar cargas de trabajo más grandes debe aumentar el tamaño máximo de pila disponible para el proceso de JVM generado.

Siga estos pasos para configurar los indicadores JVM de publicación de AEM Guides Native PDF:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete *com.adobe.fmdita.config.ConfigManager*.

1. Actualice la propiedad **Opciones de la línea de comandos de Java para el pdf nativo** (*native.pdf.java.opts*) para pasar cualquier indicador JVM estándar.



1. Haga clic en **Guardar**.
