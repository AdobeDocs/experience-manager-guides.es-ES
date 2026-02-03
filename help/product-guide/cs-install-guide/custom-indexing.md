---
title: Implementación de indexación personalizada
description: Aprenda a personalizar el contenido del índice
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 7d2d0c21001cd53244588f6b700db184a73ffa77
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 3%

---

# Implementación del índice personalizado para la función Buscar y reemplazar (vista Source)

## Información general

Esta guía proporciona instrucciones paso a paso para implementar el índice personalizado `guidesAssetLucene‑1‑custom‑1` en Adobe Experience Manager (AEM) as a Cloud Service. Aunque la función estándar Buscar y reemplazar de la vista Autor funciona sin este índice, el índice personalizado es necesario específicamente para habilitar Buscar y reemplazar en la vista de Source. Buscar y reemplazar (vista de Source) permite buscar no solo el contenido creado visible, sino también la estructura XML subyacente; incluidos elementos, etiquetas y valores de atributos.

## Requisitos previos

Antes de continuar con la implementación del índice, asegúrese de lo siguiente:

- **Entorno de AEM as a Cloud Service** con AEM Guides instalado
- **Acceso a la base de código de su proyecto** (repositorio Git)
- **Acceso a Cloud Manager** con permisos de implementación

## Definición de índice

Para habilitar la característica Buscar y reemplazar (vista de Source), debe implementar un índice personalizado denominado **`guidesAssetLucene-1-custom-1`** en el entorno de AEM Cloud Service.

### Nombre del índice

```
guidesAssetLucene-1-custom-1
```

### Definición de índice (.content.xml)

Cree la siguiente definición de índice en su proyecto en:

`ui.apps/src/main/content/jcr_root/_oak_index/guidesAssetLucene-1-custom-1/.content.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:dam="http://www.day.com/dam/1.0"
          xmlns:nt="http://www.jcp.org/jcr/nt/1.0" xmlns:oak="http://jackrabbit.apache.org/oak/ns/1.0"
          xmlns:rep="internal"
          jcr:mixinTypes="[rep:AccessControllable]"
          jcr:primaryType="oak:QueryIndexDefinition"
          async="[async,nrt]"
          compatVersion="{Long}2"
          evaluatePathRestrictions="{Boolean}true"
          includedPaths="[/content/dam]"
          reindex="{Boolean}false"
          reindexCount="{Long}1"
          seed="{Long}958982603885135223"
          selectionPolicy="tag"
          tags="[ditaSearch]"
          type="lucene">

    <aggregates jcr:primaryType="nt:unstructured">
        <dam:Asset jcr:primaryType="nt:unstructured">
            <include0
                    jcr:primaryType="nt:unstructured"
                    path="jcr:content/renditions/original/jcr:content"
                    relativeNode="{Boolean}true"/>
        </dam:Asset>
    </aggregates>

    <analyzers jcr:primaryType="nt:unstructured">
        <default jcr:primaryType="nt:unstructured">
            <tokenizer
                    jcr:primaryType="nt:unstructured"
                    name="Whitespace"/>
        </default>
    </analyzers>

    <indexRules jcr:primaryType="nt:unstructured">
        <dam:Asset
                jcr:primaryType="nt:unstructured"
                indexNodeName="{Boolean}true">
            <properties jcr:primaryType="nt:unstructured">
                <cqTags
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/cq:tags"
                        nodeScopeIndex="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        useInSpellcheck="{Boolean}true"
                        useInSuggest="{Boolean}true"/>
                <jcrLastModified
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/jcr:lastModified"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        type="Date"/>
                <jcrCreated
                        jcr:primaryType="nt:unstructured"
                        name="jcr:created"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        type="Date"/>
                <guidesParentMaps
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/guidesParentMaps"
                        propertyIndex="{Boolean}true"/>
                <guidesDirectParentMaps
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/guidesDirectParentMaps"
                        propertyIndex="{Boolean}true"/>
                <ditaClass
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/dita_class"
                        propertyIndex="{Boolean}true"/>
                <nodeNameLowerCase
                        jcr:primaryType="nt:unstructured"
                        function="fn:lower-case(fn:name())"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"/>
                <cqDriveLock
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/cq:driveLock"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <docState
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/docstate"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <jcrPath
                        jcr:primaryType="nt:unstructured"
                        function="fn:path()"
                        ordered="{Boolean}true"/>
                <dcTitleLowerCase
                        jcr:primaryType="nt:unstructured"
                        function="fn:lower-case(jcr:first(jcr:content/metadata/@dc:title))"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <dcTitle
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/dc:title"
                        propertyIndex="{Boolean}true"/>
            </properties>
        </dam:Asset>
    </indexRules>

    <tika jcr:primaryType="nt:unstructured">
        <mimeTypes jcr:primaryType="nt:unstructured">
            <application jcr:primaryType="nt:unstructured">
                <xml
                        jcr:primaryType="nt:unstructured"
                        mappedType="application/dita+xml"/>
            </application>
            <text jcr:primaryType="nt:unstructured">
                <markdown
                        jcr:primaryType="nt:unstructured"
                        mappedType="text/markdown+source"/>
            </text>
        </mimeTypes>
    </tika>
</jcr:root>
```

