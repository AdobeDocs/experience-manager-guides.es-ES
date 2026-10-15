---
title: Conexión de AEM Guides con la inteligencia artificial aplicada al conocimiento
description: Aprenda a conectar AEM Guides con la inteligencia artificial aplicada al conocimiento de Guides
feature: Introduction
role: Admin
level: Experienced
source-git-commit: 05976e2a408e57256a454f181bb93d900dc091ab
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 1%
---

# Conexión de Adobe Experience Manager Guides con la inteligencia artificial aplicada al conocimiento de guías (Beta)

>[!IMPORTANT]
>
> Esta función está desactivada de forma predeterminada. Para habilitar la función de inteligencia artificial aplicada al conocimiento de las guías, póngase en contacto con el equipo de éxito del cliente.

Este artículo proporciona a los administradores y a los ingenieros de contenido el proceso completo para configurar el acceso a la inteligencia artificial aplicada al conocimiento de las guías y cargar contenido de Experience Manager Guides para consumirlo en la inteligencia artificial aplicada al conocimiento.

## Resumen del proceso

| Paso | Lo que vas a hacer |
|---|---|
| 1 | Cree una cuenta de servicio en Adobe Developer Console y configúrela para su entorno. |
| 2 | Recupere el correo electrónico de la cuenta técnica desde el archivo de credenciales de la cuenta de servicio. |
| 3 | Conceda acceso a la cuenta de servicio en la inteligencia artificial aplicada al conocimiento creando una función y añadiendo el usuario. |
| 4 | Configure un ajuste preestablecido de salida de inteligencia artificial aplicada al conocimiento en Experience Manager Guides y cargue contenido. |


## Requisitos previos

Asegúrese de tener los siguientes permisos y acceso antes de empezar:

| Requisito | Función |
|---|---|
| Adobe Developer Console | Cree la cuenta de servicio de y descargue sus credenciales JSON. |
| Adobe Experience Manager Guides | Cree contenido y configure el ajuste preestablecido de salida para la inteligencia artificial aplicada al conocimiento. |
| [IA de conocimiento](https://guidesai.adobe.io/) | Administre funciones y usuarios, y reciba el contenido cargado. |
| Permiso: Crear cuentas de servicio | Necesario en Adobe Developer Console para crear una cuenta de servicio. |
| Permiso: Administrar usuarios y funciones en Knowledge AI | Necesario para conceder acceso a la cuenta de servicio en Knowledge AI. |

## Crear una cuenta de servicio

La inteligencia artificial aplicada al conocimiento utiliza una cuenta de servicio para autenticarse de forma segura y acceder al contenido.

1. Siga las instrucciones de [Configuración de Microservices IMT](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/kb-articles/publishing/configure-microservices-imt-config).

1. Cree una nueva cuenta de servicio y descargue el archivo de credenciales JSON generado.

1. Configure las opciones de entorno necesarias con las credenciales descargadas.

Una vez completada, la cuenta de servicio debe asociarse correctamente con su entorno.

>[!NOTE]
>
> Si ya ha creado y configurado una cuenta de servicio para su entorno, puede continuar con el siguiente paso.


## Recuperar el correo electrónico de cuenta técnica

Para conceder acceso a la inteligencia artificial aplicada al conocimiento, identifique la cuenta de servicio.

1. Abra el archivo JSON de la cuenta de servicio descargado.
1. Busque el nombre de campo `technical_account_email`. Vea un valor similar al siguiente:

   ```json
   {
   "technical_account_email": "a1b2c3d4e5f6@techacct.adobe.com"
   }
   ```

1. Copie la dirección de correo electrónico asociada con `technical_account_email`. Utilizará esta dirección de correo electrónico en el siguiente paso.

## Conceder acceso en Knowledge AI

Para permitir que la cuenta de servicio administre y cargue contenido, agréguelo a la inteligencia artificial aplicada al conocimiento con los permisos adecuados.

1. Abra [inteligencia artificial aplicada al conocimiento](https://guidesai.adobe.io/).
1. Vaya a **Seguridad > Funciones** y cree una función con los permisos mínimos requeridos.
1. Vaya a **Seguridad > Usuarios > Agregar usuario**. Agregue un nuevo usuario usando el `technical_account_email` copiado del JSON de la cuenta de servicio, seleccione los dominios del menú desplegable **Dominios** y asigne el rol creado en el paso anterior.

La cuenta de servicio ahora está autorizada para realizar operaciones de carga y administración de contenido.

## Configuración del ajuste preestablecido de Knowledge AI y carga de contenido

Para publicar contenido en Knowledge AI, configure Experience Manager Guides una vez que haya configurado los permisos.

1. Abra la **consola de mapas** en Experience Manager Guides.
1. Vaya a la pestaña **Ajustes preestablecidos de salida**.
1. Seleccione el icono + para crear un ajuste preestablecido de salida.
1. Seleccione **Inteligencia artificial aplicada al conocimiento** del menú desplegable **Tipo** en el cuadro de diálogo **Nuevo ajuste preestablecido de salida**. Escriba un **Nombre** y seleccione **Agregar al perfil de carpeta actual** para crear un ajuste preestablecido de salida dentro del perfil de carpeta actual.

   ![conocimiento-ai-preset-creation](assets/knowledge-ai-preset.png)

1. Seleccione **Añadir**. Se crea el ajuste preestablecido de inteligencia artificial aplicada al conocimiento.
1. Abra el ajuste preestablecido de inteligencia artificial aplicada al conocimiento.
1. Seleccione el dominio para el cual se le otorgó el rol a `technical_account_email` y después seleccione **Cargar contenido**. Esto déclencheur el flujo de trabajo de carga de contenido a la inteligencia artificial aplicada al conocimiento. Espere a que se complete el proceso de carga.

   ![dominio-ai-conocimiento](assets/knowledge-ai-domain.png)

1. Una vez completada la carga, seleccione **Abrir en la inteligencia artificial aplicada al conocimiento**. Esto abre el chat de inteligencia artificial aplicada al conocimiento dentro del dominio, utilizando el contenido cargado.

   ![conocimiento-ai-abrir](assets/open-knowledge-ai.png)

Ha configurado correctamente la cuenta de servicio, ha asignado los permisos necesarios y ha hecho que el contenido de Experience Manager Guides esté disponible en Knowledge AI. Cuando quiera publicar contenido actualizado, cree un nuevo ajuste preestablecido de inteligencia artificial aplicada al conocimiento y siga los pasos descritos en [configure el ajuste preestablecido de inteligencia artificial aplicada al conocimiento y cargue el contenido](#configure-knowledge-ai-preset-and-upload-content) en la sección anterior.



