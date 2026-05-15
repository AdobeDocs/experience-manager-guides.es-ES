---
title: API basada en Java para trabajar con la generación de resultados
description: Obtenga información acerca de la API basada en Java para trabajar con la generación de resultados
exl-id: e19439df-39ec-47fd-9da5-24f51750a7e5
feature: Java-Based API Publishing
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/i5mTM1VtBg3QFUa-sBmF2pH8BITRn9j-efw2dr8VwCU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 225
ht-degree: 2%

---

# API basada en Java para trabajar con la generación de resultados {#id175UB30E05Z}

>[!NOTE]
>
> Puede utilizar las API basadas en Java disponibles en Experience Manager Guides para crear complementos personalizados y ampliar los flujos de trabajo predeterminados. Este artículo se archivará en noviembre de 2024.
> Consulta [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) para obtener la documentación más reciente y detallada sobre el uso de la API basada en Java.

La siguiente API basada en Java permite generar resultados para un mapa DITA. Esta API está disponible en forma de paquete. Debe incluir este paquete en su código para utilizar estas API.

Detalles del paquete:

- Id. de grupo: **com.adobe.fmdita**

- ID de artefacto: **api**

- Versión: **3.4**

- Paquete: **&#x200B;**&#x200B;com.adobe.fmdita.api.maps&#x200B;**&#x200B;**

- Detalles de la clase:

  ```JAVA
  public class **PublishUtils** extends Object
  ```

  La clase **`PublishUtils`** contiene un método para generar resultados para uno o varios ajustes preestablecidos de salida.


## Generar salida

El método ``generateOutput`` genera resultados para un archivo de mapa DITA utilizando los ajustes preestablecidos de salida especificados.

**Sintaxis**:

```JAVA
public static void generateOutput(Session session,
String sourcePath,
String outputName)
throws GuidesApiException
```

**Parámetros**:

| Nombre | Tipo | Descripción |
|----|----|-----------|
| `session` | javax.jcr.Session | Una sesión JCR válida. |
| ``sourcePath`` | Cadena | Ruta \(en el repositorio de AEM\) del archivo de mapa DITA para el que se debe generar la salida. |
| ``outputName`` | Cadena | Nombre de los ajustes preestablecidos de salida\(s\) que se utilizarán para generar la salida. Se pueden especificar varios ajustes preestablecidos de salida utilizando un delimitador de barra vertical \(&quot;\|&quot;\), por ejemplo `aemsite\|pdfoutput`. |

**Excepción**:
Lanza ``javax.jcr.RepositoryException``, `java.io.IOException` y `java.lang.Exception`.