## Pasos de implementación

Para obtener instrucciones detalladas sobre la implementación de índices personalizados en AEM as a Cloud Service, vea [Búsqueda e indexación de contenido: AEM as a Cloud Service](https://experienceleague.adobe.com/es/docs/experience-manager-cloud-service/content/operations/indexing).

### Puntos importantes para este índice

Cuando siga la guía de implementación, utilice los siguientes detalles específicos para el índice Buscar y reemplazar:

- **Nombre de índice**: `guidesAssetLucene-1-custom-1`
- **Tipo de índice**: índice totalmente personalizado (no una personalización del índice OOTB)
- **Ubicación**: `ui.apps/src/main/content/jcr_root/_oak_index/guidesAssetLucene-1-custom-1/.content.xml`
- **Se requieren propiedades del paquete**:
   - `noIntermediateSaves=true`
   - `allowIndexDefinitions=true`

## Reindexación

AEM as a Cloud Service administra la reindexación **automáticamente** al implementar el índice a través de la canalización de CD/CI de Cloud Manager.

La indexación suele gestionarse automáticamente. Sin embargo, si no se puede buscar en los datos antiguos incluso después de una implementación correcta y de la finalización del proceso de indexación, se debe realizar una vez un reindexado manual del índice.

### Qué esperar

- El trabajo de indexación se iniciará automáticamente después de la implementación.
- Puede monitorizar el progreso en la página de compilación de Cloud Manager.
- El entorno sigue funcionando a pleno rendimiento durante la indexación.

## de verificación

Después de la implementación y la finalización de la indexación, compruebe que el índice funciona correctamente.

### Verificar implementación del índice

En su entorno de desarrollo (si CRXDE Lite está disponible):

1. Navegue hasta `/oak:index/guidesAssetLucene-1-custom-1`.
2. Compruebe que el nodo existe con la configuración esperada.

### Comprobación de la función Buscar y reemplazar

La verificación principal consiste en probar la función:

1. Abra AEM Guides.
2. Vaya a **Herramientas** > **Guías** > **Buscar y reemplazar en el repositorio**.
3. Configure una búsqueda de texto en los ficheros DITA o Markdown.
4. Compruebe que los resultados de la búsqueda se devuelven correctamente.
5. Pruebe la funcionalidad de reemplazo en un archivo de prueba.

## Recursos adicionales

- [Documentación de indexación de AEM as a Cloud Service](https://experienceleague.adobe.com/es/docs/experience-manager-cloud-service/content/operations/indexing)
- [Guía de indexación de Apache Jackrabbit Oak](https://jackrabbit.apache.org/oak/docs/query/indexing.html)
- [Documentación de AEM Guides](https://experienceleague.adobe.com/es/docs/experience-manager-guides)
- [Documentación de Cloud Manager](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager)
