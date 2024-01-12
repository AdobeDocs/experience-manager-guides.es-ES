---
title: Introducción al repositorio de extensiones
description: AEM Estructura del directorio de paquetes de extensiones de Guides
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---


# AEM Estructura del directorio de paquetes de extensiones de Guides

```text
├── src
│   ├── **/*{js,ts}
│   ├── index.ts
├── dist
│   ├── guides-extension.js
│   ├── guides-extension.umd.cjs
│   ├── build.css
├── node_modules
├── package.json
├── package-lock.json 
└── .gitignore
└── buildCSS.mjs // for creating tailwind classes
└── vite.config.js // config for specifying TS and javascript build options
└── taliwind.config.js // config for tailwind we can add custom config for a design system here
├── jsons // jsons for the aem app
│   ├── context_menus // jsons for the context menus
│   ├── review_app // jsons for the review app
│   ├── xmleditor // jsons for xmleditor
```

## /src

```text
├── src
│   ├── **/*{js,ts}
│   ├── index.ts
```

El directorio de origen contendrá los archivos typescript o javascript para la extensión. El archivo index.ts es el punto de entrada para la extensión. Puede importar todos los componentes aquí y exportarlos como un solo objeto. La extensión utilizará este objeto para procesar los componentes.

### /dist

Este es el directorio de compilación final. AEM Contiene el JS y CSS finales, que deben copiarse en la interfaz de usuario de

```test
├── dist
│   ├── gudies-extension.js // you can either choose es module (this one) or .cjs(other one) file
│   ├── gudies-extension.umd.cjs
│   ├── build.css // this is your tailwind css output
```

## /jsons

Este directorio contiene los JSON para las distintas vistas. Puede utilizar estos JSON para identificar los destinatarios y personalizar la vista.

```text
├── jsons // jsons for the aem app
│   ├── context_menus // jsons for the context menus
│   ├── review_app // jsons for the review app
│   ├── xmleditor // jsons for xmleditor
```
