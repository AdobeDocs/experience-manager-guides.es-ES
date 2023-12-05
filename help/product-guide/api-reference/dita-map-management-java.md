---
title: API basadas en Java para trabajar con mapas DITA
description: Obtenga información acerca de las API basadas en Java para trabajar con mapas DITA
exl-id: bd91fc90-75f8-487c-99d1-2637e9cf9924
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 0%

---

# API basadas en Java para trabajar con mapas DITA {#id175UB30E05Z}

AEM Las siguientes API basadas en Java le permiten trabajar con mapas DITA en Guías de. Estas API están disponibles en forma de paquete. Debe incluir este paquete en su código para utilizar estas API.

Detalles del paquete:

- ID de grupo: **com.adobe.fmdita**

- ID del artefacto: **api**

- Versión: **3,2**

- Paquete: **com.adobe.fmdita.api.maps**

- Detalles de la clase:

  ```JAVA
  public class MapUtilities extends Object
  ```

  La clase MapUtilities contiene métodos para recuperar información de metadatos de un fichero de mapa DITA.


## Descargar mapa DITA con dependientes

El `zipMapWithDependents` Este método crea un fichero .zip que contiene un mapa DITA junto con todos sus dependientes, tales como temas referenciados, submapas, imágenes y DTD. El fichero .zip para el mapa DITA se crea en función de una línea base determinada.

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

**Parámetros**: |Nombre|Tipo|Descripción| |----|----|-----------| |`session`|javax.jcr.Session|Una sesión JCR válida.| |`sourcePath`AEM |Cadena|Ruta de acceso \(en el repositorio de\) del archivo de asignación DITA que debe descargarse.| |`outputStream`|java.io.OuoutputStream|Secuencia en la que se escribirá el ZIP.| |`baseline`|Cadena|Título de la línea de base que se utiliza para recuperar el contenido con versiones. <br> **Nota:** El valor distingue entre mayúsculas y minúsculas.| |plainFS|Boolean|\(Opcional\) Si se establece en true, se devuelve una estructura plana de archivos en el archivo ZIP. Por ejemplo, si el mapa DITA hace referencia a contenido de varias carpetas, todos los ficheros a los que se hace referencia se extraerán en una sola carpeta. En caso de que haya archivos con el mismo nombre, se cambiará el nombre de esos archivos añadiendo un sufijo numérico. Todas las referencias \(en el mapa DITA y en los temas\) se gestionan automáticamente, ya que se actualizan en función de la nueva ubicación de los archivos en la estructura de carpetas plana. Si se establece en false, la estructura de carpetas se mantiene tal como está en el archivo ZIP. Si el mapa DITA hace referencia a ficheros de varias ubicaciones, todas esas ubicaciones se crearán también en el fichero ZIP. Al restaurar el archivo ZIP, se crea la estructura de carpetas exacta en la ubicación de destino. <br> El valor predeterminado de este parámetro es false.|

**Devuelve**: el contenido del ZIP se escribe en `outputStream`.

**Excepción**: lanzamientos ``javax.jcr.RepositoryException``, `java.io.IOException`.

## Descargar mapa DITA con dependientes \(asincrónicamente\)

Como alternativa, se puede descargar un mapa DITA con dependientes en modo asíncrono. Este enfoque es más útil para mapas DITA más grandes.

El `zipMapWithDependents` Este método crea un fichero .zip que contiene un mapa DITA junto con todos sus dependientes, tales como temas referenciados, submapas, imágenes y DTD. El fichero .zip para el mapa DITA se crea en función de una línea base determinada.

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

**Parámetros**: |Nombre|Tipo|Descripción| |----|----|-----------| |`session`|javax.jcr.Session|Una sesión JCR válida.| |`sourcePath`AEM |Cadena|Ruta de acceso \(en el repositorio de\) del archivo de asignación DITA que debe descargarse.| |`baseline`|Cadena|Título de la línea de base que se utiliza para recuperar el contenido con versiones. <br> **Nota:** El valor distingue entre mayúsculas y minúsculas.| |plainFS|Boolean|\(Opcional\) Si se establece en true, se devuelve una estructura plana de archivos en el archivo ZIP. Por ejemplo, si el mapa DITA hace referencia a contenido de varias carpetas, todos los ficheros a los que se hace referencia se extraerán en una sola carpeta. En caso de que haya archivos con el mismo nombre, se cambiará el nombre de esos archivos añadiendo un sufijo numérico. Todas las referencias \(en el mapa DITA y en los temas\) se gestionan automáticamente, ya que se actualizan en función de la nueva ubicación de los archivos en la estructura de carpetas plana. Si se establece en false, la estructura de carpetas se mantiene tal como está en el archivo ZIP. Si el mapa DITA hace referencia a ficheros de varias ubicaciones, todas esas ubicaciones se crearán también en el fichero ZIP. Al restaurar el archivo ZIP, se crea la estructura de carpetas exacta en la ubicación de destino.<br> El valor predeterminado de este parámetro es false.|

