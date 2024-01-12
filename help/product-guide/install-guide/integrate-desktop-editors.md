---
title: Integración de editores XML basados en escritorio
description: Aprenda a integrar editores XML basados en escritorio
exl-id: 268e8613-bb3b-4577-96fb-a588dabfd834
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
source-git-commit: 82c7feab6599440c52ecbec845b5e3b8bb4a5046
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# Integración de editores XML basados en escritorio {#id181GB01G0HS}

Hay muchos editores XML disponibles en el mercado, y es posible que ya esté utilizando uno. Adobe FrameMaker AEM es uno de los editores XML más poderosos, que viene con conector de la. AEM Con el conector de la en FrameMaker AEM, puede conectarse fácilmente con el repositorio de la, extraer y archivar archivos, y editar archivos directamente en FrameMaker. AEM También puede configurar las guías del usuario para que inicien el FrameMaker desde el Editor web. Una vez que haya abierto el archivo en el FrameMaker AEM, puede editarlo y volver a registrarlo en el repositorio de.

## Habilitar la edición de archivos en el FrameMaker desde el Editor web

Puede utilizar el FrameMaker o cualquier otro editor DITA para crear y actualizar contenido DITA. Sin embargo, si su organización utiliza el FrameMaker como editor DITA, puede ofrecer a los usuarios una opción para abrir documentos DITA directamente en el FrameMaker AEM desde el punto de vista de la.

De forma predeterminada, los usuarios no ven el **Abrir en FrameMaker** AEM en la barra de herramientas de la. AEM Siga estos pasos para agregar este botón en la barra de herramientas de la barra de herramientas de la:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** paquete.

   ![](assets/open-in-fm-toolbar.png){width="550" align="left"}

1. Seleccione el **Mostrar botón Abrir en FrameMaker** opción.

1. Haga clic en **Guardar**.


Al activar la variable **Mostrar botón Abrir en FrameMaker** y luego la opción **Abrir en FrameMaker** AEM se muestra al seleccionar cualquier fichero DITA en el repositorio de. Cuando esta opción es *sin activar*, el **Abrir en FrameMaker** El botón solo se muestra al seleccionar un archivo .fm o .book en el repositorio.
