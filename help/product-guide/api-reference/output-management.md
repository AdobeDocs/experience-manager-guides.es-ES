---
title: API de REST para la administración de resultados
description: Obtenga información acerca de las API de REST para Output management
exl-id: dab654f5-555d-4a89-bc94-55b1e938f255
feature: Rest API Output Management
role: Developer
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1175'
ht-degree: 0%

---

# API de REST para la administración de resultados {#id175UB30E05Z}

Las siguientes API de REST están disponibles para administrar los resultados en AEM Guides.

## Obtener todos los ajustes preestablecidos de salida para un mapa DITA {#get-output-presets-dita-map}

Método de POST que recupera todos los ajustes preestablecidos de salida configurados para un mapa DITA.

**URL de solicitud**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parámetros**:\
|Nombre|Tipo|Descripción|Requerida|
----|----|--------|-----------
|`:operation`|Cadena|Sí|Nombre de la operación a la que se llama. El valor de este parámetro es `getalloutputs`.<br> **Nota:** El valor no distingue entre mayúsculas y minúsculas.|
|`sourcePath`|Cadena|Sí|Ruta absoluta del archivo de mapa DITA.|

**Valores de respuesta**:
Devuelve una matriz de objetos JSON Output Preset, cada uno de los cuales contiene los siguientes elementos:

| Elemento | Descripción |
|-------|-----------|
| `outputName` | Nombre del ajuste preestablecido de salida. Los nombres de salida son únicos en el ámbito del mapa DITA en el que están definidos. |
| `outputType` | AEM Tipo de salida generada mediante este ajuste preestablecido, por ejemplo, sitio, PDF, EPUB u otro. Las opciones disponibles son:<br>-   AEMSITE <br>-   PDF <br>-   HTML 5 <br>-   EPUB <br>-   PERSONALIZADO |
| `outputTitle` | Un nombre descriptivo para la configuración del ajuste preestablecido de salida. Se utiliza para definir el valor de la propiedad Nombre del valor para el ajuste preestablecido de salida. |
| `ditaValPathList` | Matriz de rutas de archivo DITAVAL que se utilizarán para generar la salida deseada. |
| `targetPath` | Ruta de acceso en la que se publica o almacena el resultado. |
| `siteName` | AEM AEM *\(Para salida del sitio de la\)* Nombre del sitio de la. |
| `templatePath` | AEM *\(Para salida del sitio de la\)* Ruta de acceso del nodo de plantilla que se utilizará para generar la salida deseada. |
| `searchScope` | Especifique el ámbito de la operación de búsqueda. El valor de este parámetro debe establecerse en `local`. |
| `generateTOC` | AEM *\(Para salida del sitio de la\)* Especifique si se genera una tabla de contenido \(true\) o no \(false\). |
| `generateBreadcrumbs` | AEM *\(Para salida del sitio de la\)* Especifique si las rutas de exploración se generan \(true\) o no \(false\). |
| `overwriteStrategy` | AEM *\(Para salida del sitio de la\)* Especifique si los archivos del destino se sobrescriben \(true\) o no \(false\). |
| `pdfGenerator` | Especifique el motor de generación de PDF que desea utilizar. Los valores posibles son:<br>-   DITAOT <br>-   FMPS |

>[!NOTE]
>
> El elemento `DitaValPath` ya no es compatible.

## Crear ajuste preestablecido de salida

Método de POST que crea un nuevo ajuste preestablecido de salida para un mapa DITA.

**URL de solicitud**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parámetros**:
|Nombre|Tipo|Descripción|Requerida|
----|----|--------|-----------
|`:operation`|Cadena|Sí|Nombre de la operación a la que se llama. El valor de este parámetro es ``createoutput``.<br> **Nota:** El valor no distingue entre mayúsculas y minúsculas.|
|`sourcePath`|Cadena|Sí|Ruta absoluta del archivo de asignación DITA.|
|`outputTitle`|Cadena|Sí|Un nombre descriptivo para la configuración del ajuste preestablecido de salida. Se usa para definir el valor de la propiedad Nombre de configuración para el ajuste preestablecido de salida.<br> **Nota:** Cuando se crea un nuevo ajuste preestablecido de salida, el sistema back-end genera un nombre único para el ajuste preestablecido de salida a partir del título dado.|
|`outputType`|Cadena|Sí|Tipo de salida generada mediante este ajuste preestablecido, por ejemplo, sitio, PDF, EPUB o cualquier otro, por ejemplo, de un sitio o de otro tipo, de un AEM. Las opciones disponibles son:<br>-   AEMSITE <br>-   PDF <br>-   HTML 5 <br>-   EPUB <br>-   PERSONALIZADO|

