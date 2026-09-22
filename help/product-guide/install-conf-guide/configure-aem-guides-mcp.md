---
title: Configuración de MCP para Adobe Experience Manager Guides
description: Obtenga información sobre cómo conectar un asistente de IA al servidor de MCP de Experience Manager Guides para implementaciones de Cloud Service y locales
meta-feature: Authoring
meta-product: Experience Manager, Experience Manager Guides
meta-role: User
meta-type: Documentation
source-git-commit: 6841c373b75770e8691a2cac4d56aeb368b09480
workflow-type: tm+mt
source-wordcount: '1557'
ht-degree: 1%
---

# Configuración del servidor MCP de Experience Manager Guides

Este artículo trata los detalles específicos del entorno para conectarse al servidor MCP de Experience Manager Guides. La configuración varía en función de si la instancia de Experience Manager Guides ejecuta as a Cloud Service o de forma local. Seleccione la pestaña que coincida con su entorno.

>[!BEGINTABS]

>[!TAB Cloud Service]

## Extremo del servidor MCP

Experience Manager Guides expone sus capacidades de MCP a través de un único extremo HTTP.

| servidor MCP | Punto final | Descripción |
|---|---|---|
| **Experience Manager Guides** | `https://mcp.adobeaemcloud.com/adobe/mcp/guides` | Trabaje con temas y mapas, [nuevas líneas de base](../user-guide/web-editor-baseline-v2.md) e informes en Experience Manager Guides. |

Para descubrir la lista de herramientas actual para su entorno, pregunte a su asistente:

```
List all Experience Manager Guides tools available from the author https://author-pXXXX-eXXXX.adobeaemcloud.com and describe what they do.
```

## Solicite acceso para su organización

El acceso al servidor MCP de Experience Manager Guides es de **inclusión por organización**. Antes de que cualquier persona de su organización pueda conectarse:

- Experience Manager Guides debe estar habilitado en el entorno de AEM as a Cloud Service.
- El equipo de guías de Adobe debe permitir el ID de organización de IMS de su organización (ID de organización).

Para solicitar acceso, póngase en contacto con el equipo de éxito del cliente de Adobe.

## Configuración

No instale nada localmente. El cliente se dirige a la dirección URL del servidor y se autentica mediante el flujo de inicio de sesión de IMS de Adobe.

### Claude antrópico

