---
title: Configuración de las sugerencias inteligentes para la creación
description: Obtenga información sobre cómo configurar las sugerencias inteligentes para la creación
source-git-commit: f0bb8e29748ab6820d772225d1689bd5ce6f4c09
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 0%

---

# Configuración de las sugerencias inteligentes para la creación

Como administrador, puede configurar la función Sugerencias inteligentes para los autores. Dado que el servicio de sugerencias inteligentes está protegido por la autenticación basada en autenticación IMS de Adobe, integre sus entornos con los flujos de trabajo de autenticación seguros basados en tokens de Adobe y empiece a utilizar la nueva solución de sugerencias inteligentes. La siguiente configuración le ayuda a agregar la pestaña de configuración de IA al perfil de carpeta. Una vez agregadas, puede utilizar la característica de sugerencias inteligentes en el Editor Web.

## Creación de configuraciones de IMS en la consola de Adobe Developer

Realice los siguientes pasos para crear configuraciones de IMS en la consola de Adobe Developer:
1. Launch [Consola de Adobe Developer](https://developer.adobe.com/console).
1. Después de iniciar sesión correctamente en Developer Console, verá el **Inicio** pantalla. El **Inicio** Esta pantalla es donde puede encontrar fácilmente información y vínculos rápidos, incluidos los vínculos de navegación superior a Proyectos y Descargas.
1. Para crear un nuevo proyecto vacío, seleccione  **Crear nuevo proyecto** desde el  **Inicio rápido** Vínculos.
   ![Vínculos de inicio rápido](assets/conf-ss-quick-start.png) {width="550" align="left"}
   *Cree un nuevo proyecto.*

1. Seleccionar  **Añadir API**  desde el  **Proyectos** pantalla.  El **Añadir una API** se muestra. Esta pantalla muestra todas las API, los eventos y los servicios disponibles para los productos y las tecnologías de Adobe con los que puede desarrollar aplicaciones.

1. Seleccione el **API de administración de E/S** para añadirlo a su proyecto.
   ![API de administración de E/S](assets/confi-ss-io-management.png)
   *Añada la API de administración de E/S a su proyecto.*

1. Crear un nuevo **Credencial de OAuth** y guárdelo.
   ![Mosaico de credenciales de OAuth en la API de configuración](assets/conf-ss-OAuth-credential.png) {width="3000" align="left"}
   *Configure las credenciales de OAuth en la API.*

1. En el  **Proyectos** pestaña, seleccione las credenciales recién creadas.

1. Seleccione el **Servidor a servidor OAuth** para ver los detalles de credenciales del proyecto.

![credenciales conectadas](assets/conf-ss-connected-credentials.png) {width="800" align="left"}
*Conéctese al proyecto para ver los detalles de las credenciales.*
1. Copie las claves CLIENT_ID y CLIENT_SECRET.

Ya ha configurado los detalles de autenticación de OAuth. Tenga estas dos teclas a mano, ya que son necesarias en la siguiente sección.

### Añadir la configuración de IMS al entorno

Siga estos pasos para agregar la configuración de IMS al entorno:

1. Abra Experience Manager y seleccione el programa que contiene el entorno que desea configurar.
1. Cambiar a **Entornos** pestaña.
1. Seleccione el nombre del entorno que desea configurar. Debe ir a la página Información del entorno.
1. Cambiar a **Configuración** pestaña.
1. Agregue las claves CLIENT_ID y CLIENT_SECRET como se muestra en la siguiente captura de pantalla. Asegúrese de utilizar los mismos nombres y configuraciones que se resaltan a continuación.
   ![Configuración del entorno](assets/conf-ss-environment.png) {width="800" align="left"}
   *Añada los detalles de configuración del entorno.*




AEM Una vez que haya agregado la configuración de IMS al entorno, realice los siguientes pasos para vincular estas propiedades con guías de usuario mediante OSGi:

1. En su código de proyecto Git de Cloud Manager, agregue los dos archivos siguientes (para ver el contenido de los archivos, consulte ) [Apéndice](#appendix).

   * `com.adobe.fmdita.ims.service.ImsOauthUserAccountHeadersImpl.cfg.json`
   * `com.adobe.fmdita.smartsuggest.service.SmartSuggestConfigurationConsumer.cfg.json`
1. Asegúrese de que los archivos recién agregados estén cubiertos por su `filter.xml`.
1. Confirme y envíe los cambios de Git.
1. Ejecute la canalización para aplicar los cambios en el entorno.

Una vez hecho esto, debería poder usar la nueva publicación en la nube basada en microservicios.



## Apéndice {#appendix}

**Archivo**:
`com.adobe.fmdita.ims.service.ImsOauthUserAccountHeadersImpl.cfg.json`

**Contenido**:

```
{
  "client.id": "$[secret:CLIENT_ID]",
  "client.secret": "$[secret:CLIENT_SECRET]",
  "ims.url": "https://ims-na1.adobelogin.com"
}
```

**Archivo**: `com.adobe.fmdita.smartsuggest.service.SmartSuggestConfigurationConsumer.cfg.json`

**Contenido**:

```
{
  "smart.suggestion.flag":true,
  "conref.inline.threshold":0.6,
  "conref.block.threshold":0.7,
  "emerald.url":"https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1",
  "instance.type":"prod"
}
```

## Detalles de configuración de sugerencias inteligentes

| Clave | Descripción | Valores permitidos |
|---|---|---|
| smart.suggestion.flag | Controla si las sugerencias inteligentes están habilitadas o no | true/false |
| conref.inline.threshold | Umbral que controla la precisión/recuperación de las sugerencias recuperadas para la etiqueta que el usuario está escribiendo actualmente. | -1,0 &lt;= x &lt;= 1,0 |
| conref.block.threshold | Umbral que controla la precisión/recuperación de las sugerencias recuperadas para las etiquetas en todo el archivo. | -1,0 &lt;= x &lt;= 1,0 |
| emerald.url | Punto final para la base de datos vectorial Emerald | [https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1](https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1) |
| instance.type | AEM Tipo de la instancia de. AEM Asegúrese de que sea único para cada instancia en la que se configure sugerencias inteligentes en. Un caso de uso sería probar la función en el entorno de ensayo con &quot;instance.type&quot; = &quot;stage&quot; mientras que al mismo tiempo, la función también se configura en &quot;prod&quot;. | Cualquier clave única que identifique el entorno &quot;dev&quot;/&quot;stage&quot;/&quot;prod&quot;/&quot;test1&quot;/&quot;stage2&quot; |

Una vez configurada, el icono de sugerencias inteligentes se muestra en el panel derecho del editor web. Puede ver la lista de sugerencias inteligentes al editar los temas. Para obtener más información, consulte [Sugerencias inteligentes basadas en IA para la creación](../user-guide/web-editor-content-snippet.md).