**Valores de respuesta**:
|Elemento|Descripción|
|-------|-----------|
|`outputName`|Un nombre único para el ajuste preestablecido de salida recién creado. Este nombre se deriva del valor del parámetro `outputTitle`.|

## Guardar ajuste preestablecido de salida

Método de POST que guarda los cambios realizados en un ajuste preestablecido de salida.

**URL de solicitud**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parámetros**:
|Nombre|Tipo|Descripción|Requerida|
----|----|--------|-----------
|`:operation`|Cadena|Sí|Nombre de la operación a la que se llama. El valor de este parámetro es ``saveoutput``.<br> **Nota:** El valor no distingue entre mayúsculas y minúsculas.|
|`sourcePath`|Cadena|Sí|Ruta absoluta del archivo de asignación DITA.|
|`outputObj`|Cadena|Sí|Un objeto JSON que contiene propiedades del ajuste preestablecido de salida que se está actualizando. La propiedad `outputObj.outputName` contiene el nombre del ajuste preestablecido de salida que se va a actualizar. Para ver el formato del objeto JSON, consulte la tabla **Valores de respuesta** en [Obtener todos los ajustes preestablecidos de salida para un mapa DITA](#get-output-presets-dita-map).|

**Valores de respuesta**:
Devuelve una respuesta HTTP 200 \(Correcto\).

## Obtener un ajuste preestablecido de salida específico

Método de POST que recupera un ajuste preestablecido de salida existente.

**URL de solicitud**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parámetros**:
|Nombre|Tipo|Descripción|Requerida|
----|----|--------|-----------
|`:operation`|Cadena|Sí|Nombre de la operación a la que se llama. El valor de este parámetro es `getoutput`. <br>**Nota:** El valor no distingue entre mayúsculas y minúsculas.|
|`sourcePath`|Cadena|Sí|Ruta absoluta del archivo de asignación DITA.|
|`outputName`|Cadena|Sí|Nombre del ajuste preestablecido de salida para el que se deben recuperar los detalles.|

**Valores de respuesta**:
|Elemento|Descripción|
|-------|-----------|
|`outputName`|Nombre del ajuste preestablecido de salida. Los nombres de salida son únicos en el ámbito del mapa DITA en el que están definidos.|
AEM |`outputType`|Tipo de salida generada mediante este ajuste preestablecido, por ejemplo, sitio, PDF, EPUB o cualquier otro, de la que se puede obtener un nombre de usuario. Las opciones disponibles son:<br>-   AEMSITE <br>-   PDF <br>-   HTML 5 <br>-   EPUB <br>-   <br>| PERSONALIZADO
|`outputTitle`|Un nombre descriptivo para la configuración del ajuste preestablecido de salida. Se utiliza para definir el valor de la propiedad Nombre del valor para el ajuste preestablecido de salida.|
|`ditaValPathList`|Matriz de rutas de archivo DITAVAL que se utilizará para generar el resultado deseado.|
|`targetPath`|Ruta de acceso en la que se publica o almacena el resultado.|
AEM AEM |`siteName`|\(Para salida de sitio de la\) Nombre del sitio de la aplicación.|
AEM AEM |`siteTitle`|\(Para salida de sitio de la\) Título del sitio de la aplicación.|
AEM |`templatePath`|\(Para salida del sitio de la\) Ruta de acceso del nodo de plantilla que se utilizará para generar la salida deseada.|
|`searchScope`|Especifique el ámbito de la operación de búsqueda. El valor de este parámetro debe establecerse en `local`.|
AEM |`generateTOC`|\(Para salida de sitio de la\) Especifique si se genera una TDC \(true\) o no \(false\).|
AEM |`generateBreadcrumbs`|\(Para salida del sitio de la\) Especifique si las rutas de exploración se generan \(true\) o no \(false\).|
AEM |`overwriteFiles`|\(Para salida de sitio de la\) Especifique si los archivos del destino se sobrescriben \(true\) o no \(false\).|
|`pdfGenerator`|Especifique el motor de generación de PDF que se va a utilizar. Los valores posibles son:<br>-   DITAOT <br>-   FMPS|

>[!NOTE]
>
> El elemento `DitaValPath` ya no es compatible.

## Generar salida

Método de GET que genera resultados utilizando uno o más ajustes preestablecidos de salida.

**URL de solicitud**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parámetros**:
|Nombre|Tipo|Descripción|Requerida|
----|----|--------|-----------
|`operation`|Cadena|Sí|Nombre de la operación a la que se llama. El valor de este parámetro es `GENERATEOUTPUT`.<br> **Nota:** El valor distingue entre mayúsculas y minúsculas.|
|`source`|Cadena|Sí|Ruta absoluta del archivo de asignación DITA.|
|`outputName`|Cadena|Sí|Nombre del ajuste preestablecido de salida\(s\) que se va a utilizar para generar la salida. Se pueden especificar varios ajustes preestablecidos de salida utilizando un delimitador de barra vertical \(&quot;\|&quot;\), por ejemplo `aemsite|pdfoutput`.|

**Valores de respuesta**:
Devuelve una respuesta HTTP 200 \(Correcto\).

## Generar salida incremental

Un método de GET AEM que genera un resultado incremental para un sitio de mediante uno o más ajustes preestablecidos de salida.

**URL de solicitud**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parámetros**:
|Nombre|Tipo|Descripción|Requerida|
----|----|--------|-----------
|`operation`|Cadena|Sí|Nombre de la operación a la que se llama. El valor de este parámetro es `INCREMENTALPUBLISH`. <br>**Nota:** El valor distingue entre mayúsculas y minúsculas.|
|`contentPath`|JSON|Sí|Ruta absoluta del archivo de asignación DITA y los archivos de tema junto con el nombre de los ajustes preestablecidos de salida. Utilice el siguiente ejemplo como componente:|

```XML
{
   {   
   "ditamap": 
      "/content/dam/sample/sample.ditamap",   
   "topics": [     
      "/content/dam/sample/topic1.xml",     
      "/content/dam/sample/topic2.xml"   
         ],   
   "fullMaps": [     
      "/content/dam/sample/submap.ditamap"   
      ],   
   "maps": [     
      "/content/dam/sample/keyspace.ditamap"   
      ],   
   "outputs": [     
      "aemsite"   
      ] 
   }
}
```

- El atributo `ditamap` toma la ruta absoluta del mapa DITA que se utiliza para generar la salida.
- El atributo `topics` toma una matriz de temas que se actualizan y deben volver a publicarse.
- El atributo `fullMaps` contiene la ruta de los archivos de asignación \(como los submapas fragmentados\) que son necesarios junto con sus temas para la generación de resultados incrementales.
- El atributo `maps` contiene la ruta de acceso de los archivos de asignación \(para resolver referencias del espacio de claves\) que se extraen en el disco sin temas.
- El atributo `outputs` toma una matriz de nombres de ajustes preestablecidos de salida que se utilizan para generar el resultado.

**Valores de respuesta**:
Devuelve una respuesta HTTP 200 \(Correcto\).

## Eliminar ajuste preestablecido de salida

Método de POST que elimina un ajuste preestablecido de salida.

**URL de solicitud**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parámetros**:
|Nombre|Tipo|Descripción|Requerida|
----|----|--------|-----------
|`:operation`|Cadena|Sí|Nombre de la operación a la que se llama. El valor de este parámetro es `deleteoutput`.<br> **Nota:** El valor no distingue entre mayúsculas y minúsculas.|
|`sourcePath`|Cadena|Sí|Ruta absoluta del archivo de asignación DITA.|
|`outputName`|Cadena|Sí|Nombre del ajuste preestablecido de salida que se va a eliminar.|

**Valores de respuesta**:
Devuelve una respuesta HTTP 200 \(Correcto\).
