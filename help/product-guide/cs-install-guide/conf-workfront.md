---
title: Configuración de Adobe Workfront en Experience Manager Guides
description: Obtenga información sobre cómo configurar Workfront en Experience Manager Guides
feature: Authoring
role: Admin
level: Experienced
source-git-commit: 2748ecee0963028be5d9220f852f4dfbc122d4a0
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 2%

---

# Configuración de Adobe Workfront

Adobe Workfront es una solución de administración de trabajo basada en la nube que ayuda a los equipos y las organizaciones a planificar, rastrear y administrar su trabajo de forma eficiente. La integración entre Experience Manager Guides y Adobe Workfront le permite acceder a funciones de administración de proyectos sólidas además de las funciones principales de CCMS de Experience Manager Guides, lo que le permite planificar, asignar y rastrear tareas de forma eficaz.

Obtenga más información acerca de la [integración de Adobe Workfront](../user-guide/workfront-integration.md) en Experience Manager Guides.

## Requisitos previos

Antes de empezar, asegúrese de lo siguiente:

1. Tiene acceso estándar a Adobe Workfront y acceso de administrador a Experience Manager Guides.
2. Usted [crea un nuevo formulario personalizado en Adobe Workfront](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/customize/custom-forms/design-a-form/design-a-form) necesario para Experience Manager Guides utilizando específicamente los siguientes campos:

   | Tipo de campo | Etiqueta | Nombre | Opciones (mostrar valores habilitados) |
   |------------|------|------|-------------------------------|
   | Menú desplegable de selección única | Tipo de tarea | task-type | Creación (valor = AUTOR), Publicación (valor = PUBLICACIÓN), Traducción (valor = TRADUCCIÓN), Revisión (valor = REVISIÓN) |
   | Menú desplegable de selección única | Estado de tarea | task-state | Creación (valor = AUTOR), Revisión (valor = REVISIÓN) |
   | Texto con formato | Lista de autores | author-list | - |
   | Texto con formato | Lista de revisores | lista de revisores | - |
   | Texto de línea única | URL de revisión | review-url | - |

>[!NOTE]
>
> En la tabla anterior, las opciones representan las opciones disponibles en el campo **Tipo de tarea**. Para cada opción, debe proporcionar **nombre de tarea** y **valor de tarea**. El nombre y los valores de cada tipo de tarea deben ser exactamente iguales a los mencionados en la tabla anterior. Por ejemplo, para el tipo de tarea Autor, proporcione **Authoring** como nombre y **AUTHOR** como su valor correspondiente.

## Introducción

Siga estos pasos para configurar Adobe Workfront en Experience Manager Guides.

1. Abra **el panel Herramientas** y seleccione **Guías**.
2. Seleccione **Configurar Workfront**.

   Se muestra la página **configuración de Workfront**.

   ![](assets/configure-workfront-page.png)

3. En la página **Configuración de Workfront**, escriba la dirección URL completa del dominio de Workfront, el ID de cliente y la clave secreta del cliente de su organización.

   Para obtener acceso a la clave **Client ID** y **Secreto del cliente** configurada en la configuración de Adobe Workfront, vaya a `Setup >> Systems>> oAuth2 Applications`.

   Para obtener más información sobre la configuración del dominio de Adobe Workfront, consulte la sección Flujo del código de autorización en [Crear aplicaciones OAuth2 para integraciones de Workfront](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/configure-integrations/create-oauth-application#create-an-oauth2-application-using-user-credentials-authorization-code-flow).

4. Seleccione **Iniciar sesión y comprobar**.

   Se le redirigirá a la página de Adobe Workfront Sign in.
5. Inicie sesión con su dirección de correo electrónico de Adobe Workfront y, a continuación, seleccione **Permitir acceso** para permitir que la aplicación Oauth2 acceda a su cuenta de Adobe Workfront correspondiente.

   Se le redirigirá automáticamente a la página de configuración de Workfront en Experience Manager Guides.

6. En la lista desplegable Formulario personalizado, seleccione el formulario personalizado de Adobe Workfront que ha creado para Experience Manager Guides. Ver [requisitos previos](#prerequisites).
7. Seleccione **Guardar y cerrar** para aplicar y guardar los cambios de configuración de Workfront.

Una vez configurada, [agregue usuarios a Adobe Workfront](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/add-users/create-manage-users/add-users) con las mismas direcciones de correo electrónico que tienen en Experience Manager Guides.



