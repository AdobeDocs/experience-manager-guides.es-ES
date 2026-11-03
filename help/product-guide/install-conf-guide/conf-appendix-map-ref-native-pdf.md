---
title: Configuración del procesamiento del apéndice para referencias de mapa en la salida nativa de PDF
description: Aprenda a configurar Experience Manager Guides para que procese los temas agregados en un submapa dentro de un apéndice como contenido de apéndice en la salida nativa de PDF.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 63ae0f947d50646bed34cd815db6b9fb585fc015
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%
---

# Configuración del procesamiento del apéndice para referencias de mapa en la salida nativa de PDF

En la salida nativa de PDF, los temas a los que se hace referencia en un submapa dentro de un elemento `<appendix>` se pueden representar como capítulos en lugar de apéndices. De forma predeterminada, Experience Manager Guides clasifica las referencias de mapa por nombre de elemento y esa información se pierde una vez que los mapas se acoplan durante el procesamiento.

Use esta configuración para clasificar referencias de mapas usando el atributo `class` generado por DITA-OT en su lugar. Los temas de un submapa del apéndice se representan como apéndices.

>[!NOTE]
>
>Esta configuración cambia la forma en que se clasifican las referencias de mapas. Está desactivada de forma predeterminada. Habilítelo solo si su contenido coloca los temas en un submapa dentro de un `<appendix>` y los ve procesados como capítulos en la salida nativa de PDF.

## Cuándo usar esta configuración

Consideremos el siguiente ejemplo de mapa de un libro:

- Un elemento `<appendix>` hace referencia a temas directamente. Estos temas se representan como apéndices en el PDF generado.

  ```XML
  <booktitle>
      <mainbooktitle>Product Guide</mainbooktitle>
    </booktitle>
    <frontmatter>
      <booklists>
        <toc/>
        <tablelist/>
      </booklists>
      <preface href="topics/preface.dita">
      </preface>
    </frontmatter>
    <chapter class="foo" href="topics/getting-started.dita">
    </chapter>  
    <appendix href="topics/appendix-reference-tables.dita">
    </appendix>
    <appendix href="topics/appendix-troubleshooting.dita">
    </appendix>
    <backmatter>
      <booklists>
        <indexlist/>
      </booklists>
    </backmatter>
  </bookmap>`
  ```

- Otro elemento `<appendix>` hace referencia a un submapa y este hace referencia a temas que utilizan `<topicref>`.

  ```xml
  <booktitle>
      <mainbooktitle>Product Guide</mainbooktitle>
    </booktitle>
    <frontmatter>
      <booklists>
        <toc/>
        <tablelist/>
      </booklists>
      <preface href="topics/preface.dita">
      </preface>
    </frontmatter>
    <chapter class="foo" href="topics/getting-started.dita">
    </chapter>  
    <appendix format="ditamap" href="submap-for-appendix.ditamap" type="map">
    </appendix>
    <backmatter>
      <booklists>
        <indexlist/>
      </booklists>
    </backmatter>
  </bookmap>
  ```

  El submapa para el apéndice:

  ```xml
  <map id="GUID-cc306264-825c-455e-89db-d27af9197a2f">
    <title>submap-for-appendix</title>
    <topicref href="topics/appendix-reference-tables.dita" type="reference">
    </topicref>
    <topicref href="topics/appendix-troubleshooting.dita" type="topic">
    </topicref>
  </map>
  ```

Sin esta configuración, los temas del primer apéndice se procesan como apéndices, pero los temas del submapa se procesan como capítulos. Solo se publican los temas; el propio submapa se utiliza para la jerarquía y no aparece en la salida.

## Configure las opciones

A continuación se indican las instrucciones para configurar esta opción:

1. Siga las instrucciones indicadas en [Anulaciones de configuración](../install-conf-guide/download-install-config-override.md) para crear el archivo de configuración.

2. En el archivo de configuración, proporcione los siguientes detalles (propiedad):

   | PID | Clave de propiedad | Valor de propiedad |
   | --------------------------------------- | -------------------------------- | ----------------------------- |
   | `com.adobe.fmdita.config.ConfigManager` | `guides.publish.config` | {USE_DITA_OT_GENERATED_CLASS&quot;: false} |

3. Establezca el valor en `true` para habilitar la opción e implemente la configuración mediante Cloud Manager.