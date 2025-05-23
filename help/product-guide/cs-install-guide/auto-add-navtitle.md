---
title: Incluir @navtitle atributo de forma predeterminada
description: Obtenga información sobre cómo incluir @navtitle atributo de forma predeterminada
exl-id: 38711c0c-efa8-461a-92e1-ecfcdcdd36d3
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Incluir @navtitle atributo de forma predeterminada {#id2115BC0J0XA}

Se pueden añadir distintos tipos de ficheros de referencia en un mapa, por ejemplo, mapas de tema, de referencia, de tarea, \(sub\), etc. La mayoría de estos archivos admiten el atributo `@navtitle`. Sin embargo, no muchos autores lo utilizan de manera consistente. Si desea aplicar el uso del atributo `@navtitle` en todos los archivos de referencia de un mapa, puede hacerlo con una configuración simple.

Una vez habilitada, cada archivo de referencia que agregue a un mapa obtendrá automáticamente el atributo `@navtitle` agregado a sus propiedades. `@navtitle` también obtendrá el valor del elemento `title` del contenido referenciado.

Para incluir el atributo `@navtitle` de forma predeterminada en las propiedades de los archivos de referencia, realice los siguientes pasos:

1. Para descargar el archivo de configuración de la interfaz de usuario, inicie sesión en Adobe Experience Manager como administrador.

1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.
1. Seleccione **Guías** de la lista de herramientas y haga clic en **Perfiles de carpeta**.
1. Haga clic en el mosaico **Perfil global**.
1. Seleccione la ficha **Configuración del editor XML** y haga clic en el icono **Editar** de la parte superior
1. Haga clic en el icono **Descargar** para descargar el archivo ui\_config.json en su sistema local.
1. Puede realizar este cambio en el perfil de nivel Global o de nivel de carpeta. Según dónde desee realizar este cambio, debe descargar el archivo ui\_config.json correspondiente. Para obtener más información acerca de cómo descargar el archivo ui\_config.json, vea [Configurar y personalizar el Editor Web XML](conf-folder-level.md#id2065G300O5Z).

1. Busque la definición `ditaAttributes`.

   La definición predeterminada de `ditaAttributes` es:

   ```
   "ditaAttributes": {
                           "attributes": [],
                           "constraint": false,
                           "required": {}
                           },
   ```

1. Cambiar el parámetro `required` como:

   ```
   "required": {"navtitle": true}
   ```

1. Guarde el archivo.

1. Cargue el archivo en el perfil correspondiente \(Global o Folder\).


Con esta configuración, cada archivo de referencia que agregue a un mapa contendrá el atributo `@navtitle` de forma predeterminada.

**Tema principal:**&#x200B;[ Personalizar editor web](conf-web-editor.md)
