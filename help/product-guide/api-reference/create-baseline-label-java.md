---
title: API basadas en Java para trabajar con líneas de base y etiquetas
description: Obtenga información acerca de las API basadas en Java para trabajar con líneas de base y etiquetas
exl-id: 0e2ba1bb-f5bf-44da-848a-a55385460c83
feature: Java-Based API Baseline
role: Developer
level: Experienced
source-git-commit: 1860525120edc4df33b898841b9073311d3031c5
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 2%

---

# API basadas en Java para trabajar con líneas de base y etiquetas {#id175UB30E05Z}

Las siguientes API basadas en Java le permiten crear líneas de base y agregar etiquetas a los archivos en una línea de base. Estas API están disponibles en forma de paquete. Debe incluir este paquete en su código para utilizar estas API.

Detalles del paquete:

- Id. de grupo: **com.adobe.fmdita**

- ID de artefacto: **api**

- Versión: **3.5**

- Paquete: **com.adobe.fmdita.api.baselines**

- Detalles de la clase:

  ```JAVA
  public class BaselineUtils extends Object
  ```

  La clase **BaselineUtils** contiene métodos para crear líneas de base y aplicar etiquetas a los archivos de una línea de base.


## Crear una línea base

El método crear línea de base tiene dos versiones: una para la solución de XML Documentation versión 3.5 y otra para las versiones anteriores a la versión 3.5 \(que incluye las versiones 3.4, 3.3 y 3.2\). La API versión 3.5 permite crear líneas de base mediante una etiqueta, referencias directas y referencias indirectas en un archivo de mapa.

La otra versión de API utiliza la fecha y la hora para crear una línea de base. Esta API se conserva para garantizar la compatibilidad con versiones anteriores de los sistemas que utilizan las soluciones de XML Documentation 3.4, 3.3 o 3.2.

**Sintaxis \(para la versión 3.5\)**:

```JAVA
public static String createBaseline(Session session, 
String sourcePath, 
String baselineTitle, 
String label, 
LinkedHashMap directContext, 
LinkedHashMap indirectContext) 
throws GuidesApiException
```

**Parámetros**:

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `session` | javax.jcr.Session | Una sesión JCR válida. La sesión de usuario debe tener permisos de lectura y escritura para el mapa DITA y permisos de lectura para todos los ficheros de referencia incluidos en la línea base. |
| `sourcePath` | Cadena | AEM Ruta absoluta del fichero de mapa DITA en el repositorio de la. |
| `baselineTitle` | Cadena | Un título único para la línea de base. |
| `label` | Cadena | Seleccione la versión de un tema que tenga aplicada la etiqueta determinada. |
| `directContext` | LinkedHashMap&lt;String, Object\> | Las configuraciones en función de las cuales se selecciona el tema \(content\) al que se hace referencia directamente, se sigue el orden mencionado en el mapa para resolver una versión. <br> Si después de la iteración en todas las claves del mapa no se encuentra ninguna versión, el proceso de creación de la línea base falla. <br> Si el HashMap está vacío \(enviar mapa vacío y no nulo de forma predeterminada\), de forma predeterminada se rellena como: <br>`directContext.put("label", label);` <br> `directContext.put("latest", true);` <br> Si desea que la creación de la línea de base seleccione solamente la versión de una etiqueta determinada y falla si no existe dicha versión, coloque la clave `label` y la etiqueta en la que desea crear la línea de base. |
| `indirectContext` | LinkedHashMap&lt;String, Object\> | Las configuraciones en función de las cuales se selecciona el tema \(contenido referenciado\) al que se hace referencia indirectamente; se sigue el orden mencionado en el mapa para resolver una versión. <br> Si después de la iteración en todas las claves del mapa no se encuentra ninguna versión, el proceso de creación de la línea base falla. <br> Si HashMap está vacío \(enviar mapa vacío y no nulo de forma predeterminada\), de forma predeterminada, se rellena como: <br>`indirectContext.put("label", label);` <br>`indirectContext.put "pickAutomatically", null);` <br> Si desea que sea la última versión en lugar de recoger una versión automáticamente, reemplace: <br>`indirectContext.put("pickAutomatically", null);` <br> _con:_ <br>`indirectContext.put("latest", true)` |

