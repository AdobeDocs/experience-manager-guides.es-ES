---
title: Compatibilidad con Schematron en el editor web
description: Uso de Schematron en el editor web
exl-id: 3e61432f-d81e-446e-b0ad-560f5b9fa91a
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 0%

---

# Control de la calidad del contenido en el editor web

AEM Este artículo ofrece una descripción general de las posibilidades de validación dentro del editor web de Guides de.
Al diseñar, el editor web aprovecha la configuración de esquema DITA en el sistema para obligar a los usuarios a crear contenido compatible con DITA. Con esto, todo el contenido almacenado en el sistema es contenido DITA estructurado, reutilizable y válido.

Más allá de la compatibilidad con las reglas DITA, el editor web también admite la validación de contenido en función de &quot;*Schematron*&quot; reglas.

&quot;*Schematron*&quot; hace referencia a un lenguaje de validación basado en reglas que se utiliza para definir pruebas para un archivo XML. Puede importar los archivos de Schematron y también editarlos en el Editor Web. Con un fichero &quot;Schematron&quot; se pueden definir determinadas reglas y, a continuación, validarlas para un tema DITA o un mapa. Las reglas de Schematron pueden garantizar la coherencia de la estructura XML mediante la imposición de restricciones definidas como reglas. Estas restricciones están impulsadas por PYME que son propietarias de la calidad y coherencia del contenido.

    NOTA: El editor web es compatible con ISO Schematron.


## Saber cómo funciona &quot;Schematron&quot; en el editor web

### Configuración de reglas de Schematron

Consulte la sección &quot;Compatibilidad con archivos de Schematron&quot; en la [Guía del usuario](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_User-Guide_EN.pdf#page=148)


### Aplicar reglas de validación al guardar el archivo

La configuración de Editor web permite a los usuarios avanzados configurar las reglas o archivos de Schematron que se ejecutarán cada vez que un usuario actualice el contenido. Para obtener más información, consulte la sección Validación en [Guía del usuario](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_User-Guide_EN.pdf#page=58)

![Establecer reglas a partir de la configuración del editor web](../../../assets/authoring/schematron-editorsettings-validation-tab.png)


### ¿Puede ejecutar la validación manualmente?

Sí, como autor/usuario mientras crea contenido, puede utilizar el panel Schematron en el editor web para cargar un archivo schematron y ejecutar validaciones en el archivo abierto en el editor.

    Para que esto funcione, el administrador de perfiles de carpeta debe permitir que todos los usuarios agreguen archivos Schemtron en el panel Validación. Consulte la configuración del editor (captura de pantalla anterior)

![Elegir archivo de Schematron](../../../assets/authoring/schematron-rightpanel-validation-addsch.png)
![Ejecutar validación](../../../assets/authoring/schematron-rightpanel-validation-runsch.png)


### Reglas compatibles

AEM La versión actual de las Guías de admite la validación mediante reglas basadas en la &quot;Afirmación&quot; únicamente. (consulte [recurso o informe](https://schematron.com/document/205.html)) Todavía no se admiten reglas basadas en &quot;Informes&quot;.


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

- Comprensión  [Conceptos básicos de Schematron](https://da2022.xatapult.com/#what-is-schematron)
- Más información sobre [Reglas de aserción en Schematron](https://www.xml.com/pub/a/2003/11/12/schematron.html#Assertions)
- [Archivo de Schematron de muestra](../../../assets/authoring/sample_schematron.sch)
