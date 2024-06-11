---
title: Personalizar la aplicación
description: Personalizar la aplicación
role: User, Admin
exl-id: 3e454c48-2168-41a5-bbab-05c8a5b5aeb1
source-git-commit: 4f00d6b7ad45636618bafe92e643b3e288ec2643
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# Personalizar la aplicación

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
En nuestra aplicación, cada vista se define mediante un JSON. Se hace referencia a los JSON mediante sus ID únicos, denominados `id`.

## Controlador

El controlador se utiliza para controlar eventos y procesar los datos. El controlador se utiliza para recuperar y enviar datos desde el servidor, es la interfaz entre lo que se muestra en la interfaz de usuario y lo que se almacena en el servidor.

- Para establecer los valores en la inicialización, se utiliza el `init` función.
- Para agregar un método al controlador utilizamos la siguiente sintaxis:

```typescript
methodName: function(args){
    // functionality
}
```

El `methodName` aquí sirve como `key` para hacer referencia al método en el archivo JSON (vista) o en otras funciones

- Para llamar a un método en el controlador utilizamos la sintaxis

```typescript
this.next('methodName', args)
```

## Ejemplos

Veamos un ejemplo sencillo para mostrar cómo estos 3 componentes interactúan entre sí.
Agregaremos un botón que cambia su valor de etiqueta con un clic

### Ver ejemplo

A continuación, definimos el JSON de un botón que muestra un texto dinámico almacenado en el modelo bajo el nombre de la variable `buttonLabel`.
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
    init: function (context) {
      context.setValue("buttonLabel", "Submit")
    },

    switchButtonLabel(){
        const buttonLabel = this.getValue("buttonLabel") === "Submit"? "Cancel" : "Submit"
        this.setValue("buttonLabel", buttonLabel)
    }
  }
```

El siguiente GIF muestra el código anterior en acción
![basic_customization](imgs/basic_customisation.gif "Botón de personalización básica")
