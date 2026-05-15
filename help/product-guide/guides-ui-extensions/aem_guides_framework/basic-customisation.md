---
title: Personalizar la aplicación
description: Personalizar la aplicación
role: User, Admin
exl-id: 3e454c48-2168-41a5-bbab-05c8a5b5aeb1
TQID: https://experienceleague.adobe.com/7DiEcUTAvp4rT3Fy9pIv4-zaHKwswjokjlaBgx8Pbyo
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 485
ht-degree: 0%

---

# Personalizar la aplicación

## Funcionalidad expuesta en el marco de extensión

Hemos expuesto un conjunto de funciones y captadores bajo un `proxy` que puede usarse para acceder a datos y eventos de configuración y déclencheur. A continuación se muestra una lista y cómo acceder a ellas.

```typescript
interface EventData {
  key?: string,
  keys?: string[]
  view?: any,
  next?: any,
  error?: any,
  completed?: any,
  id?: any
}

* getValue(key)
* setValue(key, value)
* subject // getter
* subscribe(opts: EventData)
* subscribeAppEvent(opts: EventData)
* subscribeAppModel(key, next)
* subscribeParentEvent(opts: EventData)
* parentEventHandlerNext(eventName: string, opts: any)
* appModelNext(eventName:string, opts) 
* appEventHandlerNext(eventName:string, opts)
* next(eventName:string, opts, eventHandler?)
* viewConfig //getter
* args //getter
```

Nuestra aplicación sigue una estructura MVC (Modelo, Vista, Controlador)

## Modelo

El modelo define los distintos atributos y almacena sus valores. Se puede acceder a los valores de los distintos atributos almacenados en el modelo desde el controlador mediante la sintaxis

```typescript
this.getValue('attributeName')
```

Para la personalización en la aplicación, todos los atributos recién creados se añadirán en un mapa del modelo.
Para establecer un nuevo atributo en el modelo, se utilizará la siguiente sintaxis en el controlador:

```typescript
// If a key is not already in model then it will be added to extraProps
this.setValue('key', value)
```

Para acceder a un atributo añadido al modelo utilizaremos la siguiente sintaxis:

```typescript
const value = this.getValue("key")
```

## Ver

La vista define la interfaz de usuario de la aplicación. Utilizamos archivos JSON para definir la vista de nuestros archivos. Aquí, definimos los componentes, el css (como se indica en la clase extra de componentes) y procesamos los valores almacenados en el modelo.
En nuestra aplicación, cada vista se define mediante un JSON. Se hace referencia a los JSON mediante sus identificadores únicos denominados `id`.

## Controlador

El controlador se utiliza para controlar eventos y procesar los datos. El controlador se utiliza para recuperar y enviar datos desde el servidor, es la interfaz entre lo que se muestra en la interfaz de usuario y lo que se almacena en el servidor.

- Para establecer los valores en la inicialización, se utiliza la función `init`.
- Para agregar un método al controlador utilizamos la siguiente sintaxis:

```typescript
methodName: function(args){
    // functionality
}
```

El `methodName` sirve como `key` para hacer referencia al método en el JSON (vista) o en otras funciones

- Para llamar a un método en el controlador utilizamos la sintaxis

```typescript
this.next('methodName', args)
```

## Ejemplo

Veamos un ejemplo sencillo para mostrar cómo estos 3 componentes interactúan entre sí.
Agregaremos un botón que cambia su valor de etiqueta con un clic

### Ver ejemplo

A continuación, definimos el JSON de un botón que muestra un texto dinámico almacenado en el modelo bajo el nombre de variable `buttonLabel`.
En este ejemplo, al hacer clic en el botón se cambia la etiqueta.

```JSON
{
    "component": "button",
    "label": "@extraProps.buttonLabel",
    "variant": "cta",
    "on-click": "switchButtonLabel",
}
```

### Ejemplo de modelo

en este caso, `extraProps.buttonLabel` contiene la etiqueta del botón

### Ejemplo del controlador

```typescript
  controller: {
    init: function () {
      this.setValue("buttonLabel", "Submit")
    },

    switchButtonLabel(){
        const buttonLabel = this.getValue("buttonLabel") === "Submit"? "Cancel" : "Submit"
        this.setValue("buttonLabel", buttonLabel)
    }
  }
```

A continuación, GIF muestra el código anterior en acción
![personalización_básica](imgs/basic_customisation.gif "Botón de personalización básica")


### Ver ejemplo de configuración

En este caso, accedemos al evento de modo de búsqueda mediante `viewConfig` y almacenamos en déclencheur un evento para actualizarlo

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        console.log('Logging view config ', this.viewConfig)
        this.next(this.viewConfig.items[1].searchModeChangedEvent, { searchMode: true })
      }
    }
  }
```

### Ejemplo de suscripción

En este caso, agregamos la suscripción al nombre de archivo al registro de la consola cuando se hace clic en la opción de nombre de archivo

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribe({
          key: 'rename',
          next: () => { console.log('rename using extension') }
        })
      }
    }
  }
```

### Ejemplo de evento de suscripción de aplicación

En este caso, se cambia el inicio de sesión en la consola del documento activo (cambiando pestañas en la interfaz de usuario del editor)

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeAppEvent({
          key: 'app.active_document_changed',
          next: () => { console.log('Extension: active document changed') }
        })
      }
    }
  }
```

### Ejemplo de suscripción de eventos del modelo de aplicación

Ejemplo de suscripción de eventos de modelo de aplicación como `app.mode`

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeAppModel('app.mode',
          () => { console.log('app mode subs') }
        )
      }
    }
  }
```

### Ejemplo de eventos del controlador principal

En este caso, agregamos la suscripción al evento `tabChange`, que es un evento del controlador `left_panel_container` que actúa
como controlador principal de `repository_panel`

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeParentEvent({
          key: 'tabChange',
          next: () => { console.log('tab change subs') }
        })
        this.parentEventHandlerNext('tabChange', {
          data: 'map_panel'
        )
      }
    }
  }
```

### Modelo de aplicación y controlador de aplicación siguiente

Se pueden activar directamente conociendo el evento correcto para activar y sus datos

```typescript
  { 
    id: 'file_options', 
    controller: {
      init: function () {
        this.appModelNext('app.mode', 'author')
        this.appEventHandlerNext('app.active_document_changed', 'active doc changed')   
      }
    }
  } 
```
