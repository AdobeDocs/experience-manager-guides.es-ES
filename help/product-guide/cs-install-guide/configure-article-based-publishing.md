---
title: Instalación de paquetes para la publicación basada en artículos
description: Obtenga información sobre cómo instalar paquetes para la publicación basada en artículos
exl-id: d83fc1a9-0822-47f0-8099-22a74b9ced2a
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Instalación de paquetes para la publicación basada en artículos {#id21BNL02052Z}

AEM Guías de proporciona una potente función de publicación basada en artículos integrada con el editor web. Con esta función, puede publicar uno o más temas simultáneamente. Una vez que haya abierto un mapa en el Editor de mapas, puede navegar a la pestaña Salidas para crear un ajuste preestablecido y, a continuación, elegir uno o más temas para generar la salida. Puede utilizar la función de publicación basada en artículos para generar de forma incremental el resultado de uno o más temas o publicar el contenido en una plataforma de base de conocimiento artículo por artículo. Para obtener más información, consulte *Publicación basada en artículos desde la sección Editor web* en la Guía del usuario.

AEM Para crear un sitio de publicación para la salida basada en artículos, realice los siguientes pasos:

1. Descargar **Paquete de contenido de componentes de XML Documentation para Cloud Service** de su [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. AEM Abra el Administrador de paquetes. La URL predeterminada para acceder al administrador de paquetes es: `https://<hostname>/crx/packmgr/index.jsp`
1. Cargue el paquete de contenido de componentes de XML Documentation para Cloud Service y, a continuación, instálelo.
1. Descargue la `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` desde su [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. En Navegación global, seleccione **Sites**.
1. En la IU de Sites, haga clic en **Crear** botón en la esquina superior derecha.
1. Seleccionar **Sitio a partir de plantilla** desde el **Crear** desplegable.
1. Haga clic en **Importar** y, a continuación, seleccione el botón `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` descargado en el sistema. Una vez importada la plantilla del sitio, aparece en la parte inferior.

   >[!NOTE]
   >
   > Sólo es necesario importar el archivo ZIP por primera vez. Una vez importada, la plantilla del sitio está disponible en la lista.

   Seleccionar **Plantilla de la base de conocimiento para la publicación basada en artículos** AEM para crear el sitio de la y haga clic en **Siguiente** en la esquina superior derecha.

1. Introduzca el **Título del sitio** y el **Nombre del sitio** y haga clic en **Crear** en la esquina superior derecha. AEM Se crea un sitio de trabajo mediante la plantilla de sitio de Tragopan. AEM \(sitio de Tragopan es un sitio de base de conocimiento de muestra con plantillas para páginas de categorías, secciones y artículos.\)

   >[!NOTE]
   >
   > AEM Puede crear varios sitios de la utilizando la misma plantilla.


AEM Puede utilizar el sitio de para publicar el artículo mediante los ajustes preestablecidos de salida del Editor web.

**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
