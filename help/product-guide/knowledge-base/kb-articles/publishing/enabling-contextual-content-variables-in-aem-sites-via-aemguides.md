---
title: Activación de variables de contenido contextual (CCVAR) en AEM Sites mediante AEM Guides
description: Uso de variables de contenido contextual (CCVAR) en AEM Sites mediante AEM Guides
exl-id: null
feature: Web Editor
role: User, Admin
source-git-commit: ac40ab63b691ea31dfa1a3c9f7644b357b3167a4
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 2%

---

# Activación de variables de contenido contextual (CCVAR) en AEM Sites mediante AEM Guides

Variables de contenido contextual (CCVAR) es una capacidad de ACS Commons que permite a los autores utilizar variables de contenido dinámico directamente en el texto creado. Aunque CCVAR se usa comúnmente en AEM Sites, este artículo explica cómo lograr una funcionalidad similar a través de páginas generadas a partir de contenido creado en **AEM Guides** *principalmente mediante palabras clave definidas en el mapa DITA*.


## ¿Qué son las variables de contenido contextual (CCVAR)?

CCVAR permite a los autores insertar variables dinámicas en su contenido, que se resuelven durante la ejecución en función del contexto. Por ejemplo, variables como `((page_properties.pageTitle))` pueden extraer dinámicamente el título de la página durante la representación del contenido.


## ¿Cómo se habilita CCVAR en AEM Sites generado desde AEM Guides?

Teniendo en cuenta que AEM Guides se utiliza como fuente de todo el contenido (incluido AEM Sites, PDF o HTML5), para habilitar las CCVAR en páginas generadas a partir de AEM Guides, debe utilizar palabras clave para definir el nombre de la CCVAR. Para ello en Guides, defina **keywords** en su mapa DITA usando `<keydef>` elementos. Estas palabras clave pueden corresponder a valores dinámicos (o nombres de CCVAR), lo que permite hacer referencia a ellos en los temas DITA.


## Requisitos previos

Antes de continuar, asegúrese de que se cumplen los siguientes requisitos previos:

1. AEM **Se instaló ACS Commons de forma conjunta**:
   - AEM AEM Asegúrese de que **ACS Commons** esté instalado en la instancia de la instancia de la. Esto es necesario para utilizar CCVAR.

2. **Configuración de variables de contenido contextual**:
   - AEM Complete la configuración de **Variables de contenido contextuales** en el uso de la [documentación oficial](https://adobe-consulting-services.github.io/acs-aem-commons/features/contextual-content-variables/index.html) en el. Esto incluye:
      - Habilitando **agregación de propiedades**.
      - Configurando **reescritura de HTML** (si se usa la salida de HTML).
      - Configurando **reescritura de JSON** (si se usa la salida JSON).



## Pasos para habilitar CCVAR en AEM Guides

### 1. Definir palabras clave en el mapa DITA

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


## 2. Usar palabras clave en temas DITA

- En el tema, utilice la palabra clave dondequiera que se vaya a utilizar la CCVar.
- Por ejemplo:

```xml
  <p>This is the title of the product: <keyword keyref="product"/> </p>
```

- El atributo `keyref` señala al valor `keys` definido en el elemento `<keydef>` (`product` en este caso).
- Durante la generación de resultados, la palabra clave se reemplaza por el valor de CCVar correspondiente.


## 3. Generar salida

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
AEM [Variables de contenido contextual en Commons de la comunidad de la comunidad de la comunidad de datos](https://adobe-consulting-services.github.io/acs-aem-commons/features/contextual-content-variables/index.html)