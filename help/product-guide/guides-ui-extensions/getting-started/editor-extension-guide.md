---
title: Cambios en la estructura de extensiones de Editor 2.0
description: Obtenga información acerca de los cambios en el marco de trabajo de extensión de Editor 2.0
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 3f38264b6ce09366d07cdd302c9c53e8abcf4b7c
workflow-type: tm+mt
source-wordcount: '2003'
ht-degree: 4%

---

# Cambios en la estructura de la extensión de Editor 2.0 (nuevo editor)

Este documento cubre todas las API agregadas a `guides.editor` (y a `guides`) como parte del marco de trabajo de extensión para el nuevo editor (editor basado en ProseMirror). Estas API permiten que las extensiones externas interactúen con el editor sin manipulación DOM directa ni conocimientos de implementación interna.

## Información general

El objeto `guides` global es el punto de entrada para todas las integraciones de extensiones:

```js
guides.editor    // Editor interaction APIs
guides.util      // Utility libraries (lodash, async)
guides.ready(cb) // Lifecycle hook fires when the editor is fully loaded
```

Todas las API `guides.editor` se pueden llamar con seguridad desde controladores de extensión, controladores de barra de herramientas y lógica de diálogo.

## Ciclo de vida

`guides.ready(callback)`: registra una llamada de retorno para ejecutarla una vez que el administrador de vista de página se haya cargado completamente. Utilícelo antes de registrar complementos o realizar cualquier configuración del editor.

**Firma:**

```ts
guides.ready(callback: () => void): void
```

**Ejemplo:**

```js
guides.ready(() => {
  // Safe to access guides.editor APIs here
  guides.editor.registerPlugin(createMyPlugin);
});
```

## Propiedades de estado del editor

- `guides.editor.filePath`: devuelve la ruta de archivo del documento activo.

  **Tipo:** `string | undefined`

  **Ejemplo: leyendo ruta de archivo para una llamada de API de metadatos:**

  ```js
  const filePath = guides.editor.filePath;
  if (filePath) {
  tcx.api.getMetadata(filePath).subscribe((metadata) => {
    // use metadata...
    });
  }
  ```

  **Ejemplo: lógica condicional basada en la ubicación del archivo**

  ```js
  const filePath = guides.editor.filePath;
  if (filePath?.endsWith(".ditamap")) {
    // ditamap-specific handling
  }
  ```

- `guides.editor.version`: devuelve la cadena de versión del editor cargado actualmente.

  | Valor | Editor |
  |---------|------------------------------------|
  | `1.0.0` | Editor CKE heredado (`xml_author_view`) |
  | `2.0.0` | Nuevo editor (basado en ProseMirror) |

  **Tipo:** `string`

  **Ejemplo:**

  ```js
  if (guides.editor.version  === '1.0.0') {
    // CKEditor specific logic 
  }
  ```

- `guides.editor.appState(keyName)`: lee un valor del modelo de aplicación por nombre de clave.

  **Firma:**

  ```ts
  guides.editor.appState(keyName: string): unknown
  ```

  **Ejemplo:**

  ```js
  const editorMode = guides.editor.appState('editorMode');
  ```

## Interacción del editor

- `guides.editor.focus()`: establece el enfoque en el editor activo. Invoque esto antes de ejecutar comandos que requieran que el editor esté enfocado.

  **Firma:**

  ```ts
  guides.editor.focus(): boolean
  ```

  **Ejemplo: enfoque antes de insertar contenido**

  ```js
  guides.editor.focus();
  const hasSelection = !!guides.editor.runUtil('hasSelection');
  // ...proceed with wrap or insert
  ```

- `guides.editor.canInsertXmlElement(tagName, insertAfter?)`: comprueba si un elemento XML determinado se puede insertar en la posición actual del cursor.

  **Firma:**

  ```ts
  guides.editor.canInsertXmlElement(tagName: string, insertAfter?: boolean): boolean
  ```

  **Ejemplo: proteger antes de insertar`<xref>`**

  ```js
  const canInsert = guides.editor.canInsertXmlElement("xref");
  if (!canInsert) {
    return tcx.util.showAlert("warning", "xref is not allowed here");
  }
  ```

  **Ejemplo: proteger antes de insertar `<sup>` /`<sub>`**

  ```js
  const canInsert = guides.editor.canInsertXmlElement("sup");
  if (!canInsert) {
    return tcx.util.showAlert("warning", "superscript is not allowed here");
  }
  ```

- `guides.editor.selectCurrentBlockElement()`: selecciona el elemento de nivel de bloque actual en el editor.

  **Firma:**

  ```ts
  guides.editor.selectCurrentBlockElement(): boolean
  ```

  **Ejemplo:**

  ```js
  guides.editor.selectCurrentBlockElement();
  ```

