---
title: Explicación de los tiempos de espera de sesión en Experience Manager Guides
description: Obtenga información sobre los tiempos de espera de sesiones en Experience Manager Guides.
feature: Authoring, Publishing
role: User
exl-id: f09b1215-4753-4dfd-89ef-1629257e5efe
TQID: https://experienceleague.adobe.com/nrxkVxSUooy2-08PaUp1pjiH8w2kBBNGC9efarvepbQ
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 249
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
