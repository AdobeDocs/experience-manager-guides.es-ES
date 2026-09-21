---
title: Configuración de la conexión MCP para AEM Guides local
description: Obtenga información sobre cómo configurar las opciones de conexión de MCP para AEM Guides local.
meta-feature: Authoring
meta-product: Experience Manager, Experience Manager Guides
meta-role: Admin
meta-type: Documentation
source-git-commit: e234425f1e277990de25057971f3e2453c93360f
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 4%
---

# Configuración de la conexión MCP para Experience Manager Guides (local)

Las herramientas de IA como Claude, Cursor y Codex pueden conectarse a Experience Manager Guides mediante el protocolo de contexto de modelo (MCP). Puede configurar la conexión MCP y la configuración de autenticación desde la página Configuración de la consola web de Adobe Experience Manager.

Las configuraciones disponibles controlan la administración de tokens, las solicitudes sin información del referente y la URL externa para la instancia de autor de AEM.

## Configurar la administración de tokens de inicio de sesión

Para configurar la administración de tokens de inicio de sesión, realice los siguientes pasos:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```
   http://<server name>:<port>/system/console/configMgr
   ```

2. Busque y seleccione **Envoltura de token OAuth PKCE de AEM Guides**.

3. Configure las siguientes propiedades:

   | Propiedad | Predeterminado | Descripción |
   |---|---|---|
   | URL de base de Granite | `http://localhost:4502` | Especifica la dirección URL que utiliza AEM para comunicarse con la instancia de autor durante la autenticación. Cambie el puerto predeterminado 4502 solo si la instancia de autor utiliza un puerto diferente. |
   | Tiempo de espera de Granite (ms) | `5000` | Especifica el tiempo máximo, en milisegundos, para esperar a que se complete la solicitud de autenticación. |

4. Seleccione **Guardar**.

## Configuración de solicitudes sin información del referente

>[!NOTE]
>
> Esta configuración solo debe establecerse si se utiliza el cursor.

Algunos clientes de MCP, incluido Cursor, pueden enviar solicitudes sin información del referente. Para permitir estas solicitudes, configure el Filtro de referente de Apache Sling de la siguiente manera:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```
   http://<server name>:<port>/system/console/configMgr
   ```

2. Busque y seleccione **Filtro de referente de Apache Sling**.

3. En la propiedad **Permitir vacío**, establezca el valor en `true`.

   Esta configuración permite solicitudes que no contienen información de referente durante la autenticación.

4. Seleccione **Guardar**.

## Configure la URL externa para la instancia de autor

El servicio **Day CQ Link Externalizer** le permite definir de forma centralizada las direcciones URL externas que se usan para prefijar las rutas de recursos, incluida la URL de la instancia de autor de AEM.

Para configurar la URL externa, realice los siguientes pasos:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```
   http://<server name>:<port>/system/console/configMgr
   ```

2. Busque y seleccione **Externalizador de vínculos CQ de día**.

3. En **Dominios**, agregue o actualice la asignación `author` con el siguiente formato:

   ```
   author [scheme://]server[:port][/contextpath]
   ```

   Por ejemplo:

   ```
   author https://author.mycompany.com
   ```

4. Seleccione **Guardar**.