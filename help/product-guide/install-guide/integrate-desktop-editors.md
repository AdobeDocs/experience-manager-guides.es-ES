---
title: Integración de editores XML basados en escritorio
description: Aprenda a integrar editores XML basados en escritorio
exl-id: 268e8613-bb3b-4577-96fb-a588dabfd834
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/wILI1Y5nUtUiEuHG0wN4q2KCQko5mKN6CKy1Cs5kxTU
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: bf79f6d3-0ad0-4d82-99e4-42ce98324d60id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 322
ht-degree: 2%

---

# Integración de editores XML basados en escritorio {#id181GB01G0HS}

Hay muchos editores XML disponibles en el mercado, y es posible que ya esté utilizando uno. Adobe FrameMaker es uno de los editores XML más potentes, que viene con el conector de AEM. Con el conector de AEM en FrameMaker, puede conectarse fácilmente con el repositorio de AEM, retirar y registrar archivos y editar archivos directamente en FrameMaker. También puede configurar Experience Manager Guides para que inicie FrameMaker desde el Editor web. Una vez que haya abierto el archivo en FrameMaker, puede editarlo y volver a registrarlo en el repositorio de AEM.

## Habilitar la edición de archivos en FrameMaker desde el editor web

Puede utilizar FrameMaker o cualquier otro editor DITA para crear y actualizar contenido DITA. Sin embargo, si su organización utiliza FrameMaker como editor DITA, puede proporcionar a los usuarios una opción para abrir documentos DITA directamente en FrameMaker desde AEM.

De manera predeterminada, los usuarios no ven el botón **Abrir en FrameMaker** en la barra de herramientas de AEM. Siga estos pasos para agregar este botón en la barra de herramientas de AEM:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.
   ![](assets/open-in-fm-config.png)

1. Seleccione la opción **Mostrar botón Abrir en FrameMaker**.

1. Si usa la versión 4.6 y la actualización 3 de septiembre de FrameMaker 2022, debe habilitar la configuración de **FrameMaker versión 2022 actualización 3 o superior** para que los usuarios pasen los detalles del servidor de Experience Manager Guides a FrameMaker. De forma predeterminada, está desactivada.


1. Haga clic en **Guardar**.


Cuando activa la opción **Mostrar botón Abrir en FrameMaker**, se muestra el botón **Abrir en FrameMaker** al seleccionar cualquier archivo DITA en el repositorio de AEM. Si esta opción está *no habilitada*, el botón **Abrir en FrameMaker** solo se muestra al seleccionar un archivo .fm o .book en el repositorio.



