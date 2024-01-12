---
title: Incluir @navtitle atributo de forma predeterminada
description: Obtenga información sobre cómo incluir @navtitle atributo de forma predeterminada
exl-id: 3def20dc-dd24-4526-ae36-45708249d34a
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 1%

---

# Incluir @navtitle atributo de forma predeterminada {#id2115BC0J0XA}

Se pueden añadir distintos tipos de ficheros de referencia en un mapa, por ejemplo, mapas de tema, de referencia, de tarea, \(sub\), etc. La mayoría de estos archivos admiten el `@navtitle` atributo. Sin embargo, no muchos autores lo utilizan de manera consistente. Si desea aplicar el uso de `@navtitle` en todos los archivos a los que se hace referencia en un mapa, puede hacerlo con una configuración simple.

Una vez activada, cada archivo de referencia que añada a un mapa obtendrá automáticamente el `@navtitle` atributo añadido a sus propiedades. El `@navtitle` también obtendrá el valor del `title` del contenido referenciado.

Para incluir `@navtitle` de forma predeterminada, en las propiedades de los archivos de referencia, realice los siguientes pasos:

1. Descargue el archivo ui\_config.json.

   Puede realizar este cambio en el perfil de nivel Global o de nivel de carpeta. Según dónde desee realizar este cambio, debe descargar el archivo ui\_config.json correspondiente. Para obtener más información sobre la descarga del archivo ui\_config.json, consulte [Configurar y personalizar el Editor Web XML](conf-folder-level.md#id2065G300O5Z).

1. Busque la variable `ditaAttributes` definición.

   La definición predeterminada de `ditaAttributes` es:

   ```json
   "ditaAttributes": {
   "attributes": [],
   "constraint": false,
   "required": {}
   },
   ```

1. Cambie el `required` como parámetro:

   ```json
   "required": {"navtitle": true}
   ```

1. Guarde el archivo.

1. Cargue el archivo en el perfil correspondiente \(Global o Folder\).


Con esta configuración, cada archivo de referencia que añada a un mapa contendrá el `@navtitle` de forma predeterminada.
