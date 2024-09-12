---
title: Configuración de un conector personalizado para las fuentes de datos
description: Obtenga información sobre cómo configurar un conector personalizado para las fuentes de datos.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: fdd19363c6768860ffa2f70c934b6f71c811c08b
workflow-type: tm+mt
source-wordcount: '1521'
ht-degree: 0%

---

# Configuración de conectores de fuentes de datos personalizados

Experience Manager Guides permite personalizar los conectores según sus necesidades y, a continuación, utilizarlos con las diferentes fuentes de datos. Para personalizar un conector, debe implementar la interfaz del conector y sus funciones importantes y, a continuación, configurarla. También puede proporcionar los recursos junto con los conectores personalizados.


- [Personalización de un conector para Experience Manager Guides](#customize-connector)
- [Implementación de la interfaz del conector](#implement-interface)
- [Funciones importantes](#important-functions)
- [Tipos de implementaciones de conectores predeterminados](#default-connectors)
   - [Interfaz de configuración](#config-interface)
   - [Tipos de implementaciones de configuraciones predeterminadas](#default-config-types)
   - [Implementaciones de configuración concretas](#concrete-config-implementation)
   - [Recursos adicionales](#resources)



## Personalización de un conector para Experience Manager Guides {#customize-connector}

Puede personalizar o configurar un conector para un origen de datos mediante las interfaces predefinidas y las clases abstractas. Todo el código fuente está disponible en [https://github.com/adobe/guides-data-source-connectors/tree/main/konnect-definitions](https://github.com/adobe/guides-data-source-connectors/tree/main/konnect-definitions).


Consulte [![javadoc](https://javadoc.io/badge2/com.adobe.aem.addon.guides/konnect-definitions/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem.addon.guides/konnect-definitions) para ver las definiciones de konnect.

## Implementación de la interfaz del conector {#implement-interface}

Siga estos pasos para implementar la interfaz y sus funciones según sus necesidades:

1. Defina una forma estandarizada para que los conectores se integren con un sistema, lo que permite la ejecución de consultas, la validación de conexiones y la recuperación de metadatos.
1. Facilite la integración de la interfaz de usuario al proporcionar los métodos predeterminados para configurar plantillas, logotipos, consultas y otros ajustes.
1. Asegúrese de que los conectores están validados correctamente y de que pueden controlar errores (`KonnectException`) al interactuar con orígenes de datos.

La interfaz actúa como modelo para implementar varios tipos de conectores de datos, lo que garantiza que los conectores cumplan con cualquier integración y requisitos operativos específicos dentro de un ecosistema de software más amplio.

## Funciones importantes {#important-functions}

Implemente las siguientes funciones importantes:

| Método | Obligatorio | Descripción |
|---|---|---|
| getLogoUrl |  | <ul><li> Este método devuelve la dirección URL utilizada como logotipo del conector. <li> De forma predeterminada, devuelve una cadena vacía que indica que no se proporciona ninguna dirección URL del logotipo a menos que se anule. <br><b> notas adicionales</b>: <br> <ul><li> Si proporciona una dirección URL de logotipo y un nombre de clase de logotipo, la dirección URL del logotipo se utiliza para mostrar el logotipo en la interfaz de usuario. <li> Si especifica la dirección URL del logotipo mediante los ajustes de configuración, se anula la dirección URL establecida en el método de implementación. |
| validateConnection | Sí | <ul><li> Utilice este método para validar si el conector puede establecer una conexión con su origen de datos. <li> Toma un objeto `ConfigDto` como parámetro, que contiene los valores de configuración, como credenciales de conexión y direcciones URL de extremo. <li> El método devuelve true si la validación (prueba de conexión) se realiza correctamente, lo que indica que el conector puede conectarse a su origen de datos. |
| ejecutar | sí | <ul><li>Utilice este método para ejecutar una única consulta para el conector, interactuando con un origen de datos. <li> Los conectores que admiten esta operación administran la ejecución de la consulta, analizan la respuesta y la convierten en una cadena JSON si es necesario. <li> Encapsule la consulta que se va a ejecutar en este método dentro de un objeto `QueryInfoDto`, que contiene detalles como la cadena de consulta y parámetros. <li> El método devuelve una cadena JSON que representa la respuesta de ejecutar la consulta. <br><b> notas adicionales</b>: <li>Las implementaciones de este método varían según el conector específico y su interacción con la fuente de datos. <li> Use `KonnectException` para controlar las excepciones o errores que se produzcan durante la ejecución o la conexión al origen de datos. |
| executeWithLimit | sí | <ul><li> Utilice este método para el mismo propósito que `execute()`, pero con la funcionalidad adicional de aplicar una consulta limitante, normalmente para mostrar las vistas previas en los componentes de la interfaz de usuario. <li> Los conectores que admiten esta operación administran la ejecución de la consulta, analizan la respuesta y la convierten en una cadena JSON si es necesario. <li> Encapsule la consulta que se va a ejecutar en este método dentro de un objeto `QueryInfoDto`, similar al método anterior. <br><b> notas adicionales</b>: <ul><li> `QueryResultDto` es una clase personalizada o un objeto de transferencia de datos que encapsula el resultado de la ejecución de la consulta, incluidos los metadatos sobre la consulta y su estado de ejecución. |
| getSampleQuery | | <ul><li>Este método devuelve una cadena de consulta de ejemplo que se puede mostrar en la interfaz de usuario, por ejemplo, en el cuadro de diálogo donde los usuarios pueden insertar o editar consultas. <li>De forma predeterminada, devuelve una cadena vacía que indica que no se proporciona ninguna consulta de muestra a menos que se anule. <br><b> notas adicionales</b>: <ul> <li> Si no define una consulta de ejemplo y el método devuelve una cadena vacía, no se mostrará ninguna consulta de ejemplo en el cuadro de diálogo Insertar consulta de la interfaz de usuario. |
| getTemplates | | <ul> <li> Este método devuelve una lista de plantillas asociadas al conector. <li> De forma predeterminada, devuelve una lista vacía que indica que no se proporcionan plantillas a menos que se anulen. |
| getLogoClassName | | <ul> <li> Este método devuelve el nombre de clase como logotipo del conector. De forma predeterminada, devuelve una cadena vacía que indica que no se proporciona ningún nombre de clase de logotipo a menos que se anule. <br><b> notas adicionales</b>: <ul><li> Si proporciona una dirección URL de logotipo y un nombre de clase de logotipo, la dirección URL del logotipo se utiliza para mostrar el logotipo en la interfaz de usuario. <li> Si especifica el nombre de clase del logotipo mediante las opciones de configuración, se anula el nombre de clase establecido en la implementación del método. |
| enabled | sí | <ul><li> Este método comprueba si `connector` está habilitado. <li> De forma predeterminada, el método devuelve false, lo que significa que el conector no está habilitado a menos que una clase que implemente este método lo anule. |
| getDescription | | <ul><li>Utilice este método para devolver una cadena de descripción que se pueda mostrar en la interfaz de usuario. <li> De forma predeterminada, devuelve una cadena vacía que indica que no se proporciona ninguna descripción a menos que se anule. |
| getAuthor | | <ul><li> Este método proporciona una forma de recuperar el nombre del autor que creó el conector o es responsable de él. <li> Por lo general, ayuda a identificar y reconocer al creador o mantenedor del conector dentro de un sistema o marco de trabajo. |
| getName | sí | <ul><li>Este método proporciona una forma de recuperar el nombre único asignado a un conector. <li>El nombre devuelto es crucial para identificar el conector dentro del contexto de una interfaz de usuario (IU), especialmente si la configuración del conector no especifica un nombre explícitamente. <li>Este nombre se utiliza en varios componentes de la interfaz de usuario para mostrar o administrar los conectores de una manera fácil de usar. |
| getGroup | sí | <ul> <li>Este método proporciona una forma de recuperar el nombre de grupo asociado a un conector. <li>Los nombres de grupo generalmente se utilizan para organizar o categorizar los conectores en grupos lógicos en función de su funcionalidad, propósito o tipo. <li> Esto facilita la administración y presentación de los conectores dentro de la interfaz de usuario de configuración. |
| getDefaultTemplatePath |  | <ul><li> Este método devuelve la ruta predeterminada para las plantillas asociadas con este conector. <li> De forma predeterminada, devuelve una cadena vacía que indica que no se ha establecido ninguna ruta predeterminada a menos que se anule. |
| getLogoSvg |  | <ul><li>Utilice este método para devolver la representación del SVG del logotipo del conector. <li> De forma predeterminada, devuelve una cadena vacía que indica que no se proporcionan datos del SVG a menos que se anulen. |
| getMaxNoRowsForPreviewQuery | | <ul><li>Este método devuelve el número máximo de filas consultadas o mostradas en la vista previa de la interfaz de usuario. <li> De forma predeterminada, devuelve el valor de DEFAULT_LIMIT_PREVIEW, una constante que representa el límite predeterminado de las filas de vista previa. |
| getConfigClass | sí | <ul><li>Este método proporciona información sobre las clases que implementan la interfaz Config y que admite este conector. <li> Permite a la aplicación o el marco de trabajo descubrir y trabajar dinámicamente con configuraciones compatibles con el conector. |

## Tipos de implementaciones de conectores predeterminados {#default-connectors}

La biblioteca *konnect-definitions* incluye implementaciones de conectores abstractos y funciones predefinidas para ejecutar consultas. Estas implementaciones de conectores actúan como plantillas que se pueden ampliar directamente y utilizar tal cual. Si se requiere una implementación personalizada, sus funciones se pueden anular.

Además de implementar los conectores predeterminados, también puede implementar una de las siguientes clases abstractas predeterminadas:

- Conector REST
- Conector de archivo
- Conector de GraphQL
- Conector SQL
- Conector NoSQL


Si un conector se ajusta a uno de estos tipos, extienda el conector a la clase base correspondiente. De lo contrario, créelo desde cero implementando la interfaz del conector.

## Interfaz de configuración {#config-interface}

La interfaz `Config` está diseñada para configurar un origen de datos con un método de autenticación específico, lo que le proporciona un control preciso sobre cómo crear la conexión.

La interfaz `Config` proporciona flexibilidad en la forma en que se administran e implementan los detalles de autenticación. Las distintas implementaciones pueden ofrecer varias formas de autenticar las fuentes de datos. Un conector utiliza una instancia de configuración para ejecutar y validar consultas en un origen de datos, lo que forma un flujo de trabajo completo.
Un conector utiliza una instancia de `Config` para ejecutar y validar consultas en un origen de datos, lo que forma un flujo de trabajo completo.

Una implementación de configuración define cómo se gestiona la autenticación para conectarse a una fuente de datos. A continuación, la implementación de un conector utiliza esta configuración para interactuar con la fuente de datos, lo que garantiza que las consultas se ejecuten y validen correctamente.

En general, la interfaz `Config` es una parte crucial del flujo de trabajo para conectarse a orígenes de datos, centrándose específicamente en la configuración de autenticación.

### Tipos de implementaciones de configuraciones predeterminadas {#default-config-types}

Existen tres tipos de implementaciones de configuración abstracta predeterminadas para la autenticación:

- RestConfig
- SqlConfig
- NoSqlConfig

Si una configuración se alinea con uno de estos tipos, puede ampliar la clase base correspondiente. De lo contrario, se puede crear desde cero implementando la interfaz de configuración.

### Implementaciones de configuración concretas {#concrete-config-implementation}

La biblioteca *konnect-definitions* se distribuye con implementaciones predefinidas de la interfaz de configuración para algunas configuraciones de autenticación ampliamente utilizadas. Puede utilizar estas configuraciones directamente en el conector o definir nuevas configuraciones mediante la interfaz de configuración. Estas implementaciones incluyen:

- Configuración de autenticación de clave API
- Configuración básica basada en tokens de autenticación
- Configuración de autenticación básica
- Configuración de token de portador
- Configuración de contraseña de nombre de usuario para SQL
- Configuración de autenticación de cadena de conexión para NoSQL

### Recursos adicionales{#resources}

Experience Manager Guides también le permite proporcionar recursos personalizados para logotipos y plantillas junto con la implementación. Puede mantener estos recursos en la carpeta `resources`.
Para que el conector las pueda utilizar, es obligatorio implementar estas funciones del conector:


- `getLogoSvg` - Devuelve el SVG del logotipo en forma de cadena.

- `getTemplates` - Devuelve la lista de plantillas en el formato dado.