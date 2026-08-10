---
title: Migración de los cambios del marco de trabajo de extensión para Editor 2.0
description: Obtenga información acerca de la migración al marco de trabajo de extensión para Editor 2.0
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 75954eab3ac1738705fe2a7280973af39b9214df
workflow-type: tm+mt
source-wordcount: '2006'
ht-degree: 3%

---


# Migración del marco de extensión al Editor 2.0 (nuevo editor)

Esta guía ayuda a los autores de extensiones a comprender qué implica mover sus personalizaciones del **Editor antiguo** al **Editor nuevo** en AEM Guides, de modo que puedan planificar su transición sin problemas y con una interrupción mínima.

>[!IMPORTANT]
> 
> Si tiene una extensión de AEM Guides existente (antiguo editor), incluidos elementos de menú contextual personalizados, botones de la barra de herramientas, cuadros de diálogo, lógica de atributos o metadatos, o estilo de contenido, esta guía le ayuda a seguir trabajando con el nuevo editor.

## Información general

- **Su registro no cambia**: Siga usando `window.extension` / `tcx.extension.register`.
- **El lienzo del editor es una superficie nueva.** Los elementos de menú contextual deben declarar el nuevo ID del widget
  `markup_editor_menu`; el comportamiento en el editor debe dejar de tocar el DOM.