- `guides.editor.getValidElementNamesForInsertion(args)`: devuelve una lista de nombres de elementos XML válidos que se pueden insertar en la posición actual.

  **Firma:**

  ```ts
  guides.editor.getValidElementNamesForInsertion(args: {
    insertMode?: 'after' | 'before' | 'rename',
    strict: boolean
  }): string[] | false
  ```

  **Ejemplo:**

  ```js
  const validElements = guides.editor.getValidElementNamesForInsertion({
    insertMode: 'after',
    strict: true
  });
  ```

- `guides.editor.updateAttributeByXpath(args)`: actualiza un atributo XML específico en un nodo identificado por su XPath. Delega en el método `updateAttributeByXpath` del editor activo.

  **Firma:**

  ```ts
  guides.editor.updateAttributeByXpath(args: UpdateXpathArgs): any
  ```

## Ejecución de comandos

- `guides.editor.runCommand(commandName, ...args)`: ejecuta un comando con nombre en el nuevo editor. Devuelve `true` si el comando se realizó correctamente, `false` en caso contrario.

  **Firma:**

  ```ts
  guides.editor.runCommand(commandName: string, ...args: any[]): boolean
  ```

  **Comandos disponibles**

  >[!NOTE]
  >
  > Estabilidad: los comandos enumerados a continuación forman parte de la interfaz pública. Sus nombres, firmas y comportamiento observable se consideran estables y se mantienen para mantener la compatibilidad. Pueden existir comandos adicionales dentro del editor; sin embargo, estos son internos, no están pensados para uso externo y pueden cambiar o eliminarse sin previo aviso.

  | Categoría | Comando | Argumentos | Descripción |
  |---|---|---|---|
  | General | `undo` | _(ninguno)_ | Deshace el último cambio de documento |
  | General | `redo` | _(ninguno)_ | Rehace el último cambio deshecho |
  | Selección | `select` | `from: number, to?: number` | Selecciona el rango de `from` a `to` (o solo `from` si se omite `to`) |
  | Selección | `cursor` | `pos: number` | Mueve el cursor a `pos` |
  | Selección | `selectNodesFromXpaths` | `xpaths: Array<{path: Array<{name: string, count: number}>}>` | Selecciona nodos identificados por posiciones XPath |
  | Formato | `toggleBold` | _(ninguno)_ | Cambia el formato de negrita en la selección actual |
  | Formato | `toggleItalic` | _(ninguno)_ | Cambia el formato de cursiva en la selección actual |
  | Formato | `toggleUnderline` | _(ninguno)_ | Alterna el formato de subrayado en la selección actual |
  | Formato | `toggleFormatting` | `markType: string, allowEmptySelection?: boolean` | Alterna un elemento de formato (por ejemplo, `'b'`, `'i'`, `'sup'`, `'sub'`) en la selección |
  | Inserción | `insertText` | `text: string` | Inserta texto sin formato en el cursor |
  | Inserción | `insertXml` | `xml: string, position?: number, options?: InsertXmlOptions` | Inserta XML sin procesar en el cursor o en una posición determinada |
  | Inserción | `insertXmlAfterElement` | `elementName: string, xmlString: string` | Inserta XML inmediatamente después del antecesor más cercano que coincida con `elementName` |
  | Inserción | `replaceSelectionWithXml` | `xmlString: string` | Reemplaza la selección actual con el XML dado |
  | Operaciones del nodo | `surroundWithElement` | `tagName: string, attrs?: Record<string,unknown>, replaceTextWithEmptyNode?: boolean` | Ajusta la selección actual con el elemento dado |
  | Operaciones del nodo | `wrapNode` | `type: string, target?: number, attrs?: Record<string, unknown>` | Envuelve el nodo en `target` (o el nodo actual) en un elemento de `type` |
  | Operaciones del nodo | `renameNode` | `newNodeName: string` | Cambia el nombre del elemento del nodo actual |
  | Operaciones del nodo | `unwrapNode` | _(ninguno)_ | Quita el elemento envolvente del nodo actual y mantiene su contenido |
  | Eliminar | `deleteSelection` | _(ninguno)_ | Elimina el contenido seleccionado actualmente |
  | Eliminar | `deleteNode` | _(ninguno)_ | Elimina todo el nodo actual |
  | Atributos | `setNodeXmlAttributes` | `position: number, attrs: Record<string, unknown>` | Establece varios atributos XML en el nodo en `position` |
  | Atributos | `setNodeXmlAttribute` | `position: number, attrName: string, value: string` | Establece un único atributo XML en el nodo en `position` |
  | Listas | `toggleList` | `listName: 'ol' \| 'ul'` | Alterna el bloque actual entre una lista del tipo dado y un párrafo |
  | Tablas | `addRowAfter` | `count?: number` | Agrega `count` filas debajo de la fila actual (valor predeterminado 1) |
  | Tablas | `addColumnAfter` | `count?: number` | Agrega `count` columnas a la derecha de la columna actual (valor predeterminado 1) |
  | Tablas | `deleteRow` | _(ninguno)_ | Elimina la fila actual |
  | Tablas | `deleteColumn` | _(ninguno)_ | Elimina la columna actual |
  | Tablas | `mergeCells` | _(ninguno)_ | Combina las celdas seleccionadas actualmente |
  | Portapapeles | `copy` | _(ninguno)_ | Copia la selección actual en el portapapeles |
  | Portapapeles | `cut` | _(ninguno)_ | Corta la selección actual al portapapeles |
  | Buscar y reemplazar | `setSearchQuery` | `query: string, options?: { caseSensitive?: boolean, regex?: boolean }` | Establece la consulta de búsqueda activa |
  | Buscar y reemplazar | `findNext` | _(ninguno)_ | Se desplaza a la siguiente coincidencia de búsqueda |
  | Buscar y reemplazar | `replaceAll` | `replacement?: string` | Reemplaza cada coincidencia de la consulta de búsqueda actual por `replacement` |

   - **Ejemplo: establecer varios atributos en un nodo**

     ```js
     guides.editor.runCommand(
       "setNodeXmlAttributes",
       rootRange.from,
       { createdDate: "2024-01-01", author: "Jane Doe" }
     );
     ```

   - **Ejemplo: establecer un solo atributo en un nodo**

     ```js
     guides.editor.runCommand(
       "setNodeXmlAttribute",
       range.from,
       "placeholdertext",
       "Chapter 3 — Safety Requirements"
     );
     ```

   - **Ejemplo: ajuste la selección con un elemento y establezca los atributos**

     ```js
     const didWrap = guides.editor.runCommand(
       "surroundWithElement",
       "ph",
       { outputclass: "highlight" },
       true   // replace text content with empty node
     );
     ```

   - **Ejemplo: ajuste de selección en `<sup>` (alternar superíndice activado)**

     ```js
     const didWrap = guides.editor.runCommand('surroundWithElement', 'sup');
     if (!didWrap) {
       tcx.util.showAlert("warning", "superscript is not allowed here");
     }
     ```

   - **Ejemplo: Desenvolver nodo actual (desactivar superíndice)**

     ```js
     const didUnwrap = guides.editor.runCommand('unwrapNode');
     ```

   - **Ejemplo: Insertar XML en el cursor con el símbolo de intercalación dentro**

     ```js
     guides.editor.runCommand(
       'insertXml',
       '<sup></sup>',
       undefined,
       { setCursorInContent: true, focusEditor: true, selectInsertedXml: false }
     );
     ```

