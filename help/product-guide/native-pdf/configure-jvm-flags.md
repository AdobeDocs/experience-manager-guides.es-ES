---
title: PDF nativo | Configuración de indicadores JVM para la publicación nativa de PDF
description: Configuración de indicadores JVM para la publicación nativa de PDF
feature: Output Generation
role: Admin
level: Experienced
exl-id: d5432913-4b5a-48e7-9467-7f6c6e0adbe4
TQID: https://experienceleague.adobe.com/UvDTutOu-rfQ7tNTMZ6f1dNYJ90dwSGCtTJvWWFm638
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 128
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
