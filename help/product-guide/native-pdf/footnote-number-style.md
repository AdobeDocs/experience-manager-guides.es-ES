---
title: Función de publicación nativa de PDF | Utilizar estilos personalizados en notas al pie
description: Aprenda a aplicar estilo a los números de las notas al pie.
exl-id: f1068f2f-2ace-4bdb-b5a4-46b03d4e43d6
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 0%

---

# Aplicar estilos de nota al pie


Las notas al pie son notas colocadas en la parte inferior de una página que comentan o citan una referencia para una parte designada del texto.

Cada nota al pie tiene un marcador de nota al pie en la parte inferior de la página, que suele ser un número o un símbolo como un asterisco. Dentro del contenido principal, el mismo marcador de nota al pie aparece como una llamada de nota al pie y se indica con el mismo número o símbolo que un superíndice.




## Cambiar los estilos de las llamadas y marcadores de notas al pie

Puede cambiar los estilos de las llamadas y los marcadores de notas al pie y administrar su aspecto en la salida del PDF. Estos estilos le ayudan a identificar rápidamente las notas al pie en el documento.


**Ejemplo 1**:

Utilice el ejemplo dado para agregar un corchete antes y después de la llamada y el marcador de la nota al pie:

* Añada el prefijo &quot;(&quot; y el sufijo &quot;)&quot; utilizando el atributo content en `footnote-call` estilo, que agregará los corchetes alrededor del número de nota al pie en el contenido del tema.
* Añada el prefijo &quot;(&quot; y el sufijo &quot;)&quot; utilizando el atributo content en `footnote-marker` estilo, que agregará los corchetes alrededor del número de nota al pie en la parte inferior de la página.

```css
...
.fn::footnote-call { 
content: "(" counter(footnote, decimal) ")"; 
} 

.fn::footnote-marker { 
content: "(" counter(footnote, decimal) ")"; 
} 

...
```



<img src="./assets/pdf-output-footer-numbers.png" alt="Pie de página en salida de PDF" width="500" border="2px">

*Agregue corchetes alrededor de la llamada de nota al pie y del marcador de nota al pie.*

**Ejemplo 2**:

También puede marcar la llamada de nota al pie y el marcador con un asterisco o un carácter griego inferior en lugar de un número.


```css
.fn::footnote-call {
 content: counter(footnote, asterisks);
}
.fn::footnote-marker {
 content: counter(footnote, asterisks) " ";
}
```

En la salida, puede ver algo así como:

<img src="./assets/footnote-number-2.png" alt="Pie de página en salida de PDF" width="500" border="2px">

*Agregar un asterisco a una llamada de nota al pie y un marcador.*

## Ocultar una llamada de nota al pie

También puede aplicar un estilo a las llamadas de notas al pie con atributos específicos. Por ejemplo, use el estilo siguiente para ocultar una nota al pie con los identificadores: La llamada de nota al pie está oculta en el contenido principal, pero el marcador de nota al pie aparece en la parte inferior de la página.

```css
.fn[id]::footnote-call {
		display: none;
                        }
```

## Dar formato al área de notas al pie

El área de notas al pie es donde se colocan todas las notas al pie, generalmente en la parte inferior de una página. Puede dar formato al área de notas al pie utilizando los diseños de página o los estilos CSS.


### Diseños de página

Puede utilizar las propiedades de página de los diseños de página para aplicar estilo al área de notas al pie en las distintas secciones de un documento de PDF. Por ejemplo, puede especificar las propiedades de márgenes y relleno del área de notas al pie en un capítulo. También puede cambiar el lado del borde, el estilo, el color, la anchura y el radio.

Obtenga información sobre cómo [trabajar con las propiedades de página de un diseño de página](./design-page-layout.md#page-props-page-layout).

### Estilos CSS

Puede aplicar estilos y dar formato al área de notas al pie en un documento de PDF. Por ejemplo, puede cambiar la longitud, el estilo, el color y el ancho del borde.

```css
	@page {
	  @footnote {
   		border-top-style: solid;
   		border-top-color: #FF0000;
   		border-top-width: 3px;
 		        }
	      }
```

## Reiniciar la numeración de las notas al pie

De forma predeterminada, las notas al pie se numeran continuamente en un documento. Sin embargo, puede utilizar diseños de página o estilos CSS para reiniciar la numeración de las notas al pie.


### Diseños de página

Puede especificar un número en los diseños de página para reiniciar la numeración de las notas al pie en las diferentes secciones de un documento de PDF. Por ejemplo, seleccione un número del **Reiniciar la numeración desde** en el panel Propiedades de página para reiniciar la numeración de las notas al pie de cada capítulo.

### Estilos CSS

Utilice el siguiente estilo para restablecer la numeración de las notas al pie en cada página de la salida del PDF:

```css
@page
{
counter-reset: footnote
}
```

Las notas al pie de cada página se reinician a partir de 1.

## Mostrar notas al pie en línea

Normalmente, cada nota al pie aparece como un bloque o comienza en una nueva línea. Pero también puede colocarlos en línea o uno junto al otro.

```css
.fn{
  	display: inline;
              }
```

## Aplicar estilos a las referencias cruzadas de notas al pie

También puede hacer referencias cruzadas a una nota al pie y hacer referencia a la misma nota varias veces en la salida del PDF. Esto le ayuda a referirse a la misma cita o nota detallada varias veces en el documento sin volver a crear una nota al pie para ella.

Por ejemplo, la siguiente captura de pantalla muestra cómo se hace referencia a la misma nota al pie en todas las ciudades de la salida del PDF.
<img width="550" alt="referencias de nota al pie en un pdf" src="./assets/link-footnotes.png" border="2px">

*Insertar la referencia cruzada a una nota al pie.*





Con los estilos CSS, también puede dar formato a las referencias cruzadas en notas al pie. Por ejemplo, se puede cambiar el color de fondo de las referencias cruzadas.

```css
    .xref-fn{
	background-color: red;
	}
```



