---
title: Explicación de los tiempos de espera de sesión en Experience Manager Guides
description: Obtenga información sobre los tiempos de espera de sesiones en Experience Manager Guides.
feature: Authoring, Publishing
role: User
source-git-commit: a6e015817bc9a964e3ca6a83c50089e7fabcdd94
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 0%

---

# ¿Por qué Experience Manager Guides cierra la sesión después de un cierto período de tiempo?

Experience Manager Guides finaliza una sesión de usuario después de un período de inactividad definido (tiempo de espera de inactividad). Esta funcionalidad de cierre de sesión automático está configurada en Adobe Experience Manager. Cuando caduca la sesión, se muestra una alerta emergente para notificar al usuario la sesión caducada. Esta alerta impide que el usuario realice más cambios en el contenido.

**¿Cómo funciona el tiempo de espera de sesión?**

Experience Manager Guides envía una solicitud en segundo plano `token.json` cada 30 segundos para validar la sesión. Si la sesión sigue activa, se devuelve un token válido. Si la sesión ha caducado debido a la inactividad, se devuelve un token vacío y la sesión se considera inactiva.

**¿Qué sucede cuando caduca la sesión?**

Cuando se detecta una sesión inactiva:

- Aparece una alerta emergente para notificar que ha cerrado la sesión.

  ![](images/sign-out-prompt.png)

- La alerta desactiva todas las interacciones con la aplicación.

- Al seleccionar **Aceptar**, se actualizará el explorador y se le redirigirá a la página de inicio de sesión.
- Al iniciar sesión, se le redirigirá a la última página abierta de Experience Manager Guides.

**Pasos siguientes**

La alerta de caducidad de la sesión ayuda a evitar la pérdida de datos al restringir la realización de cambios en la aplicación durante una sesión inactiva. Para evitar la pérdida accidental de contenido, se recomienda guardar el trabajo con regularidad en el editor, especialmente antes de alejarse del sistema durante un periodo prolongado de tiempo.





