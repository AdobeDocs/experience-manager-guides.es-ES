---
title: Descargar e instalar plantillas de AEM Sites
description: Descubra cómo descargar e instalar plantillas de AEM Sites
feature: Installation
role: Admin
level: Experienced
source-git-commit: f6e34c0bc57603b4251abd4859b43c95042e8819
workflow-type: tm+mt
source-wordcount: '1130'
ht-degree: 0%

---


# Descargar e instalar plantillas de AEM Sites

Siga estos pasos para descargar e instalar plantillas de AEM Sites en Experience Manager Guides como Cloud Service:

## Instalación de paquetes{#package-installation}

Para utilizar las plantillas, instale el paquete de componentes mediante la implementación en la nube:
- [guides-components-all.zip](https://github.com/adobe/aemg-sites-components/releases/tag/v1.0.0)



Siga estos pasos para crear una AEM Sites con la plantilla:


1. Cree AEM Sites con la plantilla:
1. En la interfaz de usuario de Sites, haga clic en el botón **Crear** en la esquina superior derecha.
1. Seleccione **Sitio de la plantilla** del menú desplegable **Crear**.

1. Importar plantillas de sitios: [aemg-docs-1.0.0.zip](https://github.com/adobe/aemg-sites-template/releases/tag/v1.0.0) con la opción **Importar**.
1. Seleccione `AEMG Docs 1.0.0` y haga clic en **Siguiente**.
1. Escriba `Site title` y `Site name`.
1. Haga clic en **Crear**. El paquete se instala y se crea una plantilla de AEM Sites.

AEM Más información acerca de [Agregar una plantilla de sitio a la página de inicio de sesión de la página de inicio de sesión de la página &lbrace;1.](https://experienceleague.adobe.com/es/docs/experience-manager-cloud-service/content/sites/administering/site-creation/site-templates#adding)


>[!NOTE]
>
>Una vez creada la página principal, puede usar esta ruta como **ruta de Publish** para generar el resultado de los ajustes preestablecidos de AEM Sites. Por ejemplo, `aemg-docs-en/docs/product-abc`.


## Configuración de las plantillas para utilizarlas con los ajustes preestablecidos de AEM Sites

Una vez instalado el paquete, se crea un sitio denominado **AEMG** en la interfaz de usuario de Sites. Este sitio de ejemplo muestra cómo puede configurar la estructura del sitio para generar la salida de AEM Sites. Esto es solo una muestra. Puede crear sitios personalizados según sus necesidades.

![Páginas de muestra de sitios AEMG](assets/aemg-sites-sample-pages.png)


**AEMG** contiene los siguientes componentes.
- Hay una carpeta para el idioma inglés en la carpeta **AEMG**. Puede crear copias de idioma similares según sus necesidades. Por ejemplo, un sitio web multilingüe incluye copias en inglés (en), alemán (de) y francés (fr).  Obtenga más información acerca de cómo crear una copia de idioma con el [Asistente para copia de idioma](https://experienceleague.adobe.com/es/docs/experience-manager-65/content/sites/administering/introduction/tc-wizard).
- Dentro de la carpeta de idioma inglés(en), Experience Manager Guides proporciona muchas páginas de muestra listas para usar como **Search**, **Sign in**, **Docs** y **Support**.

- **Documentos** es la página de inicio de documentación de ejemplo. Sirve como ubicación central para toda la documentación relacionada con el producto
y muestra cada producto para el que hay documentación disponible como mosaicos individuales.

- Junto con la página de inicio de la documentación, hay páginas de muestra de **Buscar**, **Iniciar sesión** y **Soporte técnico**. Puede personalizar estos ejemplos según sus necesidades.
- Puede tener páginas de inicio de productos individuales como Product1. Hay una página de muestra **Product1** en **Docs**, que es la página de inicio de la documentación.

- Experience Manager Guides también proporciona las siguientes plantillas predefinidas:

   - Plantilla de **página de contenido**: use esta plantilla para crear las páginas estándar que contienen la mayor parte del contenido del sitio del producto. Pueden incluir texto, imágenes, vídeos y otros elementos de contenido. Esta plantilla contiene únicamente el encabezado y el pie de página. Personalícelo y utilícelo para crear cualquier página según sus necesidades. Por ejemplo, puede crear la página de soporte técnico o la página de inicio de sesión del producto.
   - Plantilla de **página de inicio**: la página de aterrizaje principal de un sitio web que incluye información general, secciones clave como elementos y características clave y vínculos de navegación. Por ejemplo, la página principal de un producto ABC se conecta a las demás páginas de contenido o características.
   - Plantilla de **página de tema**: páginas utilizadas para organizar y presentar contenido basado en temas. Por ejemplo, una guía del usuario contiene diferentes páginas de temas, cada una de las cuales contiene un tema específico relacionado con las funciones y la solución de problemas.

  ![Plantilla de sitios](assets/sites-ui-templates.png)

Utilice estos ejemplos y plantillas para generar las salidas de AEM Sites:
- Una página de inicio del producto corresponde a una página de inicio del mapa y se crea con la plantilla Página de inicio. Seleccione esta ruta en el ajuste preestablecido de AEM Sites para publicar el contenido del mapa debajo de ella. La página de inicio del producto puede incluir otras páginas de inicio.
- Por ejemplo, tiene un producto como Experience Manager Guides y necesita tres manuales para usuarios, administradores y desarrolladores.  Cree una página de inicio para cada manual con la plantilla Página de inicio y, a continuación, seleccione la página de inicio correspondiente en el ajuste preestablecido de salida de AEM Sites.

Obtenga más información sobre cómo crear y configurar [ajustes preestablecidos de AEM Sites en el editor web](../user-guide/generate-output-aem-site-web-editor.md).

## Crear una página de inicio con la plantilla{#create-a-home-page-using-the-template}

Siga estos pasos para crear la página principal del producto:
1. Una vez instalado el paquete, seleccione **Sitios** en Navegación global.
1. Seleccione la plantilla &quot;AEM Docs&quot; instalada en la interfaz de usuario de Sites.
1. En la interfaz de usuario de Sites, haga clic en el botón **Crear** en la esquina superior derecha.
1. Seleccione **Página** de la lista desplegable **Crear**.
1. Seleccione **Página principal** y haga clic en **Siguiente**.
1. Escriba el título del sitio y el nombre del sitio y haga clic en **Crear** en la esquina superior derecha. AEM Se crea una plantilla del sitio de la con la plantilla del sitio **Página de inicio**. Por ejemplo, puede crear una página de inicio para el producto `Product ABC`.


>[!NOTE]
>
>Una vez creada la página principal, puede usar esta ruta como **ruta de Publish** para generar el resultado de los ajustes preestablecidos de AEM Sites. Por ejemplo, `aemg-docs-en/docs/product-abc`.

## Editar plantillas de temas para AEM Sites

También puede personalizar las plantillas de temas para su AEM Sites. AEM Puede editar el contenido o configurar las propiedades de los diferentes componentes de la en el tema. Por ejemplo, puede agregar o quitar componentes según sus necesidades.\
Siga estos pasos para editar las plantillas de temas:
1. Seleccione la plantilla que desee editar.
1. Seleccione el icono **Editar** de la parte superior.

AEM Se abre el Editor de plantillas de. Puede editar la plantilla de tema. Más información sobre [Creación de plantillas de página](https://experienceleague.adobe.com/es/docs/experience-manager-65/content/sites/authoring/siteandpage/templates#editing-a-template-structure-template-author).


## Personalizar plantillas de AEM Sites existentes {#customize-existing-aem-sites-templates}

Además de las plantillas predefinidas, también puede utilizar las plantillas existentes con los ajustes preestablecidos de AEM Sites. Siga estos pasos para personalizar las plantillas de AEM Sites existentes:

### Configuración de plantilla

Necesita los dos tipos de plantillas siguientes:

- Categoría o plantilla de aterrizaje: esta plantilla se utiliza para la página de aterrizaje de la documentación del producto y corresponde a un mapa DITA.  AEM La página de sitio para un mapa DITA se genera mediante esta plantilla. Puede utilizar esta plantilla en cualquier nivel.
: Añada un componente de texto a la plantilla existente. El componente de texto debe tener una propiedad obligatoria, `text="$category.html$"`.
: por ejemplo, puede elegir plantillas de comercio minorista web y utilizar la plantilla de página de sección como plantilla de página de aterrizaje para el mapa DITA. Para ello, realice los cambios que se muestran en la siguiente captura de pantalla:
  ![plantilla de página de sección](assets/customize-existing-aem-templates-section.png)
   - Plantilla de página de detalles o de página de tema: utilice esta plantilla para el contenido de los temas de un mapa. Todas las páginas de Sites de contenido DITA/XML se crean mediante plantillas de página de temas. Para crear estas plantillas, existen dos requisitos previos:
      - Agregue un componente de texto a la plantilla, contenido en un componente contenedor, con una propiedad obligatoria. `text="$topic.content$"`.

        ![plantilla de página contenedora](assets/customize-existing-aem-templates-container.png)
      - Refleje el mismo contenedor y componente de texto en la estructura de la misma plantilla, como se muestra en la siguiente captura de pantalla:

        ![estructura de la plantilla contenedora](assets/customize-existing-aem-templates-structure.png)

### Etiquetar página de categoría como contenedor de documentación

Suponiendo que se crea una jerarquía de sitios para las páginas de documentación que utilizan la plantilla anterior, elija una de las páginas de categoría creadas en esa jerarquía de sitios. Etiquete la página de categoría como un contenedor de documentación, para ello asígnele un ID.
Para ello, asigne a su propiedad `id` un valor `category-page`. Consulte la siguiente captura de pantalla:

![página de categoría de etiqueta](assets/customize-existing-aem-templates-tagging.png)





