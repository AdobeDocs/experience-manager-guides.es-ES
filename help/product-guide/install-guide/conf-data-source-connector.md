---
title: Configuración de un conector de fuente de datos
description: Obtenga información sobre cómo configurar un conector de fuente de datos
exl-id: bd1188e1-0e1d-4e70-928a-10251c3d529d
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---

# Configuración de un conector de fuente de datos

AEM Guides proporciona conectores predeterminados para bases de datos JIRA y SQL (MySQL, PostgreSQL, SQL Server, SQLite). También puede añadir otros conectores ampliando las interfaces predeterminadas. La siguiente configuración le ayuda a añadir fácilmente las distintas fuentes de datos. Una vez agregados, puede ver los orígenes de datos en el Editor Web.

Realice los siguientes pasos para configurar un conector de origen de datos y, a continuación, utilizarlo desde el Editor web:

## Configuración de un conector

Puede configurar un conector listo para usar cargando un archivo JSON. Puede utilizar los siguientes archivos de instalación de ejemplo para configurar conectores para bases de datos Jira y SQL (MySQL, PostgreSQL, SQL Server, SQLite).

Un archivo de configuración de ejemplo para la autenticación básica de Jira con nombre de usuario y contraseña:

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
    "configName": "Jira",
    "templateFolders": ["/content/dam/dita-templates/konnect/jira"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
        "configData": {
            "username": "jirausername",
            "password": "jirapassword",
            "url": "https://jira.corp.adobe.com/rest/api/latest/search"
        }
    }
}
```

Por ejemplo, guarde como `jira.json`.

Archivo de configuración de ejemplo para la autenticación básica de Jira con token:

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
    "configName": "Jira",
    "templateFolders": ["/content/dam/dita-templates/konnect/jira"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
        "configData": {
            "token": "jiraauthtoken",
            "url": "https://jira.corp.adobe.com/rest/api/latest/search"
        }
    }
}
```

Por ejemplo, guarde como `jira.json`.

Archivo de configuración de muestra para la autenticación básica de Jira con el token con la palabra clave &quot;Basic&quot; presente en él:

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
    "configName": "Jira",
    "templateFolders": ["/content/dam/dita-templates/konnect/jira"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
        "configData": {
            "token": "Basic jiraauthtoken",
            "url": "https://jira.corp.adobe.com/rest/api/latest/search"
        }
    }
}
```

Por ejemplo, guarde como `jira.json`.

Archivo de instalación de ejemplo para la autenticación básica de MySql:

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.MySqlConnector",
    "configName": "MySQL",
    "templateFolders": ["/content/dam/dita-templates/konnect/sql"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
        "configData": {
            "username": "admin",
            "password": "admin",
            "driver": "com.mysql.jdbc.Driver",
            "connectionString": "jdbc:mysql://host.corp.adobe.com:3306/plm"
        }
    }
}
```

Por ejemplo, guarde como `mysql.json`.

Archivo de configuración de ejemplo para la autenticación básica de PostgreSQL:

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.PostgreSqlConnector",
    "configName": "PostgreSQL",
    "templateFolders": ["/content/dam/dita-templates/konnect/sql"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
        "configData": {
            "username": "admin",
            "password": "admin",
            "driver": "org.postgresql.Driver",
            "connectionString": "jdbc:postgresql://host:port/database"
        }
    }
}
```

Por ejemplo, guarde como `postgres.json`.

Archivo de instalación de ejemplo para la autenticación básica de MS SQL Server:

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.MsSqlServerConnector",
    "configName": "MSSQLServer",
    "templateFolders": ["/content/dam/dita-templates/konnect/sql"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
        "configData": {
            "username": "admin",
            "password": "admin",
            "driver": "com.microsoft.sqlserver.jdbc.SQLServerDriver",
            "connectionString": "jdbc:sqlserver://10.10.10.10\\SQLEXPRESS01:1433;database=TutorialDB;encrypt=false;trustServerCertificate=true"
        }
    }
}
```

Por ejemplo, guarde como `mssqlserver.json`.

Archivo de configuración de ejemplo para la autenticación básica de SQLite:

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.SqliteConnector",
    "configName": "SQLiteServer",
    "templateFolders": ["/content/dam/dita-templates/konnect/sql"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
        "configData": {
            "username": "admin",
            "password": "admin",
            "driver": "org.sqlite.JDBC",
            "connectionString": "jdbc:sqlite:sample.db"
        }
    }
}
```

Por ejemplo, guarde como `sqqlite.json`.

### Personalización de la configuración de un conector

AEM Guides permite personalizar algunos valores del archivo de configuración para satisfacer las necesidades del usuario.

| Nombre de la propiedad | Descripción |
|---|---|
| configName | El usuario puede especificar un nombre de configuración para identificar el conector |
| templateFolders | Lista de carpetas desde las que se recuperarán las plantillas |

Otros campos se personalizan según la clase de configuración seleccionada para ejecutar el conector.

## Cargue el archivo en una ubicación de AEM

Cargue el archivo en alguna ubicación de AEM Assets.

Por ejemplo, `/content/dam/jira.json`

## Crear configuración mediante la API de REST

Puede registrar la configuración mediante la API de REST. Para obtener más información, consulte la API *REST para registrar un conector de origen de datos* en la sección Referencia de la API para Adobe Experience Manager Guides.

Una vez configurado el origen de datos, el conector se muestra en el panel Fuentes de datos del Editor web. A continuación, puede conectarse al origen de datos e insertar un fragmento de contenido en los temas. Para obtener más información, vea [Insertar un fragmento de contenido de su fuente de datos](../user-guide/web-editor-content-snippet.md).
