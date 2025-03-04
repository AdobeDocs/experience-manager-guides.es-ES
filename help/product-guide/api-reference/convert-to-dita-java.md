---
title: API basadas en Java para el flujo de trabajo de conversión
description: Descubra las API basadas en Java para el flujo de trabajo de conversión
exl-id: 807d9ffa-23e3-476c-992d-c1f495233892
feature: Java-Based API Conversion Workflow
role: Developer
level: Experienced
source-git-commit: 8c80a4da8e61909aab0f2db81ef97149774b36c4
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 5%

---

# API basadas en Java para el flujo de trabajo de conversión {#id175UB30E05Z}

>[!NOTE]
>
> Puede utilizar las API basadas en Java disponibles en Experience Manager Guides para crear complementos personalizados y ampliar los flujos de trabajo predeterminados. Este artículo se archivará en noviembre de 2024.
> Consulta [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) para obtener la documentación más reciente y detallada sobre el uso de la API basada en Java.




Las siguientes API basadas en Java permiten convertir documentos de HTML y Word al formato DITA. Estas API están disponibles en forma de paquete. Debe incluir este paquete en su código para utilizar estas API.

**Detalles del paquete**:

- Id. de grupo: **com.adobe.fmdita**

- ID de artefacto: **api**

- Versión: **3.2**

- Paquete: **com.adobe.fmdita.api.conversion**

- Detalles de la clase:

  ```JAVA
  public class ConversionUtils extends Object
  ```

  La clase **ConversionUtils** contiene métodos para convertir documentos de HTML y Word al formato DITA.


## Convertir documentos de HTML

El método `convertHtmlToDita` convierte los documentos de HTML al formato DITA.

**Sintaxis**:

```JAVA
public static void convertHtmlToDita(Session session, 
                  String inputFile, 
                  String destPath, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parámetros**:

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `session` | javax.jcr.Session | Una sesión JCR válida. |
| `inputFile` | Cadena | Ruta absoluta de los archivos del HTML AEM de origen en el repositorio de la. |
| `destPath` | Cadena | Ruta absoluta de la ubicación de destino donde se guardarán los ficheros DITA convertidos. |
| `createRev` | Booleano | Especifique si se crea una revisión de los archivos \( `true`\) en el destino especificado o no \( `false`\). Esto solo se tiene en cuenta cuando la ubicación de destino contiene una versión existente de los archivos convertidos. |

**Excepción**:
Lanza `RepositoryException`.

## Convertir documentos de Word

El método ``convertWordToDita`` convierte los documentos de Word al formato DITA.

**Sintaxis**:

```JAVA
public static void convertWordToDita(Session session, 
                  String inputFile,
                  String destPath, 
                  String style2tagMap, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parámetros**:

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `session` | javax.jcr.Session | Una sesión JCR válida. |
| `inputFile` | Cadena | AEM Ruta absoluta de los archivos de Word de origen en el repositorio de la. |
| `destPath` | Cadena | Ruta absoluta de la ubicación de destino donde se guardarán los ficheros DITA convertidos. |
| `style2tagMap` | Cadena | Ruta absoluta del archivo de asignación de estilos que se utilizará para la conversión. |
| `createRev` | Booleano | Especifique si se crea una revisión de los archivos \( `true`\) en el destino especificado o no \( `false`\). Esto solo se tiene en cuenta cuando la ubicación de destino contiene una versión existente de los archivos convertidos. |

**Excepción**:
Lanza `RepositoryException`.
