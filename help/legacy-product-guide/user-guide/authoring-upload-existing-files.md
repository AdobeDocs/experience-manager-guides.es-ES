---
title: Cargar archivos
description: Obtenga información sobre cómo cargar los archivos en el repositorio de AEM y gestionar errores. Conozca la interfaz de usuario de la consola de recursos, la aplicación de escritorio de AEM, el ingestor masivo de recursos y el uso de FrameMaker para la carga masiva.
feature: Content Management
role: User
hide: true
exl-id: fcb2cc43-6a36-42f2-a695-7a50ae1031a0
TQID: https://experienceleague.adobe.com/Kcxzs3D9Vcp7hhgttmCx7jdetS8NWR8YTP85UY0DlJU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 451
ht-degree: 0%

---

# Cargar archivos {#id176FF000JUI}

Lo más probable es que tenga un repositorio de contenido DITA existente que desee utilizar con AEM Guides. Para dicho contenido existente, puede utilizar cualquiera de los siguientes métodos para cargar el contenido en lote en el repositorio de AEM:

>[!IMPORTANT]
>
> Consulte [Agregar recursos digitales a Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=es) para obtener información detallada sobre los métodos de carga de contenido admitidos en AEM.

## Interfaz de usuario de la consola Assets

Puede seleccionar contenido en el escritorio y arrastrarlo desde la interfaz de usuario de AEM \(explorador web\) a la carpeta de destino. Para obtener más información, consulte [Cargar recursos](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=es#upload-assets) en la documentación de AEM.

## Aplicación de escritorio de AEM

Utilice la aplicación de escritorio de AEM si es un profesional creativo y desea administrar los recursos en su escritorio local. Puede abrir y editar estos recursos con las aplicaciones de escritorio. También puede mantener las versiones y compartir los archivos con otros usuarios. Para obtener más información, consulte [aplicación de escritorio de AEM](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html?lang=es).

## Ingestor masivo de recursos

Si tiene migraciones a gran escala e ingestas masivas ocasionales, utilice el Ingestor masivo de recursos para cargar el contenido. Con esta herramienta, puede cargar contenido en bloque desde almacenes de datos compatibles como Azure o S3. Para obtener más información, consulte [Ingestor masivo de recursos](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=es#asset-bulk-ingestor).

## Uso de FrameMaker para cargas masivas

Adobe FrameMaker incluye un potente conector AEM que le permite cargar fácilmente su DITA existente y otros documentos de FrameMaker \(`.book` y `.fm`\) en AEM. Puede utilizar varias funcionalidades de carga de archivos, como cargar un solo archivo o cargar una carpeta completa con o sin dependencias \(como referencias de contenido, referencias cruzadas y gráficos\).

Para obtener más información sobre el uso de la función de carga masiva en FrameMaker, consulte la sección *Crear una carpeta de CRX y cargar archivos* en la Guía del usuario de FrameMaker.

## Tratamiento de errores al cargar contenido {#id201MI0I04Y4}

Si se produce un error al cargar uno o más archivos, se muestra un mensaje al final del proceso de carga con una lista de los archivos que no se han cargado:

![](images/uuid-files-failed-to-upload_cs.png){width="650" align="center"}

Para obtener más información sobre cómo cargar los distintos escenarios de archivos, consulte [Cargar contenido DITA](authoring-file-management.md#).

Si utiliza una herramienta como la aplicación de escritorio de AEM o el ingestor masivo de recursos, la acción que se va a realizar en un archivo duplicado se controla mediante una configuración en el servidor de AEM. Póngase en contacto con el administrador del sistema para conocer esta configuración.

**Tema principal:**&#x200B;[&#x200B; Administrar contenido](authoring.md)
