---
title: Exclusión de la traducción de párrafos dentro de un tema
description: Exclusión de párrafos de un tema de la traducción
feature: Translation
role: User
exl-id: 21e41bb4-52f3-4352-92d9-4a60f636de99
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Exclusión de párrafos de un tema de la traducción

La forma más sencilla es utilizar el atributo translation=no.

+ Los autores pueden insertar el atributo adicional como **translation=no** en los párrafos que no desean traducir. El proveedor de traducción debe estar informado y puede hacer una configuración al final para ignorar el texto con este atributo.
+ La traducción automática OOTB (con conector de prueba de Microsoft Translation) muestra el mismo comportamiento.
+ Pruebas con la traducción de Microsoft : si define **translate=no** a nivel de párrafo, no traduce el párrafo completo. Este atributo se puede definir en cualquier elemento y el contenido dentro de ese elemento no se traduce.


Estas son algunas capturas de pantalla que lo explican con más detalle:

**Contenido de origen**

![Contenido de origen](assets/source-content.jpg)

**Contenido traducido en español**

![Contenido traducido en español](assets/trans-content.jpg)
