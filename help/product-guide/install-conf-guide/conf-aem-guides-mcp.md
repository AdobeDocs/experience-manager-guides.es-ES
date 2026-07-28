---
title: Uso de MCP con Adobe Experience Manager Guides
description: Aprenda a utilizar el protocolo de contexto de modelo (MCP) con AEM Guides para trabajar con temas, mapas, líneas de base e informes a través de un asistente de IA
feature: Authoring, Publishing
role: User
source-git-commit: c724946a3426e28a1270ba01cdf2646bbf5f2a0d
workflow-type: tm+mt
source-wordcount: '974'
ht-degree: 0%

---


# Uso del servidor MCP de Adobe Experience Manager Guides

El Protocolo de contexto de modelo (MCP) es una forma estándar en la que los asistentes de IA se conectan a herramientas y datos externos, en lugar de que usted cambie el contexto para operar esas herramientas usted mismo.

El servidor MCP de Adobe Experience Manager Guides lleva esto a Experience Manager Guides. Permite a un asistente de IA habilitado para MCP, como Anthropic Claude, conectarse a su entorno de Experience Manager Guides y actuar en su nombre, bajo sus propios permisos de AEM. Una vez conectado, puede trabajar con sus mapas, temas, líneas de base e informes en Experience Manager Guides as a Cloud Service utilizando un lenguaje natural sencillo.

Este artículo explica por qué MCP es útil para Experience Manager Guides, qué cubre el servidor MCP, con qué aplicaciones funciona, cómo configurarlo y cómo utilizarlo.

## Por qué MCP para Experience Manager Guides es útil

Los equipos de documentación suelen dedicar un tiempo considerable a tareas repetitivas que requieren mucha navegación, como buscar temas en un mapa grande, comprobar estados de documentos, rastrear vínculos rotos, crear líneas de base para una versión o exportar informes. Con el servidor MCP de Experience Manager Guides, puede pedir a un asistente de IA que los gestione directamente, sin cambiar a la interfaz de usuario de Experience Manager Guides.

Por ejemplo:

- En lugar de abrir un mapa y comprobar el estado de cada tema uno a uno, pida al asistente que enumere los temas y sus estados.
- En lugar de iniciar manualmente un informe de vínculos rotos y esperar en la interfaz de usuario de Experience Manager Guides, pida al asistente que ejecute el informe y le indique cuándo ha terminado.
- En lugar de desplazarse a la pantalla de línea de base, pida al asistente que cree una línea de base para un mapa específico.

## Servidor MCP proporcionado por Experience Manager Guides

Experience Manager Guides expone sus capacidades de MCP a través de un único extremo HTTP.

| servidor MCP | Punto final | Descripción |
| --- | --- | --- |
| **Experience Manager Guides** | `https://mcp.adobeaemcloud.com/adobe/mcp/guides` | Trabaje con temas y mapas, líneas de base e informes en Experience Manager Guides. |

Este punto final cubre cuatro áreas:

- **Temas y mapas**: crea, lee, actualiza, elimina, crea versiones y bloquea temas y mapas.
- **Líneas bases**: cree, enumere, exporte, duplique, reconstruya y etiquete líneas bases.
- **Informes**: listas de temas, metadatos, vínculos rotos y uso multimedia.
- **Sistema**: versión de paquete, estado del paquete y diagnósticos de entorno.

Las herramientas exactas disponibles pueden cambiar con el tiempo. En lugar de depender de una lista fija, pídale al asistente que le muestre lo que está disponible:

```
List all Experience Manager Guides tools available from the author https://author-pXXXX-eXXXX.adobeaemcloud.com and describe what they do.
```

## Solicite acceso para su organización

El acceso al servidor MCP de Experience Manager Guides es de **inclusión por organización**. Antes de que cualquier persona de su organización pueda conectarse:

- Experience Manager Guides debe estar habilitado en el entorno de AEM as a Cloud Service.
- El equipo de guías de Adobe debe permitir el ID de organización de IMS de su organización (ID de organización).

Para solicitar acceso, póngase en contacto con el equipo de éxito del cliente de Adobe.

## Aplicaciones compatibles

El servidor MCP de Experience Manager Guides es un servidor **remoto**. Funciona con cualquier cliente MCP que admita servidores remotos, incluidos:

### Aplicaciones de chat

- Claude antrópico (web y escritorio)

### Herramientas para desarrolladores

- Cursor
- Código de Visual Studio
- Otros IDE compatibles con MCP

## Configuración

No instale nada localmente. El cliente se dirige a la dirección URL del servidor y se autentica mediante el flujo de inicio de sesión de IMS de Adobe.

### Claude antrópico

Siga el tutorial oficial: [Configurar Claude para AEM MCP](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/ai-in-aem/mcp-support/chat-applications/setup-claude). Al añadir el conector personalizado, utilice el punto final de Experience Manager Guides:

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

## Autenticación

El servidor MCP de Experience Manager Guides usa **Adobe IMS** para la autenticación.

- En la primera conexión, el cliente abre una ventana de inicio de sesión del explorador. Inicie sesión con su Adobe ID para completar la conexión.
- Después de iniciar sesión, cada acción se ejecuta con los permisos de AEM existentes. Si no tiene permiso para una acción en AEM, la misma acción falla a través de MCP.

## Uso del servidor MCP de Experience Manager Guides

Una vez conectado, describa lo que desee en lenguaje sencillo. El asistente selecciona la herramienta adecuada y rellena sus parámetros, como la ruta del mapa o el nombre de la línea de base.

>[!IMPORTANT]
>
>Las solicitudes que implican varios pasos o tardan tiempo en finalizarse, como exportaciones, compilaciones de línea de base y actualizaciones masivas, funcionan mejor con un modelo lógico. Estos se ejecutan en segundo plano: el asistente inicia el trabajo y, a continuación, comprueba su estado hasta que el resultado o un vínculo de descarga estén listos.

### Ejemplos de peticiones

Las siguientes indicaciones ilustran solicitudes típicas, cada una de las cuales activa una herramienta diferente:

1. **Comprobar estados de temas en un mapa**

   > Enumera todos los temas del mapa en `/content/dam/docs/user-guide.ditamap` y muestra sus títulos y estados de documento.

1. **Crear una línea de base**

   > Crear una línea de base estática de `/content/dam/docs/user-guide.ditamap` titulada &quot;Versión 3.2&quot;.

1. **Ejecutar un informe**

   > Ejecute el informe de vínculos rotos para la guía del usuario y deme el vínculo de descarga cuando esté listo.

## Gestión de expectativas

- **Validar el resultado**: el asistente puede cometer errores, como elegir el mapa o tema incorrecto. Revise un informe o una nueva línea de base antes de utilizarlo.
- **Mejora con el tiempo**: a medida que el asistente mejora, las tareas que reciben algunas indicaciones hoy pueden recibirlas más tarde.
- **Todavía realiza la llamada**: el asistente puede indicarle el estado de un tema o enumerar los vínculos rotos, pero decidir si el contenido está listo para publicarse sigue dependiendo del revisor o del editor.
- **Tenga cuidado con la aprobación automática**: algunos clientes de MCP, incluido Claude, le permiten aprobar automáticamente las acciones en lugar de confirmar cada una de ellas. Esto es aceptable para acciones de solo lectura, como ejecutar un informe. Para las acciones que crean, cambian o bloquean contenido, confirme cada una de ellas para que pueda revisarlas antes de que surta efecto.

Si tiene alguna pregunta sobre Experience Manager Guides MCP, póngase en contacto con el equipo de éxito del cliente de Adobe.