- `guides.editor.canRunCommand(commandName, ...args)`: comprueba si un comando con nombre se puede ejecutar actualmente sin ejecutarlo realmente.

  **Firma:**

  ```ts
  guides.editor.canRunCommand(commandName: string, ...args: any[]): boolean
  ```

  **Ejemplo:**

  ```js
  if (guides.editor.canRunCommand('surroundWithElement', 'sup')) {
    guides.editor.runCommand('surroundWithElement', 'sup');
  }
  ```

## Funciones de utilidad

- `guides.editor.runUtil(utilName, ...args)`: invoca una utilidad con nombre desde el Registro de utilidades del nuevo editor. Devuelve el resultado de la utilidad o `undefined` si no se encuentra la utilidad.

  **Firma:**

  ```ts
  guides.editor.runUtil(utilName: string, ...args: any[]): any
  ```

  **Utilidades disponibles**

  >[!NOTE]
  >
  > Estabilidad: las utilidades enumeradas a continuación forman parte de la interfaz pública. Sus nombres, firmas y comportamiento observable se consideran estables y se mantienen para mantener la compatibilidad. Pueden existir comandos adicionales dentro del editor; sin embargo, estos son internos, no están pensados para uso externo y pueden cambiar o eliminarse sin previo aviso.


  | Categoría | Utilidad | Argumentos | Devuelve | Descripción |
  |---|---|---|---|---|
  | Posición | `getTextPos` | _(ninguno)_ | `{ start: number, end: number }` | Posiciones inicial y final de la selección actual en el documento ProseMirror |
  | Posición | `getNodePosition` | `position?: number` | `number` | Posición del documento del nodo seleccionado/centrado actualmente |
  | Posición | `mapToXpath` | `position: number` | `XPathPosition` | Asigna una posición de ProseMirror a un descriptor XPath |
  | Posición | `inverseMap` | `xpath: XPathPosition \| number` | `number` | Asigna un descriptor XPath (o una posición numérica) de nuevo a una posición de ProseMirror |
  | Documento | `getNodeTree` | _(ninguno)_ | `NodeTree \| null` | Representación de árbol del documento, adecuada para la representación de contornos |
  | Documento | `getAncestorsNames` | `position?: number` | `string[]` | Nombres de etiquetas XML de nodos antecesores en `position` |
  | Documento | `getAncestorsDetails` | `position?: number` | `{ currNode: string, ancestors: Array<{tagName: string}>, previousSibling?: string, nextSibling?: string } \| undefined` | Nodo actual, antecesores y hermanos inmediatos en `position` |
  | Documento | `getAncestorXpaths` | `includeId?: boolean` | `AncestorXpathItem[]` | Cadenas XPath para todos los nodos antecesores |
  | Documento | `getPreviousSibling` | `position?: number` | `string \| undefined` | Nombre de etiqueta del elemento del mismo nivel anterior, si lo hay |
  | Documento | `getNextSibling` | `position?: number` | `string \| undefined` | Nombre de etiqueta del siguiente elemento secundario, si lo hay |
  | Documento | `getTagName` | `position?: number` | `string \| null` | Nombre de etiqueta del elemento en `position` (o cursor) |
  | Búsqueda de elementos | `findPositionRange` | `tagName: string` | `{ from: number, to: number } \| undefined` | Intervalo del primer elemento con la etiqueta determinada |
  | Búsqueda de elementos | `findPositionRanges` | `tagName: string` | `Array<{ from: number, to: number }>` | Todos los rangos de elementos que coinciden con `tagName` |
  | Atributos | `getAttributeAtPosition` | `position: number, attrName: string` | `unknown` | Lee un valor de atributo XML del nodo en `position` |
  | Atributos | `getSerializableAttributes` | `xpath: string` | `Record<string, unknown>` | Todos los atributos XML serializables para el nodo en `xpath` |
  | Serialización | `serialize` | _(ninguno)_ | `string` | Serializa todo el documento en XML |
  | Serialización | `serializeToText` | _(ninguno)_ | `string` | Serializa todo el documento en texto sin formato |
  | Serialización | `getRangeXml` | `xpaths: AncestorXpathItem[]` | `string` | Devuelve el XML para un intervalo definido con XPath |
  | Selección | `getSelectedXml` | _(ninguno)_ | `string` | Contenido seleccionado actualmente como cadena XML |
  | Selección | `getSelectedText` | _(ninguno)_ | `string` | Texto seleccionado sin marcas |
  | Selección | `hasSelection` | _(ninguno)_ | `boolean` | `true` si hay una selección de texto/nodo activa |
  | Selección | `isSelectionEditable` | _(ninguno)_ | `boolean` | Si la selección actual se encuentra dentro del contenido editable |
  | Selección | `isPositionEditable` | `position: number` | `boolean` | Si `position` se encuentra dentro del contenido editable |
  | Inserción | `canInsert` | `name: string, position?: number, insertMode?: 'after' \| 'before' \| 'rename'` | `boolean` | Si `name` se puede insertar en `position` (o cursor) |
  | Inserción | `getInsertPosition` | `name: string, position?: number, insertMode?: 'after' \| 'before' \| 'rename'` | `number \| null` | Posición de inserción válida para `name` o `null` si no se pueden insertar |
  | Inserción | `getNodeXml` | `nodeName: string, nodeContent?: string` | `string \| null` | Plantilla XML para un tipo de nodo |
  | Ajustar/cambiar nombre | `getValidWrapNodeElementNames` | _(ninguno)_ | `string[]` | Nombres de elementos que pueden ajustar la selección actual |
  | Ajustar/cambiar nombre | `getValidRenameNodeElementNames` | _(ninguno)_ | `string[]` | Nombres de elementos se puede cambiar el nombre del nodo actual a |
  | Tablas | `getTableInfo` | `position?: number` | `{ rows: number, cols: number, header: number }` | Dimensiones de la tabla actual |
  | Vista de etiquetas | `isTagViewActive` | _(ninguno)_ | `boolean` | Si el procesamiento de la vista de etiquetas está activo |

  **Ejemplo: obtener la posición del cursor y los nombres de antecesores**

  ```js
  const textPos = guides.editor.runUtil("getTextPos");
  const ancestorNames = guides.editor.runUtil(
    "getAncestorsNames",
    typeof textPos === "number" ? textPos : undefined
  );
  ```

  **Ejemplo: buscar todos los elementos `<xref>` y leer sus atributos**

  ```js
  const xrefRanges = guides.editor.runUtil("findPositionRanges", "xref") || [];
  xrefRanges.forEach((range) => {
    const id = guides.editor.runUtil("getAttributeAtPosition", range.from, "id");
    const placeholderText = guides.editor.runUtil(
      "getAttributeAtPosition",
      range.from,
      "placeholdertext"
    );
  });
  ```

  **Ejemplo: buscar el rango de elementos raíz y leer sus atributos**

  ```js
  const rootRange = guides.editor.runUtil("findPositionRange", "concept"); // or "topic"
  if (rootRange) {
    const createdDate = guides.editor.runUtil(
      "getAttributeAtPosition",
      rootRange.from,
      "createdDate"
    );
    const author = guides.editor.runUtil(
      "getAttributeAtPosition",
      rootRange.from,
      "author"
    );
  }
  ```

  **Ejemplo: compruebe la selección y valide el contexto antecesor antes de una operación**

  ```js
  const ancestorsDetails = guides.editor.runUtil('getAncestorsDetails');
  const selectedText = guides.editor.runUtil('getSelectedPlainText');
  const hasSelection = !!guides.editor.runUtil('hasSelection');
  
  const firstAncestor = ancestorsDetails?.currNode || ancestorsDetails?.ancestors?.[0]?.tagName;
  if (firstAncestor === 'ph') {
    tcx.util.showAlert("warning", "Operation is not allowed inside this element type.");
    return;
  }
  ```

  **Ejemplo: obtener ID de elementos de XPath antecesores**

  ```js
  const ancestorItems = guides.editor.runUtil('getAncestorXpaths', true);
  for (const item of ancestorItems) {
    const attrs = guides.editor.runUtil('getSerializableAttributes', item.xpath);
    if (attrs?.id) { /* use element ID */ }
  }
  ```

