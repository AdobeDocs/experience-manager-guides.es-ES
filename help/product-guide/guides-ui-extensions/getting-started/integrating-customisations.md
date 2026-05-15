---
title: Instalación y configuración
description: Instalación y uso del paquete de extensión de AEM Guides
role: User, Admin
exl-id: 0304c8d0-35a8-4712-a9af-36557e3b247f
TQID: https://experienceleague.adobe.com/ngU5TVcI7yva051ZscfGCfBb6vEbtG4cvjoOgplqmoA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 362
ht-degree: 1%

---

# Instalación y uso del paquete de extensión de AEM Guides

Las extensiones le ofrecen la oportunidad de personalizar su aplicación de AEM Guides para adaptarla mejor a sus necesidades. Este marco de trabajo de extensión es compatible con AEM Guides 4.3 (local) y 2310 (en la nube) en adelante.

## Requisitos

Este paquete requiere [git bash](https://github.com/git-guides/install-git) y npm

## Instalación

La forma más sencilla de arrancar la instalación del marco de AEM Guides es a través de cli

```bash
npx @adobe/create-guides-extension
```

## Adición del código de personalización

1. Agregue archivos de código para cada componente que desee extender en el directorio `src/`. Ya se han agregado algunos archivos de muestra.
2. Ahora en el archivo `index.ts` ubicado en el directorio `src/`:
   - Importe los archivos de `.ts` con las personalizaciones que desee agregar en la compilación.
   - Agregar las importaciones a `window.extension`
   - Registrar `id` del componente personalizado y la importación correspondiente en `tcx extensions`
   - Consulte la muestra `/src/index.ts`

## Creación del código personalizado

- Ejecute `npm run build` en el directorio raíz. Obtendrá 3 archivos en el directorio, `dist/`:
   - `build.css`
   - `guides-extension.js`
   - `guides-extension.umd.cjs`

![Salida de compilación](./../imgs/build_output.png)

## Añadir la personalización a AEM

- Ir a `CRXDE` `crx/de/index.jsp#/`
- En la carpeta `apps`, cree un nuevo nodo de tipo `cq:ClientLibraryFolder`

![Estructura de carpetas](./../imgs/crxde_folder_structure.png)

- En `properties` del nodo, seleccione `Multi` y agregue la siguiente propiedad
Nombre: `categories`
Tipo: `String []`
Valor: `apps.fmdita.review_overrides`, `apps.fmdita.xml_editor.page_overrides`

>[!NOTE]
>
> Para la penúltima interfaz de usuario, los valores serían: `apps.fmdita.penultimate.xml_editor.page_overrides` y `apps.fmdita.review_overrides`


![Propiedades de carpeta](./../imgs/crxde_folder_properties.png)

- Para agregar el archivo js generado, cree un nuevo archivo, por ejemplo, `tcx1.js`, en el nodo creado anteriormente. Agregue el código de `dist/guides-extension.umd.cjs` o `dist/guides-extension.js`. Ahora cree un nuevo archivo `js.txt`, aquí agregamos el nombre de nuestro archivo js, que en este caso sería:

```t
#base=.
tcx1.js
```

- Para agregar el css generado, cree un nuevo archivo, por ejemplo, `tcx1.css`, en el nodo creado anteriormente. Aquí, agregue el código de `dist/build.css`. Ahora cree un nuevo archivo `css.txt`, aquí agregamos el nombre de nuestro archivo css, que en este caso sería:

```t
#base=.
tcx1.css
```

- Haga un `shift + refresh` para cargar la aplicación con las personalizaciones.

## Resolución de problemas

Compruebe que todos los pasos anteriores se hayan realizado correctamente.
Después de agregar el código a tcx.js, asegúrese de realizar una actualización completa (mayús+actualización).
Ahora abra AEM, haga clic con el botón derecho y haga clic en `Inspect`
Vaya a Orígenes y busque su archivo `[node_name].js` (por ejemplo: extensions.js). Haga un Control / Cmd + D para buscar el archivo. Si el archivo `.js` existe con el código JS que pegó de `dist/guides-extension.umd.cjs` o `dist/guides-extension.js`, la instalación se ha completado
