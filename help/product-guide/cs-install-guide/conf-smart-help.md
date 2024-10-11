---
title: Configurar la Ayuda inteligente para buscar contenido
description: Obtenga información sobre cómo configurar la Ayuda inteligente para buscar contenido
source-git-commit: 48f7b38448e821a7ad5931a685dedc95303aea95
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 0%

---


# Configurar la ayuda inteligente con tecnología de IA para buscar contenido

Como administrador, puede configurar la función de Ayuda inteligente para los autores. El servicio de ayuda inteligente está protegido por la autenticación basada en autenticación IMS de Adobe. Integre su entorno con los flujos de trabajo de autenticación seguros basados en tokens de Adobe y comience a utilizar la nueva función de ayuda inteligente. Las siguientes configuraciones le ayudan a agregar la ficha **Configuración de IA** a un perfil de carpeta. Una vez agregada, puede utilizar la característica Ayuda inteligente del Editor Web.

## Creación de configuraciones de IMS en Adobe Developer Console

Realice los siguientes pasos para crear configuraciones de IMS en Adobe Developer Console:

>[!NOTE]
>
>Si ya ha creado un proyecto de OAuth para configurar la función de sugerencias inteligentes o la publicación basada en microservicios, puede omitir los siguientes pasos para crear el proyecto. Puede comenzar con el paso 8.

1. Iniciar [Adobe Developer Console](https://developer.adobe.com/console).
1. Después de iniciar sesión correctamente en Developer Console, verá la pantalla **Inicio**. En la pantalla de **Inicio** encontrará información y vínculos rápidos, incluidos los vínculos de navegación superior a Proyectos y Descargas.
1. Para crear un nuevo proyecto vacío, selecciona **Crear nuevo proyecto** de los vínculos **Inicio rápido**.
   ![Vínculos de inicio rápido](assets/conf-ss-quick-start.png) {width="550" align="left"}
   *Crear un nuevo proyecto.*

1. Seleccione **Agregar API** de la pantalla **Proyectos**.  Aparecerá la pantalla **Agregar una API**. Esta pantalla muestra todas las API, los eventos y los servicios disponibles para los productos y las tecnologías de Adobe con los que puede desarrollar aplicaciones.

1. Seleccione la **API de administración de E/S** para agregarla a su proyecto.
   ![API de administración de E/S](assets/confi-ss-io-management.png)
   *Agregar la API de administración de E/S a su proyecto.*

1. Cree una nueva **credencial de OAuth** y guárdela.
   ![Mosaico de credenciales de OAuth en la API de configuración](assets/conf-ss-OAuth-credential.png) {width="3000" align="left"}
   *Configure las credenciales de OAuth en su API.*

1. En la ficha **Proyectos**, elija la opción **Servidor OAuth en Servidor** y, a continuación, seleccione las credenciales recién creadas.

1. Seleccione el vínculo **Servidor a servidor de OAuth** para ver los detalles de credenciales de su proyecto.

   ![credenciales conectadas](assets/conf-ss-connected-credentials.png) {width="800" align="left"}

   *Conéctese al proyecto para ver los detalles de las credenciales.*

1. Vuelva a la ficha **Proyectos** y seleccione **Información general del proyecto** a la izquierda.

   <img src="assets/project-overview.png" alt="resumen del proyecto" width="500">

   *Empiece en el nuevo proyecto.*

1. Haga clic en el botón **Descargar** de la parte superior para descargar el JSON del servicio.

   <img src="assets/download-json.png" alt="descargar json" width="500">

   *Descargar los detalles del servicio JSON.*

Ha configurado los detalles de autenticación de OAuth y descargado los detalles del servicio JSON. Mantenga este archivo a mano, ya que es necesario en la siguiente sección.

### Añadir la configuración de IMS al entorno

Siga estos pasos para agregar la configuración de IMS al entorno:

1. Abra Experience Manager y seleccione el programa que contiene el entorno que desea configurar.
1. Cambie a la ficha **Entornos**.
1. Seleccione el nombre del entorno que desea configurar. Esto lo llevará a la página **Información del entorno**.
1. Cambie a la ficha **Configuración**.
1. Actualice el campo JSON SERVICE_ACCOUNT_DETAILS. Asegúrese de utilizar el mismo nombre y configuración que se indican en la siguiente captura de pantalla.

![configuración de cuenta de servicio de ims](assets/ims-service-account-config.png){width="800" align="left"}


*Agregar los detalles de configuración del entorno.*




Una vez añadida la configuración de IMS al entorno, realice los siguientes pasos para vincular estas propiedades con AEM Guides mediante OSGi:

1. En el código de su proyecto Git de Cloud Manager, agregue los dos archivos indicados a continuación (para el contenido de los archivos, vea [Apéndice](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

1. Asegúrese de que los archivos recién agregados estén cubiertos por su `filter.xml`.
1. Confirme y envíe los cambios de Git.
1. Ejecute la canalización para aplicar los cambios al entorno.

Una vez hecho esto, debería poder usar la característica **Ayuda inteligente**.



## Apéndice {#appendix}

**Archivo**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Contenido**:

```
{
 "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
}
```


Una vez configurada, el icono de **Ayuda inteligente** ![Ayuda inteligente](assets/smart-help-icon.svg) se muestra en el panel derecho del editor web. Seleccione el icono para ver el panel **Ayuda inteligente**.
Para obtener más información, consulte la sección [Ayuda inteligente con tecnología de IA para buscar contenido](../user-guide/ai-based-smart-help.md) en la Guía del usuario del Experience Manager.
