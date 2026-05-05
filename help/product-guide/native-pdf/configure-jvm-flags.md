---
title: PDF nativo | Configuración de indicadores JVM para la publicación nativa de PDF
description: Configuración de indicadores JVM para la publicación nativa de PDF
feature: Output Generation
role: Admin
level: Experienced
exl-id: d5432913-4b5a-48e7-9467-7f6c6e0adbe4
source-git-commit: ccaf2ead1a9a24ab822298c6b9ef6866a1c32e8c
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
