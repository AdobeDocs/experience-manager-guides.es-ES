---
title: Asignación de componentes para AEM Sites
description: Obtenga información sobre cómo realizar la asignación de componentes para AEM Sites
feature: Installation
role: Admin
level: Experienced
exl-id: 376aea7a-7850-44d4-a620-6b1a798a0801
source-git-commit: beb1ca15fdfb0e7ea30e6e685ac67a2a398cc064
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 0%

---

# Asignación de componentes para AEM Sites

El artículo habla sobre los distintos aspectos de la asignación de componentes para sitios de AEM (mediante la asignación de componentes compuestos).

## Reglas de asignación de componentes

Utilice una matriz de reglas JSON (su `componentmapping.json`) para convertir HTML en componentes. Mantenga las reglas tan simples, explícitas y específicas como sea posible.

### Oriente el elemento HTML y su clase

- Escriba el nombre de la etiqueta HTML en `name`.
- Incluya la clase CSS aplicada a ese elemento en `class`, si la clase existe.
Ejemplo:

  ```html
  <div class ="sample-class">
  <p> Sample html element </p>
  </div>
  ```

  ```json
  {
  "name": "div",
  "class": "sample-class",
  "resourceType": "guides-components/components/table",
  "attributeMap": []
  }
  ```

Al definir los elementos anteriores, asegúrese de lo siguiente:

- `name` puede ser una lista separada por comas (por ejemplo, `"h1, h2"`).
- `class` debe estar presente en el elemento (todas las clases enumeradas deben coincidir).
- `resourceType` indica que desea utilizar el componente `table`. El paquete `guides-components` es un OOTB proporcionado por las guías. También puede utilizar otros paquetes de componentes, como `core/wcm/`, según sea necesario.

### Utilice attributeMap para guardar las propiedades en el nodo JCR

Agregue entradas a `attributeMap` para establecer propiedades en el nodo de salida. Cada entrada genera `attrs[to] = value`.
Patrones comunes:

```json
// copy an attribute
{ "attribute": "src", "to": "image-src" }
// read content or tag name
{ "from": "textContent", "to": "jcr:title" }
{ "from": "outerHTML",  "to": "text" }
{ "from": "innerHTML",  "to": "text" }
{ "from": "name",       "to": "type" }  // the tag name, e.g., "h2"
// constant value
{ "value": true, "to": "textIsRich" }
```

A continuación se muestra un ejemplo de HTML a JSON para un elemento de imagen.

```html
<img src="/content/dam/aemg-docs/tragopan.svg" class="cmp-image__image" itemprop="contentUrl" data-cmp-hook-image="image" alt="">
```

```json
{
    "name": "img",
    "resourceType": "core/wcm/components/image/v2/image",
    "attributeMap": [
      {
        "from": "src",
        "to": "fileReference"
      },
      {
        "value": ["fileReference"],
        "to": "path-attributes"
      }
    ]
  }
```

### Normalizar rutas mediante una entrada dedicada

Si desea normalizar valores (convertir en absolutos), declare qué claves de atributo deben normalizarse utilizando:

```json
{
  "value": ["text"],
  "to": "path-attributes"
}
```

Asegúrese de tener en cuenta los siguientes puntos importantes:

- Coloque la lista de los nombres de propiedad que desea normalizar en `value` (por ejemplo, `["text"]` o `["href", "src"]`).
- El sistema normalizará cualquier valor encontrado en esos nombres de propiedad al crear el componente final.


### Extraer valores de HTML antes de dividirlos en componentes

Use `from` para especificar cómo leer un valor del elemento antes de que el documento se divida en componentes independientes:

- `"textContent"`: texto sin formato del elemento
- `"outerHTML"`: el elemento y su marcado interno
- `"innerHTML"`: solo el marcado interno del elemento
- Cualquier otra cadena: tratada como un nombre de atributo (por ejemplo, `"src"`, `"href"`)


Ejemplos:

```json
{ "from": "textContent", "to": "jcr:title" }
{ "from": "outerHTML",  "to": "text" }
{ "from": "innerHTML",  "to": "snippet" }
{ "from": "src",        "to": "image#src" }
```

### Ejemplo mínimo de extremo a extremo en componentmapping.json

```json
[
  {
    "name": "h1, h2",
    "class": "topic-title",
    "resourceType": "core/wcm/components/title/v2/title",
    "attributeMap": [
      { "from": "textContent", "to": "text" },
      { "from": "name",        "to": "type" }
    ]
  },
  {
    "name": "img",
    "class": "hero",
    "resourceType": "weretail/components/content/heroimage",
    "attributeMap": [
      { "from": "src", "to": "image#src" },
      { "value": ["image#src"], "to": "path-attributes" }
    ]
  },
  {
    "name": "#element",
    "resourceType": "core/wcm/components/text/v2/text",
    "attributeMap": [
      { "from": "outerHTML", "to": "text" },
      { "value": true,        "to": "textIsRich" }
    ]
  }
]
```

