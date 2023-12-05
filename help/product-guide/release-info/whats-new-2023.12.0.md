---
title: Notas de versión | Novedades de la versión de Adobe Experience Manager Guides, diciembre de 2023
description: Conozca las funciones nuevas y mejoradas de la versión de diciembre de 2023 de las guías de Adobe Experience Manager as a Cloud Service.
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1032'
ht-degree: 0%

---

# Novedades de la versión de diciembre de 2023 de Adobe Experience Manager Guides as a Cloud Service

Este artículo cubre las funciones nuevas y mejoradas de la versión de diciembre de 2023 de las guías de Adobe Experience Manager (más adelante denominadas *Guías del Experience Manager as a Cloud Service*).

Para obtener más información sobre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en esta versión, consulte [Notas de versión](release-notes-2023.12.0.md).


## Usar variables en la salida del PDF nativo

Puede utilizar conjuntos de variables para insertar y administrar de forma dinámica información que pueda cambiar según condiciones específicas, como nombres y versiones de productos. Esta función le ayuda a utilizar el mismo diseño de PDF y a generar salidas con valores diferentes. No es necesario crear diseños independientes para cada conjunto de valores.

Por ejemplo, puede crear un conjunto de variables para cada producto. Este conjunto de variables puede constar de variables para distintos detalles del producto, como ProductName, VersionNumber y ReleaseDate. A continuación, puede agregar valores diferentes para estas variables.

**Conjunto de variables 1: conjunto de Adobes 1**

* Nombre del producto: Guías del Experience Manager
* Número de versión: 2311
* Fecha de versión: 2/11/2023

**Conjunto de variables 1: conjunto de Adobes 2**

* Nombre del producto: Guías del Experience Manager
* Número de versión: 2310
* Fecha de versión: 27/09/2023


![variables pdf nativas](assets/native-pdf-variables.png){width="800" align="left"}

*Cree variables desde la pestaña Output en el editor web.*

También puede crear variables con valores que tengan etiquetas de HTML. Por ejemplo, añada imágenes del DAM de contenido utilizando `<img>` etiqueta.

Una vez creadas las variables, puede agregarlas a los lugares adecuados del documento mediante los diseños de página de las plantillas de salida. Los valores se seleccionan automáticamente en la salida del PDF en función del conjunto de variables seleccionado en el ajuste preestablecido de salida.



<img src="./assets/native-pdf-variable-output.png" alt="Pie de página en salida de PDF" width="500" border="2px">

*Genere la salida del PDF nativo utilizando variables en el diseño del PDF.*

Esta función ayuda a generar resultados personalizados con contenido dinámico en la documentación y a administrar los cambios de forma eficaz. También puede aplicar estilos y utilizar marcado de HTML para dar formato a las variables.

También puede actualizar rápidamente los valores de cualquier conjunto de variables cuando sea necesario y volver a generar la salida. Por ejemplo, si necesita actualizar los detalles de una versión, puede actualizar el valor de la versión en VersionNumber y volver a generar el resultado.


## Experiencia modificada para editar los atributos

Ahora, obtiene una experiencia renovada para agregar o editar los atributos de un elemento desde el **Propiedades del contenido** Panel en el editor web.

![Panel Atributos](assets/attributes-multiple-properties.png){width="300" align="left"}

*Agregue atributos desde el panel Propiedades del contenido.*

También puede editar y eliminar fácilmente los atributos.