## API de decoración

La API Decoration proporciona una alternativa de nivel superior a la escritura de complementos ProseMirror completos para personalizaciones visuales comunes. En lugar de administrar `Plugin`, `PluginKey` y `DecorationSet` manualmente, se describe *qué* decorar y *cómo*, y el administrador de decoración central del editor administra internamente el estado de ProseMirror.

Las decoraciones se identifican mediante una cadena `id` para que se puedan actualizar o quitar de forma independiente en cualquier momento.

>[!NOTE]
>
> **Solo editor nuevo** Estas API no son operaciones en el editor heredado (`version === '1.0.0'`).

- `guides.editor.addDecoration(id, selector, options)`: agrega o reemplaza una regla de decoración. Todos los nodos que coincidan con `selector` en el documento actual estarán decorados según `options`. La decoración se vuelve a aplicar automáticamente en cada cambio de documento.

  **Firma:**

  ```ts
  guides.editor.addDecoration(
    id: string,
    selector: string,
    options: DecorationOptions
  ): boolean
  ```

  **`DecorationOptions`campos:**

  | Campo | Tipo | Descripción |
  |---|---|---|
  | `class` | `string` | Nombres de clase CSS añadidos a nodos coincidentes |
  | `computeAttributes` | `(node, context) => Record<string, string>` | Función que devuelve `data-*` dinámico u otros atributos de HTML por nodo |
  | `filter` | `(node) => boolean` | Predicado opcional: sólo se muestran los nodos donde devuelve `true` |

  El objeto `context` pasado a `computeAttributes` incluye:
   - `index` — posición basada en 0 del nodo entre hermanos que coinciden con el selector

  **Ejemplo: agregar una clase CSS a todos los elementos `<section>`**

  ```js
  guides.editor.addDecoration('highlight-sections', 'section', {
    class: 'my-section-highlight'
  });
  ```

  **Ejemplo: agregar un atributo `data-number-label` calculado a cada sección**

  ```js
  guides.editor.addDecoration('section-numbers', 'section', {
    computeAttributes: (node, context) => ({
      'data-number-label': String(context.index + 1)
    })
  });
  ```

  **Ejemplo: decorar solo secciones que tengan `importance="high"` atributo**

  ```js
  guides.editor.addDecoration('important-sections', 'section', {
    class: 'section-important',
    filter: (node) => node.attrs?.xmlAttrs?.importance === 'high'
  });
  ```

  **Ejemplo: combinar clase y atributos calculados**

  ```js
  guides.editor.addDecoration('numbering-mode', 'conbody', {
    class: 'legacy-numbering'
  });
  
  guides.editor.addDecoration('section-numbers', 'section', {
    computeAttributes: (node, context) => ({
      'data-number-label': String(context.index + 1)
    })
  });
  ```