Defina el elemento y la clase a los que se va a dirigir, use `attributeMap` para establecer las propiedades del nodo, agregue una entrada `path-attributes` para normalizar las rutas y elija el `from` correcto para los valores que desee extraer. El(la) `heroimage` utilizado(a) arriba es un componente en un sitio `we-retail`.

**Nota**: Es importante analizar el texto enriquecido predeterminado e identificar los elementos para los que se utiliza.

## Crear un componente personalizado

Aprenda a crear un componente de tabla personalizado que muestre imágenes dentro de sus celdas. Este enfoque garantiza un diseño limpio y reutilizable para el contenido dinámico. Abarca lo que va a crear, por qué es eficaz, los requisitos previos clave, el diseño de alto nivel, etc.

### Lo que va a generar

Componente de tabla personalizado que acepta contenido de tabla de HTML y reemplaza cada `<img>` dentro de él con la salida del componente de imagen principal de AEM. Esto le permite reutilizar las funciones de la imagen principal (imágenes adaptables, control alternativo, accesibilidad) mientras mantiene un control total sobre el marcado de la tabla.
Con este método, puede crear otros componentes personalizados para su sitio web de AEM (mediante la asignación de componentes compuestos).

### Por qué este enfoque

- **Reutilizar**: aprovecha el comportamiento maduro de la imagen principal en lugar de volver a implementarla.
- **Coherencia**: las imágenes de la tabla se comportan de la misma manera que las imágenes de cualquier otra parte del sitio.
- **Lado del servidor**: las imágenes se representan en el servidor para rendimiento, SEO y accesibilidad.

### Requisitos previos

- AEM SDK en ejecución y este proyecto desprotegido.
- Componentes principales instalados en la instancia de AEM.
- Maven disponible para compilar e implementar.

### Diseño de alto nivel

- El autor proporciona HTML para la tabla en el cuadro de diálogo del componente.
- Un modelo Sling analiza ese HTML, encuentra `<img>` etiquetas y, para cada imagen, llama a un servicio que procesa el componente de imagen principal del lado del servidor.
- El modelo intercambia el(la) `<img>` original con el HTML de imagen principal capturado y pasa el HTML completado a HTL para su salida.

La tabla se genera una vez, y ya contiene el marcado de la imagen principal. No es necesaria ninguna manipulación DOM del lado del cliente.

### Estructura de carpetas y archivos de claves (en este repositorio)

- HTL de componente y clientlibs: `ui.apps/src/main/content/jcr_root/apps/guides-components/components/table/`
   - `table.html` (procesador HTL)
   - `_cq_editConfig.xml` (actualizar agentes de escucha)
   - `clientlibs/` con `css.txt`, `js.txt`, `css/table.css`, `js/table.js`
- Modelo Sling: `core/src/main/java/com/adobe/guides/aem/components/core/models/TableModel.java`
- Servicio de procesamiento de imágenes: `core/src/main/java/com/adobe/guides/aem/components/core/services/ImageComponentRenderer.java`

### Pasos de la implementación

**Defina el componente Tabla (nodo de componente)**

Cree el componente en `apps/guides-components/components/table`. Si todavía no tiene uno, agregue un mínimo de `.content.xml` como el que se muestra a continuación para registrarlo en el panel lateral.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          xmlns:jcr="http://www.jcp.org/jcr/1.0"
          jcr:primaryType="cq:Component"
          jcr:title="Table"
          componentGroup="Guides - Custom"/>
```

Indica a AEM que este es un componente disponible para que los autores lo agreguen a las páginas.

**Procesar con HTL e incluir estilos**

Utilice un modelo Sling y envíe el HTML procesado. Incluya la categoría clientlib para CSS/JS.

```html
<sly data-sly-use.model="com.adobe.guides.aem.components.core.models.TableModel"
     data-sly-use.clientLib="/libs/granite/sightly/templates/clientlib.html">
</sly>
<sly data-sly-call="${clientLib.css @ categories='guides-components.table'}"></sly>
<sly data-sly-test="${wcmmode.edit && !model.hasContent}">
  <div class="cq-placeholder" data-emptytext="${component.title}"></div>
</sly>
<div data-sly-test="${model.hasContent}"
     class="gu-table-wrapper ${model.enableResponsive ? 'gu-table--responsive' : ''} gu-table--style-${model.tableStyle}"
     id="${model.componentId}">
  ${model.processedTableHtml @ context='unsafe'}
