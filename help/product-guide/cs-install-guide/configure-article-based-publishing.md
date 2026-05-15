---
title: Instalación de paquetes para la publicación basada en artículos
description: Obtenga información sobre cómo instalar paquetes para la publicación basada en artículos
exl-id: d83fc1a9-0822-47f0-8099-22a74b9ced2a
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/ZX3-rirhXTcufDkFQOF12vj3uh28gSfIpxFwlOQF-Yk
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: afb45297-4313-4f67-818e-bc0b03abe086id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 374
ht-degree: 0%

---

# Instalación de paquetes para la publicación basada en artículos {#id21BNL02052Z}

AEM Guides proporciona una potente función de publicación basada en artículos integrada con el editor web. Con esta función, puede publicar uno o más temas simultáneamente. Una vez que haya abierto un mapa en el Editor de mapas, puede navegar a la pestaña Salidas para crear un ajuste preestablecido y, a continuación, elegir uno o más temas para generar la salida. Puede utilizar la función de publicación basada en artículos para generar de forma incremental el resultado de uno o más temas o publicar el contenido en una plataforma de base de conocimiento artículo por artículo. Para obtener más información, consulte *Publicación basada en artículos desde la sección del editor web* en la guía del usuario.

Para crear un sitio de AEM para publicar resultados basados en artículos, realice los siguientes pasos:

1. Descargue el **Paquete de contenido de componentes de XML Documentation para Cloud Service** desde su [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. Abra el Administrador de paquetes de AEM. La dirección URL predeterminada para acceder al administrador de paquetes es: `https://<hostname>/crx/packmgr/index.jsp`
1. Cargue el paquete de contenido de componentes de XML Documentation para Cloud Service y, a continuación, instálelo.
1. Descargue el archivo de `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` de su [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. En Navegación global, seleccione **Sitios**.
1. En la interfaz de usuario de Sites, haga clic en el botón **Crear** en la esquina superior derecha.
1. Seleccione **Sitio de la plantilla** del menú desplegable **Crear**.
1. Haga clic en el botón **Importar** y, a continuación, seleccione el(la) `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` descargado(a) en el sistema. Una vez importada la plantilla del sitio, aparece en la parte inferior.

   >[!NOTE]
   >
   > Sólo es necesario importar el archivo ZIP por primera vez. Una vez importada, la plantilla del sitio está disponible en la lista.

   Seleccione **Plantilla de base de conocimiento para publicación basada en artículos** para crear el sitio de AEM y haga clic en **Siguiente** en la esquina superior derecha.

1. Escriba el **título del sitio** y el **nombre del sitio** y haga clic en **Crear** en la esquina superior derecha. Se crea un sitio de AEM con la plantilla de sitio Tragopan. \(el sitio de Tragopan es un sitio de AEM de base de conocimiento de ejemplo con plantillas para una categoría, sección y páginas de artículos.\)

   >[!NOTE]
   >
   > Puede crear varios sitios de AEM con la misma plantilla.


Puede utilizar el sitio de AEM para publicar el artículo mediante los ajustes preestablecidos de salida del Editor web.

**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
