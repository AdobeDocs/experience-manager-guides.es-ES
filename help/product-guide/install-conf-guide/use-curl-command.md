---
title: Usar comandos curl
description: Aprenda a utilizar comandos curl en el contenido cargado en Experience Manager Guides.
feature: Migration
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 1%

---

# Usar comandos curl

También puede utilizar comandos curl para crear una carpeta en DAM, cargar archivos y agregar metadatos al contenido cargado.

## Crear una carpeta.

Ejecute el siguiente comando para crear una carpeta en el repositorio de AEM:

```curl
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Especifique los siguientes parámetros para crear una carpeta:

- `<username>:<passowrd>`: especifique el nombre de usuario y la contraseña para acceder al repositorio de AEM. Este usuario debe tener los privilegios de creación de carpetas.

- `jcr:primaryType=sling:Folder`: especifique este parámetro *como está* para crear un recurso de tipo carpeta.

- `<server folder path>`: ruta de carpeta completa que incluye el nombre de la nueva carpeta que desea crear en el repositorio de AEM. Por ejemplo, si especifica la ruta como `http://192.168.1.1:4502/content/dam/projects/AEM-Guides`, la carpeta `AEM-Guides` se creará dentro de la carpeta `projects` en DAM.


## Cargar un archivo

Ejecute el siguiente comando para cargar un archivo en el repositorio de AEM:

```curl
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Especifique los siguientes parámetros para cargar un archivo:

- `<username>:<passowrd>`: especifique el nombre de usuario y la contraseña para acceder al repositorio de AEM. Este usuario debe tener privilegios de escritura en `server folder path`.

- ``local file path``: ruta de archivo completa del sistema local que desea cargar.

- `<server folder path>`: ruta de acceso completa a la carpeta del servidor de AEM donde desea cargar el archivo.


## Añadir metadatos

Ejecute el siguiente comando para agregar metadatos a un archivo:

```curl
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Especifique los siguientes parámetros para agregar información de metadatos:

- `<username>:<passowrd>`: especifique el nombre de usuario y la contraseña para acceder al repositorio de AEM. Este usuario debe tener privilegios de escritura en ``metadata node path``.

- ``-F<attribute name>=<value>``: `<attribute name>` es el nombre del atributo de metadatos, como `audience` y `<value>` podría ser `internal`. Puede especificar varios pares de nombre-valor de atributo separados por espacio.

- `<metadata node path>`: ruta de carpeta completa que incluye el nombre de archivo y su nodo de metadatos. Por ejemplo, si especifica la ruta de acceso como `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata`, la información de metadatos especificada se establecerá en el archivo `intro.xml`.