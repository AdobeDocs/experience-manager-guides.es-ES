---
title: Cargar archivos
description: Obtenga información sobre cómo cargar los archivos en el repositorio de AEM y gestionar errores. Conozca la interfaz de usuario de la consola de recursos, la aplicación de escritorio de AEM, el ingestor masivo de recursos y el uso de FrameMaker para la carga masiva.
exl-id: b5430242-1122-43df-a0b2-275b1dea33f2
feature: Content Management
role: User
source-git-commit: 0259c0c0b7270d860198f17e6ea5f5829df038d5
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 1%

---

# Cargar archivos {#id176FF000JUI}

Lo más probable es que tenga un repositorio de contenido DITA existente que desee utilizar con Adobe Experience Manager Guides. Para dicho contenido existente, puede utilizar cualquiera de los siguientes métodos para cargar el contenido en lote en el repositorio de Adobe Experience Manager.

>[!IMPORTANT]
>
> Vea [Agregar recursos digitales a Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html) para obtener información detallada en los métodos de carga de contenido admitidos en Adobe Experience Manager.

## Interfaz de usuario de la consola Assets

Para [agregar recursos digitales a Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html#filename-handling#upload-assets) mediante la interfaz de usuario de la consola de Assets, seleccione el recurso necesario en el escritorio y arrastre en la interfaz de usuario de Adobe Experience Manager \(explorador web\) a la carpeta de destino. Al cargar recursos, asegúrese de que los nombres de archivo no incluyan caracteres no admitidos o prohibidos.

Para obtener más información, consulte la sección [Administración de nombres de archivo y caracteres prohibidos](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html#filename-handling) en la documentación de Adobe Experience Manager.

## Aplicación de escritorio de Adobe Experience Manager

Utilice la aplicación de escritorio de Adobe Experience Manager si es un profesional creativo y desea administrar los recursos en su escritorio local. Puede abrir y editar estos recursos con las aplicaciones de escritorio. También puede mantener las versiones y compartir los archivos con otros usuarios. Para obtener más información, vea [Aplicación de escritorio de Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html).

## Ingestor masivo de recursos

Si tiene migraciones a gran escala e ingestas masivas ocasionales, utilice el Ingestor masivo de recursos para cargar el contenido. Con esta herramienta, puede cargar contenido masivo desde almacenes de datos compatibles como Azure o S3. Para obtener más información, vea [Ingestor masivo de recursos](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=en#asset-bulk-ingestor).

## Uso de FrameMaker para cargas masivas

Adobe FrameMaker incluye un potente conector Adobe Experience Manager que le permite cargar fácilmente su DITA existente y otros documentos de FrameMaker \(`.book` y `.fm`\) en Adobe Experience Manager. Puede utilizar varias funcionalidades de carga de archivos, como cargar un solo archivo o cargar una carpeta completa con o sin dependencias \(como referencias de contenido, referencias cruzadas y gráficos\).

Para obtener más información sobre el uso de la función de carga masiva en FrameMaker, consulte la sección *Crear una carpeta de CRX y cargar archivos* en la Guía del usuario de FrameMaker.

## Tratamiento de errores al cargar contenido {#id201MI0I04Y4}

Si se produce un error al cargar uno o más archivos, se muestra un mensaje al final del proceso de carga con una lista de los archivos que no se han cargado, como se muestra en el siguiente fragmento de código.

![](images/uuid-files-failed-to-upload_cs.png){width="650" align="center"}

Para obtener más información sobre cómo funcionan los distintos escenarios de carga de archivos, vea [Administrar archivos y carpetas](authoring-file-management.md#).

Si utiliza una herramienta como la aplicación de escritorio de Adobe Experience Manager o el ingestor masivo de recursos, la acción que se va a realizar en un archivo duplicado se controla mediante una configuración en el servidor de Adobe Experience Manager. Póngase en contacto con el administrador del sistema para conocer esta configuración.

**Tema principal:**[ Administrar contenido](authoring.md)
