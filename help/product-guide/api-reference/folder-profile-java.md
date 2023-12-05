---
title: API basada en Java para trabajar con perfiles de carpeta
description: Obtenga información acerca de la API basada en Java para trabajar con perfiles de carpeta
exl-id: 388ae654-c4f9-4bb7-ba98-370b8919e3a6
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# API basada en Java para trabajar con perfiles de carpeta {#id175UB30E05Z}

La siguiente API basada en Java le permite agregar atributos condicionales a un perfil de nivel de carpeta. Esta API está disponible en forma de paquete. Debe incluir este paquete en su código para utilizar estas API.

Detalles del paquete:

- ID de grupo: **com.adobe.fmdita**

- ID del artefacto: **api**

- Versión: **3,2**

- Paquete: **com.adobe.fmdita.api.profiles**

- Detalles de la clase:

  ```JAVA
  public class FolderProfileUtils extends Object
  ```

  El **`FolderProfileUtils`** contiene un método para agregar atributos condicionales en un perfil de carpeta.


## Añadir atributos condicionales a un perfil de carpeta

El ``addAttributeProfiles`` El método agrega atributos condicionales a un perfil de nivel de carpeta.

**Sintaxis**:

```JAVA
public static boolean addAttributeProfiles
(List
<String> attributeNames, 
List
    <String> values, 
List
        <String> labels,
String profileName, 
Session session) throws GuidesApiException
```

**Parámetros**: |Nombre|Tipo|Descripción| |----|----|-----------| |``attributeNames``|Cadena|Lista de nombres de atributos.| |``values``|Cadena|Lista de valores para los atributos dados.| |`labels`|Cadena|Una lista de etiquetas para `attribute`- `value` pares. [1](#fntarg_1)| |`profileName`|Cadena|Nombre del perfil de nivel de carpeta al que se deben aplicar estos atributos, valores y etiquetas. **Importante:** Todos los atributos, valores y etiquetas existentes definidos en el perfil se sobrescriben.| |`session`|javax.jcr.Session|Una sesión JCR válida.|

**Devuelve**:
`true` para el éxito. En caso de error, se genera una excepción.

**Excepción**: lanzamientos ``java.lang.Exception`` en los siguientes casos:

- Si la API no pudo obtener `resourceResolverFactory` objeto. En ese caso, debe reiniciar el paquete.
- Si los parámetros pasados a la API no son válidos.
- Si se llama a la API mediante una sesión de usuario no autorizada, como el usuario que no es administrador del perfil de carpeta dado.

[1](#fnsrc_1) El `attributeNames`, `values`, y `labels` en el mismo índice de una lista de matriz debe corresponder a la misma entrada.
