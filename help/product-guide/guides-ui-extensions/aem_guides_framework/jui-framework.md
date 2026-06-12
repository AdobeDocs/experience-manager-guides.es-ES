---
title: Marco de jui
description: Entender El Marco De Jui
role: User, Admin
exl-id: c193cf90-5916-4d8c-88f1-be5014beca1c
TQID: https://experienceleague.adobe.com/AQFEy2bHTDHXq6QH8KTBOEzUvtA3Hf2ojhxvD0dsI7o
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552eid: c6d09140-3c91-45d3-b7ed-b681af752f43id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 249
ht-degree: 1%

---

# Marco de jui

Antes de entrar en cómo escribir extensiones, entenderemos la arquitectura del marco de trabajo.
Para que podamos extenderlo de manera efectiva.

## Introducción

JUI es un marco de MVC sobre los componentes React y Adobe React Spectrum. JUI es la interfaz de usuario de JSON. Consta de varios repositorios de Git.

JUI-Core es la biblioteca principal con toda la lógica para convertir la configuración JSON en componentes de React en funcionamiento y vincularla con una instancia de clase de controlador relevante.
La biblioteca JUI-React-Spectrum tiene widgets envolventes de componentes de Adobe React Spectrum

## Diseño principal de JUI

### Diseño de IU de MVC

![Flujo MVC de JUI](./imgs/jui-mvc-flow.png)

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
