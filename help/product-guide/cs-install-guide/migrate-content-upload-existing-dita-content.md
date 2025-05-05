---
title: Cargar contenido DITA existente
description: Obtenga información sobre cómo cargar contenido DITA existente
exl-id: 2b385eef-00a7-4c25-9e78-367a0c9e44ba
feature: Migration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 0%

---

# Cargar contenido DITA existente {#id176FF000JUI}

Lo más probable es que tenga un repositorio de contenido DITA existente que desee utilizar con AEM Guides. Para ese contenido existente, puede usar cualquiera de los métodos admitidos explicados en [Agregar recursos digitales a Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=es).

## Configurar patrón de nombre de archivo UUID

Al importar contenido, no es necesario que los nombres de archivo estén basados en el UUID. En un sistema que utiliza nombres de archivo basados en UUID, es obligatorio que se haga referencia a todos los archivos utilizando sus UUID en lugar de sus nombres de archivo originales. Si un archivo importado no tiene nombres de archivo basados en UUID, puede configurar el sistema para agregar un UUID a su propiedad de archivo. A continuación, este UUID se utiliza para hacer referencia a estos archivos donde UUID no se utiliza para nombrar los archivos.

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar el patrón de nombre de archivo UUID:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `uuid.regex` | Cadena que especifica la regex para el patrón de nombre de archivo UUID. <br> Si un archivo no sigue el patrón especificado, se agrega un UUID a la propiedad del archivo y todas las referencias al archivo se actualizan con el UUID asignado al archivo. <br> **Valor predeterminado**: `"^GUID-(?<id>.*)"` |

## Usar comandos curl

También puede utilizar comandos curl para crear una carpeta en DAM, cargar archivos y agregar metadatos al contenido cargado.

**Crear una carpeta**

AEM Ejecute el siguiente comando para crear una carpeta en el repositorio de:

```
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Especifique los siguientes parámetros para crear una carpeta:

- AEM `<username>:<passowrd>`: especifique el nombre de usuario y la contraseña para tener acceso al repositorio de. Este usuario debe tener los privilegios de creación de carpetas.

- `jcr:primaryType=sling:Folder`: especifique este parámetro *como está* para crear un recurso de tipo carpeta.

- AEM `<server folder path>`: ruta de acceso completa de la carpeta, incluido el nombre de la nueva carpeta que desea crear en el repositorio de la. Por ejemplo, si especifica la ruta como `http://192.168.1.1:4502/content/dam/projects/AEM-Guides`, la carpeta `AEM-Guides` se creará dentro de la carpeta `projects` en DAM.


**Cargar un archivo**

AEM Ejecute el siguiente comando para cargar un archivo en el repositorio de:

```
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Especifique los siguientes parámetros para cargar un archivo:

- AEM `<username>:<passowrd>`: especifique el nombre de usuario y la contraseña para tener acceso al repositorio de. Este usuario debe tener privilegios de escritura en `server folder path`.

- ``local file path``: ruta de archivo completa del sistema local que desea cargar.

- AEM `<server folder path>`: complete la ruta de acceso a la carpeta en el servidor de donde desee cargar el archivo.


**Agregar metadatos**

Ejecute el siguiente comando para agregar metadatos a un archivo:

```
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Especifique los siguientes parámetros para agregar información de metadatos:

- AEM `<username>:<passowrd>`: especifique el nombre de usuario y la contraseña para tener acceso al repositorio de. Este usuario debe tener privilegios de escritura en ``metadata node path``.

- ``-F<attribute name>=<value>``: `<attribute name>` es el nombre del atributo de metadatos, como `audience` y `<value>` podría ser `internal`. Puede especificar varios pares de nombre-valor de atributo separados por espacio.

- `<metadata node path>`: ruta de carpeta completa que incluye el nombre de archivo y su nodo de metadatos. Por ejemplo, si especifica la ruta de acceso como `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata`, la información de metadatos especificada se establecerá en el archivo `intro.xml`.


**Tema principal:**&#x200B;[ Migrar contenido existente](migrate-content.md)
