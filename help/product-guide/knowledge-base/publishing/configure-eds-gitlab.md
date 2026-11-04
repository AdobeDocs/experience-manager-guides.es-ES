---
title: Configuración de GitLab para Edge Delivery Services
description: Obtenga información sobre cómo configurar repositorios de GitLab, acceder a tokens, Cloud Manager, webhooks y traer su propio Git para publicar contenido de Experience Manager Guides en Edge Delivery Services.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 97620587a9e736e0886ea4d7158af330814e6392
workflow-type: tm+mt
source-wordcount: '1256'
ht-degree: 3%
---

# Configuración de GitLab para Edge Delivery Services

Para publicar contenido de Experience Manager Guides en Edge Delivery Services (EDS) mediante GitLab, debe conectar un repositorio de GitLab a su sitio de EDS mediante la funcionalidad *Traer su propio Git* (BYOG) de Cloud Manager. Este artículo enumera los pasos en secuencia. Para obtener más información sobre cada paso, consulte la documentación vinculada.

## Funcionamiento

- Un **repositorio de GitHub** crea el sitio EDS a través de la aplicación AEM Code Sync.
- Un **repositorio de GitLab** almacena el contenido publicado desde Experience Manager Guides.
- **Cloud Manager** vincula los dos al recibir eventos push de GitLab (gancho web) y sincronizarlos con el sitio EDS.

## Requisitos previos