Para obtener más información, consulte la **Propiedades del contenido** descripción de funciones dentro de [Panel derecho](../user-guide/web-editor-features.md#id2051EB003YK) sección.


## Edición de metadatos durante la creación

Ahora, durante la creación, puede actualizar las etiquetas de metadatos del archivo mediante la lista desplegable de **Propiedades de archivo** en el panel derecho. También puede seleccionar **Editar más propiedades** para actualizar más metadatos.

![file-properties](assets/file-properties-general.png){width="300" align="left"}

*Actualice los metadatos y edite las propiedades del archivo desde el panel derecho.*

Para obtener más información, consulte la **Propiedades de archivo** descripción de funciones dentro de [Panel derecho](../user-guide/web-editor-features.md#id2051EB003YK) sección.

## Capacidad para publicar contenido en la base de conocimiento de ServiceNow

Ahora también puede publicar el contenido en la plataforma de base de conocimiento ServiceNow.

Con la versión de diciembre de 2023, como administrador, puede crear un perfil de publicación para el servidor de la base de conocimiento de ServiceNow. A continuación, como autor o editor, puede elegir ese perfil de publicación ServiceNow en el ajuste preestablecido de salida para publicar la salida en la base de conocimiento especificada.

Esta función le ayuda a publicar contenido, como texto, vídeos e imágenes, en la plataforma de base de conocimiento de ServiceNow y a mantener un repositorio completo.


![ajuste preestablecido de base de conocimiento de servicio ahora](assets/knowledgebase--output-preset.png){width="300" align="left"}

*Cree un ajuste preestablecido de salida para la base de conocimiento de ServiceNow.*


## Panel de recopilación de mapas mejorado

Guías del Experience Manager proporciona un panel de recopilación de mapas mejorado. En una colección de mapas, puede configurar rápidamente las propiedades de metadatos de forma masiva para los mapas DITA. Esta función es útil, ya que no es necesario actualizar las propiedades de metadatos para cada mapa DITA de forma individual.

Ahora puede ver el nombre de archivo del mapa DITA. También puede ver las líneas base. Esto le ayudará a encontrar rápidamente la línea de base utilizada para un ajuste preestablecido.

![Tablero de colección de mapas](assets/map-collection-dashboard.png){width="800" align="left"}

*Vea, edite y genere resultados desde el panel de recopilación de mapas.*

Obtenga información sobre cómo [usar la colección de mapas para generar resultados](../user-guide/generate-output-use-map-collection-output-generation.md).

## Ver los atributos clave en la vista Mapa

Al definir atributos clave para el tema o las referencias de mapa, también puede ver el título, el icono correspondiente y la clave en el panel izquierdo. La tecla se muestra como `key=<key-name>`.

Para obtener más información, consulte la **Vista de mapa** descripción de la función en [Panel izquierdo](../user-guide/web-editor-features.md#id2051EA0M0HS) sección.

![claves en la vista de mapa](assets/view-key-title-map-view.png) {width="300" align="left"}

*Consulte el atributo clave en la vista Mapa.*

## Capacidad para duplicar una línea de base según una etiqueta

Las guías del Experience Manager ahora proporcionan una experiencia de usuario mejorada para crear las líneas de base desde el Editor Web.\
![crear nueva línea base](assets/create-new-baseline.png) {width="300" align="left"}
*Cree una línea base desde el Editor Web.*

También le permite duplicar una línea de base basada en la etiqueta. La versión de referencia se selecciona en función de la etiqueta dada (si existe) mientras se duplica o, de lo contrario, elige la versión de la línea de base duplicada.


![duplicar una línea base ](assets/duplicate-baseline.png) {width="300" align="left"}

*Duplique una línea base basada en una etiqueta o cree una copia exacta.*

## Proceso mejorado para la creación de la recopilación de mapas de activación masiva

El proceso de creación de una colección de mapas de activación masiva es ahora más armonioso. Ahora, cuando se muestra la página de resultados de la activación, puede ver los resultados de la activación y los registros.
Para obtener más información, consulte [Creación de una colección de mapas de activación masiva](../user-guide/conf-bulk-activation-create-map-collection.md).



## AEM Resolución de vínculos de mapas cruzados en la salida del sitio de la

AEM Los vínculos de mapas cruzados (XREF con ámbito del mismo nivel) que se representan en la salida del sitio de la publicación de la lista de distribución ahora se resuelven según el título de archivo del contexto de publicación establecido para la asignación generada.


## AEM Configure la dirección URL de la salida del sitio de para utilizar el título del documento

Las guías del Experience Manager AEM le permiten, como administrador, configurar la dirección URL de la salida del sitio de la aplicación de la interfaz de usuario (URL) de la página de salida del sitio de la. AEM Si el nombre de archivo no existe o contiene todos los caracteres especiales, puede configurarlos para reemplazarlos con un separador en la dirección URL de la salida del sitio de la página de la página de la página de inicio de sesión (). También puede reemplazarlos con el nombre del primer tema secundario. Obtenga información sobre cómo [AEM configure la dirección URL de la salida del sitio de para utilizar el título del documento](../cs-install-guide/conf-output-generation.md#configure-the-url-of-the-aem-site-output-to-use-the-document-title).

