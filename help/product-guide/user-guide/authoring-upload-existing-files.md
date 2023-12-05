---
title: Cargar archivos
description: AEM Obtenga información sobre cómo cargar los archivos en el repositorio de y gestionar errores. AEM Conozca la interfaz de usuario de la consola de recursos, la aplicación de escritorio de la aplicación de la aplicación de la consola de recursos, el ingestor masivo de recursos y el uso del FrameMaker para la carga masiva.
exl-id: b5430242-1122-43df-a0b2-275b1dea33f2
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 0%

---

# Cargar archivos {#id176FF000JUI}

AEM Lo más probable es que tenga un repositorio de contenido DITA existente que le gustaría utilizar con guías de. AEM Para dicho contenido existente, puede utilizar cualquiera de los siguientes métodos para cargar por lotes el contenido en el repositorio de la:

>[!IMPORTANT]
>
> Consulte [Añadir recursos digitales a Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html) AEM para obtener información detallada en los métodos de carga de contenido admitidos en la documentación de, haga lo siguiente en la documentación de.

## Interfaz de usuario de la consola Assets

AEM Puede seleccionar contenido en el escritorio y arrastrarlo en la interfaz de usuario de la interfaz de usuario de la aplicación \(explorador web\) a la carpeta de destino. Para obtener más información, consulte [Cargar recursos](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html#upload-assets) AEM en la documentación de.

## Aplicación de escritorio de AEM 

AEM Utilice la aplicación de escritorio de si es un profesional creativo y desea administrar los recursos en su escritorio local. Puede abrir y editar estos recursos con las aplicaciones de escritorio. También puede mantener las versiones y compartir los archivos con otros usuarios. Para obtener más información, consulte [AEM aplicación de escritorio de](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html).

## Ingestor masivo de recursos

Si tiene migraciones a gran escala e ingestas masivas ocasionales, utilice el Ingestor masivo de recursos para cargar el contenido. Con esta herramienta, puede cargar contenido masivo desde almacenes de datos compatibles como Azure o S3. Para obtener más información, consulte [Ingestor masivo de recursos](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=en#asset-bulk-ingestor).

## Usar FrameMaker para carga masiva

Adobe FrameMaker AEM incluye un potente conector de que permite cargar fácilmente los documentos DITA y de otros FrameMakeres \(`.book` y `.fm`AEM \) a la dirección de correo electrónico Puede utilizar varias funcionalidades de carga de archivos, como cargar un solo archivo o cargar una carpeta completa con o sin dependencias \(como referencias de contenido, referencias cruzadas y gráficos\).

Para obtener más información sobre el uso de la función de carga masiva en FrameMaker, consulte la sección *Crear una carpeta CRX y cargar archivos* en la Guía del usuario de FrameMaker.

## Tratamiento de errores al cargar contenido {#id201MI0I04Y4}

Si se produce un error al cargar uno o más archivos, se muestra un mensaje al final del proceso de carga con una lista de los archivos que no se han cargado:

![](images/uuid-files-failed-to-upload_cs.png){width="650" align="center"}

Para obtener más información sobre los distintos escenarios de carga de archivos, consulte [Cargar contenido DITA](authoring-file-management.md#).

AEM AEM Si utiliza una herramienta como una aplicación de escritorio o un ingestor masivo de recursos, la acción que se va a realizar en un archivo duplicado se controla mediante una configuración en el servidor de. Póngase en contacto con el administrador del sistema para conocer esta configuración.

**Tema principal:**[ Administrar contenido](authoring.md)