**Devuelve**: El nodo del archivo zip se ajusta en la variable `CompletableFuture`clase. El usuario puede seguir gestionándolo de forma asíncrona y puede utilizar `.get()`del futuro para bloquear el subproceso cuando se necesite el nodo. El valor devuelto también puede terminar con un error, que se puede controlar con `.exceptionally()` método.

## Obtener una lista de líneas de base

El ``getBaselineList`` El método recupera una lista de todas las líneas base que existen para un mapa DITA determinado.

**Sintaxis**:

```JAVA
public static List<HashMap<String,String>> getBaselineList( 
                  javax.jcr.Session session, 
                  String sourcePath)
                  throws javax.jcr.RepositoryException
```

**Parámetros**: |Nombre|Tipo|Descripción| |----|----|-----------| |`session`|javax.jcr.Session|Una sesión JCR válida.| |`sourcePath`AEM |Cadena|Ruta de acceso \(en el repositorio de\) del archivo de asignación DITA para el que se va a recuperar la información de línea de base.|

**Devuelve**: una lista de `HashMap` objetos. Cada `HashMap` representa una línea base y contiene el nombre y título de la línea base.

**Excepción**: lanzamientos ``javax.jcr.RepositoryException``.

## Obtener una lista de ajustes preestablecidos condicionales

El ``getConditionalPresetList`` Este método recupera una lista de todos los ajustes preestablecidos condicionales que existen para un mapa DITA determinado.

**Sintaxis**:

```JAVA
public static List<HashMap<String,String>> getConditionalPresetList (
                  javax.jcr.Session session,
                  String sourcePath)
                  throws javax.jcr.RepositoryException
```

**Parámetros**: |Nombre|Tipo|Descripción| |----|----|-----------| |`session`|javax.jcr.Session|Una sesión JCR válida.| |`sourcePath`AEM |Cadena|Ruta de acceso \(en el repositorio de\) del archivo de asignación DITA para el que se va a recuperar la información de ajuste preestablecido condicional.|

**Devuelve**: una lista de `HashMap` objetos. Cada `HashMap` representa un ajuste preestablecido condicional y contiene el nombre y el título del ajuste preestablecido condicional.

**Excepción**: lanzamientos ``javax.jcr.RepositoryException``.

## Obtenga la información del archivo DITAVAL para un ajuste preestablecido condicional

El ``getDitavalFromConditionalPreset`` Este método recupera la ruta del fichero DITAVAL correspondiente a un ajuste preestablecido condicional para un mapa DITA determinado.

**Sintaxis**:

```JAVA
public static String getDitavalFromConditionalPreset
    (Session session,
    String sourcePath, 
    String cpName) throws RepositoryException
```

**Parámetros**: |Nombre|Tipo|Descripción| |----|----|-----------| |`session`|javax.jcr.Session|Una sesión JCR válida.| |`sourcePath`AEM |Cadena|Ruta de acceso \(en el repositorio de\) del archivo de asignación DITA para el que se va a recuperar el archivo DITAVAL.| |`cpName`|Cadena|Nombre del ajuste preestablecido condicional en el mapa DITA para el que se va a recuperar el archivo DITAVAL.|

**Devuelve**: Ruta del fichero DITAVAL correspondiente al ajuste preestablecido condicional definido en el fichero de mapa DITA.

## Obtener todas las dependencias de un nodo

El ``getAllDependencies`` El método devuelve todas las dependencias de un nodo determinado.

**Sintaxis**:

```JAVA
public static List
<Node> getAllDependencies 
(Node rootNode) throws GuidesApiException
```

**Parámetros**: |Nombre|Tipo|Descripción| |----|----|-----------| |`rootNode`|javax.jcr.Node|Nodo raíz para el que se van a recuperar todas las dependencias.|

**Devuelve**: una lista de nodos que contiene todas las dependencias del nodo raíz.
