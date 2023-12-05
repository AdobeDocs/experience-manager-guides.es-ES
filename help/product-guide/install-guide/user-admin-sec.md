---
title: Administración de usuarios y seguridad
description: Descubra cómo funcionan la administración y la seguridad de los usuarios
exl-id: 1269a652-5261-413d-9ea0-b4f75003e9d8
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 10%

---

# Administración de usuarios y seguridad {#id181AED00G5Z}

AEM Para acceder y configurar las funciones de las Guías de, debe crear usuarios. AEM A estos usuarios se les pueden asignar permisos para acceder a todas las funciones o a determinadas funciones de las Guías de la. AEM Aprenda a configurar y mantener la autorización de usuarios, y también comprenda la teoría detrás de cómo funciona la autenticación y la autorización en los entornos de trabajo de los usuarios de la.

AEM Los siguientes temas de la documentación de la le ayudarán a comprender la administración de usuarios y los conceptos y características relacionados con la seguridad:

- [AEM Usuarios y grupos en la](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#UsersandGroupsinAEM)

- [AEM Permisos en la](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#PermissionsinAEM)

- [Administración de usuarios y grupos](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#ManagingUsersandGroups)

- [Administración de permisos](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#ManagingPermissions)


## AEM Grupos de usuarios creados por guías de usuario de {#id181TF0K0MHT}

AEM Guías de proporciona tres grupos predeterminados para administrar diferentes tareas en un proyecto DITA. Estos grupos son: *Autores*, *Revisores*, y *Editores*. Según el grupo con el que esté asociado un usuario, se le permite realizar tareas específicas. Por ejemplo, la tarea de publicación solo la puede realizar un editor, pero no un autor o un revisor. Del mismo modo, un autor puede crear un nuevo tema y un revisor solo puede revisar un tema.

>[!TIP]
>
> Consulte la *Permisos* de la guía de prácticas recomendadas para conocer las prácticas recomendadas sobre la configuración de permisos de usuario.

En la tabla siguiente se enumeran varias tareas y los grupos que pueden realizarlas:

| Tarea | Autores | Revisores | Editores |
|----|-------|---------|----------|
| Crear tema DITA | Sí |   | Sí |
| Crear mapa DITA | Sí |   | Sí |
| Asignar colecciones | Sí |   | Sí |
| Crear tarea de revisión | Sí |   | Sí |
| Revisar tema[1](#fntarg_1) | Sí | Sí | Sí |
| Resolución de clave | Sí |   | Sí |
| Abrir en FrameMaker | Sí |   | Sí |
| Check-out/Check-in | Sí |   | Sí |
| Editar tema | Sí |   | Sí |
| Mover tema | Sí |   | Sí |
| Editar propiedades del tema | Sí |   | Sí |
| Copiar | Sí |   | Sí |
| Eliminar | Sí |   | Sí |
| Compartir | Sí |   | Sí |
| **Estado del documento** |
| Crear/editar perfil de estado del documento |   |   | Sí |
| Cambiar estado del documento[2](#fntarg_2) | Sí | Sí | Sí |
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

- Si desea que un usuario inicie el flujo de trabajo de traducción o revisión, asegúrese de que el usuario sea miembro de *Editores* y *grupo de administradores de proyectos*.

- Los usuarios deben tener los permisos de lectura, creación, eliminación y modificación disponibles en las carpetas de idioma de origen y destino en las que deben trabajar.

- Si crea un proyecto, usted es el propietario del proyecto con *Editores* permisos. Para que otros usuarios de un proyecto puedan ver a los integrantes del equipo, crear tareas o crear flujos de trabajo, deben tener acceso de lectura a `/home/users` y `/home/groups` nodos. Una forma de proporcionar acceso de lectura en `/home/users` y `/home/groups` node proporciona acceso de lectura a la variable `projects-users` grupo.

- *Revisores* Puede acceder a los comentarios de revisión de un tema que se está revisando y agregarlos desde la consola Proyecto o desde el vínculo de notificación de la bandeja de entrada. Además, este acceso solo está disponible hasta el momento en que se abra la tarea de revisión.

- De forma predeterminada, *Editores* Se les concede acceso y permisos en las siguientes carpetas de DAM:

   - ``/var/dxml``-\> Lectura y escritura

   - `/content/dam/fmdita-outputs` -\> Lectura y escritura

   - `/content/output/sites` -\> Lectura y escritura

  Debe conceder permisos explícitos de lectura y escritura al editor si utiliza cualquier otra ubicación que no sea la predeterminada mencionada anteriormente.

- Todos los usuarios en *Autores*, *Revisores*, y *Editores* Los grupos de tienen acceso de lectura a todo el contenido de DAM.

- Los permisos de nivel de carpeta deben asignarse a los usuarios a través de la página de administración de usuarios.

- Si desea que los usuarios puedan realizar operaciones de búsqueda en DAM, haga que los usuarios sean miembros de *dam-users* grupo.

- AEM Si desea otorgar derechos de administración a cualquier usuario, puede hacerlo dándole acceso a través de grupos estándar como *administradores*, *projects-administrators* o la configuración OSGI \(Consola Felix\).

- Para otorgar a un usuario derechos para cambiar el estado de un documento, asegúrese de agregar el usuario en la sección de transición de estado del perfil de estado del documento.

[1](#fnsrc_1) If *Autores* y *Editores* están invitados a una revisión.[2](#fnsrc_2) Según los derechos otorgados al usuario en el perfil de estado del documento.
