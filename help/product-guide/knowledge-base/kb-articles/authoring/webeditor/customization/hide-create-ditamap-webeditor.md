---
title: Oculte la opción Crear mapa digital en las opciones del menú contextual de la carpeta para usuarios o grupos específicos.
description: Aprenda a personalizar el editor web ocultando la opción "DitaMap" del menú contextual de carpeta para usuarios/grupos específicos
exl-id: 796bfe3a-3950-4ade-9215-c33534791055
TQID: https://experienceleague.adobe.com/fAMBEOKlPA4KHsE81zfI-6EJ6zwaQOgRfx0w-cx-mmw
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 571
ht-degree: 0%

---

# Mostrar/ocultar &quot;Crear DitaMAP&quot; del menú contextual de carpeta en el editor web

En este artículo, aprenderemos a personalizar el Editor web de guías para ocultar o mostrar la opción &quot;Crear DitaMap&quot; en el menú contextual de la carpeta en función de los permisos de usuario/grupo.
En este caso de uso, ocultaremos esta opción para todos los usuarios que no sean autores.

## Requisitos previos

Aprovecharemos el paquete de extensión de AEM Guides que le permite personalizar la interfaz de usuario de su aplicación según sus necesidades.
Consulte esta [documentación](https://github.com/adobe/guides-extension/tree/main) para obtener más información sobre cómo funciona el marco de trabajo de extensión de guías.

Ahora vamos a empezar y aprender a personalizar el menú contextual de la carpeta para ocultar esta opción para todos los usuarios que no sean autores.

Como puede ver en el siguiente fragmento, la opción &quot;create DitaMap&quot; es visible para un usuario autor.

![Mostrar opción para crear DitaMap](../../../assets/authoring/ditamap-show-author.png)

Ahora veamos cómo podemos ocultar esta opción mediante el marco de trabajo de extensión de Guides.

## Pasos de implementación

La implementación se desglosa en las siguientes partes:

- **Cambios en el controlador Folder_options**

  Cada menú contextual tiene asociado un identificador de controlador. Este controlador administra la funcionalidad en el evento para las distintas opciones del menú contextual.

  En este ejemplo, personalizaremos el menú contextual de la carpeta para ocultar la opción &quot;Crear DitaMap&quot; para los no autores. Para ello, realizaremos cambios en el archivo folder_options.ts presente en /src en el repositorio del marco de trabajo de la extensión de guías.

  Se utiliza &quot;viewState&quot; como &quot;REPLACE&quot; para ocultar esta opción en el menú contextual.
Estamos llamando a un nuevo widget en esta folder_options a través de la clave &quot;id&quot;.

```typescript
const folderOptions = {
  id: "folder_options",
  contextMenuWidget: "repository_panel",
  view: {
    items: [
      {
        component: "widget",
        id: "customditamap",
        target: {
          key: "displayName",
          value: "DITA Map",
          viewState: VIEW_STATE.REPLACE,
        },
      },
    ],
  },
};
```

- **Creación de un widget nuevo para controlar la lógica**

  Se necesita una nueva creación de widget (customoptions.ts) para escribir la lógica que oculte esta opción solo para usuarios que no sean autores. Para lograrlo, hemos utilizado la clave &quot;show&quot; que actúa como alternativa en nuestra estructura JSON.

  Puede escribir su propio servlet externo para comprobar los detalles del grupo. De este modo, también puede personalizar las opciones del menú de carpeta para su grupo personalizado.
En este ejemplo, hemos aprovechado la llamada &quot;rolesapi&quot; de OOTB AEM para recuperar los detalles del usuario y establecer la respuesta en &quot;isAuthor&quot; como se muestra en fragmentos anteriores.

```typescript
const folderOptions = {
  id: "customditamap",
  view: {
    component: "button",
    quiet: true,
    icon: "breakdownAdd",
    label: "DITA Map",
    "on-click": "createNewDitaMap",
    show: "@extraProps.isAuthor",
  },
};
```

A través de esto, podemos ocultar el botón con la etiqueta como &quot;Mapa de datos&quot; en función del valor de &quot;mostrar&quot;.

Se ha agregado un controlador para establecer el atributo isAuthor en el modelo. Esto se puede hacer con la siguiente sintaxis en el controlador.

```typescript
this.model.extraProps.set("key", value);
```

Aquí la clave es &quot;isAuthor&quot; y el valor es la respuesta de la llamada a rolesapi.
También se ha definido el evento &quot;createNewDitaMap&quot; para activar la opción &quot;createDitaMap&quot; (para usuarios autores).

```typescript
controller: {
    init: function () {
      this.model.extraProps.set("isAuthor", false);

      rolesApiResponse.then((result) => {
        console.log(result);
        this.model.extraProps.set(
          "isAuthor",
          result["/content/dam"].roles.authors
        );

        console.log("testresult" + result["/content/dam"].roles.authors);
      });
    },
    createNewDitaMap() {
      repositoryController && repositoryController.next("create_new.map");
    },
  },
```

- **Agregando el código personalizado**

  Importe folder_options.ts y customoptions.ts al archivo index.ts en /src.

## Pruebas

- Inicie sesión en AEM con un usuario que no forme parte del grupo de autores. La opción Crear DitaMap estaría oculta en cualquier menú contextual de carpeta, como se muestra a continuación.
Este caso de uso se ha añadido a GIT; consulte los recursos relacionados a continuación.

![Ocultar la opción create DitaMap](../../../assets/authoring/ditamap-hide-non-author.png)

### Recursos relacionados

- **Repositorio base de módulo de extensión** - [GIT](https://github.com/adobe/guides-extension/tree/main)

- **Documentación** - [en Experience League](../../../../../guides-ui-extensions/aem_guides_framework/basic-customisation.md)

- **Casos de uso común documentados** - [en Experience League](../../../../../guides-ui-extensions/aem_guides_framework/jui-framework.md)

- **Repositorio público con ejemplos** - [en GIT](https://github.com/adobe/guides-extension/tree/sc-expert-session). Rama de referencia sc-expert-session

```

```
