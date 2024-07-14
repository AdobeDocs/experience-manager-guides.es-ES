---
title: Personalización
description: Personalización de la aplicación de revisión
role: User, Admin
exl-id: 9f6a4e9f-fc13-40b5-a30f-151c94faff81
source-git-commit: 4f00d6b7ad45636618bafe92e643b3e288ec2643
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Personalización de la aplicación de revisión

Para facilitar la personalización de la aplicación de revisión, hemos proporcionado algunos enlaces que se enumeran y explican a continuación:

## Revisar-Comentario

- id.: `review_comment`
- gancho: `this.updateExtraProps`:

Como se ha mencionado [aquí](../../aem_guides_framework/basic-customisation.md), cualquier atributo nuevo agregado durante la personalización pasa a ser de `this.model.extraProps`. El método `updateExtraProps` le permite agregar atributos a un comentario de revisión, controlando también la actualización y el almacenamiento del atributo agregado en el servidor.

### Ejemplo de uso

Supongamos, por ejemplo, que desea agregar los campos `commentRationale` y `severity` a los comentarios.
Actualicemos `commentRationale` a &quot;Esta es una oración importante&quot;. y `severity` a &quot;CRÍTICO&quot;.
Esto se puede hacer con la sintaxis:

```typescript
  this.next('updateExtraProps', {
    'commentRationale': 'This is an important sentence.',
    'severity': 'CRITICAL'
  })
```

El fragmento de código anterior gestiona la actualización y el guardado de los valores. Los valores guardados se pueden representar en la interfaz de usuario definiendo la vista.

```JSON
{
    "component" : "label",
    "label": "@extraProps.commentRationale"
}
```

## Panel de revisión en línea

- id.: `inline_review_panel`

1. gancho: `onNewCommentEvent`
El vínculo `onNewCommentEvent` le permite desencadenar un evento o llamar a un método en un nuevo evento de comentario o respuesta.
Los argumentos recibidos en `onNewCommentEvent` incluyen:
   - events: el evento de comentario/respuesta enviado.
   - newComment: booleano
Si el evento enviado fue un nuevo evento de comentario, por ejemplo: `highlight`, `insertion`, `deletion`, `sticky note comment`
   - newReply: booleano
Si el evento enviado era un nuevo evento de respuesta.

2. gancho: `sendExtraProps`

Este vínculo es útil si desea extender un `event` y enviar `extraProps` desde el panel de revisión en línea. Explicaremos el uso de estos dos ganchos a continuación.

### Ejemplo del panel de revisión en línea

Supongamos que queremos enviar un extraProp, `userInfo`, cada vez que se envíe un nuevo comentario o respuesta. Ahora esto se hará a través del panel de revisión en línea, sin embargo, no tenemos la referencia al commentId del comentario recién generado, por lo tanto para lograrlo podemos escribir el siguiente código.

```typescript
    onNewCommentEvent(args){
      const events = _.get(args, "events")
      const currTopicIndex = tcx.model.getValue(tcx.model.KEYS.REVIEW_CURR_TOPIC) || this.getValue('currTopicIndex') || "0"
      const event = _.get(_.get(events, currTopicIndex), '0')
      const newComment = _.get(args, 'newComment')
      const newReply = _.get(args, 'newReply')
      if ((newComment || newReply) && event) {
        this.next('setUserInfo', event)
      }
    },
```

En el fragmento de código anterior, comprobamos si el evento enviado era un comentario o una respuesta nuevos. En caso de un nuevo comentario o respuesta, se llama al método `setUserInfo`

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
        this.next(
          'sendExtraProps',
          data
        )
      })
    },
```

En el método anterior, ampliamos el evento para enviar propiedades adicionales que incluyen el nombre, el correo electrónico, el título, etc. del usuario. Ampliar el evento de esta manera garantiza que las extraProps se envíen con el commentId correcto, lo que garantiza que se adjunten al comentario correcto.

El vínculo `updateExtraProps` llama de forma inherente al vínculo `sendExtraProps`, por lo que, ¿cuándo usar qué?

Utilizamos `updateExtraProps` en el controlador `review_comment`, que ya tiene `id` del comentario y, por lo tanto, solo necesita mencionar `extraProps.`

Sin embargo, `inline_review_panel` no tiene acceso al identificador del comentario, por lo que siempre que necesite enviar un evento desde el panel de revisión en línea, `sendExtraProps` le resultará útil.
