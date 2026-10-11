---
title: Habilitar variables de contenido contextual (CCVAR) en páginas de AEM Sites generadas desde AEM Guides
description: Uso de variables de contenido contextual (CCVAR) en páginas de AEM Sites generadas desde AEM Guides
feature: Web Editor
role: User, Admin
exl-id: f9adbb3f-6c1c-4d6f-b55d-1fb45acca91a
TQID: 'https://experienceleague.adobe.com/ehW4uJQaj3XqejwquxVwFo4vFx6q7qCsVIm6MowolZE'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
subfeature_v2:
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
    internal-label: Web Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 2%
---
# Habilitar variables de contenido contextual (CCVAR) en páginas de AEM Sites generadas desde AEM Guides

Variables de contenido contextual (CCVAR) es una capacidad de ACS Commons que permite a los autores utilizar variables de contenido dinámico directamente en el texto creado. Aunque CCVAR se usa comúnmente en AEM Sites, este artículo explica cómo lograr una funcionalidad similar a través de páginas generadas a partir de contenido creado en **AEM Guides** *principalmente mediante palabras clave definidas en el mapa DITA*.


## ¿Qué son las variables de contenido contextual (CCVAR)?

CCVAR permite a los autores insertar variables dinámicas en su contenido, que se resuelven durante la ejecución en función del contexto. Por ejemplo, variables como `((page_properties.pageTitle))` pueden extraer dinámicamente el título de la página durante la representación del contenido.


## ¿Cómo se habilita la CCVAR en las páginas de AEM Sites generadas desde AEM Guides?

Teniendo en cuenta que AEM Guides se utiliza como fuente de todo el contenido (incluido AEM Sites, PDF o HTML5), para habilitar las CCVAR en páginas generadas a partir de AEM Guides, debe utilizar palabras clave para definir el nombre de la CCVAR. Para ello en Guides, defina **keywords** en su mapa DITA usando `<keydef>` elementos. Estas palabras clave pueden corresponder a valores dinámicos (o nombres de CCVAR), lo que permite hacer referencia a ellos en los temas DITA.


## Requisitos previos

Antes de continuar, asegúrese de que se cumplen los siguientes requisitos previos:

1. **AEM ACS Commons instalado**:
   - Asegúrese de que **ACS AEM Commons** esté instalado en la instancia de AEM. Esto es necesario para utilizar CCVAR.

2. **Configuración de variables de contenido contextual**:
   - Complete la configuración de **Variables de contenido contextual** en AEM con la [documentación oficial](https://adobe-consulting-services.github.io/acs-aem-commons/features/contextual-content-variables/index.html). Esto incluye lo siguiente:
     - Habilitando **agregación de propiedades**.
     - Configurando **reescritura de HTML** (si se usa la salida de HTML).
     - Configurando **reescritura de JSON** (si se usa la salida JSON).



## Pasos para habilitar CCVAR en AEM Guides

### &#x200B;1. Definición de palabras clave en el mapa DITA

- En AEM Guides, defina palabras clave utilizando `<keydef>` elementos en el mapa DITA para corresponder a la CCVAR.
- Por ejemplo:

```xml
  <keydef keys="product">
    <topicmeta>
      <keywords>
        <keyword>((page_properties.pageTitle))</keyword>
      </keywords>
    </topicmeta>
  </keydef>
```

- El atributo `keys` (`product` en este ejemplo) se utilizará para hacer referencia a esta variable en los temas DITA.


## &#x200B;2. Uso de palabras clave en temas DITA

- En el tema, utilice la palabra clave dondequiera que se vaya a utilizar la CCVar.
- Por ejemplo:

```xml
  <p>This is the title of the product: <keyword keyref="product"/> </p>
```

- El atributo `keyref` señala al valor `keys` definido en el elemento `<keydef>` (`product` en este caso).
- Durante la generación de resultados, la palabra clave se reemplaza por el valor de CCVar correspondiente.


## &#x200B;3. Generar salida

- Cuando se genera una salida para AEM Sites, las referencias de palabras clave se resuelven en los valores dinámicos correspondientes.
- Por ejemplo:
  - Si `((page_properties.pageTitle))` se resuelve en `My Product`, se mostrará el resultado:

```xml
   This is the title of the product: My Product.
```


## Ejemplo de caso de uso

Supongamos que desea insertar dinámicamente el idioma de la página en los temas DITA. A continuación se indica cómo lograrlo:

**Definir la palabra clave en el mapa DITA**:

```xml
   <keydef keys="pageLanguage">
     <topicmeta>
       <keywords>
         <keyword>((inherited_page_properties.jcr:language))</keyword>
       </keywords>
     </topicmeta>
   </keydef>
```

**Hacer referencia a la palabra clave en un tema DITA**:

```xml
   <p>The title of this page is: <keyword keyref="pageLanguage"/>.</p>
```

**Salida generada**:

Si `((inherited_page_properties.jcr:language))` se resuelve en `en`, se mostrará el resultado:

```
     The language of this page is: en.
```


### Recursos

Para obtener más información sobre **variables de contenido contextual**, consulte la documentación oficial:\
[Variables de contenido contextual en AEM Commons](https://adobe-consulting-services.github.io/acs-aem-commons/features/contextual-content-variables/index.html)
