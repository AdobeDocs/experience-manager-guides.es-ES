---
title: Instalación de paquetes para la publicación basada en artículos
description: Obtenga información sobre cómo instalar paquetes para la publicación basada en artículos
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 0%

---

# Instalación de paquetes para la publicación basada en artículos {#id21BNL02052Z}

AEM Guides proporciona una potente función de publicación basada en artículos integrada con el editor web. Con esta función, puede publicar uno o más temas simultáneamente. Una vez que haya abierto un mapa en el Editor de mapas, puede navegar a la pestaña Salidas para crear un ajuste preestablecido y, a continuación, elegir uno o más temas para generar la salida. Puede utilizar la función de publicación basada en artículos para generar de forma incremental el resultado de uno o más temas o publicar el contenido en una plataforma de base de conocimiento artículo por artículo. Para obtener más información, consulte *Publicación basada en artículos desde la sección del editor web* en la guía del usuario.

Las siguientes pestañas proporcionan instrucciones para crear un sitio de AEM para publicar resultados basados en artículos en función de la configuración de Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

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

>[!TAB Local]

Para habilitar la publicación basada en artículos, descargue e instale los siguientes paquetes de su Portal de distribución de software de Adobe. Instálelos para crear un sitio Tragopan. \(sitio de Tragopan es un sitio de AEM de base de conocimiento de muestra con plantillas para una categoría, sección y páginas de artículo.\) Actualice el sitio Tragopan para generar el resultado del sitio AEM mediante los ajustes preestablecidos de salida del Editor Web.

- Plantilla de la base de conocimiento para la publicación basada en artículos
- Paquete de componentes para la publicación basada en artículos

>[!ENDTABS]


**Tema principal:**&#x200B;[&#x200B; Personalizar editor web](customize-overview.md)