- Acceso a GitHub y GitLab (GitLab.com o autoalojado) para crear repositorios y tokens.
- Acceso a Cloud Manager, con una función que permite agregar repositorios (Administrador de implementación o Propietario empresarial).
- Función Administrador del sistema o Desarrollador de API en su organización de Adobe para crear la integración de la API de Cloud Manager.
- Una organización de `aem.live` se registró en el servicio de configuración. Obtenga más información en [Configuración del servicio](https://www.aem.live/docs/config-service-setup).

## Secuencia de configuración

1. [Creación del sitio de EDS con GitHub](#1-create-the-eds-site-using-github-create-eds-site)
2. [Creación del repositorio de GitLab](#2-create-the-gitlab-repository)
3. [Configuración de la dirección URL del punto de montaje](#3-configure-the-mountpoint-url)
4. [Creación de tokens de acceso a GitLab](#4-create-gitlab-access-tokens)
5. [Añadir el repositorio de GitLab a Cloud Manager](#5-add-the-gitlab-repository-to-cloud-manager)
6. [Generación de una clave de API de Cloud Manager](#6-generate-a-cloud-manager-api-key)
7. [Configuración del webhook de GitLab](#7-configure-the-gitlab-webhook)
8. [Añadir el sitio de EDS a Cloud Manager](#8-add-the-eds-site-to-cloud-manager)
9. [Conecte el repositorio mediante Traer su propio Git](#9-connect-the-repository-using-bring-your-own-git)
10. [Configuración del sitio de EDS para utilizar Cloud Manager](#10-configure-the-eds-site-to-use-cloud-manager)
11. [Sincronización y verificación](#11-sync-and-verify)
12. [Publicar desde Experience Manager Guides](#12-publish-from-experience-manager-guides)

### &#x200B;1. Creación del sitio de EDS con GitHub {#create-eds-site}

Cree un repositorio de GitHub a partir de la plantilla de AEM Guides e instale la aplicación de sincronización de código de AEM en él. Guarde la **URL activa** (`https://<branch>--<github-repo>--<github-username>.aem.live`) generada para más adelante.

Para ver los pasos, vea [Crear un repositorio de GitHub para EDS](./configure-eds.md#create-a-github-repository-for-eds) y [Conectar GitHub a Adobe mediante la sincronización de código de AEM](./configure-eds.md#connect-github-to-adobe-via-aem-code-sync).

>[!IMPORTANT]
>
> No cree el sitio de EDS con la opción de un solo clic en Cloud Manager. Los sitios creados de esa manera no le proporcionan los permisos de administración necesarios para los pasos posteriores. Más información en [Preparar tu sitio Edge Delivery Services](https://www.aem.live/developer/byo-git#1.-prepare-your-edge-delivery-services-site).

### &#x200B;2. Creación del repositorio de GitLab

Cree un repositorio de GitLab independiente (por ejemplo, `my-eds-gitlab`) a partir de la misma plantilla de AEM Guides. Experience Manager Guides publica el resultado generado en este repositorio. EDS espera una rama `main`.

Para crear el repositorio, cree un proyecto en blanco e inserte en él el contenido de [aem-guides-boilerplate](https://github.com/adobe/aem-guides-boilerplate), o importe la plantilla en un nuevo proyecto. Para ver los pasos, vea [Crear un proyecto](https://docs.gitlab.com/user/project/) e [Importar su proyecto de GitHub a GitLab](https://docs.gitlab.com/user/project/import/github/) en la documentación de GitLab.

### &#x200B;3. Configuración de la dirección URL del punto de montaje

En el repositorio de GitHub, actualice `fstab.yaml` de modo que el origen del contenido apunte al repositorio de GitLab y confirme el cambio en `main`.

```text
https://<worker URL>/gitlab/<git acc domain>/<git username>/<git repo>/main/docs
```

| Parámetro | Descripción |
|---|---|
| `<worker URL>` | URL del nodo de trabajo proporcionada por Adobe. |
| `<git acc domain>` | Dominio de GitLab, como `gitlab.com`, o su dominio autoalojado. |
| `<git username>` | Su nombre de usuario de GitLab. |
| `<git repo>` | Nombre del repositorio de GitLab. |
| `main` / `docs` | Rama y carpeta raíz. Valores predeterminados de Experience Manager Guides. |

### &#x200B;4. Creación de tokens de acceso a GitLab

Cree los tokens de acceso necesarios para lo siguiente:

- **Cloud Manager**, para validar y acceder al repositorio. Obtenga más información en [Agregar repositorios externos en Cloud Manager](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager/content/managing-code/external-repositories).
- **Perfil de publicación de Experience Manager Guides** para confirmar el resultado publicado. Cree un token de acceso al proyecto GitLab con el rol **Desarrollador** y el ámbito `api`. Obtenga más información en la [documentación de GitLab](https://docs.gitlab.com/ee/user/project/settings/project_access_tokens.html).

>[!NOTE]
>
> Renovar tokens antes de que caduquen. La publicación falla si el token del perfil de publicación ha caducado. Para actualizar un token usado por Cloud Manager, vea [Administrar tokens de acceso para repositorios externos](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager/content/managing-code/manage-access-tokens).

### &#x200B;5. Añadir el repositorio de GitLab a Cloud Manager

En Cloud Manager, vaya a **Repositorios** > **Agregar repositorio**, seleccione **Repositorio privado** y valide la propiedad mediante el token de acceso. Espere hasta que el estado del repositorio sea **Listo**. La opción BYOG solo está disponible después de que al menos un repositorio externo esté listo.

Para ver los pasos, vea [Agregar repositorios externos en Cloud Manager](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager/content/managing-code/external-repositories).

### &#x200B;6. Generación de una clave de API de Cloud Manager

Cree una integración de API en la API de Adobe Developer Console (**Cloud Manager**, **servidor a servidor OAuth**) y copie el **ID de cliente (clave de API)**.

Para ver los pasos, vea [Creación de un proyecto de integración de API](https://developer.adobe.com/experience-cloud/cloud-manager/guides/getting-started/create-api-integration).

### &#x200B;7. Configuración del webhook de GitLab

En Cloud Manager, seleccione **Config Webhook** para el repositorio y copie la **URL de webhook** y el **Secreto**. Anexe la clave de API a la dirección URL (`<webhook URL>&api-key=<CLIENT_ID>`). En GitLab, vaya a **Configuración** > **Webhooks**, agregue la URL y el secreto, seleccione la rama `main` y habilite **eventos push**.

Para obtener más información, vea [Configurar el repositorio externo en Cloud Manager](https://www.aem.live/developer/byo-git#2.-configure-your-external-repository-in-cloud-manager).

### &#x200B;8. Añadir el sitio de EDS a Cloud Manager

En Cloud Manager, ve a **Edge Delivery** > **Agregar sitio de Edge Delivery** e introduce la URL de Live URL guardada en el paso 1. Complete la validación de propiedad.

Para ver los pasos, vea [Agregar un sitio Edge Delivery](https://experienceleague.adobe.com/es/docs/experience-manager-cloud-service/content/implementing/using-cloud-manager/edge-delivery-sites/add-edge-delivery-site).

### &#x200B;9. Conecte el repositorio mediante Traer su propio Git

En el sitio EDS de Cloud Manager, seleccione **Traer su propio Git (BYOG)**, elija el repositorio de GitLab y confirme. Copie y almacene de forma segura el secreto generado. Se muestra solo una vez y se genera un nuevo secreto si se vuelve a configurar el sitio.

Para obtener más información, vea [Configurar el sitio de Edge Delivery en Cloud Manager](https://www.aem.live/developer/byo-git#3.-configure-your-edge-delivery-site-in-cloud-manager).

### &#x200B;10. Configuración del sitio de EDS para utilizar Cloud Manager

Establezca el origen de código del sitio EDS en el repositorio de Cloud Manager, utilizando el **ID de programa** (`/program/<PROGRAM_ID>/`) y el **ID de repositorio** (`/repo/<REPO_ID>/`) de la URL del webhook. A continuación, cree un secreto con el nombre exacto `cm-byog` con el secreto del paso 9.

Para las llamadas de la API de administración, consulta [Configurar tu sitio de AEM para que use Cloud Manager](https://www.aem.live/developer/byo-git#4.-configure-your-aem-site-to-use-cloud-manager).

### &#x200B;11. Sincronización y verificación

En Cloud Manager, selecciona **Código de sincronización** en el menú del sitio y elige la rama `main`. A continuación, abra `https://main--<site>--<org>.aem.page` para comprobar el sitio.

Para obtener más información, ve [Déclencheur tu primera sincronización](https://www.aem.live/developer/byo-git#5.-trigger-your-first-sync) y [Comprueba tu sitio de AEM](https://www.aem.live/developer/byo-git#6.-verify-your-aem-site).

### &#x200B;12. Publicar desde Experience Manager Guides

Cree un perfil de publicación de EDS con **tipo de cuenta Git** establecido en **GitLab**, utilizando el token de acceso al proyecto del paso 4. A continuación, seleccione este perfil en un ajuste preestablecido de salida EDS y genere la salida. La salida se ha confirmado en la carpeta `docs` del repositorio de GitLab.

Para ver los pasos, vea [Crear el perfil de publicación de EDS](./configure-eds.md#create-the-eds-publish-profile-for-github-or-gitlab) y [Crear un ajuste preestablecido de salida para EDS y generar salida](./configure-eds.md#create-an-output-preset-for-eds-and-generate-output).

## Resolución de problemas

- **El sitio muestra contenido antiguo después de una inserción:** Compruebe que el gancho web está enviando eventos a Cloud Manager y, a continuación, compruebe el estado del último trabajo de sincronización.
- **Error de sincronización `Unable to fetch hlxignore: 401`:** El secreto `cm-byog` es incorrecto. Vuelva a crearlo con el secreto del paso 9.
- **Repositorio vinculado a otro sitio:** Un repositorio de Cloud Manager solo se puede vincular a un sitio a la vez. Para compartir un repositorio entre sitios, usa [Repoless](https://www.aem.live/docs/repoless).

Para obtener más información, vea [Solución de problemas en Traer su propio Git](https://www.aem.live/developer/byo-git#troubleshooting).
