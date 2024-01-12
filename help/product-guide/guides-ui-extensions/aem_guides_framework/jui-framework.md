---
title: Marco de jui
description: Entender El Marco De Jui
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 1%

---

# Marco de jui

Antes de entrar en cómo escribir extensiones, entenderemos la arquitectura del marco de trabajo.
Para que podamos extenderlo de manera efectiva.

## Introducción

JUI es un módulo de MVC sobre los componentes React y Adobe React Spectrum. JUI es la interfaz de usuario de JSON. Consta de varios repositorios de Git.

JUI-Core es la biblioteca principal con toda la lógica para convertir la configuración JSON en componentes de React en funcionamiento y vincularla con una instancia de clase de controlador relevante.
La biblioteca JUI-React-Spectrum tiene widgets envolventes de componentes de Adobe de React Spectrum

## Diseño principal de JUI

### Diseño de IU de MVC

![Flujo JUI MVC](./imgs/jui-mvc-flow.png)

### Widget

- Tiene un ID único.
- Tiene un archivo JSON individual para ver.
- Puede tener un controlador propio o compartido.
- Puede utilizar el modelo principal o el nuevo modelo.
- Puede tener elementos de interfaz de usuario (componentes de React)
- Puede tener otros widgets
- La aplicación es un widget

![Widget de JUI](./imgs/jui-widget.png)

### Elemento

- Es un componente de HTML/React.
- No tiene ningún modelo, su utiliza el modelo de widget principal.

### Controlador de eventos

- Siguiente (eventOpts)
   - Para almacenar en déclencheur el evento con algunas opciones
- Suscribirse (llamada de retorno)
   - Obtener notificación de que el evento se activa con la configuración de

### Modelo global/de aplicación

- Siguiente (nuevo valor)
   - Para publicar un nuevo valor
- Suscribirse (llamada de retorno)
   - Para obtener una notificación del valor cambiado
   - Primera vez que se obtiene un valor antiguo
- GetValue()
   - Para obtener el valor actual

### Controlador

- Debe ampliarse desde la clase Controller
- API
- CreateModel
   - Para crear un modelo independiente de widget secundario
- InitEventHandler
   - Para crear un widget secundario, separe el controlador de eventos
- RegisterCommands
   - Para registrar eventos locales, principales o de aplicación
- Next(eventName, eventHandler)
   - Para almacenar en déclencheur el evento del controlador de eventos de widget secundario, el controlador de eventos de widget principal o el controlador de eventos de aplicación
- Suscribirse (devolución de llamada, eventHandler)
- SubscribeAppModel(callback)

### Diseño de aplicación de ejemplo

![Aplicación de ejemplo](./imgs/jui-sample-app.png)
