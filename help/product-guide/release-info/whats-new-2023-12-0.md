---
title: Notas de versión | Novedades de la versión de Adobe Experience Manager Guides de diciembre de 2023
description: Conozca las funciones nuevas y mejoradas de la versión de diciembre de 2023 de Adobe Experience Manager Guides as a Cloud Service.
feature: What's New
role: Leader
exl-id: bf8d98e9-97fe-4195-9286-60d8517ab19c
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 0%

---

# Novedades de la versión de diciembre de 2023 de Adobe Experience Manager Guides as a Cloud Service

Este artículo cubre las funciones nuevas y mejoradas de la versión de diciembre de 2023 de Adobe Experience Manager Guides (más adelante denominada *Experience Manager Guides as a Cloud Service*).

Para obtener más información sobre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en esta versión, vea [Notas de la versión](release-notes-2023-12-0.md).


## Usar variables en la salida del PDF

Puede utilizar variables para insertar y administrar de forma dinámica información reutilizable. Experience Manager Guides le ayuda a crear, editar y previsualizar variables mientras genera la salida del PDF. Puede modificar rápidamente los valores de las variables y hacer que sus documentos sean portátiles y fáciles de actualizar.

![variables de pdf nativas](assets/add-variable-default.png){width="800" align="left"}

*Crear y administrar variables en el editor web.*

También puede crear conjuntos de variables que anulen los valores predeterminados y asignen valores alternativos a las variables. Inserte estas variables dentro del diseño de página y utilice el mismo diseño de PDF. No es necesario crear diseños independientes para cada conjunto de valores. Por ejemplo, puede crear un conjunto de variables para cada versión del producto. Este conjunto de variables puede constar de variables para distintos detalles del producto, como el nombre del producto, el número de versión y la fecha de lanzamiento. A continuación, puede agregar valores diferentes para estas variables.

**Conjunto de variables 1: Adobe-set1**

* Nombre del producto: Experience Manager Guides
* Número de versión: 2311
* Fecha de versión: 2/11/2023

**Conjunto de variables 2: Adobe-set2**

* Nombre del producto: Experience Manager Guides
* Número de versión: 2310
* Fecha de versión: 27/09/2023



<img src="./assets/native-pdf-variable-output.png" alt="Pie de página en salida de PDF" width="500" border="2px">

*Generar la salida del PDF mediante variables en el diseño del PDF.*

Puede aplicar estilos y utilizar marcado de HTML para dar formato a las variables.  También puede actualizar rápidamente los valores de cualquier variable siempre que sea necesario y volver a generar la salida. Por ejemplo, si necesita actualizar los detalles de una versión, puede editar el valor de la versión en la variable VersionNumber y volver a generar el resultado.


Obtenga más información acerca de cómo usar [variables en la salida del PDF](../native-pdf/native-pdf-variables.md).





## Experiencia modificada para editar los atributos

Ahora, obtendrá una experiencia renovada para agregar o editar los atributos de un elemento desde el panel **Propiedades de contenido** del Editor Web.

![Panel de atributos](assets/attributes-multiple-properties.png){width="300" align="left"}

*Agregar atributos desde el panel Propiedades de contenido.*

También puede editar y eliminar fácilmente los atributos.

