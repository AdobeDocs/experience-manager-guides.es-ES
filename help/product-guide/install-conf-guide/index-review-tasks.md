---
title: Realice la indexación para incluir todas las tareas de revisión en el panel Comentarios
description: Aprenda a indexar las tareas de revisión existentes para que aparezcan junto a las más recientes en la lista desplegable de tareas de revisión del panel Comentarios.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 7d0c757b647a2e6c5e563f0ed7db6a7225769033
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---

# Realice la indexación para incluir todas las tareas de revisión de un tema en el panel Comentarios

La característica [Ver todas las tareas de revisión de un tema](../user-guide/review-address-review-comments.md#view-all-review-tasks-for-a-topic), disponible en el panel Comentarios, permite a los autores seleccionar cualquier tarea de revisión (abierta o cerrada) asociada al tema abierto actualmente, sin cambiar de proyecto de revisión. Cuando está habilitado, el panel **Comentarios** del Editor incluye una lista desplegable de todas las tareas de revisión de las que forma parte el tema, junto con el estado de cada tarea y el proyecto al que pertenece.

De forma predeterminada, cuando esta función está habilitada en una instancia, las tareas de revisión se indexan a medida que se crean, por lo que están disponibles automáticamente en esta lista desplegable.

Sin embargo, si la función está deshabilitada en el momento en que Experience Manager Guides se implementa en una instancia, las tareas de revisión creadas mientras permanece deshabilitada no se indexan. Como Administrador, si activa la función después de que ya existan dichas tareas de revisión, dichas tareas no aparecerán en la lista desplegable hasta que se indexen. Para que estén disponibles, debe ejecutar un script de una sola vez para indexar las tareas de revisión existentes.

Ejecute el siguiente comando cURL una vez para indexar las tareas de revisión existentes:

```bash
curl --location 'http://<host>:<port>/bin/guides/script/start' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Basic <base64-encoded-credentials>' \
--header 'Cookie: cq-authoring-mode=TOUCH' \
--data-urlencode 'jobType=review-topic-guids-migration'
```
