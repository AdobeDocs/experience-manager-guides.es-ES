---
title: API basadas en Java para el flujo de trabajo de conversión
description: Descubra las API basadas en Java para el flujo de trabajo de conversión
exl-id: 807d9ffa-23e3-476c-992d-c1f495233892
feature: Java-Based API Conversion Workflow
role: Developer
level: Experienced
TQID: 'https://experienceleague.adobe.com/gAntb7T-OGlwRNInxAsV8orxL3H9qL19Dsjwf5FZ14I'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
    internal-label: APIs
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
subfeature_v2:
  - id: c2674c69-1bed-41fa-ba40-ab1a5382af59
    internal-label: Java Based API Conversion Workflow
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 4%
---
# API basadas en Java para el flujo de trabajo de conversión {#id175UB30E05Z}

>[!NOTE]
>
> Puede utilizar las API basadas en Java disponibles en Experience Manager Guides para crear complementos personalizados y ampliar los flujos de trabajo predeterminados. Este artículo se archivará en noviembre de 2024.
> Consulta [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) para obtener la documentación más reciente y detallada sobre el uso de la API basada en Java.




Las siguientes API basadas en Java le permiten convertir documentos de HTML y Word a formato DITA. Estas API están disponibles en forma de paquete. Debe incluir este paquete en su código para utilizar estas API.

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
| `inputFile` | Cadena | Ruta absoluta de los archivos HTML de origen en el repositorio de AEM. |
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
| `inputFile` | Cadena | Ruta absoluta de los archivos de origen de Word en el repositorio de AEM. |
| `destPath` | Cadena | Ruta absoluta de la ubicación de destino donde se guardarán los ficheros DITA convertidos. |
| `style2tagMap` | Cadena | Ruta absoluta del archivo de asignación de estilos que se utilizará para la conversión. |
| `createRev` | Booleano | Especifique si se crea una revisión de los archivos \( `true`\) en el destino especificado o no \( `false`\). Esto solo se tiene en cuenta cuando la ubicación de destino contiene una versión existente de los archivos convertidos. |

**Excepción**:
Lanza `RepositoryException`.
