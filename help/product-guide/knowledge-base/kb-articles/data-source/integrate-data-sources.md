---
title: Arquitectura de la integración de fuentes de datos externas en AEM Guides
description: Obtenga información acerca de la arquitectura de la integración de fuentes de datos externas en AEM Guides.
source-git-commit: b0cf652023770eda24ea27ff105ed6dc2cdd1f08
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 0%

---

# Integración de fuentes de datos externas

Los datos de sistemas externos se pueden integrar fácilmente en la instancia de Experience Manager Guides. La conexión a fuentes de datos externas puede mejorar considerablemente la funcionalidad y facilidad de uso del sistema de administración de contenido.


Puede conectar y recuperar datos de fuentes externas de forma eficaz mediante la integración de datos de. Con esta función, no tiene que depender del equipo de TI para obtener los datos y luego copiarlos y pegarlos manualmente o actualizar constantemente los cambios en el sistema externo.

Esta función garantiza la sincronización con el origen original y permite realizar actualizaciones armoniosas de la documentación sin depender de las operaciones manuales de copiar y pegar. También ayuda a mantener la coherencia de los datos entre Experience Manager Guides y la fuente de datos externa.

Además, después de recuperar el contenido de fuentes de datos externas, puede crearlo en formato DITA y también reutilizar el contenido integrado.


## Marco de integración de fuentes de datos

El marco de trabajo de integración de una fuente de datos incluye principalmente dos componentes principales: las fuentes de datos externas y su integración en la instancia de Experience Manager Guides.

### Fuentes de datos externas

Algunas de las fuentes de datos que se pueden conectar desde Experience Manager Guides son las siguientes:

- Bases de datos relacionales (RDBMS)
   - PostgreSQL, MySQL, Microsoft SQL Server, MariaDB y SQLite
- Bases de datos no relacionales
   - MongoDB, Apache Cassandra, Apache CouchDB y Redis
- Administración de la información del producto (PIM) / Administración del ciclo de vida del producto (PLM)
   - Pimcore, Salsify, Akeneo e Informatica
- Sistemas de gestión de productos
   - JIRA y Microsoft Azure DevOps Boards (ADO)
- Procesamiento analítico en línea (OLAP) y sistemas de Analytics

### Integración en Experience Manager Guides



Mediante el uso de un conector autenticado, los datos se transfieren desde un sistema externo y se generan en Experience Manager Guides.
![Arquitectura](assets/konnect-architecture.png)


### Integración en Experience Manager Guides

Siga estos pasos para integrar el contenido en Experience Manager Guides:

1. **Configurar el conector de origen de datos**
   - El conector de la fuente de datos sirve como interfaz para establecer la conectividad con las fuentes de datos externas. Debe configurar el conector para establecer la conexión e incluir los métodos de autenticación, como `Basic Auth` o `API key Auth`. Todos los detalles de configuración, incluida la información cifrada, se almacenan de forma segura en Adobe Experience Manager.
   - La capa de conector está diseñada para ser extensible, lo que le permite crear implementaciones para conectarse a varios sistemas que Experience Manager Guides no proporciona de forma predeterminada.
     ![Capa de conector](assets/data-source-connector-layer.jpg)
   >[!NOTE]
   >
   > Acceda al módulo de definición de Konnect e implemente la interfaz Connector para crear un conector personalizado. Más información acerca de cómo [configurar conectores de origen de datos personalizados](./conf-custom-data-source-connector.md).

1. **Personalizar las plantillas de Velocity**

   - Experience Manager Guides admite Velocity (https://velocity.apache.org/), un motor de creación de plantillas muy robusto para transformar los datos de archivos JSON en contenido DITA. Velocity ofrece la flexibilidad de navegar por estructuras JSON con cualquier nivel de anidamiento.
   - El siguiente ejemplo muestra cómo se pueden integrar plantillas de Velocity y datos procedentes de Jira para generar tablas o listas ordenadas sin esfuerzo.
      - Respuesta de Jira

        ```
        {
            "expand": "schema,names",
            "total": 5,
            "hostname": "https://jira.corp.adobe.com",
            "maxResults": "200",
            "issues": [
                {
                    "key": "DXML-12756",
                    "fields": {
                        "description": "Implement the snippet generator in External Data Source integration",
                        "summary": "Implement the snippet generator in External Data Source integration"
                    }
                },
                {
                    "key": "DXML-12755",
                    "fields": {
                        "description": "Implement the topic generator in External Data Source integration",
                        "summary": "Implement the topic generator in External Data Source integration"
                    }
                },
                {
                    "key": "DXML-12745",
                    "fields": {
                        "description": "Implement the ability to register a new connector",
                        "summary": "Implement the ability to register a new connector"
                    }
                }
            ],
            "startAt": 0
        }
        ```

      - Plantillas
        ![Motor de plantillas](assets/data-source-TemplatingEngine.png){width="800" align="left"}
      - Datos generados a partir de la misma fuente de datos pero con plantillas diferentes
        ![Datos generados](assets/data-source-templates-topics.png){width="800" align="left"}

1. **Generar contenido mediante las plantillas**
   - Puede generar el contenido a partir de las plantillas que ha creado.
   - Puede generar varios tipos de contenido:
      - Fragmento de código: contenido que se puede utilizar una vez. Puede generar los datos desde el conector en la plantilla definida y luego incrustarlos en la etiqueta deseada.
      - Tema DITA: genera varios temas para usarlos tal cual en el contenido o pueden reutilizarse como *componente reutilizable*.
      - Tema DITA + Mapa: también puede generar un mapa completo que también puede usar con el tema y, a continuación, utilizar los datos para publicarlos directamente o utilizarlos como *componente reutilizable* en otros datos.


1. **Publish usa el contenido integrado**
   - La publicación es la función OOTB de Experience Manager Guides y puede publicar directamente todos los datos generados desde el sistema externo como salida de PDF AEM o sitio de la.

>[!MORELIKETHIS]
>
> Los siguientes documentos proporcionan más detalles sobre la configuración de los conectores y su uso en la instancia.
> - [Configurar un conector de origen de datos](../../../install-guide/conf-data-source-connector-tools.md)
> - [Generar contenido mediante fragmentos o temas](../../../user-guide/web-editor-content-snippet.md)