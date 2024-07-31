---
title: API basadas en Java para trabajar con mapas DITA
description: Obtenga información acerca de las API basadas en Java para trabajar con mapas DITA
exl-id: bd91fc90-75f8-487c-99d1-2637e9cf9924
feature: Java-Based API Dita Map
role: Developer
level: Experienced
source-git-commit: 83966cc9187b13dd3b5956821e0aa038b41db28e
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 3%

---

# API basadas en Java para trabajar con mapas DITA {#id175UB30E05Z}

Las siguientes API basadas en Java le permiten trabajar con mapas DITA en AEM Guides. Estas API están disponibles en forma de paquete. Debe incluir este paquete en su código para utilizar estas API.

Detalles del paquete:

- Id. de grupo: **com.adobe.fmdita**

- ID de artefacto: **api**

- Versión: **3.2**

- Paquete: **com.adobe.fmdita.api.maps**

- Detalles de la clase:

  ```JAVA
  public class MapUtilities extends Object
  ```

  La clase MapUtilities contiene métodos para recuperar información de metadatos de un fichero de mapa DITA.


## Descargar mapa DITA con dependientes

El método `zipMapWithDependents` crea un archivo .zip que contiene un mapa DITA junto con todos sus dependientes, como temas a los que se hace referencia, submapas, imágenes y DTD. El fichero .zip para el mapa DITA se crea en función de una línea base determinada.

También permite mantener la misma estructura \(carpetas principales y secundarias\) o crear una estructura de archivos plana dentro de una sola carpeta para todos los archivos dependientes.

>[!IMPORTANT]
>
> La API generará una excepción y no podrá crear un archivo .zip si falta alguno de los archivos dependientes.

**Sintaxis**:

```JAVA
public static void zipMapWithDependents(Session session, 
                     String sourcePath, 
                     String baseline, 
                     OutputStream outputStream,
                     boolean flatFS) 
                     throws RepositoryException, IOException
```

**Parámetros**:

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `session` | javax.jcr.Session | Una sesión JCR válida. |
| `sourcePath` | Cadena | AEM Ruta \(en el repositorio de la\) del archivo de mapa DITA que debe descargarse. |
| `outputStream` | java.io.OutputStream | Flujo en el que se escribe el ZIP. |
| `baseline` | Cadena | Título de la línea de base que se utiliza para recuperar el contenido con versiones. <br> **Nota:** El valor distingue entre mayúsculas y minúsculas. |
| plainFS | Booleano | \(Opcional\) Si se establece en true, se devuelve una estructura plana de archivos en el archivo ZIP. Por ejemplo, si el mapa DITA hace referencia a contenido de varias carpetas, todos los ficheros a los que se hace referencia se extraerán en una sola carpeta. En caso de que haya archivos con el mismo nombre, se cambiará el nombre de esos archivos añadiendo un sufijo numérico. Todas las referencias \(en el mapa DITA y en los temas\) se gestionan automáticamente, ya que se actualizan en función de la nueva ubicación de los archivos en la estructura de carpetas plana. Si se establece en false, la estructura de carpetas se mantiene tal como está en el archivo ZIP. Si el mapa DITA hace referencia a ficheros de varias ubicaciones, todas esas ubicaciones se crearán también en el fichero ZIP. Al restaurar el archivo ZIP, se crea la estructura de carpetas exacta en la ubicación de destino. <br>: el valor predeterminado de este parámetro es false. |

**Devuelve**:
El contenido del ZIP se escribe en `outputStream`.

**Excepción**:
Lanza ``javax.jcr.RepositoryException``, `java.io.IOException`.

## Descargar mapa DITA con dependientes \(asincrónicamente\)

Como alternativa, se puede descargar un mapa DITA con dependientes en modo asíncrono. Este enfoque es más útil para mapas DITA más grandes.

El método `zipMapWithDependents` crea un archivo .zip que contiene un mapa DITA junto con todos sus dependientes, como temas a los que se hace referencia, submapas, imágenes y DTD. El fichero .zip para el mapa DITA se crea en función de una línea base determinada.

También permite mantener la misma estructura \(carpetas principales y secundarias\) o crear una estructura de archivos plana dentro de una sola carpeta para todos los archivos dependientes.

>[!NOTE]
>
> Este nodo se elimina automáticamente después de un tiempo en función de la configuración output.history.purgetime si se define, o 5 días como predeterminado.

**Sintaxis**:

```JAVA
public static CompletableFuture<Node> zipMapWithDependencies(Session session,
                     String sourcePath, 
                     String baseline, 
                     boolean flatFS) 
```

