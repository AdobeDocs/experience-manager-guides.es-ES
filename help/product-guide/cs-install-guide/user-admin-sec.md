---
title: Administración de usuarios y seguridad
description: Descubra cómo funcionan la administración de usuarios y la seguridad
exl-id: 10ab0f3c-97dc-4293-ab73-75b438c03d99
feature: User Management
role: Admin
level: Experienced
source-git-commit: 6aaa5c1eeb9b74ababc7ebf427babfff101acc70
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 10%

---

# Administración de usuarios y seguridad {#id181AED00G5Z}

Para acceder y configurar las funciones de AEM Guides, debe crear usuarios. A estos usuarios se les pueden asignar permisos para acceder a todas las funciones o a determinadas funciones de AEM Guides. Aprenda a configurar y mantener la autorización de usuarios, y también comprenda la teoría detrás del funcionamiento de la autenticación y la autorización en AEM.

Los siguientes temas de la documentación de AEM le ayudarán a comprender la administración de usuarios y los conceptos y características relacionados con la seguridad:

- [Usuarios, grupos y permisos de AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/accessing/aem-users-groups-and-permissions.html)

- [Administración y seguridad de usuarios](https://experienceleague.adobe.com/docs/experience-manager-65/administering/security/security.html?lang=es)


## Grupos de usuarios creados por AEM Guides {#id181TF0K0MHT}

AEM Guides proporciona tres grupos listos para usar. Estos grupos son: *Autores*, *Revisores* y *Editores*. Según el grupo con el que esté asociado un usuario, se le permite realizar tareas específicas. Por ejemplo, la tarea de publicación solo la puede realizar un editor, pero no un autor o un revisor. Del mismo modo, un autor puede crear un nuevo tema y un revisor solo puede revisar un tema.

>[!TIP]
>
> Consulte la sección *Permisos* en la guía de prácticas recomendadas para conocer las prácticas recomendadas sobre la configuración de permisos de usuario.

En la tabla siguiente se enumeran varias tareas y los grupos que pueden realizarlas:

| Tarea | Autores | Revisores | Editores |
|----|-------|---------|----------|
| Crear tema DITA | Sí |   | Sí |
| Crear mapa DITA | Sí |   | Sí |
| Asignar colecciones | Sí |   | Sí |
| Crear tarea de revisión | Sí |   | Sí |
| Revisar tema[1](#fntarg_1) | Sí | Sí | Sí |
| Resolución de clave | Sí |   | Sí |
| Check-out/Check-in | Sí |   | Sí |
| Editar tema | Sí |   | Sí |
| Mover tema | Sí |   | Sí |
| Editar propiedades del tema | Sí |   | Sí |
| Copiar | Sí |   | Sí |
| Eliminar | Sí |   | Sí |
| Compartir | Sí |   | Sí |
| **Estado del documento** |
| Crear/editar perfil de estado del documento |   |   | Sí |
| Cambiar el estado del documento[2](#fntarg_2) | Sí | Sí | Sí |
| **Funciones disponibles en la consola de mapas DITA \(ficha Ajustes preestablecidos de salida\)** |
| Generar |   |   | Sí |
| Editar |   |   | Sí |
| Duplicar |   |   | Sí |
| Crear |   |   | Sí |
| Eliminar ajuste preestablecido |   |   | Sí |
| **Funciones disponibles en la consola de mapas DITA \(ficha Salidas\)** |
| Ver salida generada | Sí |   | Sí |
| **Funciones disponibles en la consola de mapas DITA \(ficha Temas\)** |
| Crear tarea de revisión | Sí |   | Sí |
| Editar | Sí |   | Sí |
| **Funciones disponibles en la consola de mapas DITA \(ficha Líneas bases\)** |
| Crear |   |   | Sí |
| Editar |   |   | Sí |
| Duplicar |   |   | Sí |
| Quitar |   |   | Sí |
| Consola de mapas DITA \(ficha Informes\) | Sí |   | Sí |
| **Funciones disponibles en la consola de mapas DITA \(Ajustes preestablecidos de condición\)** |
| Crear/editar ajuste preestablecido de condición |   |   | Sí |

## Notas adicionales sobre los grupos de usuarios

La siguiente lista contiene algunas recomendaciones y puntos relacionados con grupos de usuarios y los permisos correspondientes:

- Si desea que un usuario inicie el flujo de trabajo de traducción o revisión, asegúrese de que el usuario sea miembro de *Publishers* y de *projects-administrators group*.

- Los usuarios deben tener los permisos de lectura, creación, eliminación y modificación disponibles en las carpetas de idioma de origen y destino en las que deben trabajar.

- Si crea un proyecto, usted es el propietario del proyecto con permisos de *editores*. Para que otros usuarios de un proyecto puedan ver a los integrantes del equipo, crear tareas o crear flujos de trabajo, deben tener acceso de lectura en los nodos `/home/users` y `/home/groups`. Una forma de conceder acceso de lectura en los nodos `/home/users` y `/home/groups` consiste en conceder acceso de lectura al grupo `projects-users`.

- *Los revisores* pueden tener acceso y agregar comentarios de revisión sobre un tema que se está revisando desde la consola Proyecto o desde el vínculo de notificación de la bandeja de entrada. Además, este acceso solo está disponible hasta el momento en que se abra la tarea de revisión.

- De manera predeterminada, se concede acceso y permisos a *Publishers* en las siguientes carpetas de DAM:

   - `/content/fmdita` -\> leer y escribir

   - `/content/dam/fmdita-outputs` -\> leer y escribir

   - `/content/output/sites` -\> leer y escribir

  Debe conceder permisos explícitos de lectura y escritura al editor si utiliza cualquier otra ubicación que no sea la predeterminada mencionada anteriormente.

- Todos los usuarios de los grupos *Autores*, *Revisores* y *Publicadores* tienen acceso de lectura a todo el contenido de DAM.

- Los permisos de nivel de carpeta deben asignarse a los usuarios a través de la página de administración de usuarios.

- Si desea que los usuarios puedan realizar operaciones de búsqueda en DAM, haga que los usuarios sean miembros del grupo *dam-users*.

- Si desea otorgar derechos de administración a cualquier usuario, puede hacerlo dándole acceso a través de grupos estándar de AEM como *administradores*, *proyectos-administradores* o la configuración OSGI \(Consola Felix\).

- Para otorgar a un usuario derechos para cambiar el estado de un documento, asegúrese de agregar el usuario en la sección de transición de estado del perfil de estado del documento.

[1](#fnsrc_1) Si *Autores* y *Editores* están invitados a una revisión.[2](#fnsrc_2) según los derechos otorgados al usuario en el perfil de estado del documento.
