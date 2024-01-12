---
title: AEM Configuración de una nueva publicación basada en microservicios para guías de la aplicación de la as a Cloud Service
description: AEM Aprenda a configurar nuevas publicaciones basadas en microservicios para guías de.
exl-id: 92e3091d-6337-4dc6-9609-12b1503684cd
feature: Microservice in AEM Guides
role: User, Admin
source-git-commit: 462647f953895f1976af5383124129c3ee869fe9
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 0%

---

# AEM Configuración de una nueva publicación basada en microservicios para guías de la aplicación de la as a Cloud Service

AEM El nuevo microservicio de publicación permite a los usuarios ejecutar grandes cargas de trabajo de publicación simultáneamente en guías de publicación as a Cloud Service y aprovechar la plataforma Adobe I/O Runtime sin servidor líder del sector.

AEM Para cada solicitud de publicación, Guías de publicación ejecuta un contenedor as a Cloud Service que se adapta horizontalmente según las solicitudes de los usuarios. AEM Esto proporciona a los usuarios las funciones para ejecutar varias solicitudes de publicación y obtener un mejor rendimiento que sus grandes servidores locales de la aplicación de forma local (On-).

>[!NOTE]
>
> AEM La publicación basada en microservicios en las guías de admite los tipos de ajustes preestablecidos de salida PDF (tanto nativos como basados en DITA-OT), HTML 5, JSON y PERSONALIZADOS.

Como el nuevo servicio de publicación en la nube está protegido por la autenticación basada en JWT de Adobe IMS, los clientes deben seguir los pasos que se indican a continuación para integrar sus entornos con los flujos de trabajo de autenticación seguros basados en tokens de Adobe y comenzar a utilizar la nueva solución de publicación escalable basada en la nube.


## Creación de configuraciones de IMS en la consola de Adobe Developer

**Función necesaria para crear las confusiones**: administrador del sistema

Realice los siguientes pasos para crear configuraciones de IMS en la consola de Adobe Developer:

1. Abra Developer Console: `https://developer.adobe.com/console`.

1. Cambiar a **Proyectos** desde la parte superior.

   <img src="assets/projects-tab.png" alt="pestaña proyectos" width="500">

1. Para crear un nuevo proyecto vacío, seleccione **Proyecto vacío** desde el **Crear nuevo proyecto** desplegable.

   <img src="assets/create-new-project.png" alt="crear nuevo proyecto" width="500">

1. Seleccionar **API** desde el **Agregar al proyecto** para agregar la API de administración de E/S a su proyecto.

   <img src="assets/add-project.png" alt="agregar proyecto" width="300">

   <img src="assets/io-management-api.png" alt="administración de io" width="500">

1. Cree un nuevo par de claves pública y privada al agregar la API. Esto descargará automáticamente la clave privada en el sistema.

   <img src="assets/generate-key-pair.png" alt="generar par de claves" width="500">

1. Guarde la API configurada.

   <img src="assets/save-api.png" alt="guardar api" width="600">

1. Volver atrás a **Proyectos** y haga clic en **Resumen del proyecto** a la izquierda.

   <img src="assets/project-overview.png" alt="resumen del proyecto" width="500">

1. Clic **Descargar** en la parte superior para descargar el servicio JSON.

   <img src="assets/download-json.png" alt="descargar json" width="500">

Ahora ha configurado los detalles de autenticación JWT y también ha descargado la clave privada y los detalles del servicio JSON. Mantenga estos dos archivos a mano, ya que estos archivos son necesarios en la siguiente sección.

### Añadir la configuración de IMS al entorno

Siga estos pasos para agregar la configuración de IMS al entorno:

1. Abra Experience Manager y, a continuación, seleccione el programa que contiene el entorno que desea configurar.
1. Cambiar a **Entornos** pestaña.
1. Haga clic en el nombre del entorno que desea configurar. Debe ir a la página Información del entorno.
1. Cambiar a **Configuración** pestaña.
1. Cargue la clave privada y el JSON del proyecto como se muestra en la captura de pantalla siguiente. Asegúrese de utilizar los mismos nombres y configuraciones que se resaltan a continuación.

   <img src="assets/ims-config-environment.png" alt="configuraciones de ims" width="500">

>[!NOTE]
>
> Debe abrir, copiar y pegar el contenido de la clave privada y el archivo JSON de detalles de servicio en la columna de valor del panel Configuración, como se muestra en la captura de pantalla anterior.

AEM Una vez que haya agregado la configuración de IMS al entorno, realice los siguientes pasos para vincular estas propiedades con guías de usuario mediante OSGi:

1. En su código de proyecto Git de Cloud Manager, agregue los dos archivos siguientes (Para ver el contenido de los archivos, consulte [Apéndice](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`
1. Asegúrese de que los archivos recién agregados estén cubiertos por su `filter.xml`.
1. Confirme y envíe los cambios de Git.
1. Ejecute la canalización para aplicar los cambios en el entorno.

Una vez hecho esto, debería poder usar la nueva publicación en la nube basada en microservicios.

## Preguntas frecuentes

1. ¿Se puede utilizar una sola clave en varios entornos de nube?
   * Sí, puede generar una clave privada y utilizarla para todos los entornos, pero debe configurar variables de entorno para todos los entornos y utilizar la misma clave.
1. AEM Si las configuraciones de OSGi para utilizar microservicios están habilitadas, ¿funcionará el proceso de publicación en un servidor local con la misma base de código?
   * No, si el indicador `dxml.use.publish.microservice` se establece en `true` a continuación, siempre busca configuraciones de microservicio. Establecer `dxml.use.publish.microservice` hasta `false` para que la publicación funcione en su local.
1. ¿Cuánta memoria se asigna al proceso DITA cuando se utiliza la publicación basada en microservicios? ¿Se conduce mediante parámetros de hormiga de perfil DITA?
   * Con la publicación basada en microservicios, la asignación de memoria no se controla mediante parámetros de hormiga de perfil DITA. La memoria total disponible en el contenedor de servicios es de 8 GB, de los cuales 6 GB se asignan al proceso DITA-OT.


## Apéndice {#appendix}

**Archivo**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Contenido**:

```
{
  "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
  "private.key": "$[secret:PRIVATE_KEY]"
}
```

**Archivo**: `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`

**Contenido**:
* `dxml.use.publish.microservice`: cambie para habilitar la publicación basada en microservicios mediante DITA-OT
* `dxml.use.publish.microservice.native.pdf`: cambie para habilitar la publicación de PDF nativos basada en microservicios

```
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          jcr:primaryType="sling:OsgiConfig"
          dxml.publish.microservice.url="https://adobeioruntime.net/api/v1/web/543112-guidespublisher/default/publishercaller.json"
          dxml.use.publish.microservice="{Boolean}true"
          dxml.use.publish.microservice.native.pdf="{Boolean}true"
/>
```
