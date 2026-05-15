---
title: Compatibilidad con Schematron en el editor web
description: Uso de Schematron en el editor web
exl-id: 3e61432f-d81e-446e-b0ad-560f5b9fa91a
feature: Web Editor
role: User, Admin
TQID: https://experienceleague.adobe.com/gF-ylj-r-PDXduhUU-60-hiJ4UaYEdsCYTaCIyUiT0s
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 437
ht-degree: 0%

---

# Control de la calidad del contenido en el editor web

Este artículo ofrece una descripción general de las posibilidades de validación dentro del editor web de AEM Guides.
Al diseñar, el editor web aprovecha la configuración de esquema DITA en el sistema para obligar a los usuarios a crear contenido compatible con DITA. Con esto, todo el contenido almacenado en el sistema es contenido DITA estructurado, reutilizable y válido.

Más allá de la compatibilidad con las reglas DITA, el editor web también admite la validación de contenido basado en reglas de &quot;*Schematron*&quot;.

&quot;*Schematron*&quot; hace referencia a un lenguaje de validación basado en reglas que se usa para definir pruebas para un archivo XML. Puede importar los archivos de Schematron y también editarlos en el Editor Web. Con un fichero &quot;Schematron&quot; se pueden definir determinadas reglas y, a continuación, validarlas para un tema DITA o un mapa. Las reglas de Schematron pueden garantizar la coherencia de la estructura XML mediante la imposición de restricciones definidas como reglas. Estas restricciones están impulsadas por PYME que son propietarias de la calidad y coherencia del contenido.

NOTA: El editor web es compatible con ISO Schematron.


## Saber cómo funciona &quot;Schematron&quot; en el editor web

### Configuración de reglas de Schematron

Consulte la sección &quot;Compatibilidad con archivos de Schematron&quot; en la [Guía del usuario](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_User-Guide_EN.pdf#page=148)


### Aplicar reglas de validación al guardar el archivo

La configuración de Editor web permite a los usuarios avanzados configurar las reglas o archivos de Schematron que se ejecutarán cada vez que un usuario actualice el contenido. Para obtener más información, consulte la sección &quot;Validación&quot; en [Guía del usuario](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_User-Guide_EN.pdf#page=58)

![Establecer reglas a partir de la configuración del editor web](../../../assets/authoring/schematron-editorsettings-validation-tab.png)


### ¿Puede ejecutar la validación manualmente?

Sí, como autor/usuario mientras crea contenido, puede utilizar el panel Schematron en el editor web para cargar un archivo schematron y ejecutar validaciones en el archivo abierto en el editor.

Para que esto funcione, el administrador de perfiles de carpeta debe permitir que todos los usuarios agreguen archivos Schemtron en el panel Validación. Consulte la configuración del editor (captura de pantalla anterior)

![Elegir archivo de Schematron](../../../assets/authoring/schematron-rightpanel-validation-addsch.png)
![Ejecutar validación](../../../assets/authoring/schematron-rightpanel-validation-runsch.png)


### Reglas compatibles

La versión actual de AEM Guides admite la validación mediante reglas basadas en la &quot;Afirmación&quot; únicamente. (ver [recurso vs. informe](https://schematron.com/document/205.html))
Aún no se admite ninguna regla basada en &quot;Informes&quot;.


### Ejemplos y más ayuda sobre las reglas de Schematron

#### Ejemplos de uso

- Compruebe si un vínculo es externo y si tiene un ámbito &quot;externo&quot;

  ```
  <sch:pattern>
      <sch:rule context="xref[contains(@href, 'http') or contains(@href, 'https')]">
          <sch:assert test="@scope = 'external' and @format = 'html'">
              All external xref links must be with scope='external' and format='html'
          </sch:assert>
      </sch:rule>
  </sch:pattern>
  ```

- Compruebe si hay al menos una &quot;referencia de tema&quot; en un mapa o al menos una &quot;li&quot; debajo de una &quot;ul&quot;

  ```
  <sch:pattern>
      <sch:rule context="map">
          <sch:assert test="count(topicref) > 0">
              There should be atleast one topicref in map
          </sch:assert>
      </sch:rule>
  
      <sch:rule context="ul">
          <sch:assert test="count(li) > 1" >
              A list must have more than one item.
          </sch:assert>
      </sch:rule>
  </sch:pattern>
  ```

- El elemento &quot;indexterm&quot; siempre debe estar presente en un &quot;prólogo&quot;

  ```
  <sch:pattern>
      <sch:rule context="*[contains(@class, ' topic/indexterm ')]">
          <sch:assert test="ancestor::node()/local-name() = 'prolog'">
              The indexterm element should be in a prolog.
          </sch:assert>
      </sch:rule>
  </sch:pattern>
  ```

#### Recursos

- Explicación de [conceptos básicos de Schematron](https://da2022.xatapult.com/#what-is-schematron)
- Más información sobre [Reglas de afirmación en Schematron](https://www.xml.com/pub/a/2003/11/12/schematron.html#Assertions)
- [Archivo de Schematron de muestra](../../../assets/authoring/sample_schematron.sch)