**Parámetros**:

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `session` | javax.jcr.Session | Una sesión JCR válida. |
| `sourcePath` | Cadena | AEM Ruta \(en el repositorio de la\) del archivo de mapa DITA que debe descargarse. |
| `baseline` | Cadena | Título de la línea de base que se utiliza para recuperar el contenido con versiones. <br> **Nota:** El valor distingue entre mayúsculas y minúsculas. |
| plainFS | Booleano | \(Opcional\) Si se establece en true, se devuelve una estructura plana de archivos en el archivo ZIP. Por ejemplo, si el mapa DITA hace referencia a contenido de varias carpetas, todos los ficheros a los que se hace referencia se extraerán en una sola carpeta. En caso de que haya archivos con el mismo nombre, se cambiará el nombre de esos archivos añadiendo un sufijo numérico. Todas las referencias \(en el mapa DITA y en los temas\) se gestionan automáticamente, ya que se actualizan en función de la nueva ubicación de los archivos en la estructura de carpetas plana. Si se establece en false, la estructura de carpetas se mantiene tal como está en el archivo ZIP. Si el mapa DITA hace referencia a ficheros de varias ubicaciones, todas esas ubicaciones se crearán también en el fichero ZIP. Al restaurar el archivo ZIP, se crea la estructura de carpetas exacta en la ubicación de destino.<br>: el valor predeterminado de este parámetro es false. |

**Devuelve**:
El nodo del archivo zip está dentro de la clase `CompletableFuture`. El usuario puede seguir manejándolo asincrónicamente y puede usar el `.get()`método del futuro para bloquear el subproceso cuando se necesite el nodo. El valor devuelto también puede terminar con un error, y eso se puede controlar con el método `.exceptionally()`.

## Obtener una lista de líneas de base

El método ``getBaselineList`` recupera una lista de todas las líneas de base que existen para un mapa DITA determinado.

**Sintaxis**:

```JAVA
public static List<HashMap<String,String>> getBaselineList( 
                  javax.jcr.Session session, 
                  String sourcePath)
                  throws javax.jcr.RepositoryException
```

**Parámetros**:

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `session` | javax.jcr.Session | Una sesión JCR válida. |
| `sourcePath` | Cadena | AEM Ruta \(en el repositorio de\) del fichero de mapa DITA para el que se va a recuperar la información de línea base. |

**Devuelve**:
Lista de `HashMap` objetos. Cada objeto `HashMap` representa una línea de base y contiene el nombre y el título de la línea de base.

**Excepción**:
Lanza ``javax.jcr.RepositoryException``.

## Obtener una lista de ajustes preestablecidos condicionales

El método ``getConditionalPresetList`` recupera una lista de todos los ajustes preestablecidos condicionales que existen para un mapa DITA determinado.

**Sintaxis**:

```JAVA
public static List<HashMap<String,String>> getConditionalPresetList (
                  javax.jcr.Session session,
                  String sourcePath)
                  throws javax.jcr.RepositoryException
```

**Parámetros**:

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `session` | javax.jcr.Session | Una sesión JCR válida. |
| `sourcePath` | Cadena | AEM Ruta \(en el repositorio de\) del fichero de mapa DITA para el que se va a recuperar la información de ajuste preestablecido condicional. |

**Devuelve**:
Lista de `HashMap` objetos. Cada objeto `HashMap` representa un ajuste preestablecido condicional y contiene el nombre y el título del ajuste preestablecido condicional.

**Excepción**:
Lanza ``javax.jcr.RepositoryException``.

## Obtenga la información del archivo DITAVAL para un ajuste preestablecido condicional

El método ``getDitavalFromConditionalPreset`` recupera la ruta del fichero DITAVAL correspondiente a un ajuste preestablecido condicional para un mapa DITA determinado.

**Sintaxis**:

```JAVA
public static String getDitavalFromConditionalPreset
    (Session session,
    String sourcePath, 
    String cpName) throws RepositoryException
```

**Parámetros**:

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `session` | javax.jcr.Session | Una sesión JCR válida. |
| `sourcePath` | Cadena | AEM Ruta \(en el repositorio de\) del fichero de mapa DITA para el que se va a recuperar el fichero DITAVAL. |
| `cpName` | Cadena | Nombre del ajuste preestablecido condicional en el mapa DITA para el que se va a recuperar el fichero DITAVAL. |

**Devuelve**:
Ruta del fichero DITAVAL correspondiente al ajuste preestablecido condicional definido en el fichero de mapa DITA.

## Obtener todas las dependencias de un nodo

El método ``getAllDependencies`` devuelve todas las dependencias de un nodo determinado.

**Sintaxis**:

```JAVA
public static List
<Node> getAllDependencies 
(Node rootNode) throws GuidesApiException
```

**Parámetros**:

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `rootNode` | javax.jcr.Node | Nodo raíz para el que se van a recuperar todas las dependencias. |

**Devuelve**:
Lista de nodos que contiene todas las dependencias del nodo raíz.
