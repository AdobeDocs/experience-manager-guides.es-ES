---
title: Acerca de esta guía
description: Obtenga información acerca de esta guía
exl-id: cdd40267-3f0c-40d2-acbc-2ebe43633c2f
feature: Introduction
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 2%

---

# Acerca de esta guía {#id175MC0P0S5Z}

Adobe Experience Manager Guides \(más adelante denominado *AEM Guides*\) es una potente solución de administración de contenido de componentes de nivel empresarial basada en la nube \(CCMS\). Permite la compatibilidad nativa con DITA en Adobe Experience Manager AEM, lo que permite a los gestionar la creación y la entrega de contenido basado en DITA. Permite a los autores crear contenido mediante un editor web integrado fácil de usar y publicarlo en varios formatos de salida.

Esta guía proporciona instrucciones para descargar, instalar y configurar AEM Guides. En esta guía, encontrará instrucciones detalladas para configurar AEM Guides según sus necesidades de creación y publicación en la organización.

Esta guía está diseñada para los siguientes tipos de audiencias:

- Administradores, que instalarían y administrarían AEM Guides.

- Los editores, que ejecutarían la tarea de publicación para generar resultados en varios formatos.


## Estructura del contenido

La información de esta guía está organizada de la siguiente manera:

- [Acerca de esta guía](#id175MC0P0S5Z): En este tema se proporciona una introducción a esta guía, a la audiencia objetivo y a cómo se organiza la información en esta guía.

- [Descargar e instalar](download-install.md#): En este tema se describe cómo descargar, instalar o actualizar AEM Guides.

- AEM [Administración y seguridad de usuarios](user-admin-sec.md#): En este tema se describe el concepto básico de usuarios y autenticación en los grupos de usuarios predeterminados y los grupos de usuarios creados por AEM Guides en los grupos de usuarios predeterminados de los que se crea la aplicación.

- [Usar la especialización DITA-OT y DITA personalizada](dita-ot-specialization.md#): en este tema se explica cómo configurar complementos DITA-OT personalizados y utilizar la especialización DITA.

- [Configurar estados de documentos](customize-doc-state.md#): en este tema se explica cómo configurar estados personalizados para los documentos DITA.

- AEM [Migrar contenido existente](migrate-content.md#): En este tema se describe cómo incorporar el contenido existente en el repositorio de la aplicación de la aplicación de la aplicación de la aplicación de la aplicación de la aplicación de seguridad de datos de usuario de la plataforma de almacenamiento de datos.

- [Configurar nombres de archivo](conf-file-names.md#): En este tema se explica cómo configurar la opción para asignar automáticamente nombres de archivo y definir una regex para los caracteres de nombre de archivo válidos.

- [Configurar plantillas de temas y asignaciones](conf-template-tags.md#): En este tema se describe cómo configurar plantillas de temas y asignaciones para satisfacer sus necesidades de creación. AEM Obtenga información sobre el sistema de etiquetado en las etiquetas y cómo configurarlas para que funcionen con AEM Guides.

- [Personalizar editor web](conf-web-editor.md#): En este tema se explican las distintas personalizaciones que puede realizar en el editor web para mejorar su funcionalidad.

- [Incluir atributo @navtitle de forma predeterminada](auto-add-navtitle.md#): En este tema se explica cómo agregar el atributo `@navtitle` a un archivo de referencia en un mapa de forma predeterminada.

- [Configurar perfiles globales o de nivel de carpeta](conf-folder-level.md#): En este tema se explica el proceso de creación de perfiles de carpeta y de concesión de permisos a usuarios específicos.

- [Administración de versiones](version-management.md#): En este tema se describe cómo configurar la desprotección automática de archivos para los archivos que se abren para su edición en el Editor Web.

- [Configurar opciones de generación de resultados](conf-output-generation.md#): En este tema se describen las distintas configuraciones que puede realizar para personalizar el proceso de generación de resultados predeterminado.

- [Configurar y personalizar flujos de trabajo](customize-workflows.md#): En este tema se describen varias configuraciones para personalizar los flujos de trabajo predeterminados enviados en AEM Guides.

- AEM [Traducir contenido](translation.md#): En este tema se proporcionan vínculos a los artículos de ayuda relevantes de la documentación de la traducción para ayudarle a comprender y configurar el marco de trabajo de traducción. Además, aprenda a habilitar el flujo de trabajo de traducción basado en componentes.

- [Configurar la búsqueda para la interfaz de usuario de AEM Assets](conf-dita-search.md#): en este tema se describe cómo configurar la búsqueda de contenido DITA en la interfaz de usuario de Assets y cómo agregar los atributos personalizados en la búsqueda.


## Descripción general de Adobe Experience Manager AEM \(\)

[Adobe Experience Manager AEM \(\)](https://business.adobe.com/es/products/experience-manager/adobe-experience-manager.html?lang=es) es una solución de administración de contenido completa para crear sitios web, aplicaciones móviles y formularios. AEM le ayuda a administrar el contenido y los recursos de marketing. AEM La está disponible as a Cloud Service. AEM as a Cloud Service AEM AEM le ayuda a proporcionar a sus clientes experiencias personalizadas basadas en contenido combinando la potencia del sistema de administración de contenido de la con la administración de recursos digitales de la red de recursos de la red de recursos digitales de la red. Algunos de los recursos clave que pueden ayudarle a empezar e implementar en AEM as a Cloud Service son los siguientes:

- [Información general as a Cloud Service del Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=es)
- [Introducción al Recorrido de migración a AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/migration-journey/getting-started.html?lang=es)
- [Iniciar la incorporación al Experience Manager as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/onboarding/home.html?lang=eshttps://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/home.html?lang=en)
- [Implementación de aplicaciones para AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/home.html?lang=es)
- [Implementación en AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/deploying/overview.html?lang=es)
- [Guía as a Cloud Service de Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/home.html?lang=es)

## Recursos adicionales

A continuación se muestra una lista de otros recursos útiles de AEM Guides, que están disponibles en la página [Aprendizaje y asistencia](https://helpx.adobe.com/es/support/xml-documentation-for-experience-manager.html):

- Guía del usuario
- Guía de referencia de API
