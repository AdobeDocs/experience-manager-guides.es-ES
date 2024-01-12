---
title: Instalación y configuración
description: AEM Instalación y uso del paquete de extensión de las guías de usuario de
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---


# AEM Instalación y uso del paquete de extensión de las guías de usuario de

AEM Las extensiones le dan la oportunidad de personalizar su aplicación de Guías de la para adaptarla mejor a sus necesidades. AEM Este marco de trabajo de extensión es compatible con las guías de la versión 4.3 (local) y 2310 (nube) de las Guías de la.

## Requisitos 

Este paquete requiere [git bash](https://github.com/git-guides/install-git) y npm

## Instalación

AEM La forma más sencilla de arrancar la instalación del marco de trabajo de Guías de usuario es a través de cli

```bash
npx @adobe/create-guides-extension
```

## Adición del código de personalización

1. Agregue archivos de código para cada componente que desee ampliar en la `src/` directorio. Ya se han agregado algunos archivos de muestra.
2. Ahora, en `index.ts` archivo ubicado en el `src/` directorio :
   - Importe el `.ts` archivos con las personalizaciones que desee agregar en la compilación.
   - Añadir las importaciones a `window.extension`
   - Registre el del componente personalizado `id` y la importación correspondiente a `tcx extensions`
   - Consulte la muestra `/src/index.ts`

## Creación del código personalizado

- Ejecutar `npm run build` en el directorio raíz. Obtendrá 3 archivos en el directorio, `dist/`:
   - `build.css`
   - `guides-extension.js`
   - `guides-extension.umd.cjs`

![Generar salida](./../imgs/build_output.png)

## AEM Adición de la personalización a los elementos de la

- Ir a `CRXDE` `crx/de/index.jsp#/`
- En el `apps` carpeta, cree un nuevo nodo del tipo `cq:ClientLibraryFolder`

![Estructura de carpetas](./../imgs/crxde_folder_structure.png)

- En el `properties` del nodo, seleccione `Multi` Agregue la siguiente propiedad Nombre: `categories`
Tipo: `String []`
Valor: `apps.fmdita.review_overrides`, `apps.fmdita.xml_editor.page_overrides`

![Propiedades de carpeta](./../imgs/crxde_folder_properties.png)

- Para agregar los archivos JS generados, cree un nuevo archivo, por ejemplo, `tcx1.js` en el nodo creado anteriormente. Aquí, añada el código de `dist/guides-extension.umd.cjs` o `dist/guides-extension.js`. Ahora cree un nuevo archivo `js.txt`, aquí agregamos el nombre de nuestro archivo js, que en este caso sería:

```t
#base=.
tcx1.js
```

- Para agregar el css generado, cree un nuevo archivo, por ejemplo, `tcx1.css` en el nodo creado anteriormente. Aquí, añada el código de `dist/build.css`. Ahora cree un nuevo archivo `css.txt`, aquí agregamos el nombre de nuestro archivo css, que en este caso sería:

```t
#base=.
tcx1.css
```

- Realice una `shift + refresh` para cargar la aplicación con las personalizaciones.

## Solución de problemas

Compruebe que todos los pasos anteriores se hayan realizado correctamente.
Después de agregar el código a tcx.js, asegúrese de realizar una actualización completa (mayús+actualización).
AEM A continuación, abra la, haga clic con el botón derecho y seleccione `Inspect`
Vaya a Orígenes y busque su `[node_name].js` (para p. ej.: extensions.js). Haga un Control / Cmd + D para buscar el archivo. Si la variable `.js` el archivo existe con el código JS desde el que lo pegó `dist/guides-extension.umd.cjs` o `dist/guides-extension.js`, se ha completado la configuración
