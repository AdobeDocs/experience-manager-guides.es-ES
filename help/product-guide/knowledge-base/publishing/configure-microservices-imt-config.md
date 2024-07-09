---
title: Configuración de la publicación basada en Microservice con autenticación de OAuth para AEM Guides as a Cloud Service
description: Obtenga información sobre cómo configurar la publicación basada en microservicios con autenticación OAuth para AEM Guides.
feature: Microservice in AEM Guides
role: Admin
exl-id: db0c83c7-1ece-4010-b214-f8d806d26bc9
source-git-commit: c51a372dc44921a489219f5ac99e3ad180ccc91d
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 0%

---

# Configuración de la publicación basada en microservicios con autenticación OAuth

El microservicio de publicación le permite ejecutar grandes cargas de trabajo de publicación simultáneamente en Experience Manager Guides as a Cloud Service y aprovechar la plataforma Adobe I/O Runtime sin servidor líder del sector.

Para cada solicitud de publicación, Experience Manager Guides as a Cloud Service ejecuta un contenedor independiente que se escala horizontalmente según las solicitudes de los usuarios. Esto permite ejecutar varias solicitudes de publicación y obtener un mejor rendimiento que sus grandes servidores locales de Adobe Experience Manager.

>[!NOTE]
>
> La publicación basada en microservicios en Experience Manager Guides admite los tipos de ajustes preestablecidos de salida PDF (tanto nativos como basados en DITA-OT), HTML 5, JSON y PERSONALIZADOS.

Como el servicio de publicación en la nube está protegido por la autenticación basada en OAuth de Adobe IMS, realice los siguientes pasos para integrar sus entornos con los flujos de trabajo de autenticación seguros basados en tokens de Adobe y empiece a utilizar la solución de publicación escalable basada en la nube.


## Creación de configuraciones de IMS en Adobe Developer Console

**Función necesaria para crear las configuraciones**: administrador del sistema

Siga estos pasos para crear configuraciones de IMS en **Adobe Developer Console**:

>[!NOTE]
>
>Si ya ha creado un proyecto de OAuth para configurar las sugerencias inteligentes con tecnología de IA para la creación, puede omitir los siguientes pasos para crear el proyecto.

1. Abrir **Developer Console**: `https://developer.adobe.com/console`.

1. Cambie a la **Proyectos** desde la parte superior.

   <img src="assets/projects-tab.png" alt="pestaña proyectos" width="500">

   *Seleccione el **Proyectos**de la pestaña **Adobe Developer Console***

1. Para crear un nuevo proyecto vacío, seleccione **Proyecto vacío** desde el **Crear nuevo proyecto** desplegable.

   <img src="assets/create-new-project.png" alt="crear nuevo proyecto" width="500">

   *Cree un nuevo proyecto vacío.*

1. Seleccionar **API** desde el **Agregar al proyecto** para agregar la API de administración de E/S a su proyecto.

   <img src="assets/add-project.png" alt="agregar proyecto" width="300">

   *Seleccione un proyecto de API en la lista desplegable.*

   <img src="assets/io-management-api.png" alt="administración de io" width="500">

   *Agregue la API de administración de E/S a su proyecto.*

1. Cree una nueva credencial de OAuth y guárdela.

   <img src="assets/microservice-api-oauth.png" alt="generar par de claves" width="500">

   *Configure las credenciales de OAuth en la API.*


1. Vuelva a la **Proyectos** y seleccione **Resumen del proyecto** a la izquierda.

   <img src="assets/project-overview.png" alt="resumen del proyecto" width="500">

   *Empiece en el nuevo proyecto.*

1. Haga clic en **Descargar** en la parte superior para descargar el servicio JSON.

   <img src="assets/download-json.png" alt="descargar json" width="500">

   *Descargue los detalles del servicio JSON.*

Ha configurado los detalles de autenticación de OAuth y descargado los detalles del servicio JSON. Mantenga este archivo a mano, ya que es necesario en la siguiente sección.


## Añadir la configuración de IMS al entorno

>[!NOTE]
>
>Si ya ha creado un proyecto de OAuth para sugerencias inteligentes, puede reutilizar el mismo proyecto para microservicios y omitir los siguientes pasos para agregar la configuración de IMS al entorno.

### Actualizar configuración existente (JWT a OAuth shift )

Si ya está utilizando un microservicio para publicar con JWT (obsoleto), realice los siguientes pasos para actualizar las configuraciones:



1. Abrir **Experience Manager** y seleccione el programa que contiene el entorno que desea configurar.
1. Cambie a la **Entornos** pestaña.
1. Seleccione el nombre del entorno que desea configurar. Esto le llevará a la **Información del entorno** página.
1. Cambie a la **Configuración** pestaña.

1. Actualice el campo JSON SERVICE_ACCOUNT_DETAILS con el nuevo archivo JSON de OAuth que descargó.
1. Elimine el campo PRIVATE_KEY.



   <img src="assets/ims-service-account-config.png" alt="configuración de cuenta de servicio ims" width="500">

   *Actualice las configuraciones del entorno JWT existentes.*

### Configuración por primera vez

Para utilizar un microservicio de publicación por primera vez, actualice las configuraciones según los pasos siguientes:
1. Abrir **Experience Manager** y seleccione el programa que contiene el entorno que desea configurar.
1. Cambie a la **Entornos** pestaña.
1. Seleccione el nombre del entorno que desea configurar. Esto le llevará a la **Información del entorno** página.
1. Cambie a la **Configuración** pestaña.

1. Cree una nueva configuración denominada SERVICE_ACCOUNT_DETAILS. En el valor, agregue el contenido del archivo JSON de OAuth que descargó de la consola del desarrollador


<img src="assets/jws-service-account-config.png" alt="configuración de cuenta de servicio ims" width="500">

*Configure el entorno por primera vez.*


### Primera vez que cambia el código para la habilitación de publicaciones basadas en microservicios

>[!NOTE]
>
> Omita los siguientes pasos si ya está utilizando la publicación basada en microservicios:

Una vez añadida la configuración de IMS al entorno, realice los siguientes pasos para vincular estas propiedades con Experience Manager Guides mediante OSGi:

1. En el código de su proyecto Git de Cloud Manager, agregue los dos archivos siguientes a `/apps/fmditaCustom/config` (para ver el contenido del archivo, consulte [Apéndice](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`
1. Asegúrese de que los archivos recién agregados estén cubiertos por su `filter.xml`.
1. Confirme y envíe los cambios de Git.
1. Ejecute la canalización para aplicar los cambios al entorno.

Una vez hecho esto, puede utilizar la publicación en la nube basada en microservicios.

## Preguntas frecuentes


1. Si las configuraciones de OSGi para utilizar microservicios están habilitadas, ¿funcionará el proceso de publicación en el servidor Experience Manager local con la misma base de código?
   * No, si el indicador `dxml.use.publish.microservice` se establece en `true`, siempre busca configuraciones de microservicio. Establecer `dxml.use.publish.microservice` hasta `false` para que la publicación funcione en el servidor local.
1. ¿Cuánta memoria se asigna al proceso DITA cuando se utiliza la publicación basada en microservicios? ¿Se conduce a través del perfil y los parámetros de DITA?
   * Con la publicación basada en microservicios, la asignación de memoria no se controla mediante los parámetros y el perfil DITA. La memoria total disponible en el contenedor de servicios es de 8 GB, de los cuales 6 GB se asignan al proceso DITA-OT.


## Apéndice {#appendix}

**Archivo**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Contenido**:

```
{
"service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
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
