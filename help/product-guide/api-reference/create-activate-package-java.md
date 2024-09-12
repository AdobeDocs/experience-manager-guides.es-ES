---
title: API basada en Java para crear y activar paquetes
description: Obtenga información acerca de la API basada en Java para crear y activar paquetes
exl-id: b801c2b3-445f-4aa7-a4f2-029563d7cb3a
feature: Java-Based API Packages
role: Developer
level: Experienced
source-git-commit: ed0b0e6124a8656e711a8e64b290b805569fbd48
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 1%

---

# API basada en Java para crear y activar paquetes {#id175UB30E05Z}

>[!NOTE]
>
> Puede utilizar las API basadas en Java disponibles en Experience Manager Guides para crear complementos personalizados y ampliar los flujos de trabajo predeterminados. Este artículo se archivará en noviembre de 2024.
> Consulta [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) para obtener la documentación más reciente y detallada sobre el uso de la API basada en Java.


La siguiente API basada en Java le permite crear y activar paquetes de CRX. Esta API está disponible en forma de paquete. Debe incluir este paquete en su código para utilizar estas API.

Detalles del paquete:

- Id. de grupo: **com.adobe.fmdita**

- ID de artefacto: **api**

- Versión: **3.3**

- Paquete: **com.adobe.fmdita.api.crxactivate**

- Detalles de la clase:

  ```JAVA
  public class CRXActivator
  ```

  La clase **`CRXActivator`** contiene un método para crear paquetes CRX y replicarlos en la instancia de publicación.


## Creación y activación de paquetes

El método `activate` crea un paquete de CRX en la instancia de autor y lo replica en la instancia de publicación, si es necesario. AEM Se da por hecho que los parámetros de replicación de la ya se han configurado en la instancia de autor. Este método crea el paquete de CRX en función de una lista de reglas proporcionadas como parámetros de entrada en una cadena JSON.
>[!NOTE]
>
> Los errores encontrados durante el proceso de creación o activación se escriben en `outputstream`.

### Ejemplo con dos parámetros

**Sintaxis**:


```JAVA
public static void activate
(
  String json, 
  OutputStream outputstream, 
  Session session
) 
throws GuidesApiException
```

### Ejemplo con el tercer parámetro opcional

```JAVA
public static void activate
(
  String json, 
  OutputStream outputstream,
  String activationTarget, 
  Session session
) 
throws GuidesApiException
```

**Parámetros**:

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `json` | Cadena | Cadena JSON que determina el paquete de CRX que se va a crear. Utilice el siguiente formato para crear la cadena JSON: <br>- `activate`: Es del tipo booleano \(`true`/`false`\). Determina si el paquete de CRX creado en la instancia de autor se replica en la instancia de publicación. <br> - `rules`: es de tipo matriz JSON. Una matriz de reglas JSON, que se procesan secuencialmente para crear el paquete de CRX. <br> - `rootPath`: es de tipo cadena. Ruta base en la que se ejecutan las consultas de nodo/propiedad. Si no hay consultas de nodo/propiedad presentes, la ruta raíz y todos los nodos presentes bajo la ruta raíz se incluyen en el paquete de CRX. <br> - `nodeQueries`: es de tipo matriz Regex. Matriz de expresiones regulares que se utiliza para incluir archivos específicos en la ruta raíz. <br> - `propertyQueries`: es de tipo matriz JSON. Una matriz de objetos JSON con cada objeto JSON que consta de una consulta XPath que se ejecutará en la ruta raíz y el nombre de una propiedad presente en cada nodo JCR después de ejecutar la consulta. El valor de la propiedad en cada nodo JCR debe ser una ruta o una matriz de rutas. Las rutas presentes en esta propiedad se añaden al paquete de CRX. |
| `outputstream` | java.io.OutputStream | Se utiliza para escribir el resultado de varias fases, como la ejecución de consultas, la inclusión de archivos, la creación de paquetes de CRX o la activación. Cualquier error encontrado durante el proceso de creación o activación se escribe en `outputstream`. Esto resulta útil para la depuración. |
| `session` | Cadena | Una sesión JCR válida con permiso de activación. |
| `activationTarget` | Cadena | (*Opcional*) `preview` o `publish` para el Cloud Service y `publish` para el software On-Premise <br> - Para el Cloud Service, si el parámetro contiene un valor no válido, se produce un error en la activación del paquete. <br>: para el software local, si el parámetro contiene un valor no válido, el error se registra y la publicación se realiza con el valor predeterminado `publish`. |

**Excepción**:

Lanza `java.io.IOException` y `java.io.IllegalArgumentException`


Si no define el parámetro opcional `activationTarget`, se activará usando el agente de publicación predeterminado tanto para el Cloud Service como para el software On-Premise.


**Ejemplo**:
El siguiente ejemplo muestra cómo crear una consulta JSON:

```JSON
{
  "activate": true,
  "rules": [
    {
      "rootPath": "/content/dam/nested",
      "nodeQueries": [
        ".*\\.jpg",
        ".*\\.png",
        ".*\\.gif"        
      ]
    },
    {
      "rootPath": "/content/output/sites/hierarchy_ditamap"
    },
    {
      "rootPath": "/content/output/sites/hierarchy_ditamap",
      "propertyQueries": [
        {
          "query": "//*[@fileReference]",
          "property": "fileReference"
        }
      ]
    }
  ]
}
```

La consulta JSON de ejemplo consta de las siguientes reglas:

- En el paquete solo se incluyen las imágenes .png, .jpg y .gif en la ruta /content/dam/nested.
- Todos los nodos bajo /content/output/sites/hierarchy\_ditamap están incluidos en el paquete.
- Las rutas de acceso presentes en la propiedad `fileReference` de los nodos bajo /content/output/sites/hierarchy\_ditamap se incluyen en el paquete.
