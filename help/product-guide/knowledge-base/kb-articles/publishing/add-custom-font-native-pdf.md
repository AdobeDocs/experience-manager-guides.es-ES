---
title: Añadir fuentes personalizadas al PDF DITA
description: Consiga una integración de fuentes personalizada para reforzar la identidad de marca y la coherencia visual en todo el contenido en archivos PDF DITA nativos.
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: 151e3b1c-6340-4ff2-84d4-246bc4b68065
TQID: https://experienceleague.adobe.com/xqr9eYA2XTcyXL8X4aS-Wu2-FmU8-aCWDpb-L2BBFqI
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
source-wordcount: 223
ht-degree: 0%

---

# Añadir fuentes personalizadas al PDF nativo DITA

## Este artículo trata sobre:

Añadir la fuente personalizada para reforzar la identidad de la marca y la coherencia visual en todo el contenido.

Este proceso consta de 3 pasos:

- [Cargar la fuente personalizada](#step-1--upload-the-custom-font-to-the-resource-folder-of-your-template)
- [Realice los cambios necesarios en la hoja de estilo de las plantillas de PDF](#step-2--make-necessary-changes-in-pdf-templatess-stylesheet)

- [Incrustar fuentes utilizadas (opcional)](#step-3-optional--embed-used-font-in-pdf)

## Paso 1 : Cargue la fuente personalizada en la carpeta de recursos de la plantilla

![Cargar e importar fuentes personalizadas &#x200B;](../assets/publishing/custom-font1.png)

## Paso 2: Realice los cambios necesarios en la hoja de estilo de las plantillas de PDF

![Cara de fuente en la hoja de estilo de la plantilla de PDF &#x200B;](../assets/publishing/custom-font2.png)

## Paso 3 (opcional) : Fuente utilizada incrustada en PDF

![Incrustación de fuente personalizada en DITA PDF &#x200B;](../assets/publishing/custom-font3.png)

## Preguntas frecuentes

### ¿Puedo usar Adobe Fonts?

> Sí, vaya a fonts.adobe.com y haga clic en &quot;Agregar a proyecto web&quot;.
> 
> Copiar código de importación como `" @import url("https://use.typekit.net/xxxx.css")`;
>
> Pegue en el CSS de contenido y realice los cambios deseados en el archivo CSS.

![Usar adobe font en DITA PDF](../assets/publishing/custom-font4.png)


### Mi fuente no se muestra en PDF

> Comprobar la ortografía del nombre de la fuente (error más común)
>
> Asegúrese de incrustar la fuente si estas no están disponibles en el sistema donde se abre PDF

## Para cualquier otra consulta, póngase en contacto con sus respectivos CSM


## Otros recursos:

- [Cómo incluir la tabla de contenido de DITA Bookmap en PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Cómo incluir el índice en la publicación de PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Vídeo de sesión de expertos sobre PDF nativo](../../expert-sessions/native-pdf-publishing-eamples-part1-june2023.md)