Siga el tutorial oficial: [Configurar Claude para AEM MCP](https://experienceleague.adobe.com/es/docs/experience-manager-cloud-service/content/ai-in-aem/mcp-support/chat-applications/setup-claude). Al añadir el conector personalizado, utilice el punto final de Experience Manager Guides:

```
https://mcp.adobeaemcloud.com/adobe/mcp/guides
```

### Cursor / código de Visual Studio

Añada el servidor a la configuración de MCP. Para el cursor, agréguelo a `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "aem-guides": {
      "url": "https://mcp.adobeaemcloud.com/adobe/mcp/guides"
    }
  }
}
```

Para los clientes que solo admiten servidores locales (stdio), vincule al extremo remoto con [`mcp-remote`](https://www.npmjs.com/package/mcp-remote):

```json
{
  "mcpServers": {
    "aem-guides": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://mcp.adobeaemcloud.com/adobe/mcp/guides"]
    }
  }
}
```

>[!TAB On-Premise]

Puede conectar clientes de IA admitidos a una instancia local de Experience Manager Guides mediante el protocolo de contexto de modelo (MCP). Una vez establecida la conexión, el cliente puede acceder a las operaciones de Experience Manager Guides disponibles en su cuenta de usuario de AEM.

Todas las operaciones se realizan con **su identidad y permisos de AEM**. El cliente conectado solo puede ver o modificar el contenido y los recursos a los que su cuenta de AEM tiene autorización para acceder.

La autenticación utiliza el flujo del código de autorización de OAuth 2.0 con clave de prueba para intercambio de código (PKCE). La autenticación con AEM se realiza al conectar un cliente por primera vez. Después de la autenticación correcta, la conexión actualiza los tokens de acceso automáticamente.

Puede conectar los siguientes clientes:

| Cliente | Método de conexión | Requisitos de instancia de AEM |
| ------------------ | ----------------------------------------- | --------------------------------------------------------------------------------------------------- |
| **Escritorio Claude** | Extensión de escritorio (`.mcpb`) | Admite extremos HTTP y HTTPS, incluidos hosts internos accesibles desde la red corporativa. |
| **ChatGPT (web y escritorio)** | Conector personalizado | Requiere un extremo HTTPS accesible públicamente con un certificado TLS válido y de confianza pública. |
| **Cursor** | Configuración de MCP en `~/.cursor/mcp.json` | Admite extremos HTTP y HTTPS, incluidos hosts internos accesibles desde la red corporativa. |

## Requisitos previos

Antes de conectar un cliente, trabaje con su administrador de AEM para comprobar la siguiente configuración:

1. **Compruebe que la característica MCP esté implementada.**: Asegúrese de que la característica MCP esté implementada y se esté ejecutando en la instancia de Experience Manager Guides.

2. **Configure la URL de base de Granite.**: En el Administrador de configuración de la consola web de AEM (`/system/console/configMgr`), busque la configuración **Envolvente de token OAuth PKCE de Experience Manager Guides** y compruebe que la URL de base de Granite esté configurada. Si la dirección URL base de Granite no está configurada correctamente, el cliente no puede establecer la conexión.

3. **Configure el Day CQ Link Externalizer.**: En el Administrador de configuración de la consola web de AEM, busque la configuración de **Day CQ Link Externalizer** y compruebe que la dirección URL del autor externo apunte a la instancia de autor de AEM correcta. La dirección URL del autor externo se utiliza durante la detección de OAuth. Una dirección URL incorrecta puede impedir que el cliente complete la conexión.

   Para obtener más información, vea [Configurar las opciones de conexión de MCP para AEM Guides local](./configure-aem-guides-mcp-on-prem.md)

4. **Obtener la URL del servidor MCP.**: La URL del servidor MCP utiliza el siguiente formato:

   ```
   http(s)://<AEM-HOST>/bin/guides/v1/mcp/sse
   ```

   >[!NOTE]
   >
   > Utilice el punto de conexión SSE completo al configurar un cliente. No agregue una barra diagonal a la dirección URL.

   Por ejemplo:

   **Instancia de autor interna de AEM:**

   ```
   http://10.42.42.20:4502/bin/guides/v1/mcp/sse
   ```

   **Instancia de autor de AEM pública:**

   ```
   https://author.example.com/bin/guides/v1/mcp/sse
   ```



5. **Compruebe sus credenciales y permisos de AEM.**: Debe tener una cuenta válida para la instancia de AEM. Utilice las mismas credenciales que utiliza para iniciar sesión en la interfaz de usuario de AEM. Las operaciones disponibles a través de MCP están determinadas por los permisos asignados a esta cuenta.

## Conectar Claude Desktop

Claude Desktop admite extensiones de escritorio (`.mcpb`). La extensión MCP de Experience Manager Guides empaqueta la configuración de conexión para que no necesite editar manualmente una configuración JSON de MCP.

1. Obtener el archivo de extensión [`aem-guides-mcp.mcpb`](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/other-packages/guides-mcp/aem-guides-mcp.zip).

2. Abra **Claude Desktop** y vaya a **Configuración > Extensiones**.

3. Instale `aem-guides-mcp.mcpb` haciendo doble clic en el archivo o arrastrándolo a la ventana Extensiones.

   **Adobe Experience Manager Guides MCP** se muestra en el cuadro de diálogo Instalación.

4. Seleccione **Instalar**.

5. En el campo **URL del servidor MCP de Experience Manager Guides**, introduzca el punto final SSE completo para la instancia de AEM.

   Por ejemplo:

   ```
   http://<AEM-HOST>:4502/bin/guides/v1/mcp/sse
   ```

6. Seleccione **Guardar** y asegúrese de que la extensión esté habilitada.

## Conectar ChatGPT

Puede configurar el servidor MCP de Experience Manager Guides como un conector personalizado en ChatGPT.

>[!IMPORTANT]
>
> ChatGPT requiere que el servidor MCP esté disponible a través de un extremo HTTPS de acceso público **con un certificado TLS válido y de confianza pública**.
>
> No se admiten los extremos HTTP, `localhost`, direcciones IP privadas y certificados autofirmados. La instancia de AEM debe exponerse a través de un host HTTPS, como un equilibrador de carga, un proxy inverso o Dispatcher configurado con TLS.
>
> La URL de autor externo configurada en **Day CQ Link Externalizer** también debe apuntar a la dirección HTTPS pública. De lo contrario, los metadatos de detección de OAuth pueden anunciar puntos de conexión de autenticación incorrectos e impedir el inicio de sesión.

1. Compruebe que el servidor MCP esté disponible en una URL HTTPS pública con el siguiente formato:

   ```
   https://<PUBLIC-AEM-HOST>/bin/guides/v1/mcp/sse
   ```

   Abra el extremo en un explorador y compruebe que puede llegar al host sin una advertencia de certificado o un error de conexión.

2. En ChatGPT, abra **Configuración > Complementos**.

   >[!NOTE]
   >
   > La disponibilidad del conector depende de su plan de ChatGPT y de la configuración del espacio de trabajo. Es posible que el administrador del espacio de trabajo tenga que habilitar conectores personalizados o de desarrollador.

3. Seleccione la opción para añadir o crear un complemento.

4. Especifique los detalles del conector:

   * **Nombre:** Escriba `Experience Manager Guides` u otro nombre descriptivo.
   * **URL del servidor MCP:** Escriba el extremo público HTTPS SSE.
   * **Autenticación:** Seleccione **OAuth**.

   No es necesario que proporcione un ID de cliente o un secreto de cliente de OAuth. El servidor MCP admite el registro automático de clientes.

5. Cree el conector.

## Cursor de conexión

Configure el servidor MCP de Experience Manager Guides en Cursor añadiendo los detalles del servidor a la configuración de MCP.

1. En el cursor, vaya a **Personalizar > MCP > Nuevo**.

   El cursor abre el archivo de configuración `~/.cursor/mcp.json`.

2. Añada la configuración del servidor MCP de Experience Manager Guides.

   Por ejemplo:

   ```json
   {
     "mcpServers": {
       "aem-guides": {
         "url": "http://10.42.34.176:4502/bin/guides/v1/mcp/sse",
         "type": "http"
       }
     }
   }
   ```

3. Reemplace la URL de ejemplo con el punto final MCP SSE para la instancia de AEM.

4. Guarde la configuración.

5. Habilite el servidor MCP configurado.

>[!ENDTABS]

## Autenticar y utilizar Experience Manager Guides

Después de configurar la conexión MCP en su cliente, autentique con su cuenta de AEM.

1. Inicie el proceso de autenticación desde el cliente.

   * **Claude Desktop:** El flujo de autenticación se inicia cuando Claude intenta usar la conexión de Experience Manager Guides por primera vez.
   * **ChatGPT:** La autenticación se inicia después de crear y conectar el conector de Experience Manager Guides.
   * **Cursor:** Habilite el servidor MCP configurado y seleccione **Autenticar**.

2. Cuando se abra la página de inicio de sesión de AEM en el explorador, inicie sesión con las credenciales de AEM.

3. Apruebe la solicitud de acceso cuando se le solicite.

4. Una vez finalizada la autenticación, vuelva al cliente.

Ahora puede utilizar las operaciones de Experience Manager Guides disponibles en su cuenta. Por ejemplo, pruebe con indicadores como:

```
List the available Experience Manager Guides operations.
```

```
Get the topic list for my map in Experience Manager Guides.
```

```
Show me the broken-link report for my map.
```

>[!NOTE]
>
> Las operaciones y el contenido disponibles a través de MCP están determinados por los permisos de la cuenta de AEM utilizada para autenticarse. La conexión MCP no proporciona privilegios de AEM adicionales.

Después de la autenticación correcta, el cliente actualiza los tokens de autenticación automáticamente. No suele ser necesario que vuelva a iniciar sesión a menos que la sesión caduque o que se revoque el acceso.

## Solucionar problemas de conexión

Utilice la siguiente información para solucionar problemas comunes de conexión y autenticación.

| Cliente | Problema | Posible causa y resolución |
| -------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Claude Desktop | La extensión no se puede instalar o está deshabilitada. | Es posible que la versión de Claude Desktop no admita la extensión. Actualice Claude Desktop e inténtelo de nuevo. |
| Claude Desktop | El explorador no se abre para la autenticación o la conexión no se completa. | Compruebe la URL del servidor MCP. Debe finalizar con `/bin/guides/v1/mcp/sse` y no debe contener una barra diagonal. Compruebe también que la instancia de AEM es accesible desde el equipo. |
| ChatGPT | ChatGPT no puede acceder al servidor MCP o no le permite agregar el conector. | Compruebe que el punto de conexión es de acceso público a través de HTTPS. No se admiten los extremos HTTP, `localhost`, direcciones IP privadas y extremos de red privada. |
| ChatGPT | Se muestra un certificado o un error de seguridad. | Compruebe que el servidor utiliza un certificado válido y no caducado emitido por una autoridad de certificación de confianza pública. No se admiten los certificados autofirmados. |
| ChatGPT | La autenticación redirige a un host incorrecto o falla durante la detección. | Compruebe que la dirección URL del autor externo en **Day CQ Link Externalizer** señala a la dirección de autor HTTPS AEM pública. |
| Todos los clientes | El registro falla durante la autenticación. | Compruebe la configuración de registro de OAuth del lado del servidor con su administrador de AEM. |
| Todos los clientes | La autenticación falla o no se completa. | Compruebe la URL de base de Granite, la configuración de Day CQ Link Externalizer, la URL del servidor MCP y la conectividad con la instancia de AEM. |
| Todos los clientes | La conexión se realiza correctamente, pero no hay operaciones ni resultados de Experience Manager Guides disponibles. | Compruebe que la cuenta de AEM autenticada tiene los permisos de Experience Manager Guides necesarios y que la operación solicitada está disponible para la cuenta. |
| Todos los clientes | El cliente solicita autenticación después de que la conexión funcionara anteriormente. | Es posible que la sesión de autenticación haya caducado o que se haya revocado el acceso. Vuelva a autenticarse con AEM. |