</div>
```

El modelo devuelve HTML completo con la imagen principal ya representada, por lo que HTL solo la imprime.

**Agregar el modelo Sling para procesar HTML y procesar la imagen principal**

El modelo lee campos de diálogo, analiza la tabla de HTML, encuentra cada `<img>` y lo reemplaza por Core Image HTML a través de un servicio.

A continuación se indican algunos de los conocimientos importantes de `TableModel`:

- Lee `tableHtml`, `enableResponsive`, `tableStyle` desde las propiedades del recurso.
- Utiliza Jsoup para analizar y editar HTML de forma segura.
- Llama a `ImageComponentRenderer` para procesar la imagen principal y capturar HTML.
- Conserva las clases CSS y el estilo del objeto `<img>` original.
- Normaliza las rutas DAM (elimina `/jcr:content/renditions/*`).

```java
@Model(adaptables = {Resource.class, SlingHttpServletRequest.class},
       defaultInjectionStrategy = DefaultInjectionStrategy.OPTIONAL)
public class TableModel {
  @ValueMapValue private String tableHtml;
  @ValueMapValue private boolean enableResponsive;
  @ValueMapValue private String tableStyle;
  @OSGiService private ImageComponentRenderer imageRenderer;
  // ...
  @PostConstruct
  protected void init() {
    // parse HTML, for each <img> build image props (fileReference, alt, title)
    // call imageRenderer.renderImageComponent(...)
    // replace <img> with returned Core Image HTML
  }
  public String getProcessedTableHtml() { /* return final HTML */ }
}
```

Esto centraliza la lógica en el servidor y reutiliza el comportamiento de la imagen principal.

**Procesar imagen principal mediante un servicio (incluido en el servidor)**

`ImageComponentRenderer` procesa el componente de imagen principal y captura el resultado. It

- ajusta un recurso que fuerza `core/wcm/components/image/v2/image`.
- utiliza `RequestDispatcher#include` para procesarlo.
- captura la respuesta como una cadena.

```java
@Component(service = ImageComponentRenderer.class)
public class ImageComponentRenderer {
  private static final String IMAGE_RESOURCE_TYPE = "core/wcm/components/image/v2/image";
  public String renderImageComponent(Resource base, Map<String,Object> props,
                                     SlingHttpServletRequest req, SlingHttpServletResponse resp) {
    // create wrapped resource with IMAGE_RESOURCE_TYPE and props
    // dispatcher.include(...) with a response wrapper to capture HTML
    // return captured HTML
  }
}
```

Esto le permite **colocar** imagen principal donde la necesite, no solo como componente secundario.

**Bibliotecas de cliente**

Cree una clientlib para estilos pequeños o JS futuros. El HTL anterior carga la categoría `guides-components.table`.

```java
clientlibs/css.txt
  #base=css
  table.css
clientlibs/js.txt
  #base=js
  table.js
  
```

Esto mantiene los estilos/scripts modulares y reconocibles.

**Campos de diálogo (entradas del autor)**

Añada un cuadro de diálogo con al menos estas propiedades:

- **HTML de tabla**: `./tableHtml` (área de texto); el HTML de la tabla.
- **Habilitar capacidad de respuesta**: `./enableResponsive` (casilla de verificación); activa o desactiva una clase contenedora adaptable.
- **Estilo de tabla**: `./tableStyle` (seleccionar); aplica una clase de modificador de estilo.

Estos asignan 1:1 a las propiedades y controlan la representación del modelo Sling.

**Permitir el componente en las plantillas**

En el Editor de plantillas, edite la directiva Contenedor de diseños > Componentes permitidos > Habilite el componente Tabla en **Guías - Personalizadas**.

Los autores no pueden agregar componentes hasta que las directivas lo permitan.

## Sugerencias de creación

- Pegue un HTML válido para la tabla. El modelo sanea y ajusta las direcciones URL de la imagen.
- Utilice rutas de recursos DAM para imágenes; las representaciones se normalizan a la ruta de recursos original.
- Proporcione texto alternativo en HTML siempre que sea posible; de lo contrario, las imágenes se marcarán como decorativas.

## Restricciones

- El servicio fuerza la imagen principal v2. Para cambiar de versión, actualice `IMAGE_RESOURCE_TYPE`.
- Para el procesamiento sintético, el modelo reemplaza las URL `.coreimg.` generadas por la imagen principal con rutas DAM directas y elimina `srcset` para evitar URL rotas.
- Todos los procesamientos se realizan una vez en el servidor; JavaScript es opcional.

## Referencia rápida (implementación)

- HTML: `ui.apps/.../components/table/table.html`
- Clientlibs: `ui.apps/.../components/table/clientlibs/`
- Modelo: `core/.../models/TableModel.java`
- Servicio: `core/.../services/ImageComponentRenderer.java`

Este patrón muestra cómo componer un componente personalizado con un componente principal del lado del servidor, conservando el marcado y reutilizando la lógica principal.