- `guides.editor.removeDecoration(id)`: quita una decoración previamente agregada por su identificador.

  **Firma:**

  ```ts
  guides.editor.removeDecoration(id: string): boolean
  ```

  **Ejemplo:**

  ```js
  guides.editor.removeDecoration('section-numbers');
  ```

- `guides.editor.batchDecorations(changes)`: aplica varios cambios de decoración de agregar o quitar en un solo envío de ProseMirror. Utilícelo al alternar varias decoraciones a la vez para evitar varias representaciones nuevas.

  **Firma:**

  ```ts
  guides.editor.batchDecorations(changes: DecorationBatchChange[]): boolean
  
  type DecorationBatchChange =
    | { action: 'add', id: string, selector: string, options: DecorationOptions }
    | { action: 'remove', id: string }
  ```

  **Ejemplo: cambiar entre dos modos de numeración automáticamente**

  ```js
  guides.editor.batchDecorations([
    { action: 'remove', id: 'legacy-numbering' },
    {
      action: 'add',
      id: 'division-numbering',
      selector: 'conbody',
      options: { class: 'division-numbering' }
    }
  ]);
  ```

  **Ejemplo: borrar una decoración y agregar dos nuevas**

  ```js
  guides.editor.batchDecorations([
    { action: 'remove', id: 'old-highlights' },
    {
      action: 'add',
      id: 'section-labels',
      selector: 'section',
      options: {
        computeAttributes: (node, ctx) => ({ 'data-section-index': String(ctx.index) })
      }
    },
    {
      action: 'add',
      id: 'note-style',
      selector: 'note',
      options: { class: 'styled-note' }
    }
  ]);
  ```

