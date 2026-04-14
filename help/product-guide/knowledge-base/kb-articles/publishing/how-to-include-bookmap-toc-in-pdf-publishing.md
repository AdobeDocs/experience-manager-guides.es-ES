---
title: Publicación de índices (tabla de contenido) mediante PDF nativo
description: Publicar una tabla de contenido y otra lista de libros para su mapa de datos con NativePDF
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: c551f0a8-f973-4c5a-bd34-f52890a91342
source-git-commit: 9c53ac725618db1164b0ed310a47b258a7224778
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Generación de la tabla de contenido de Bookmap en publicaciones de PDF

## Configure su Bookmap

Incluir el elemento `<toc>`:
Dentro del elemento `<frontmatter>` del mapa de libros, busque el elemento `<booklists>`.  Anide un elemento `<toc>` dentro de `<booklists>` de esta manera:

```
<frontmatter>
  <booklists>
    <toc/>  <figurelist/>
    <tablelist/>
  </booklists>
</frontmatter>
```

La especificación DITA también permite colocar el índice y las listas de libros dentro de la sección `<backmatter>`.


```
<backmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <indexlist/>
    </booklists>
  </backmatter>
```

Estructura de muestra del bookmap con el TOC , la lista de figuras y la lista de tablas en el frontmatter y la lista de índices en el backmatter.

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

El índice y las listas de libros se generan automáticamente en función de la estructura definida en el mapa de libros.

Una vez configurado el bookmap, utilice PDF nativo para generar la salida de PDF. Procesa la estructura del mapa de libros y las referencias, incluidas la tabla de contenido y las listas de libros.

## Diseño de la tabla de contenido y su orden en PDF

La funcionalidad nativa de PDF proporciona un método cómodo para adaptar el diseño de la tabla de contenido.

Puede controlar el diseño mediante un diseño de página independiente para la tabla de contenido y los estilos mediante layout.css.

El orden de los índices y otras listas de libros en PDF se basa únicamente en la estructura del mapa de libros.

![toc](../assets/publishing/toc.png)


## Preguntas frecuentes

### Cómo incluir el índice de un mapa de datos en un PDF

Los propios mapas de datos no tienen directamente una tabla de contenido (TOC) como lo hace un mapa de libros. Sin embargo, los mapas de contenido desempeñan un papel crucial a la hora de definir la estructura del contenido y contribuyen indirectamente al proceso de generación de índices.

Si publica Ditamap, Native PDF ofrece la funcionalidad de generar TDC y listas de libros automáticamente . Puede habilitar o deshabilitar la generación de TDC en ditamap desde la configuración nativa de PDF.

![Habilitar Deshabilitar TDC](../assets/publishing/pageorder.png)

## Recursos adicionales:

- [Documentación de diseño de página de diseño nativa de PDF](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/install-guide/on-prem-ig/output-gen-config/config-native-pdf-publish/design-page-layout)
- [Sesión de expertos pregrabada de elementos esenciales de PDF nativos](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/expert-session/native-pdf-publishing-essentials-feb23)

<br>
<br>

Publica en la comunidad de AEM Guides [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) para cualquier consulta.



