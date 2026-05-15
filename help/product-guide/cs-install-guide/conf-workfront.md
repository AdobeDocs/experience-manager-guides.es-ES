---
title: Configuración de Adobe Workfront en Experience Manager Guides
description: Obtenga información sobre cómo configurar Workfront en Experience Manager Guides
feature: Authoring
role: Admin
level: Experienced
exl-id: 1f72642c-e694-47cd-9182-f4f4aaf69655
TQID: https://experienceleague.adobe.com/Yua4Y6xsnec3O-hpTNhSmK4HvsCwaGYbLTxUxEeQAKY
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: ae478996-b206-4712-9b0c-dc78a2644453
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: f7774ebe-aec9-42b6-97e4-5002acdc712e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 600
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
   | Menú desplegable de selección única | Estado de tarea | task-state | Creación (valor = AUTOR), Publicación (valor = PUBLICACIÓN), Traducción (valor = TRADUCCIÓN), Revisión (valor = REVISIÓN) |
   | Texto con formato | Lista de autores | author-list | - |
   | Texto con formato | Lista de revisores | lista de revisores | - |
   | Texto de línea única | URL de revisión | review-url | - |
   | Texto de línea única | URL de tarea | task-url | - |
   | Texto de una sola línea | Asunto del correo electrónico | asunto del correo electrónico | - |

>[!NOTE]
>
> * En la tabla anterior, las opciones representan las opciones disponibles en el campo **Tipo de tarea**. Para cada opción, debe proporcionar **nombre de tarea** y **valor de tarea**. El nombre y los valores de cada tipo de tarea deben ser exactamente iguales a los mencionados en la tabla anterior. Por ejemplo, para el tipo de tarea Autor, proporcione **Authoring** como nombre y **AUTHOR** como su valor correspondiente.
> * Cuando trabaje con servicios locales, asegúrese siempre de que `localhost` se reemplaza con la dirección de servidor correcta en la configuración de **Day CQ Link Externalizer** para recibir correctamente el vínculo de tarea resuelto en las notificaciones por correo electrónico.
> * Al crear una tarea de revisión en Workfront, los usuarios (autores o revisores) deben formar parte del grupo **workflow-users**. Además, como **autor**, debes ser parte del grupo **content-authors** y **authors**, mientras que como **revisor**, debes ser parte del grupo **revisores**.


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