- **Dejar de leer y escribir en el DOM**: reemplace el acceso DOM de `tcx.curEditor.*` por el
  API `guides.editor`: [leer con `runUtil(...)`](#migrate-reads-dom-runutil), [escribir con `runCommand(...)`](#migrate-writes-dom-mutation-runcommand), [estilo con decoraciones](#migrate-rendering-only-logic-dom-paint-decorations) y [ejecutar acciones globales (guardar) mediante eventos de aplicación](#migrate-global-actions-savefocus-app-events) .
- **Los menús del shell de la aplicación (repositorio, visor de mapas, archivo/carpeta) no han cambiado**: se siguen ejecutando en
el marco heredado.
- **Ambos editores coexisten**: Dirija ambos con matrices. Al cargar los complementos de **Register** de forma incondicional; bloquee solo las acciones de *runtime* por `guides.editor.version` (que permanece `1.0.0` hasta que se abra un archivo, vea [Detectar el editor y el bootstrap de forma segura](#detect-the-Editor-and-bootstrap-safely)).


## ¿Por qué el cambio?

| Criterios | CKEditor heredado | Nuevo editor de marcado |
|---|---|---|
| Source de la verdad | DOM | Documento de ProseMirror |
| Selección | `getSelection()` en un documento raíz | Selección de ProseMirror (posiciones/intervalos) |
| Para cambiar el contenido | Mutar atributos o clases de DOM | Enviar un comando (transacción) |
| Procesamiento | DOM es permanente | DOM es un procesamiento efímero en un DOM en la sombra, reconstruido en cualquier momento |
| Estilo | CSS de página o clientlib | CSS insertado en el DOM de sombra mediante el complemento de registro. Consulte [Hello world: un complemento destacado solo para CSS](#hello-world-a-css-only-highlight-plugin) para usar clases existentes y agregar CSS y [Migrar lógica de solo procesamiento](#migrate-rendering-only-logic-dom-paint-decorations) para agregar una nueva clase y agregar estilo. |

No se retiene ninguna extensión que mute el DOM ni ningún cambio del DOM, por lo que se borra en el siguiente procesamiento. Básicamente, la migración es *pasar de DOM-first a model-first*.

## Detecte el editor y el bootstrap de forma segura

El objeto `guides` global es el punto de entrada para todas las integraciones nuevas:

```js
guides.editor    // editor interaction APIs
guides.util      // bundled utility libs (lodash, async)
guides.ready(cb) // fires once at app load (view system ready) — before any file is open
```

`guides.editor.version` informa de **editor abierto actualmente**, por lo que solo tiene sentido una vez al
el archivo está abierto:

| `guides.editor.version` | Significado |
|---|---|
| `2.0.0` | Hay abierto un archivo MarkupEditor (ProseMirror) |
| `1.0.0` | Hay un archivo CKEditor heredado abierto o no hay ningún archivo abierto todavía |

>[!IMPORTANT]
>
> Cuando se produce el evento `guides.ready`, no se ha abierto ningún archivo, por lo que `version` se registrará como `1.0.0` independientemente de si MarkupEditor está habilitado o no. No use `version` para determinar si los complementos obtienen *registro* (vea [Registro de complementos y Puerta de tiempo de ejecución](#plugin-registration-and-runtime-gating)). Utilícelo solamente para bifurcar el comportamiento *runtime* y evaluarlo en el punto de ejecución (por ejemplo, dentro de un controlador de menú), donde se garantiza que un archivo está abierto.

### Registro de complementos y acceso en tiempo de ejecución

- **Registro** (`registerPlugin`, configuración única): ejecútelo **sin condiciones** en `guides.ready`. Es una operación inofensiva en el editor heredado: el editor heredado nunca lee el registro de complementos y el generador se ejecuta solo cuando se construye realmente un MarkupEditor. No produce **not**.

- **Llamadas en tiempo de ejecución** (`runCommand`, `runUtil`, `addDecoration`, ...): la puerta por versión existe y no es igual a &quot;1.0.0&quot; en el momento de la llamada. No activan el editor heredado (devuelven `false`/`undefined` de forma segura), pero la activación evita las advertencias de no operación y le permite mantener una reserva heredada.

```js
guides.ready(() => {
  // Always register — inert on legacy, applied only when a MarkupEditor opens.
  guides.editor.registerPlugin(createMyPlugin);
});

function onMenuClick() {
  if (guides.editor.version && guides.editor.version !== "1.0.0") {
    guides.editor.runCommand('surroundWithElement', 'sup'); // MarkupEditor path
  } else {
    // legacy path (or no-op)
  }
}
```

Pase una **fábrica** `() => ({ plugin, css })` a `registerPlugin`, nunca una instancia de complemento construida. Una no función es la única entrada que rechaza (activa ambos editores). No almacene en caché la instancia del editor; llame a `guides.editor.*` de nuevo cada vez.

### Hello world: un complemento destacado solo para CSS

La extensión útil más pequeña incluye **solo CSS** un complemento ProseMirror sin operación más estilos. Esta
resalta cada elemento `<note>` con un fondo amarillo dentro del editor:

```js
guides.ready(() => {
  guides.editor.registerPlugin(() => ({
    plugin: new guides.editor.prosemirror.state.Plugin({}), // no behavior — CSS only
    css: `[data-xml-element="note"] { background: #fff3cd; outline: 1px solid #ffe08a; }`
  }));
});
```

- Cada elemento se procesa como `data-xml-element="<tag>"`, por lo que puede segmentar cualquier elemento DITA de esa manera
(`note`, `codeblock`, `section`, `table`, ...).
- CSS **must** ship vía registerPlugin: el editor se encuentra en un DOM en la sombra, por lo que el CSS page/clientlib no puede
Alcanzalo.
- Abra un tema DITA que contenga `<note>` para verlo aplicado. El registro es incondicional (§2.1),
por lo tanto, esto es seguro a pesar de que `version` sigue siendo `1.0.0` a las `guides.ready`.


## Inventario de la extensión (lista de comprobación general)

```bash
# DOM-first reads that will break
grep -rnE "rootDocument|rootElement|getSelection\(|selectedHtml|selectedText|\.xmlDoc|\.ancestors\b" src

# DOM/legacy writes that will break
grep -rnE "updateAttributes\(|setAttribute\(|classList\.|\.saveFile\(|resetDirty\(|validateRangeForInsertion\(" src

# The editor handle itself
grep -rn "tcx.curEditor" src

# Context-menu targeting + page CSS
grep -rnE "contextMenuWidget|dita_editor_menu|author_outline_element" src
grep -rn "dita_content_overrides" .
```

Cada visita es un elemento de migración. Clasificar cada uno como: *superficie de menú contextual*, *estado leído*, *contenido
write*, *acción global*, *solo procesamiento* o *CSS*.


## Común para ambos editores

Los siguientes comportamientos y estructuras se aplican de forma idéntica a ambos editores:

- **Registro:** `window.extension[id] = config` y/o `tcx.extension.register(id, config)` el
el evento `tcx-loaded`.
- **Forma de objeto de configuración:** `{ id, contextMenuWidget, view: { items }, controller }`.
- **Menús contextuales del shell de la aplicación** conservan sus identificadores de widget existentes y el comportamiento heredado:

  | Superficie | ID del widget (sin modificar) |
  |---|---|
  | Panel Repositorio (archivo/carpeta) | `repository_panel` / `file_options` / `folder_options` |
  | Visualizador de mapas | `ditamap_viewer` / `map_view_options` |
  | Paneles previstos/de línea base | `baseline_panel_menu` / `preset_item_menu` |

  Los elementos dirigidos a estas superficies no necesitan **ningún cambio** para el nuevo editor, no los mueva a
  `markup_editor_menu`.

## Referencia de reemplazo de API

| Heredado (`tcx.curEditor…` / DOM) | Nuevo editor de marcado |
|---|---|
| `tcx.curEditor.filePath` | `guides.editor.filePath` |
| `getSelection()` / `selectedHtml` / `selectedText` | `runUtil('getSelectedXml' / 'getSelectedPlainText' / 'hasSelection')` |
| `rootDocument.querySelector(tag)` | `runUtil('findPositionRange' / 'findPositionRanges', tag)` |
| element `.getAttribute` / `xmlDoc.attributes` | `runUtil('getAttributeAtPosition', pos, name)` / `getSerializableAttributes(xpath)` |
| id. raíz (`querySelector('[concept]').id`) | `runUtil('getAttributeAtPosition', 0, 'id')` |
| `editor.ancestors` | `runUtil('getAncestorsDetails' / 'getAncestorXpaths')` |
| `editor.updateAttributes(attrs, root)` | `runCommand('setNodeXmlAttributes', 0, attrs)` |
| establecer attr en el elemento | `runCommand('setNodeXmlAttribute', pos, name, value)` |
| ajustar/insertar/desajustar selección | `runCommand('surroundWithElement' / 'insertXml' / 'unwrapNode', …)` |
| `canInsertXmlElement` / `validateRangeForInsertion` | `canRunCommand(name, …)` / `canInsertXmlElement(tag)` |
| `editor.focus()` | `guides.editor.focus()` |
| `tcx.curEditor.saveFile()` | `tcx.eventHandler.next(KEYS.AUTHOR_SAVE_KEY)` |
| `setAttribute` / `classList` para el estilo | `addDecoration` / `batchDecorations` / `registerPlugin` |
| CSS page/clientlib para contenido de editor | `registerPlugin({ css })` (DOM de sombra) |
| `contextMenuWidget: 'dita_editor_menu'` | `['dita_editor_menu', 'markup_editor_menu']` |


## Migrar elementos de menú contextual (lienzo del editor)

Esto solo se aplica a los menús dirigidos al **editor** (`dita_editor_menu`,
`author_outline_element`), es decir, el menú contextual/de ruta de exploración dentro de la superficie de edición.

### Cómo se enruta en el nuevo editor

```
window.extension[id]  ─►  filtered by contextMenuWidget == 'markup_editor_menu'
                      ─►  view.items rendered in the canvas menu
   (click) ───────────►  fires an extension event:
                          • eventid is a known global key  → run as a built-in editor command
                          • otherwise                       → your controller[eventid]() runs
```

### Añadir el nuevo ID del widget (la matriz mantiene el funcionamiento del heredado)

```js
// BEFORE
contextMenuWidget: 'dita_editor_menu',
// AFTER
contextMenuWidget: ['dita_editor_menu', 'markup_editor_menu'],
```

### Mantener la forma esperada

- Los elementos procesables residen en `view.items` con `data.eventid`.
- Cada nombre de método `controller` **coincide** con su `eventid` exactamente.

```js
view: {
  items: [{
    displayName: 'Edit Cross Reference',
    icon: 'link',
    data: { eventid: 'editCrossReference' },
    target: { key: 'displayName', value: 'Cut', viewState: 'prepend' }
  }]
},
controller: {
  editCrossReference() { /* runs on click */ }
}
```

### Volver a anclar `target`

El nuevo menú resuelve `target` con los elementos de menú propios del MarkupEditor.

- `target.key`: `displayName | id | icon | eventid`
- `target.viewState`: `append | prepend | replace`
- Anclar a un elemento nativo estable como **`Cut`**.
- Si el anclaje no se resuelve, el elemento seguirá apareciendo pero aterrizará en la posición predeterminada
(no es un error, corrija el anclaje).

### Seleccione la ruta por artículo

```js
data: { eventid: 'AUTHOR_CUT' }          // built-in command → routed natively, no controller needed
data: { eventid: 'editCrossReference' }  // custom → runs controller.editCrossReference()
```

Agregue `readOnly: true` a un elemento que debe permanecer habilitado en el contenido de solo lectura.

### Reescribir el cuerpo del controlador

Los controladores suelen leer la selección y mutar un nodo, y migran los del DOM.

## Migrar lecturas (DOM: `runUtil`)

```js
// BEFORE — DOM selection / queries
const { editor } = tcx.curEditor;
const html = editor.selectedHtml;
const topicId = editor.rootDocument.querySelector('[data-tcx-tag="concept"]').id;

// AFTER — read from the document model
const selectedXml = guides.editor.runUtil('getSelectedXml');
const hasSel      = !!guides.editor.runUtil('hasSelection'); // check if selection is empty
const topicId     = guides.editor.runUtil('getAttributeAtPosition', 0, 'id'); // root = position 0
```

Buscar un nodo por etiqueta, coincidencia por id, leer un atributo XML:

```js
let value = '';
for (const range of (guides.editor.runUtil('findPositionRanges', 'xref') || [])) {
  const id = guides.editor.runUtil('getAttributeAtPosition', range.from, 'id');
  if (String(id) !== String(targetId)) continue;
  value = guides.editor.runUtil('getAttributeAtPosition', range.from, 'placeholdertext') || '';
  break;
}
```

**Utilidades de lectura:** `getTextPos`, `getNodePosition`, `getSelectedXml`, `getSelectedPlainText`,
`hasSelection`, `getAncestorsNames`, `getAncestorsDetails`, `getAncestorXpaths`,
`findPositionRange`, `findPositionRanges`, `getAttributeAtPosition`, `getSerializableAttributes`. Consulte [Apéndice](#appendix-a-more-exposed-utils-examples).


## Migrar escrituras (mutación DOM: `runCommand`)

```js
// BEFORE
const root = editor.rootElement.findOne('[data-tcx-tag="concept"]');
editor.updateAttributes({ docOwner: 'Jane' }, root);

// AFTER — update the model; persists across rerenders
guides.editor.runCommand('setNodeXmlAttributes', 0, { docOwner: 'Jane' });
```

```js
// Set one attribute at a found position
guides.editor.runCommand('setNodeXmlAttribute', pos, 'placeholdertext', text);

// Wrap / insert / unwrap
guides.editor.runCommand('surroundWithElement', 'sup');
guides.editor.runCommand('insertXml', '<sup></sup>', undefined, { setCursorInContent: true });
guides.editor.runCommand('unwrapNode');
```

**Requisitos previos**

```js
guides.editor.focus();
if (!guides.editor.canInsertXmlElement('xref')) {
  return tcx.util.showAlert('warning', 'xref is not allowed here'); 
}
if (guides.editor.canRunCommand('surroundWithElement', 'sup')) {
  guides.editor.runCommand('surroundWithElement', 'sup');
}
```

**Comandos:** `setNodeXmlAttributes`, `setNodeXmlAttribute`, `surroundWithElement`, `insertXml`,
`unwrapNode`. Consulte [Apéndice](#appendix-b-more-exposed-commands-examples).

## Migrar acciones globales (guardar/enfocar: eventos de aplicación)

```js
// BEFORE
tcx.curEditor?.saveFile?.();
// AFTER
tcx.eventHandler.next(tcx.eventHandler.KEYS.AUTHOR_SAVE_KEY);
```

`resetDirty(...)` y `tcx.curEditor.html` no tienen un MarkupEditor equivalente, así que suéltelos; guardando
a través del evento gestiona el estado sucio de forma centralizada. Usar `guides.editor.focus()` para el enfoque.


## Migrar lógica de solo procesamiento (DOM paint: decorations)

Todo lo que agregue clases CSS, atributos `data-*` o &quot;texto para mostrar&quot; al mutar el DOM debe
se convierte en una **decoración** o desaparece al procesarla. A continuación se muestran casos declarativos simples:

```js
guides.editor.addDecoration('important-sections', 'section', {
  class: 'section-important',
  computeAttributes: (node, ctx) => ({ 'data-number-label': String(ctx.index + 1) }),
  filter: (node) => node.attrs?.xmlAttrs?.importance === 'high'
});

guides.editor.batchDecorations([
  { action: 'remove', id: 'legacy-numbering' },
  { action: 'add', id: 'division-numbering', selector: 'conbody', options: { class: 'division-numbering' } }
]);

guides.editor.removeDecoration('important-sections');
guides.editor.clearDecorations();
guides.editor.getDecorations();
```

Casos complejos (estado personalizado, estado interrumpido mediante metadatos de transacción, texto de widget): Registrar una
Complemento ProseMirror una vez, con las bibliotecas expuestas:

```js
const createXrefPlugin = () => {
  const { Plugin, PluginKey } = guides.editor.prosemirror.state;
  const { Decoration, DecorationSet } = guides.editor.prosemirror.view;
  return {
    plugin: new Plugin({ key: new PluginKey('xrefDisplay'), props: { decorations(state) { /* … */ } } }),
    css: `.xref-broken { text-decoration: underline wavy red; }`
  };
};

guides.ready(() => guides.editor.registerPlugin(createXrefPlugin));
```

Registre complementos al cargar la aplicación (una vez), no dentro de cuadros de diálogo ni de forma repetida, el registro no se desduplica. `registerPlugin` solo acepta una **función de fábrica**, no una instancia de complemento.
`guides.editor.prosemirror` expone: `state`, `model`, `view`, `transform`, `commands`, `keymap`,
`history`, `tables`, `dropcursor`, `collab`, `markdown`.


## Migrar CSS (página clientlib → sombra DOM)

El MarkupEditor se procesa dentro de un **DOM en la sombra**; el CSS clientlib de AEM y de nivel de página no lo alcanzan.

```js
guides.editor.registerPlugin(() => ({
  plugin: new guides.editor.prosemirror.state.Plugin({}),   // no-op, CSS only
  css: `[data-xml-element="codeblock"] { font-family: monospace; background: #f5f5f5; }`
}));
```

La categoría clientlib de contenido heredado (`apps.guides.xml_editor.dita_content_overrides`) sigue siendo
diseña el editor heredado únicamente, manténgalo si admite ambos, pero sepa que es inerte en MarkupEditor.

## Acceso al editorView activo (complemento `view` prop): rayado de escape DOM

Las decoraciones y los comandos son el enfoque preferido. Sin embargo, algunos efectos no se pueden implementar como decoraciones. En esos casos, use la propiedad del complemento `view` para obtener acceso al `EditorView` activo y operar en `editorView.dom`. Esta es la única manera compatible de interactuar directamente con el DOM de editor procesado.

```js
const createMyPlugin = () => {
  const { Plugin } = guides.editor.prosemirror.state;
  return {
    plugin: new Plugin({
      view(editorView) {
        const root = editorView.dom;          // the shadow-DOM editor node
        const apply = () => { /* re-color / rewrite target nodes in `root` */ };
        apply();
        return {
          update(view, prevState): apply,                       // re-apply after every rerender
          destroy() { /* remove any listeners/observers */ },
        };
      },
    }),
    css: `/* ... */`,
  };
};

guides.ready(() => guides.editor.registerPlugin(createMyPlugin));
```

**Protecciones**:

- Excluye la trama, utiliza decoraciones para clases, etiquetas y estilo.
- `editorView.dom` es el único identificador compatible;
- Volver a aplicar desde `update()` para que el cambio sobreviva a los procesamientos; limpiar en `destroy()`.

## Ciclo de registro de complemento

`registerPlugin` en `guides.ready` solo registra la fábrica una vez. La propia fábrica vuelve a funcionar
cada vez que se abre un archivo: cada archivo MarkupEditor abierto lo invoca de nuevo para generar el archivo
instancia del complemento.

## Problemas comunes

- Donde el código DOM se dirige a nodos y `Range`s, MarkupEditor se dirige a **posiciones**, enteros simples que se indizan en el documento (`0` = inicio del documento, es decir, la raíz). Un(a) `range` es `{ from, to }`, dos posiciones que limitan un intervalo, no un(a) DOM `Range`. Las posiciones cambian a medida que cambia el documento, por lo que no se debe almacenar en caché una en una edición.
- **El elemento no aparece en el menú Nuevo editor**: falta `contextMenuWidget`
  `markup_editor_menu` o la configuración se registró *después de* de que se abriera el editor (la configuración es de lectura)
  una vez en el registro de construcción del editor (al cargar la aplicación).
- **El elemento aparece en el lugar incorrecto**: el anclaje de `target` no se resuelve; el anclaje a un elemento que
existe en el nuevo menú (p. ej. `Cut`).
- **Cambiar &quot;funciona&quot; y luego desaparece**: Ha mutado el DOM. Utilice un comando (escritura) o una decoración
(estilo) en su lugar.
- **CSS no tiene efecto**: es de nivel de página; el editor se encuentra en un DOM en la sombra. Usar `registerPlugin({ css })`.
- **Lanzamiento de guardias inseguros**: los patrones como `if (!tcx.curEditor && !tcx.curEditor.editor)` evalúan
  `.editor` en un objeto falso. Proteja las capacidades de `guides.editor` en su lugar:
  `if (!guides?.editor) return;`.
- **Intentando migrar menús del shell de la aplicación**: Los menús de repositorio, mapa o archivo no son el lienzo del editor;
déjelos en sus widgets id heredados.

## Lista de comprobación de verificación

- Los elementos de menú contextual aparecen en **ambos** menús del Editor de revisiones y del Editor de revisiones.
- Los elementos aterrizan en la posición esperada.
- La opción personalizada `eventid` ejecuta `controller[eventid]`; las claves globales activan el comando integrado.
- Las lecturas de estado devuelven valores correctos después de escribir/procesar (modelo, no DOM antiguo).
- Las escrituras de contenido *persisten después de guardar y volver a abrir*.
- Las decoraciones sobreviven a un renderizado.
- CSS de DOM en la sombra se aplica visiblemente dentro del editor.
- Guarde los incendios a través de `AUTHOR_SAVE_KEY` y borre el estado sucio.
- `readOnly` elementos se comportan correctamente en el contenido bloqueado.
- Vista previa o en paralelo; el trabajo DOM intencional de solo lectura se deja tal cual.
- `grep -rn "tcx.curEditor" src` está limpio (o solo el resto intencional documentado).
- Complementos registrados exactamente una vez, dentro de `guides.ready`.


## Secuencia de despliegue sugerida

1. **Bootstrap**: ajuste la configuración en `guides.ready`; registre los complementos de forma incondicional y agregue `version` que se desplacen alrededor de *tiempo de ejecución* acciones solamente (para obtener detalles, vea [Registro de complementos y Puerta de ejecución](#plugin-registration-and-runtime-gating)).
2. **Superficie de menú contextual**: Agregar `markup_editor_menu`, corregir `target` anclajes. Ahora aparecen los elementos.
3. **Lecturas**: Migre lecturas de selección/atributo a `runUtil`.
4. **Escrituras**: Migrar mutaciones a `runCommand`; guarda en eventos de aplicación.
5. **Procesamiento**: mover el estilo DOM a las decoraciones / `registerPlugin`; mover CSS a DOM en la sombra.
6. **Endurecer**: corrija los protecciones no seguras, quite el identificador del editor y verifique en ambos editores.

Migre una superficie a la vez y mantenga las rutas heredadas en funcionamiento (matrices + acceso a versiones) de modo que
la versión de extensión única se ejecuta en ambos editores durante toda la transición.

## Apéndice A: utilidades más expuestas (ejemplos)

Busque las siguientes utilidades para usar hasta `runUtil`.

| Util | Parámetros → Devuelve | Qué hace |
|---|---|---|
| `getTextPos` | `(): { start, end }` | Límites del nodo de texto seleccionado actual |
| `getValidElementNames` | `(ancestorLevel?): ElementName[]` | Nombres de elementos que legalmente podrían insertarse o ajustarse en la selección actual. |
| `getValidElementNamesBefore` | `(): ElementName[]` | Nombres de elementos válidos inmediatamente antes de la selección actual. |
| `getSelectedText` | `(): string` | Texto seleccionado sin procesar. |
| `getSerializableAttributes` | `(): { [key]: string }` | Asignación de atributos XML para el nodo actual, escrito por el nombre del atributo. |
| `getTagName` | `(): string \| null` | Nombre de etiqueta del nodo actual. |
| `hasSelection` | `(): boolean` | Indica si hay algún contenido seleccionado actualmente. |
| `isSelectionEditable` | `(): boolean` | Indica si la selección actual se puede editar. |
| `getAncestorPos` | `(name): number \| undefined` | Posición del antecesor más cercano con el nombre de elemento dado, de la selección actual. |
| `getValidWrapNodeElementNames` | `(): ElementName[]` | Nombres de elementos válidos para `wrapNode` en la selección actual. |
| `getValidRenameNodeElementNames` | `(): ElementName[]` | El nombre del elemento del nodo actual no se puede cambiar legalmente a. |
| `getValidSurroundElementNames` | `(): ElementName[]` | Nombres de elementos válidos para `surroundWithElement` en la selección actual. |
| `serialize` | `(doc?): string` | Serializa un documento ProseMirror (o todo el documento) en XML. |
| `getSelectedXml` | `(range?): string` | XML para la selección actual o un intervalo `{ from, to }` explícito. |
| `getRangeXml` | `(xpaths): string` | XML para uno o más rangos xpath-object (consulte la advertencia xpath de §8: se trata del formulario de objetos, no del formulario de cadenas). |
| `mapToXpath` | `(position, doc?): XPathPosition` | Convierte una posición en el objeto-formulario xpath. |
| `inverseMap` | `(xpath \| position, doc?): number` | Convierte un objeto-formulario xpath (o posición) de nuevo a una posición. |
| `getAncestorsDetails` | `(): { ancestors, previousSibling, nextSibling, currNode } \| undefined` | Cadena antecesora más hermanos inmediatos para el nodo actual. |
| `getAncestorsNames` | `(): ElementName[]` | Cadena antecesora solo como nombres de elemento, para el nodo actual. |
| `getPreviousSibling` | `(): ElementName \| undefined` | Nombre del elemento del mismo nivel anterior. |
| `getNextSibling` | `(): ElementName \| undefined` | Nombre del siguiente elemento relacionado. |
| `getAncestorXpaths` | `(includeNodeAtPosition?): { tag, xpath }[]` | Cadena antecesora como pares `{tag, xpath}`: xpath con formato de objeto, no el formulario de cadena `updateAttributeByXpath` (§8). |
| `getSelectedPlainText` | `(range?): string` | Texto sin formato de la selección actual o un intervalo explícito. |
| `getDecorations` | `(): string[]` | ID de todas las decoraciones aplicadas actualmente. |
| `getResolvedDitaDocumentTitle` | `(props?): string` | Se ha resuelto el título de visualización del documento DITA. `props`: `doc` para destinar un documento específico, `allowedPrefixElements` para permitir elementos de prefijo de título. |

## Apéndice B: Comandos más expuestos (ejemplos)

Los comandos siguientes son ejemplos adicionales de lo que se expone mediante `guides.editor.runCommand(name, ...args)`.
Proteja primero cualquier comando con `guides.editor.canRunCommand(name, ...args)` si es posible que no se aplique en el contexto actual.

| Comando | Parámetros | Qué hace |
|---|---|---|
| `focusEditor` | `()` | Enfoca el editor. |
| `unwrapNode` | `()` | Quita el elemento de ajuste de la selección actual, conservando sus elementos secundarios. |
| `surroundWithElement` | `(elementName, attrs?, groupInline?)` | Ajusta la selección actual en un nuevo elemento dentro de la línea/bloque. `attrs`: asignación de atributo XML para establecer en el nuevo elemento envolvente. |
| `insertXml` | `(xml)` | Inserta un fragmento XML en el cursor. |
| `replaceSelectionWithXml` | `(xml)` | Reemplaza la selección actual por XML. |
| `insertText` | `(text)` | Inserta texto sin formato en el cursor. |
| `selectNodesFromXpaths` | `(xpaths)` | Selecciona uno o más nodos dados xpath de forma de objeto. |
| `delete` | `()` | Elimina la selección actual. |
| `undo` / `redo` | `()` | Deshacer y rehacer estándar. |
| `removeDecoration` | `(id)` | Elimina una sola decoración por ID. |
| `clearDecorations` | `()` | Quita todas las decoraciones del archivo abierto actual. |
| `setFileReadOnly` | `(readOnly: boolean)` | Alterna el modo de solo lectura para el archivo. |
| `generateUniqueId` | `()` | Genera y asigna un atributo de ID único al nodo actual. |