Para obtener más información, consulte la descripción de la característica **Propiedades de contenido** en la sección [Panel derecho](../user-guide/web-editor-features.md#id2051EB003YK).


## Edición de metadatos durante la creación

Ahora, durante la creación, puede actualizar las etiquetas de metadatos del archivo mediante el menú desplegable de **Propiedades del archivo** en el panel derecho. También puede seleccionar **Editar más propiedades** para actualizar más metadatos.

![propiedades de archivo](assets/file-properties-general.png){width="300" align="left"}

*Actualice los metadatos y edite las propiedades del archivo desde el panel derecho.*

Para obtener más información, consulte la descripción de la característica **Propiedades del archivo** en la sección [Panel derecho](../user-guide/web-editor-features.md#id2051EB003YK).

## Capacidad para publicar contenido en la base de conocimiento de ServiceNow

Ahora también puede publicar el contenido en la plataforma de base de conocimiento ServiceNow.

Con la versión de diciembre de 2023, como administrador, puede crear un perfil de publicación para el servidor de la base de conocimiento de ServiceNow. A continuación, como autor o editor, puede elegir ese perfil de publicación ServiceNow en el ajuste preestablecido de salida para publicar la salida en la base de conocimiento especificada.

Esta función le ayuda a publicar contenido, como texto, vídeos e imágenes, en la plataforma de base de conocimiento de ServiceNow y a mantener un repositorio completo.


![servicio ahora ajuste preestablecido de la base de conocimiento](assets/knowledgebase--output-preset.png){width="300" align="left"}

*Cree un ajuste preestablecido de salida para la base de conocimiento ServiceNow.*

Obtenga más información acerca de los ajustes preestablecidos de salida de [Knowledge Base](../user-guide/generate-output-knowledge-base.md).

## Panel de recopilación de mapas mejorado

Experience Manager Guides proporciona un panel de recopilación de mapas mejorado. En una colección de mapas, puede configurar rápidamente las propiedades de metadatos de forma masiva para los mapas DITA. Esta función es útil, ya que no es necesario actualizar las propiedades de metadatos para cada mapa DITA de forma individual.

Ahora puede ver el nombre de archivo del mapa DITA. También puede ver las líneas base. Esto le ayudará a encontrar rápidamente la línea de base utilizada para un ajuste preestablecido.

![Panel de recopilación de mapas](assets/map-collection-dashboard.png){width="800" align="left"}

*Ver, editar y generar resultados desde el panel de recopilación de mapas.*

Aprenda a [usar la colección de mapas para generar resultados](../user-guide/generate-output-use-map-collection-output-generation.md).

## Ver los atributos clave en la vista Mapa

Al definir atributos clave para el tema o las referencias de mapa, también puede ver el título, el icono correspondiente y la clave en el panel izquierdo. La clave se muestra como `key=<key-name>`.

Para obtener más información, consulte la descripción de la característica **Vista de mapa** en la sección [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS).

![claves en la vista de mapa](assets/view-key-title-map-view.png) {width="300" align="left"}

*Ver el atributo clave en la vista de mapa.*

## Capacidad para duplicar una línea de base según una etiqueta

Experience Manager Guides ahora proporciona una experiencia de usuario mejorada para crear las líneas de base desde el Editor web.\
![crear nueva línea base](assets/create-new-baseline.png) {width="300" align="left"}
*Crear línea de base desde el editor web.*

También le permite duplicar una línea de base basada en la etiqueta. La versión de referencia se selecciona en función de la etiqueta dada (si existe) mientras se duplica o, de lo contrario, elige la versión de la línea de base duplicada.


![duplicar una línea de base ](assets/duplicate-baseline.png) {width="300" align="left"}

*Duplicar una línea de base basándose en una etiqueta o crear una copia exacta.*

Obtenga más información sobre cómo [crear y administrar líneas de base desde el Editor web](../user-guide/web-editor-baseline.md).

## AEM Resolución de vínculos de mapas cruzados en la salida del sitio de la

AEM Los vínculos de mapas cruzados (XREF con ámbito del mismo nivel) que se representan en la salida del sitio de la publicación de la lista de distribución ahora se resuelven según el título de archivo del contexto de publicación establecido para la asignación generada.


## AEM Configure la dirección URL de la salida del sitio de para utilizar el título del documento

Experience Manager Guides AEM le permite, como administrador, configurar la dirección URL de la salida del sitio de la. AEM Si el nombre de archivo no existe o contiene todos los caracteres especiales, puede configurarlos para reemplazarlos con un separador en la dirección URL de la salida del sitio de la página de la página de la página de inicio de sesión (). También puede reemplazarlos con el nombre del primer tema secundario. AEM Aprenda a [configurar la dirección URL de la salida del sitio de para que use el título del documento](../cs-install-guide/conf-output-generation.md#configure-the-url-of-the-aem-site-output-to-use-the-document-title).
