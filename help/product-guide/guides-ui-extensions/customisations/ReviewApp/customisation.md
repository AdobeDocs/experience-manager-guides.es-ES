---
title: Personalización
description: Personalización de la aplicación de revisión
source-git-commit: a61abc0d2b480e276991db916ba0cbf630ca7996
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---


# Personalización de la aplicación de revisión

Para facilitar la personalización de la aplicación de revisión, hemos proporcionado algunos enlaces que se enumeran y explican a continuación:

## Revisar-Comentario

- id: `review_comment`
- gancho: `this.updateExtraProps`:

Como se discutió [aquí](../../aem_guides_framework/basic-customisation.md), cualquier atributo nuevo añadido durante la personalización pasa a `this.model.extraProps`. El método `updateExtraProps` permite agregar atributos a un comentario de revisión, y administrar la actualización y el almacenamiento del atributo agregado en el servidor.

### Ejemplo de uso

Supongamos, por ejemplo, que desea agregar campos `commentRationale` y `severity` a sus comentarios.
Vamos a actualizar el `commentRationale` a &quot;Esta es una frase importante&quot;. y el `severity` a &quot;CRÍTICO&quot;.
Esto se puede hacer con la sintaxis:

```typescript
 this.updateExtraProps(
        {'commentRationale': 'This is an important sentence.',
        'severity': 'CRITICAL'}
      )
```

El fragmento de código anterior gestiona la actualización y el guardado de los valores. Los valores guardados se pueden representar en la interfaz de usuario definiendo la vista.

```JSON
{
    "component" : "label",
    "label": "@extraProps.commentRationale"
}
```

## Panel de revisión en línea

- id: `inline_review_panel`

1. gancho: `onNewCommentEvent`
El gancho `onNewCommentEvent` permite iniciar un evento o llamar a un método en un nuevo evento de comentario o respuesta.
Los argumentos recibidos en la `onNewCommentEvent` incluir:
   - events: el evento de comentario/respuesta enviado.
   - newComment: booleano Si el evento enviado fue un nuevo evento de comentario, es decir, `highlight`, `insertion`, `deletion`, `sticky note comment`
   - newReply: booleano Si el evento distribuido era un nuevo evento de respuesta.

2. gancho: `sendExtraProps`

Este vínculo es beneficioso si desea ampliar una `event` y enviar `extraProps` del panel de revisión en línea. Explicaremos el uso de estos dos ganchos a continuación.

### Ejemplo del panel de revisión en línea

Supongamos que queremos enviar un extraProp, `userInfo`, cada vez que se envía un nuevo comentario o respuesta. Ahora esto se hará a través del panel de revisión en línea, sin embargo, no tenemos la referencia al commentId del comentario recién generado, por lo tanto para lograrlo podemos escribir el siguiente código.

```typescript
    onNewCommentEvent(args){
      const events = _.get(args, "events")
      const currTopicIndex = tcx.model.getValue(tcx.model.KEYS.REVIEW_CURR_TOPIC) || this.model.currTopicIndex || "0"
      const event = _.get(_.get(events, currTopicIndex), '0')
      const newComment = _.get(args, 'newComment')
      const newReply = _.get(args, 'newReply')
      if ((newComment || newReply) && event) {
        this.next('setUserInfo', event)
      }
    },
```

En el fragmento de código anterior, comprobamos si el evento enviado era un comentario o una respuesta nuevos. En caso de un nuevo comentario o respuesta, llamamos al método `setUserInfo`

```typescript
    setUserInfo(event) {
      this.loader?.getUserInfo(event.user).subscribe(userData => {
        const extraProps = {
          "userFirstName": userData?.givenName || '',
          "userLastName": userData?.familyName || '',
          "userTitle": userData?.title || '',
          "userJobTitle": userData?.jobTitle || '',
          'userEmail': userData?.email || '',
        }
        const data = {... event, extraProps}
        this.sendExtraProps(
          data
        )
      })
    },
```

En el método anterior, ampliamos el evento para enviar propiedades adicionales que incluyen el nombre, el correo electrónico, el título, etc. del usuario. Ampliar el evento de esta manera garantiza que las extraProps se envíen con el commentId correcto, lo que garantiza que se adjunten al comentario correcto.

El gancho `updateExtraProps` llama al vínculo de forma inherente `sendExtraProps`, así que, ¿cuándo usar qué?

Utilizamos `updateExtraProps` en el `review_comment` controlador, que ya tiene el del comentario `id` y por lo tanto, solo tiene que mencionar el `extraProps.`

El `inline_review_panel` sin embargo, no tiene acceso al id del comentario, por lo que cada vez que necesite enviar un evento desde el panel de revisión en línea, la variable `sendExtraProps` será útil.