- `guides.editor.clearDecorations()`: quita todas las decoraciones activas administradas por el administrador de decoración.

  **Firma:**

  ```ts
  guides.editor.clearDecorations(): boolean
  ```

  **Ejemplo:**

  ```js
  guides.editor.clearDecorations();
  ```

- `guides.editor.getDecorations()`: devuelve los identificadores de todas las decoraciones activas actualmente.

  **Firma:**

  ```ts
  guides.editor.getDecorations(): string[]
  ```

  **Ejemplo:**

  ```js
  const active = guides.editor.getDecorations();
  console.log('Active decorations:', active);
  // e.g. ['section-numbers', 'numbering-mode', 'note-style']
  ```


### API de decoración frente a `registerPlugin`

| Escenario | Utilizar |
|---|---|
| Aplicar una clase CSS o atributos `data-*` a elementos coincidentes | `addDecoration` |
| Alternar o actualizar el estilo en función del estado de ejecución (metadatos, acción del usuario) | `addDecoration` / `removeDecoration` / `batchDecorations` |
| Lógica compleja del complemento: estado personalizado, enlaces de claves, decoraciones de widgets, controladores de eventos | `registerPlugin` |
| Inserción de CSS en el DOM de sombra | `registerPlugin` con el campo `css` |


## Registro del complemento ProseMirror

- `guides.editor.registerPlugin(factory)`: registra un generador de complementos de ProseMirror para incluirlos en cada nueva instancia de editor. Solo se aceptan las funciones de fábrica, las instancias de complemento directo se rechazan. La fábrica se llama una vez por instancia de editor, lo que garantiza un estado de complemento aislado.

  **Firma:**

  ```ts
  guides.editor.registerPlugin(factory: () => PluginConfig): void
  
  interface PluginConfig {
    plugin: ProseMirrorPlugin | ProseMirrorPlugin[]
    css?: string  // Injected into editor's shadow DOM
  }
  ```

  **Ejemplo: registrar complementos después de que el editor esté listo**

  ```js
  guides.ready(() => {
    guides.editor.registerPlugin(createNumberingPlugin);
    guides.editor.registerPlugin(createXrefPlugin);
  });
  ```

  **Ejemplo: generador en línea con CSS**

  ```js
  guides.editor.registerPlugin(() => ({
    plugin: new guides.editor.prosemirror.state.Plugin({
      key: new guides.editor.prosemirror.state.PluginKey("myPlugin"),
      props: {
        decorations(state) {
          // return DecorationSet...
        }
      }
    }),
    css: `.my-decoration { background: yellow; }`
  }));
  ```

  >[!NOTE]
  >
  > CSS pasado a través de `css` se inserta en el DOM en la sombra del editor. Las hojas de estilo normales a nivel de página no se aplican dentro del editor.

## Bibliotecas ProseMirror

- `guides.editor.prosemirror`: expone los paquetes de ProseMirror directamente para usarlos en el desarrollo de complementos. Esto evita la necesidad de agrupar ProseMirror por separado en el código de extensión.

  | Propiedad | Paquete |
  |---|---|
  | `state` | `prosemirror-state` |
  | `model` | `prosemirror-model` |
  | `view` | `prosemirror-view` |
  | `transform` | `prosemirror-transform` |
  | `commands` | `prosemirror-commands` |
  | `keymap` | `prosemirror-keymap` |
  | `history` | `prosemirror-history` |
  | `tables` | `prosemirror-tables` |
  | `dropcursor` | `prosemirror-dropcursor` |
  | `markdown` | `prosemirror-markdown` |

  **Ejemplo: crear un complemento de decoración de nodo**

  ```js
  const myPluginKey = new guides.editor.prosemirror.state.PluginKey("myPlugin");
  
  const createMyPlugin = () => {
    const { Plugin } = guides.editor.prosemirror.state;
    const { Decoration, DecorationSet } = guides.editor.prosemirror.view;
  
    return {
      plugin: new Plugin({
        key: myPluginKey,
        state: {
          init() { return { enabled: true }; },
          apply(tr, value) {
            const meta = tr.getMeta(myPluginKey);
            return meta ? { ...value, ...meta } : value;
          }
        },
        props: {
          decorations(state) {
            const decorations = [];
            state.doc.descendants((node, pos) => {
              if (node.type.name === "section") {
                decorations.push(
                  Decoration.node(pos, pos + node.nodeSize, { class: "my-section" })
                );
              }
            });
            return DecorationSet.create(state.doc, decorations);
          }
        }
      }),
      css: `.my-section { border-left: 3px solid #ccc; padding-left: 8px; }`
    };
  };
  ```

  **Ejemplo: crear un complemento de decoración de widget (texto para mostrar en línea)**

  ```js
  const xrefPluginKey = new guides.editor.prosemirror.state.PluginKey("xrefDisplay");
  
  const createXrefPlugin = () => {
    const { Plugin } = guides.editor.prosemirror.state;
    const { Decoration, DecorationSet } = guides.editor.prosemirror.view;
  
    return {
      plugin: new Plugin({
        key: xrefPluginKey,
        props: {
          decorations(state) {
            const decorations = [];
            state.doc.descendants((node, pos) => {
              if (node.type.name.includes("xref")) {
                const display = node.attrs?.xmlAttrs?.placeholdertext;
                if (display) {
                  decorations.push(
                    Decoration.widget(pos + 1, () => {
                      const el = document.createElement("span");
                      el.textContent = `[${display}]`;
                      el.setAttribute("contenteditable", "false");
                      return el;
                    }, { key: `xref-${pos}` })
                  );
                }
              }
            });
            return DecorationSet.create(state.doc, decorations);
          }
        }
      }),
      css: `.xref-display-text { color: #0074d9; pointer-events: none; }`
    };
  };
  ```

## Inserción de CSS en el editor

El editor DITA de guías carga sus estilos de contenido en modo de autor desde una clientlib con categoría `apps.guides.dita_editor.content`. Esa clientlib tiene una declaración `embed` que extrae automáticamente cualquier clientlib registrada en la categoría:

```
apps.guides.xml_editor.dita_content_overrides
```

Para insertar CSS personalizado en el área de contenido del editor, cree un nodo clientlib de AEM con esta categoría. No se necesita cableado adicional, Guides lo recoge automáticamente cuando se carga la página del editor.

**Estructura del nodo clientlib de AEM (`/apps/my-extension/clientlibs/editor-content-overrides/.content.xml`)**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:cq="http://www.day.com/jcr/cq/1.0"
          xmlns:jcr="http://www.jcp.org/jcr/1.0"
    jcr:primaryType="cq:ClientLibraryFolder"
    categories="[apps.guides.xml_editor.dita_content_overrides]"/>
```

