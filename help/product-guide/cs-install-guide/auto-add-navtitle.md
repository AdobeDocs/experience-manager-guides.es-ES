---
title: Incluir @navtitle atributo de forma predeterminada
description: Obtenga información sobre cómo incluir @navtitle atributo de forma predeterminada
exl-id: 38711c0c-efa8-461a-92e1-ecfcdcdd36d3
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Incluir @navtitle atributo de forma predeterminada {#id2115BC0J0XA}

Se pueden añadir distintos tipos de ficheros de referencia en un mapa, por ejemplo, mapas de tema, de referencia, de tarea, \(sub\), etc. La mayoría de estos archivos admiten el `@navtitle` atributo. Sin embargo, no muchos autores lo utilizan de manera consistente. Si desea aplicar el uso de `@navtitle` en todos los archivos a los que se hace referencia en un mapa, puede hacerlo con una configuración simple.

Una vez activada, cada archivo de referencia que añada a un mapa obtendrá automáticamente el `@navtitle` atributo añadido a sus propiedades. El `@navtitle` también obtendrá el valor del `title` del contenido referenciado.

Para incluir `@navtitle` de forma predeterminada, en las propiedades de los archivos de referencia, realice los siguientes pasos:

1. Para descargar el archivo de configuración de la interfaz de usuario, inicie sesión en Adobe Experience Manager como administrador.

1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.
1. Seleccionar **Guías** en la lista de herramientas y haga clic en **Perfiles de carpeta**.
1. Haga clic en **Perfil global** mosaico.
1. Seleccione el **Configuración del editor XML** y haga clic en **Editar** en la parte superior
1. Haga clic en **Descargar** para descargar el archivo ui\_config.json en su sistema local.
1. Puede realizar este cambio en el perfil de nivel Global o de nivel de carpeta. Según dónde desee realizar este cambio, debe descargar el archivo ui\_config.json correspondiente. Para obtener más información sobre la descarga del archivo ui\_config.json, consulte [Configurar y personalizar el Editor Web XML](conf-folder-level.md#id2065G300O5Z).

1. Busque la variable `ditaAttributes` definición.

   La definición predeterminada de `ditaAttributes` es:

   ```
   "ditaAttributes": {
                           "attributes": [],
                           "constraint": false,
                           "required": {}
                           },
   ```

1. Cambie el `required` como parámetro:

   ```
   "required": {"navtitle": true}
   ```

1. Guarde el archivo.

1. Cargue el archivo en el perfil correspondiente \(Global o Folder\).


Con esta configuración, cada archivo de referencia que añada a un mapa contendrá el `@navtitle` de forma predeterminada.

**Tema principal:**[ Personalizar editor web](conf-web-editor.md)