**Devuelve**:
El nombre de la línea base, que es el nombre de nodo de la línea base en el repositorio JCR. El título de la línea base recién creada se mostrará al usuario en la página Línea base del mapa DITA.

**Excepción**:
Inicia ``ItemExistExceptiom`` si ya existe una línea de base con el mismo título.

**Sintaxis \(para las versiones 3.4, 3.3 y 3.2\)**

```JAVA
public static String createBaseline
(Session session, 
String sourcePath, 
String baselineTitle, 
Date versionDate) throws GuidesApiException
```

**Parámetros**:

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `session` | javax.jcr.Session | Una sesión JCR válida. La sesión de usuario debe tener permisos de lectura y escritura para el mapa DITA y permisos de lectura para todos los ficheros de referencia incluidos en la línea base. |
| ``sourcePath`` | Cadena | AEM Ruta absoluta del fichero de mapa DITA en el repositorio de la. |
| `baselineTitle` | Cadena | Un título único para la línea de base. |
| `versionDate` | Fecha | La línea base se crea utilizando las versiones de los temas\(directamente referenciadas desde el mapa DITA\) en esta fecha. Especifique la fecha en formato `d-MM-yyyy H:mm`. |

**Devuelve**:
El nombre de la línea base, que es el nombre de nodo de la línea base en el repositorio JCR. El título de la línea base recién creada se mostrará al usuario en la página Línea base del mapa DITA.

**Excepción**:
Lanzamientos ``RepositoryException.``

## Aplicar etiquetas

El método ``applyLabel`` aplica una o varias etiquetas a los archivos de una línea de base.

**Sintaxis**:

```JAVA
public static void applyLabel(Session session,
                  String sourcePath,
                  String baselineName,
                  String label)
                  throws RepositoryException, WorkflowException, Exception
```

**Parámetros**:

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `session` | javax.jcr.Session | Una sesión JCR válida. |
| `sourcePath` | Cadena | AEM Ruta absoluta del fichero de mapa DITA en el repositorio de la. |
| ``baselineName`` | Cadena | Nombre del nodo de línea base en el que se debe aplicar la etiqueta. Para obtener el nombre del nodo de línea de base, puede utilizar el método [\#id185NFF0085Z](#id185NFF0085Z) o comprobar el nodo de líneas de base del mapa DITA en CRXDE.<br> **Nota:** La etiqueta se aplica a la versión de los archivos a los que se hace referencia directamente desde el archivo de asignación en la línea de base. |
| `label` | Cadena | Etiqueta que se aplica a los archivos de la línea de base. Asegúrese de que la etiqueta no contenga los siguientes caracteres: &amp;sol; &amp;comma; &amp; &amp;colon; &amp;comma; &amp;lbrack; &amp;comma; &amp;rbrack; &amp;comma; &amp;vert; &amp;comma; &amp;ast; <br> Si desea establecer varias etiquetas, sepárelas con una coma; por ejemplo, Label1, Label2. |

**Excepción**:
Lanza `RepositoryException`.

## Eliminar etiquetas

El método ``deleteLabel`` elimina una o varias etiquetas de los archivos de una línea de base.

**Sintaxis**:

```JAVA
public static Map
<String, String> deleteLabel(Session session, 
String sourcePath, 
String baselineName, 
String label) throws GuidesApiException
```

**Parámetros**:

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `session` | javax.jcr.Session | Una sesión JCR válida. |
| `sourcePath` | Cadena | AEM Ruta absoluta del fichero de mapa DITA en el repositorio de la. |
| `baselineName` | Cadena | Nombre de la línea base de la que se debe eliminar la etiqueta. <br> **Nota:** Se ha eliminado la etiqueta de la versión de los archivos a los que se hace referencia directamente desde el archivo de asignación en la línea de base. |
| `label` | Cadena | Etiqueta que se va a eliminar de los archivos de la línea de base. <br> Si desea eliminar varias etiquetas, sepárelas con una coma; por ejemplo, Etiqueta1, Etiqueta2. |

**Devuelve**:
Asignación con par *key:value* de `path:deletedlabels` para todos los archivos de la línea de base.

**Excepción**:
Lanza ``RepositoryException`, `VersionException`, `Exception``.
