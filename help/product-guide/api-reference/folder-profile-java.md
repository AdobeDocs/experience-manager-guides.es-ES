---
title: API basada en Java para trabajar con perfiles de carpeta
description: Obtenga información acerca de la API basada en Java para trabajar con perfiles de carpeta
exl-id: 388ae654-c4f9-4bb7-ba98-370b8919e3a6
feature: Java-Based API Folder Profiles
role: Developer
level: Experienced
source-git-commit: 8c80a4da8e61909aab0f2db81ef97149774b36c4
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 2%

---

# API basada en Java para trabajar con perfiles de carpeta {#id175UB30E05Z}

>[!NOTE]
>
> Puede utilizar las API basadas en Java disponibles en Experience Manager Guides para crear complementos personalizados y ampliar los flujos de trabajo predeterminados. Este artículo se archivará en noviembre de 2024.
> Consulta [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) para obtener la documentación más reciente y detallada sobre el uso de la API basada en Java.




La siguiente API basada en Java le permite agregar atributos condicionales a un perfil de nivel de carpeta. Esta API está disponible en forma de paquete. Debe incluir este paquete en su código para utilizar estas API.

Detalles del paquete:

- Id. de grupo: **com.adobe.fmdita**

- ID de artefacto: **api**

- Versión: **3.2**

- Paquete: **com.adobe.fmdita.api.profiles**

- Detalles de la clase:

  ```JAVA
  public class FolderProfileUtils extends Object
  ```

  La clase **`FolderProfileUtils`** contiene un método para agregar atributos condicionales en un perfil de carpeta.


## Añadir atributos condicionales a un perfil de carpeta

El método ``addAttributeProfiles`` agrega atributos condicionales a un perfil de nivel de carpeta.

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

**Parámetros**:

| Nombre | Tipo | Descripción |
|----|----|-----------|
| ``attributeNames`` | Cadena | Una lista de nombres de atributos. |
| ``values`` | Cadena | Una lista de valores para los atributos dados. |
| `labels` | Cadena | Una lista de etiquetas para los pares `attribute`- `value`. [1](#fntarg_1) |
| `profileName` | Cadena | El nombre del perfil de nivel de carpeta al que se deben aplicar estos atributos, valores y etiquetas. **Importante:** Todos los atributos-valores-etiquetas existentes definidos en el perfil se sobrescriben. |
| `session` | javax.jcr.Session | Una sesión JCR válida. |

**Devuelve**:
`true` para éxito. En caso de error, se genera una excepción.

**Excepción**:
Genera ``java.lang.Exception`` en los siguientes casos:

- Si la API no pudo obtener el objeto `resourceResolverFactory`. En ese caso, debe reiniciar el paquete.
- Si los parámetros pasados a la API no son válidos.
- Si se llama a la API mediante una sesión de usuario no autorizada, como el usuario que no es administrador del perfil de carpeta dado.

[1](#fnsrc_1): `attributeNames`, `values` y `labels` en el mismo índice de una lista de matriz deben corresponder a la misma entrada.
