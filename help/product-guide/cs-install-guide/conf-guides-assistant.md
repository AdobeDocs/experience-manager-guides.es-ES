---
title: Configuración del asistente de guías para buscar contenido
description: Aprenda a configurar el Asistente para guías para buscar contenido
source-git-commit: 8ac0ed6b867a3efdef750cb19ed4955a67def9ee
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 0%

---


# Configuración del Asistente para guías con tecnología de IA para buscar contenido

Como administrador, puede configurar la función Ayudante de guías para los autores. El servicio Guides Assistant está protegido por la autenticación basada en autenticación IMS de Adobe. Integre su entorno con los flujos de trabajo de autenticación seguros basados en tokens de Adobe y comience a utilizar la nueva función Asistente para guías. Las siguientes configuraciones le ayudan a agregar lo siguiente **Configuración de IA** a un perfil de carpeta. Una vez agregado, puede utilizar la función Asistente para guías en el Editor Web.

## Creación de configuraciones de IMS en la consola de Adobe Developer

Realice los siguientes pasos para crear configuraciones de IMS en la consola de Adobe Developer:

>[!NOTE]
>
>Si ya ha creado un proyecto de OAuth para configurar la función de sugerencias inteligentes o la publicación basada en microservicios, puede omitir los siguientes pasos para crear el proyecto.

1. Launch [Consola de Adobe Developer](https://developer.adobe.com/console).
1. Después de iniciar sesión correctamente en Developer Console, verá el **Inicio** pantalla. El **Inicio** Esta pantalla es donde puede encontrar fácilmente información y vínculos rápidos, incluidos los vínculos de navegación superior a Proyectos y Descargas.
1. Para crear un nuevo proyecto vacío, seleccione **Crear nuevo proyecto** desde el **Inicio rápido** Vínculos.
   ![Vínculos de inicio rápido](assets/conf-ss-quick-start.png) {width="550" align="left"}
   *Cree un nuevo proyecto.*

1. Seleccionar **Añadir API** desde el **Proyectos** pantalla.  El **Añadir una API** aparece la pantalla. Esta pantalla muestra todas las API, los eventos y los servicios disponibles para los productos y las tecnologías de Adobe con los que puede desarrollar aplicaciones.

1. Seleccione el **API de administración de E/S** para añadirlo a su proyecto.
   ![API de administración de E/S](assets/confi-ss-io-management.png)
   *Agregue la API de administración de E/S a su proyecto.*

1. Crear un nuevo **Credencial de OAuth** y guárdelo.
   ![Mosaico de credenciales de OAuth en la API de configuración](assets/conf-ss-OAuth-credential.png) {width="3000" align="left"}
   *Configure las credenciales de OAuth en la API.*

1. En el  **Proyectos** , seleccione la pestaña **Servidor OAuth a servidor** y, a continuación, seleccione las credenciales recién creadas.

1. Seleccione el **Servidor a servidor OAuth** para ver los detalles de credenciales del proyecto.

   ![credenciales conectadas](assets/conf-ss-connected-credentials.png) {width="800" align="left"}

   *Conéctese al proyecto para ver los detalles de las credenciales.*

1. Vuelva a la **Proyectos** y seleccione **Resumen del proyecto** a la izquierda.

   <img src="assets/project-overview.png" alt="resumen del proyecto" width="500">

   *Empiece en el nuevo proyecto.*

1. Haga clic en **Descargar** en la parte superior para descargar el servicio JSON.

   <img src="assets/download-json.png" alt="descargar json" width="500">

   *Descargue los detalles del servicio JSON.*

Ha configurado los detalles de autenticación de OAuth y descargado los detalles del servicio JSON. Mantenga este archivo a mano, ya que es necesario en la siguiente sección.

### Añadir la configuración de IMS al entorno

Siga estos pasos para agregar la configuración de IMS al entorno:

1. Abra Experience Manager y seleccione el programa que contiene el entorno que desea configurar.
1. Cambie a la **Entornos** pestaña.
1. Seleccione el nombre del entorno que desea configurar. Esto le llevará a la **Información del entorno** página.
1. Cambie a la **Configuración** pestaña.
1. Actualice el campo JSON SERVICE_ACCOUNT_DETAILS. Asegúrese de utilizar el mismo nombre y configuración que se indican en la siguiente captura de pantalla.

![configuración de cuenta de servicio ims](assets/ims-service-account-config.png){width="800" align="left"}


*Añada los detalles de configuración del entorno.*




AEM Una vez que haya agregado la configuración de IMS al entorno, realice los siguientes pasos para vincular estas propiedades con guías de usuario mediante OSGi:

1. En el código de su proyecto Git de Cloud Manager, agregue los dos archivos siguientes (para el contenido del archivo, vea [Apéndice](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

1. Asegúrese de que los archivos recién agregados estén cubiertos por su `filter.xml`.
1. Confirme y envíe los cambios de Git.
1. Ejecute la canalización para aplicar los cambios al entorno.

Una vez hecho esto, debe poder usar el **Ayudante de guías** función.



## Apéndice {#appendix}

**Archivo**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Contenido**:

```
{
 "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
}
```


Una vez configurada, la variable **Ayudante de guías** ![Ayudante de guías](assets/guides-assistant-icon.svg) El icono se muestra en el panel derecho del editor web. Seleccione el icono para ver el **Ayudante de guías** panel.
Para obtener más información, consulte [Asistente de guías con tecnología de IA para buscar contenido](../user-guide/ai-based-guides-assistant.md) de la Guía del usuario de Experience Manager.