Coloque el archivo CSS (`css.txt` + su archivo `.css`) dentro de esta carpeta. Se incrusta automáticamente en la hoja de estilos de contenido del editor.

**Ejemplo: reemplazar estilos de título de sección en el modo Autor**

```css
/* /apps/my-extension/clientlibs/editor-content-overrides/css/content.css */

/* Increase section title font size in author mode */
.section > title {
  font-size: 1.4em;
  font-weight: bold;
  color: #333;
}

/* Highlight note blocks */
.note {
  border-left: 4px solid #0074d9;
  padding-left: 12px;
  background: #f0f7ff;
}
```

>[!NOTE]
>
>Este CSS se dirige únicamente a la superficie de creación heredada basada en CKEditor. No tiene efecto dentro del nuevo editor (ProseMirror), que utiliza un DOM en la sombra.


### Nuevo editor: `css` en `registerPlugin`

El nuevo editor se procesa dentro de un **DOM en la sombra**, lo que lo aísla de todos los estilos de nivel de página, incluido AEM `clientlibs`. Para insertar CSS en la superficie de creación del nuevo editor, pase una cadena `css` como parte de `PluginConfig` que devuelve el generador de complementos.

El CSS se inserta como una etiqueta `<style>` directamente dentro de la raíz en la sombra del editor cada vez que se crea una instancia de editor.

**Ejemplo: inyectar estilos junto a un complemento de decoración**

```js
guides.ready(() => {
  guides.editor.registerPlugin(() => ({
    plugin: createMyPlugin(), // your ProseMirror plugin
    css: `
      /* Styles scoped to the New Editor shadow DOM */
      .section > .title-node {
        font-size: 1.4em;
        font-weight: bold;
        color: #333;
      }

      .note-node {
        border-left: 4px solid #0074d9;
        padding-left: 12px;
        background: #f0f7ff;
      }
    `
  }));
});
```

**Ejemplo: complemento solo CSS (sin lógica de decoración)**

```js
guides.ready(() => {
  guides.editor.registerPlugin(() => ({
    plugin: new guides.editor.prosemirror.state.Plugin({}), // no-op plugin
    css: `
      /* Custom author-mode typography */
      [data-xml-element="codeblock"] {
        font-family: monospace;
        background: #f5f5f5;
        padding: 8px;
        border-radius: 4px;
      }
    `
  }));
});
```

>[!NOTE]
>
> Este CSS solo se aplica dentro del DOM en la sombra del nuevo editor. No afecta al resto de la página ni al editor anterior.


## Extensiones de menú contextual (`contextMenuWidget`)

Las extensiones pueden agregar elementos al menú contextual del editor que se abre al hacer clic con el botón derecho/ruta de exploración declarando un campo `contextMenuWidget` en su configuración de extensión. Esto indica al marco de trabajo qué menú del editor se va a orientar.

### ID de widget

| ID del widget | Editor |
|---|---|
| `dita_editor_menu` | Superficie de autor de CKEditor heredado (ruta de exploración + menú contextual de elemento) |
| `markup_editor_menu` | Menú contextual de ruta de exploración y elemento del nuevo editor (ProseMirror) |

