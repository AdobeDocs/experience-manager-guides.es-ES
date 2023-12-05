---
title: API basadas en Java para el flujo de trabajo de conversión
description: Descubra las API basadas en Java para el flujo de trabajo de conversión
exl-id: 807d9ffa-23e3-476c-992d-c1f495233892
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---

# API basadas en Java para el flujo de trabajo de conversión {#id175UB30E05Z}

Las siguientes API basadas en Java permiten convertir documentos de HTML y Word al formato DITA. Estas API están disponibles en forma de paquete. Debe incluir este paquete en su código para utilizar estas API.

**Detalles del paquete**:

- ID de grupo: **com.adobe.fmdita**

- ID del artefacto: **api**

- Versión: **3,2**

- Paquete: **com.adobe.fmdita.api.conversion**

- Detalles de la clase:

  ```JAVA
  public class ConversionUtils extends Object
  ```

  El **ConversionUtils** contiene métodos para convertir documentos de HTML y Word al formato DITA.


## Convertir documentos de HTML

El `convertHtmlToDita` convierte los documentos de HTML en formato DITA.

**Sintaxis**:

```JAVA
public static void convertHtmlToDita(Session session, 
                  String inputFile, 
                  String destPath, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parámetros**: |Nombre|Tipo|Descripción| |----|----|-----------| |`session`|javax.jcr.Session|Una sesión JCR válida.| |`inputFile`|Cadena|Ruta absoluta de los archivos del HTML AEM de origen en el repositorio de la.| |`destPath`|Cadena|Ruta absoluta de la ubicación de destino donde se guardarán los archivos DITA convertidos.| |`createRev`|Booleano|Especifique si se ha creado una revisión de los archivos \( `true`\) en el destino especificado o no \( `false`\). Esto solo se tiene en cuenta cuando la ubicación de destino contiene una versión existente de los archivos convertidos.|

**Excepción**: lanzamientos `RepositoryException`.

## Convertir documentos de Word

El ``convertWordToDita`` convierte los documentos de Word en formato DITA.

**Sintaxis**:

```JAVA
public static void convertWordToDita(Session session, 
                  String inputFile,
                  String destPath, 
                  String style2tagMap, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parámetros**: |Nombre|Tipo|Descripción| |----|----|-----------| |`session`|javax.jcr.Session|Una sesión JCR válida.| |`inputFile`AEM |Cadena|Ruta absoluta de los archivos de Word de origen en el repositorio de la.| |`destPath`|Cadena|Ruta absoluta de la ubicación de destino donde se guardarán los archivos DITA convertidos.| |`style2tagMap`|Cadena|Ruta absoluta del archivo de asignación de estilos que se utilizará para la conversión.| |`createRev`|Booleano|Especifique si se ha creado una revisión de los archivos \( `true`\) en el destino especificado o no \( `false`\). Esto solo se tiene en cuenta cuando la ubicación de destino contiene una versión existente de los archivos convertidos.|

**Excepción**: lanzamientos `RepositoryException`.
