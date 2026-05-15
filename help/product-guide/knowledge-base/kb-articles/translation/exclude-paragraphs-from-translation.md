---
title: Exclusión de la traducción de párrafos dentro de un tema
description: Exclusión de párrafos de un tema de la traducción
feature: Translation
role: User
exl-id: 21e41bb4-52f3-4352-92d9-4a60f636de99
TQID: https://experienceleague.adobe.com/IAY5PLpWlHEpMygjmHI-BqS75-VqAU5x1o9mdiu4Aac
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 148
ht-degree: 0%

---

# Exclusión de párrafos de un tema de la traducción

La forma más sencilla es utilizar el atributo translation=no.

+ Los autores pueden insertar el atributo adicional como **translation=no** en los párrafos que no desean traducir. El proveedor de traducción debe estar informado y puede hacer una configuración al final para ignorar el texto con este atributo.
+ La traducción automática OOTB (con conector de prueba de Microsoft Translation) muestra el mismo comportamiento.
+ Pruebas con la traducción de Microsoft: si define el atributo **translate=no** en el nivel de párrafo, no traduce el párrafo completo. Este atributo se puede definir en cualquier elemento y el contenido dentro de ese elemento no se traduce.


Estas son algunas capturas de pantalla que lo explican con más detalle:

**Contenido de Source**

![Contenido de Source](assets/source-content.jpg)

**Contenido traducido al español**

![Contenido traducido al español](assets/trans-content.jpg)
