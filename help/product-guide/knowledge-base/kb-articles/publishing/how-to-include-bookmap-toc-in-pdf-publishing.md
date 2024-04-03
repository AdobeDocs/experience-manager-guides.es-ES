---
title: Publicación de índices (tabla de contenido) mediante PDF nativo
description: Publicar una tabla de contenido y otra lista de libros para su mapa de datos con NativePDF
feature: Native PDF Output
role: User, Admin
source-git-commit: 6ccaef5d35d492fe8dbe0f8b52af8d11258f3d2a
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 0%

---

# Generación de la tabla de contenido de Bookmap en publicaciones de PDF

## Configure su Bookmap

Incluya el `<toc>`  Elemento: Dentro del mapa de libros `<frontmatter>`, busque el elemento `<booklists>` Elemento.  Anidar una `<toc>` elemento interior `<booklists>` así:

```
<frontmatter>
  <booklists>
    <toc/>  <figurelist/>
    <tablelist/>
  </booklists>
</frontmatter>
```

La especificación DITA permite colocar el índice y las listas de libros dentro de la `<backmatter>` también en la sección.


```
<backmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <indexlist/>
    </booklists>
  </backmatter>
```

El índice y las listas de libros se generan automáticamente en función de la estructura definida en el mapa de libros.

Una vez configurado el bookmap, utilice el PDF nativo para generar la salida del PDF. Procesa la estructura del mapa de libros y las referencias, incluidas la tabla de contenido y las listas de libros.

## Diseño de la tabla de contenido y su orden en PDF

La funcionalidad de PDF nativo proporciona un método conveniente para adaptar el diseño de la tabla de contenido.

Puede controlar el diseño mediante un diseño de página independiente para la tabla de contenido y los estilos mediante layout.css.

El orden de la tabla de contenido y otras listas de libros en PDF solo se basa en la estructura del mapa de libros.

![tdc](../assets/publishing/toc.png)


## Preguntas más frecuentes

- ### Cómo incluir el índice de Ditamap en un PDF

Los propios mapas de datos no tienen directamente una tabla de contenido (TOC) como lo hace un mapa de libros. Sin embargo, los mapas de contenido desempeñan un papel crucial a la hora de definir la estructura del contenido y contribuyen indirectamente al proceso de generación de índices.

Si publica Ditamap, el PDF nativo proporciona la funcionalidad para generar TDC y listas de libros automáticamente . Puede habilitar o deshabilitar la generación de TDC en ditamap desde la configuración del PDF nativo.

![Habilitar Deshabilitar TDC](../assets/publishing/pageorder.png)

## Recursos adicionales:

- [Documentación del diseño de página de diseño del PDF nativo](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/install-guide/on-prem-ig/output-gen-config/config-native-pdf-publish/design-page-layout)
- [Aspectos básicos del PDF nativo sesión de experto pregrabada](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/expert-session/native-pdf-publishing-essentials-feb23)

<br>
<br>

AEM Publica tus preguntas en la Comunidad de Guías de la [foro](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) para cualquier consulta.


