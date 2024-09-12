---
title: API basada en Java para trabajar con la generación de resultados
description: Obtenga información acerca de la API basada en Java para trabajar con la generación de resultados
exl-id: e19439df-39ec-47fd-9da5-24f51750a7e5
feature: Java-Based API Publishing
role: Developer
level: Experienced
source-git-commit: ee4eb829ebe215315b05cd1f376e934c02a73b1e
workflow-type: tm+mt
source-wordcount: '201'
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

- Paquete: ****com.adobe.fmdita.api.maps****

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
| ``sourcePath`` | Cadena | AEM Ruta \(en el repositorio de la\) del archivo de mapa DITA para el que se debe generar la salida. |
| ``outputName`` | Cadena | Nombre de los ajustes preestablecidos de salida\(s\) que se utilizarán para generar la salida. Se pueden especificar varios ajustes preestablecidos de salida utilizando un delimitador de barra vertical \(&quot;\|&quot;\), por ejemplo `aemsite\|pdfoutput`. |

**Excepción**:
Lanza ``javax.jcr.RepositoryException``, `java.io.IOException` y `java.lang.Exception`.
