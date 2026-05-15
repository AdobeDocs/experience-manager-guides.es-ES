---
title: Añadir la promoción de marca empresarial a la primera página de un PDF DITA
description: Lograr la promoción de la marca de la empresa integrando la portada y la página de capítulo, lo que garantiza que la identidad de la empresa se muestre claramente en la parte superior del contenido.
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: ab452529-3c7f-4057-a0f6-212b9f52a99d
TQID: https://experienceleague.adobe.com/6CGRK2QWFZ6nIXmIAQZy3lX7t4KYP2-HeyqlVW2-7eE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2:
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 422
ht-degree: 0%

---

# Añadir la promoción de marca empresarial a la primera página de un PDF DITA

## Este artículo trata sobre:

Lograr la promoción de la marca empresarial combinando sin problemas la página de portada con la página del capítulo, lo que garantiza que la identidad de la empresa se muestre de forma destacada en la parte superior del contenido.

- [Configurar el contenido](#set-up-your-content)
- [Realice los cambios necesarios en la plantilla de PDF](#create-necessary-changes-in-pdf-template)

**Antes:**

![Antes de corregir la marca: captura de pantalla que muestra el diseño de PDF premarcado](../assets/publishing/branding-image1.png)
<br>
<br>

**Después:**

![Después de corregir la marca: captura de pantalla que muestra el diseño de PDF posterior a la marca](../assets/publishing/branding-image2.png)

## Configurar el contenido

Para publicar contenido en formato PDF, debe crear un Ditamap o un Bookmap.

Estructura de Bookmap de muestra:

```
<bookmap>
  <title>My Bookmap Title </title>
  <frontmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <tablelist/>
    </booklists>
  </frontmatter>

  <chapter href="chapter1.ditamap">
  <chapter href="chapter2.ditamap">
  </chapter>

  <backmatter>
    <booklists>
      <indexlist/>
    </booklists>
  </backmatter>
</bookmap>
```

Estructura de Ditamap de muestra:

```
<map title="My map Title">

  <topicref href="topic1.dita" >
  </topicref>
  <topicref href="topic2.dita">
  </topicref>
  
</map>
```

La portada de PDF se genera automáticamente si Bookmap contiene `<frontmatter>`.


## Realice los cambios necesarios en la plantilla de PDF

En esta sección, configuraremos nuestra plantilla. (Puede utilizar o duplicar la plantilla de alta tecnología para comenzar).

### Configure la plantilla:

- Vaya a la plantilla nativa de PDF.
- Vaya al diseño de página de la portada y edítelo.
- Agregue su imagen de marca en `data-region="content"`.
- Añada otros cambios necesarios en la plantilla de capítulo si es necesario.
- Ahora siga los pasos a continuación según su contenido.


#### Si utiliza Ditamap para la generación de PDF:

Al publicar un DITAMAP, Native PDF proporciona la funcionalidad para generar automáticamente una página de portada. La opción para habilitar o deshabilitar la generación de páginas de portada se puede configurar en la plantilla nativa de PDF.

Para combinar:
- Vaya a la configuración de la plantilla nativa de PDF —> Page Layout Order
- Ahora, combine FrontCover con Next page, es decir, Chapter &amp; Topics.
  ![Combinando la portada con el capítulo: captura de pantalla que muestra la configuración nativa de la plantilla de PDF](../assets/publishing/branding-image3.png)
- Guardar plantilla, seleccione esta plantilla para el ajuste preestablecido y publicar.


#### Si utiliza Bookmap para la generación de PDF

En el caso de un Bookmap, la secuencia del orden de diseño de página se controla mediante la estructura del Bookmap en lugar del orden de la plantilla.

Para conseguirlo para Bookmap , utilizaremos la función JavaScript de NativePDF.

- Añada a continuación de JavaScript en la carpeta de recursos de su plantilla

```
window.addEventListener('DOMContentLoaded', function () {
    window.pdfLayout.onAfterPagination(function () {
        var frontMatterWrappers = document.querySelectorAll('.rh-front-matter-wrapper');

        frontMatterWrappers.forEach(function(wrapper) {
            var contentDiv = wrapper.querySelector('div[data-region="content"]');
            var chapterBody = document.querySelector('.chapter-body');

            if (contentDiv && chapterBody) {
                chapterBody.insertBefore(contentDiv, chapterBody.firstChild);
            }

            wrapper.remove();
        });
    });
});
```

- Incluya esta JavaScript en la plantilla de capítulo.
  ![Incluir JavaScript en la plantilla de capítulo: captura de pantalla que muestra la entrada en la plantilla de diseño de página de PDF](../assets/publishing/branding-image4.png)

- Habilitar JavaScript desde la opción de ajuste preestablecido
  ![Habilitar la configuración de ajustes preestablecidos de JavaScript: captura de pantalla que muestra la configuración de ajustes preestablecidos para habilitar JavaScript](../assets/publishing/branding-image5.png)

- ¡Publicar!

## Datos adjuntos :

- [Descargue el paquete de plantillas de PDF de ejemplo para ver los cambios aplicados.](../assets/publishing/NativePDF_DemoTemplate.zip)
- [Descargue el paquete de ajustes preestablecidos de PDF de ejemplo para ver los cambios aplicados.](../assets/publishing/Preset_Package.zip)


## Otros recursos:

- [Cómo incluir la tabla de contenido de DITA Bookmap en PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Vídeo de sesión de expertos sobre PDF nativo](../../expert-sessions/native-pdf-publishing-eamples-part1-june2023.md)
