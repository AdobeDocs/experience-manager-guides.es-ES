---
title: Integración de editores XML basados en escritorio
description: Aprenda a integrar editores XML basados en escritorio
exl-id: 268e8613-bb3b-4577-96fb-a588dabfd834
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '317'
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