Ambos widgets se montan en la página simultáneamente. El marco de trabajo hace coincidir cada extensión con el menú correcto en función de este campo.

> Las extensiones también pueden dirigirse a ambos editores pasando una matriz: `contextMenuWidget: ["dita_editor_menu", "markup_editor_menu"]`

### Editor heredado: `dita_editor_menu`

Utilice esto para las extensiones que deben aparecer en el menú contextual heredado de CKEditor.

```js
const myContextMenuExtension = {
  id: "dita_author_view_menu",
  contextMenuWidget: "dita_editor_menu",
  view: {
    items: [
      {
        displayName: "My Custom Action",
        data: { eventid: "myCustomAction" },
        icon: "textSpaceAfter",
        target: {
          key: "displayName",
          value: "Wrap Element",   // insert after this existing menu item
          viewState: "append",
        },
      },
    ],
  },
  controller: {
    myCustomAction() {
      console.log("Custom action triggered");
    },
  },
};
```

### Nuevo editor: `markup_editor_menu`

Utilícelo para las extensiones que deben aparecer en el menú contextual Nuevo editor (rutas de exploración y clic con el botón derecho en los elementos). El controlador recibe eventos a través de `handleExtensionEvent`, que enruta los controladores locales al controlador `markup_editor_menu` y distribuye los eventos globales a través del controlador de eventos de la aplicación.

```js
const myMarkupContextMenu = {
  id: "dita_author_view_menu",
  contextMenuWidget: "markup_editor_menu",
  view: {
    items: [
      {
        displayName: "Edit Cross Reference",
        data: { eventid: "editCrossReference" },
        icon: "link",
        target: {
          key: "displayName",
          value: "Cut",
          viewState: "prepend",
        },
      },
      {
        displayName: "Remove Cross Reference",
        data: { eventid: "removeCrossReference" },
        icon: "deleteOutline",
        target: {
          key: "displayName",
          value: "Edit Cross Reference",
          viewState: "append",
        },
      },
    ],
  },
  controller: {
    editCrossReference() {
      // Use guides.editor APIs to read context
      const ancestorXpaths = guides.editor.runUtil("getAncestorXpaths", true);
      // open dialog or take action...
    },
    removeCrossReference() {
      guides.editor.runCommand("unwrapNode");
    },
  },
};
```

## Bibliotecas de utilidades

- `guides.util.lodash`:The biblioteca de utilidad lodash, la misma instancia incluida con el editor.

  ```js
  const uniqueIds = guides.util.lodash.uniq(ids);
  ```

- `guides.util.async`: biblioteca de utilidades asíncrona para uso de extensión.

  ```js
  guides.util.async.parallel([task1, task2], callback);
  ```

## Referencia de API completa

| API | Descripción |
|---|---|
| `filePath` | Obtener la ruta de acceso del archivo del documento activo |
| `version` | Obtener la cadena de versión del editor cargada |
| `appState(key)` | Leer un valor del modelo de aplicación |
| `focus()` | Enfocar el editor activo |
| `canInsertXmlElement(tag, insertAfter?)` | Comprobar si un elemento se puede insertar en el cursor |
| `selectCurrentBlockElement()` | Seleccionar el elemento de bloque actual |
| `getValidElementNamesForInsertion(args)` | Enumerar nombres de elemento válidos para la inserción |
| `updateAttributeByXpath(args)` | Actualizar un atributo mediante XPath |
| `runCommand(name, ...args)` | Ejecutar un comando de editor con nombre |
| `canRunCommand(name, ...args)` | Comprobar si un comando se puede ejecutar |
| `runUtil(name, ...args)` | Invocar una utilidad de editor con nombre |
| `addDecoration(id, selector, options)` | Agregar o reemplazar una regla de decoración con nombre en elementos coincidentes |
| `removeDecoration(id)` | Eliminación de una regla de decoración por ID |
| `batchDecorations(changes)` | Aplicar varios cambios de decoración de adición o eliminación en un envío |
| `clearDecorations()` | Eliminar todas las reglas de decoración activas |
| `getDecorations()` | Obtener los ID de todas las decoraciones activas actualmente |
| `registerPlugin(factory)` | Registre una fábrica de plugins ProseMirror (también el mecanismo para la inyección de CSS DOM en la sombra) |
| `prosemirror.state` | `prosemirror-state` paquete |
| `prosemirror.model` | `prosemirror-model` paquete |
| `prosemirror.view` | `prosemirror-view` paquete |
| `prosemirror.transform` | `prosemirror-transform` paquete |
| `prosemirror.commands` | `prosemirror-commands` paquete |
| `prosemirror.keymap` | `prosemirror-keymap` paquete |
| `prosemirror.history` | `prosemirror-history` paquete |
| `prosemirror.tables` | `prosemirror-tables` paquete |
| `prosemirror.dropcursor` | `prosemirror-dropcursor` paquete |
| `prosemirror.collab` | `prosemirror-collab` paquete |
| `prosemirror.markdown` | `prosemirror-markdown` paquete |
