---
title: Notas de versión | Novedades de las guías de Adobe Experience Manager, versión de octubre de 2023
description: Conozca las funciones nuevas y mejoradas de la versión de octubre de 2023 de las guías de Adobe Experience Manager as a Cloud Service.
exl-id: 41bfed0d-5901-4ada-b6d7-a5be93b25ba8
feature: What's New
role: Leader
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Novedades de la versión de octubre de 2023 de Adobe Experience Manager Guides as a Cloud Service

Este artículo cubre las funciones nuevas y mejoradas de la versión de octubre de 2023 de las guías de Adobe Experience Manager (más adelante denominadas *AEM Guías de as a Cloud Service*).

Para obtener más información sobre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en esta versión, consulte [Notas de versión](release-notes-2023.10.0.md).


## Configuración de un conector de fuente de datos desde la interfaz de usuario

Guías del Experience Manager ahora proporciona un **Fuentes de datos** que le ayuda a configurar conectores predeterminados para fuentes de datos. Puede crear fácilmente los conectores para bases de datos JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce y Elasticsearch.

También puede editar, volver a conectar, duplicar o eliminar fácilmente un conector de origen de datos. Obtenga información sobre cómo [configurar fácilmente un conector de fuente de datos desde la interfaz de usuario](../cs-install-guide/conf-data-source-connector-tools.md).

![conectores de fuente de datos enumerados en el panel fuentes de datos](assets/data-sources-create-window.png){width="550" align="left"}

*Cree y visualice los conectores de fuente de datos desde el panel Fuentes de datos.*

## Ver registros del generador de temas

Ahora también puede ver el archivo de registro de generación de contenido. Este archivo de registro le ayuda a comprobar las advertencias, errores y excepciones.  Obtenga más información acerca de cómo [opciones para un generador de temas](../user-guide/web-editor-content-snippet.md#options-for-a-topic-generator) le ayuda a generar y administrar fácilmente los generadores de temas.

## Compatibilidad con las herramientas de Velocity en las plantillas de fuente de datos

Ahora puede utilizar las herramientas de Velocity en las plantillas de guías del Experience Manager. Estas herramientas le ayudan a aplicar varias funciones a los datos que obtiene de las fuentes de datos. Puede utilizar las plantillas al crear un fragmento de contenido o un tema. Esta función le ayuda a ahorrar tiempo y esfuerzo para aplicar manualmente la misma función a cada conjunto de datos.  También garantiza resultados precisos.
Por ejemplo, puede utilizar $mathTool para realizar funciones matemáticas.
Obtenga más información sobre cómo [usar las herramientas de Velocity en las plantillas de fuente de datos](../user-guide/web-editor-content-snippet.md#use-velocity-tools).


## Mejoras del PDF nativo

En la versión de octubre de 2023 de se realizaron las siguientes mejoras en el PDF nativo:

### Restablecer el número de página de la primera página de un diseño

En la salida del PDF nativo, puede reiniciar los números de página y especificar el número a partir del cual comienza la numeración. Ahora también puede iniciar la numeración solo para la primera aparición de una sección.
Obtenga más información sobre cómo [trabajar con las propiedades de página de un diseño de página](../native-pdf/design-page-layout.md#page-props-page-layout).


### Ver capítulos sin números automáticos en la TDC

Las Guías del Experience Manager muestran los números de capítulo junto con los nombres de capítulo en la Tabla de contenido (TDC). Ahora puede elegir publicar solo los nombres de capítulo sin los números de capítulo. Vea más detalles sobre cómo configurar el [configuración avanzada de PDF de una plantilla](../native-pdf/components-pdf-template.md#advanced-pdf-settings).

## Descarga de un mapa desde el editor web

Ahora no solo puede editar un mapa en la vista de mapa del Editor Web, sino también descargarlo. Puede elegir descargar el mapa con una línea de base específica. También tiene la opción de acoplar la jerarquía y guardar todos los archivos y carpetas en una sola carpeta.

Para obtener más información, consulte la **Vista de mapa** descripción de funciones dentro de [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS) sección.

![menú opciones de un archivo en la vista del repositorio](assets/options-menu-repo-view-file-level-2310.png){width="550" align="left"}

*Seleccione un archivo en la vista del repositorio y elija la opción para realizar una acción en el archivo.*

## Edición de un archivo en el complemento Conector de oxígeno

Guías del Experience Manager ahora le permite seleccionar un archivo en el Editor web y, a continuación, elegir editar el archivo en el complemento Conector de oxígeno. Esta opción no está habilitada como parte de la compatibilidad predeterminada. No se requiere que esté habilitada.

Para obtener más información, consulte la **Opciones de un archivo** descripción de funciones dentro de [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS) sección.
