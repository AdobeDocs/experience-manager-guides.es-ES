---
title: Incluir @navtitle atributo de forma predeterminada
description: Obtenga información sobre cómo incluir @navtitle atributo de forma predeterminada
exl-id: 3def20dc-dd24-4526-ae36-45708249d34a
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/bwVOZrkVrn6QPq7BoUttFvnFAzdLIL6--JGCoHYkA0o
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 221
ht-degree: 1%

---

# Incluir @navtitle atributo de forma predeterminada {#id2115BC0J0XA}

Se pueden añadir distintos tipos de ficheros de referencia en un mapa, por ejemplo, mapas de tema, de referencia, de tarea, \(sub\), etc. La mayoría de estos archivos admiten el atributo `@navtitle`. Sin embargo, no muchos autores lo utilizan de manera consistente. Si desea aplicar el uso del atributo `@navtitle` en todos los archivos de referencia de un mapa, puede hacerlo con una configuración simple.

Una vez habilitada, cada archivo de referencia que agregue a un mapa obtendrá automáticamente el atributo `@navtitle` agregado a sus propiedades. `@navtitle` también obtendrá el valor del elemento `title` del contenido referenciado.

Para incluir el atributo `@navtitle` de forma predeterminada en las propiedades de los archivos de referencia, realice los siguientes pasos:

1. Descargue el archivo ui\_config.json.

   Puede realizar este cambio en el perfil de nivel Global o de nivel de carpeta. Según dónde desee realizar este cambio, debe descargar el archivo ui\_config.json correspondiente. Para obtener más información acerca de cómo descargar el archivo ui\_config.json, vea [Configurar y personalizar el Editor XML](conf-folder-level.md#id2065G300O5Z).

1. Busque la definición `ditaAttributes`.

   La definición predeterminada de `ditaAttributes` es:

   ```json
   "ditaAttributes": {
   "attributes": [],
   "constraint": false,
   "required": {}
   },
   ```

1. Cambiar el parámetro `required` como:

   ```json
   "required": {"navtitle": true}
   ```

1. Guarde el archivo.

1. Cargue el archivo en el perfil correspondiente \(Global o Folder\).


Con esta configuración, cada archivo de referencia que agregue a un mapa contendrá el atributo `@navtitle` de forma predeterminada.
