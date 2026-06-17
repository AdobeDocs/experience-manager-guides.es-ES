---
title: Nuevo motor de publicación para PDF nativo | Generación de resultados de PDF
description: Aprenda a trabajar con el nuevo motor de publicación para la publicación nativa de PDF
feature: Publishing, Native PDF Output
role: User
TQID: https://experienceleague.adobe.com/GV3iYtBdFVrQwFjdvfqnfDIWPMugO3hFjS4FZqspG2M
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: afb45297-4313-4f67-818e-bc0b03abe086
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
  - id: f6b497f1-f8e0-42ce-8e95-56c28d94026e
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 010a11e20d518064549ce7d66648586f49f572ec
workflow-type: tm+mt
source-wordcount: 913
ht-degree: 0%

---

# Trabajo con el motor nativo de PDF v2

El nuevo motor de publicación *Native PDF engine v2* se basa en un marco de trabajo actualizado de generación de PDF e incluye cambios en la administración de fuentes, el procesamiento CSS y el comportamiento de procesamiento.

Como resultado, la salida de PDF generada con el nuevo motor de publicación puede diferir de la salida generada con el motor de PDF existente (*Motor de PDF nativo v1*). Las diferencias pueden ser visibles en áreas como el diseño del texto, el espaciado, el estilo, el procesamiento de imágenes y el formato de notas al pie.

Por ejemplo, el motor nativo PDF v2 admite fuentes `OpenType`, mientras que el motor nativo PDF v1 se basa principalmente en fuentes `TrueType`. Mejoras de procesamiento similares pueden afectar al aspecto general de los PDF generados.

Para obtener más información sobre cómo habilitar el motor de publicación nativo de PDF v2 en su entorno, vea [Configurar el nuevo motor de publicación para PDF nativo](./conf-new-pdf-engine.md).

## Actualizaciones CSS recomendadas para el nuevo motor de publicación

Si desea conservar el aspecto de la salida de PDF generada por el motor nativo de PDF v1 mientras utiliza el motor nativo de PDF v2, es posible que tenga que actualizar el CSS personalizado. Los cambios CSS recomendados que se describen a continuación pueden ayudar a mantener la coherencia de la salida después de habilitar la nueva configuración.

| Descripción | Actualización de CSS recomendada |
|-------------|------------------------------------------------|
| Las imágenes a escala pueden parecer diferentes debido a los cambios en el comportamiento de procesamiento de las imágenes. | Para restaurar el comportamiento de procesamiento de imágenes, agregue:<br><br><pre><code>&quot;css
image-rendering: pixelado;
&quot;</code></pre> |
| La alineación de la directriz de la tabla de contenido (TOC) puede aparecer ligeramente diferente debido a los cambios en el comportamiento de la renderización de la directriz. | Para restaurar la alineación de la línea directriz de la TDC, ajuste el estilo de los elementos directrices de la TDC en la hoja de estilo personalizada. Los cambios de CSS necesarios pueden variar según el diseño y el formato de la tabla de contenido. |
| El espaciado del texto y el ajuste de línea pueden diferir debido a los cambios en la renderización de la fuente y el procesamiento del diseño de glifos. | Si la hoja de estilo usa la familia de fuentes `sans-serif` o fuentes que muestran diferencias de espaciado, agregue:<br><br><pre><code>&quot;css
body { -ro-glyph-layout-mode: quality; }
&quot;</code></pre> |
| Es posible que las referencias a notas al pie ya no aparezcan como marcadores de superíndice debido a los cambios en el estilo predeterminado de las notas al pie. | Para restaurar los marcadores de notas al pie de página de estilo superíndice, agregue:<br><br><pre><code>&quot;css
.fn::marcador de nota al pie &lbrace;
  content: counter(nota al pie) &quot; &quot;;
  vertical-align: super;
  font-size: 65%;
&rbrace;
&quot;</code></pre> |
| El texto subrayado puede aparecer con más espacio entre el texto y el subrayado debido a los cambios en la posición del subrayado. | Para restaurar la posición del subrayado, utilice la propiedad `text-underline-offset` y ajuste el valor de desplazamiento según sea necesario. Por ejemplo:<br><br><pre><code>&quot;css
text-decoration: underline;
text-underline-offset: -0.1em;
&quot;</code></pre> |
| El espaciado entre los marcadores de lista y el texto del elemento de lista puede diferir debido a los cambios en el comportamiento de representación de la lista. | Para restaurar el espaciado, aumente el relleno izquierdo de los elementos de la lista. Por ejemplo:<br><br><pre><code>&quot;css
.step &lbrace;
  margin-top: 0,3 rem;
  margin-bottom: 0.5rem;
  padding-left: calc(1.5rem + 1ch);
&rbrace;
&quot;</code></pre> |
| El espaciado antes de los títulos puede diferir debido a los cambios en el comportamiento de contracción de los márgenes. | Para restaurar el espaciado, revise los márgenes de los elementos adyacentes y reduzca o quite los márgenes superiores e inferiores superpuestos donde sea necesario. Por ejemplo:<br><br><pre><code>&quot;css
h1.chapter { margin-top: 0; }
.chaptoc-body { margin-bottom: 0; }
&quot;</code></pre> |
| Los marcadores de verificación generados con CSS pueden aparecer con diferentes tamaños o estilos porque se representan con diferentes fuentes de reserva. | Para representar los marcadores de forma coherente, utilice una familia de fuentes que contenga ambos glifos. Por ejemplo:<br><br><pre><code>&quot;css
::marcador &lbrace;
  font-family: -ro-symbol !important;
&rbrace;
&quot;</code></pre> |
| Los marcadores de lista circular generados por CSS pueden aparecer parcialmente recortados o truncados debido a los cambios en el comportamiento de colocación de los marcadores. | Para restaurar el aspecto de los marcadores de lista circular, evite utilizar una posición absoluta para el marcador. Si se requiere una posición absoluta, especifique explícitamente un valor `top` apropiado para colocar correctamente el marcador. |
| El orden de lectura de los elementos de lista en la salida de PDF/UA puede diferir cuando los elementos de lista utilizan estilos de colocación como `position: relative`. | Para hacer que el orden de lectura siga más de cerca la estructura del documento de origen, aplique la siguiente propiedad CSS a los elementos de la lista:<br><br><pre><code>&quot;css
li &lbrace;
  -ro-pintura-reordenación: evitar;
&rbrace;
&quot;</code></pre> |


## Soluciones para problemas conocidos

Las siguientes soluciones pueden ayudar a resolver problemas conocidos en la salida de PDF generada al utilizar el motor de PDF nativo v2.

- `text-decoration` propiedades css aplicadas al contenido de la tabla no se representan en la salida de PDF.

  **Solución alternativa**: aplique las propiedades de decoración de texto a `span` elementos dentro del contenido de la tabla en lugar de aplicarlas directamente a los elementos de la tabla.

- Las propiedades CSS `-ro-colorbar-top-left` y `-ro-colorbar-top-right` no afectan a la barra de color en la salida de PDF.

  **Solución alternativa**: quite los valores correspondientes de la hoja de estilos de usuario de `mergedHTML.json` o agregue `!important` a los valores de las propiedades del documento CSS para que la hoja de estilos de usuario no los anule.

- Las barras de color pueden aparecer combinadas cuando el ancho de página está restringido porque las barras de color no se reducen con el tamaño de página en la salida de PDF.

  **Solución alternativa**: muestre las barras grises y de color en diferentes lados de la página o ajuste la configuración de la barra de color para que no se superpongan en anchos de página más pequeños.

## Se han corregido problemas con el nuevo motor de publicación

Los siguientes problemas en la salida de PDF generados con _Native PDF Engine v1_ se han corregido en _Native PDF Engine v2_:

- Al generar una salida nativa de PDF para determinado contenido, solo se procesa la primera página en PDF, a pesar de que la HTML intermedia contenga el contenido completo en varias páginas. (GUIDES-28270)
- El orden de lectura del contenido en la salida nativa de PDF con la configuración de accesibilidad habilitada es incorrecto. Los números de página de los pies de página se leen antes del contenido principal en lugar de al final. (GUIDES-27790)
- La barra de color de la salida nativa de PDF no se extiende por el ancho de página completo y se superpone cuando se personaliza el tamaño de página, lo que provoca que algunos cuadros de color se oculten. (GUIDES-15505)
- El selector `CSS:is()pseudo-class` no se cumple en la salida nativa de PDF, lo que provoca diferencias de estilo en comparación con la representación del explorador. (GUIDES-11328)