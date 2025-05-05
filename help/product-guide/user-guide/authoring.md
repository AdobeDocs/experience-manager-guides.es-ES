---
title: Administrar contenido
description: Administre contenido e identifique sus funciones y permisos en AEM Guides. Conozca los conceptos clave de la administración de contenido y del trabajo con los perfiles globales o de nivel de carpeta.
exl-id: 84926dc2-1180-48ef-85d0-50e3478bf26a
feature: Content Management
role: User
source-git-commit: 461692ce786f914dd196f289efef726e42bf9660
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 13%

---

# Administrar contenido {#id164JBG0M0T1}

Antes de empezar a crear contenido, debe familiarizarse con algunos conceptos básicos de administración de contenido en Adobe Experience Manager Guides. A continuación, comience con la creación de diferentes grupos de usuarios y la organización de sus recursos.

## Conceptos clave

Algunos conceptos clave de la administración de contenido en Adobe Experience Manager son los siguientes:

**Administración de recursos**

Experience Manager Guides utiliza la administración de recursos digitales \(DAM\) de Adobe Experience Manager para administrar los archivos DITA. Los archivos que carga o registra en DAM se almacenan como recursos digitales. Puede administrar y editar sus recursos en Adobe Experience Manager Assets. Para obtener más información acerca de la administración de recursos, vea [Administrar recursos](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html?lang=es).

**Administración de vínculos**

Mueva o cambie el nombre de los archivos o la estructura de carpetas en el repositorio de contenido, sin preocuparse por las referencias rotas. Todas las referencias hacia y desde el contenido afectado se actualizan automáticamente. Obtenga advertencias al eliminar contenido al que se hace referencia desde cualquier otra parte para evitar roturas no intencionadas.

**Administración de versiones**

Experience Manager Guides proporciona administración de versiones para sus recursos digitales. Puede activar fácilmente esta funcionalidad desde la aplicación de creación DITA que desee. Permite a los escritores realizar las funciones estándar de control de versiones, como el registro y la desprotección.

Para obtener más información acerca de cómo crear versiones o revertir a una versión específica, vea [Rama, reversión y versiones posteriores](web-editor-preview-topics.md#branch-revert-and-subsequent-versioning).

**Administración DITA nativa**

Aunque Experience Manager Guides mantiene la estructura de los ficheros DITA, también permite a Adobe Experience Manager gestionar DITA de forma nativa mediante la asignación de elementos para asignar los elementos DITA a los componentes de Adobe Experience Manager. El tratamiento nativo de DITA se utiliza en funciones como la previsualización de temas, la publicación en Adobe Experience Manager Sites y los flujos de trabajo de revisión.

## Identificación de la función y los permisos {#id181TF0K0MHT}

Experience Manager Guides proporciona tres grupos listos para usar. Estos grupos son: *Autores*, *Revisores* y *Editores*. Según el grupo con el que esté asociado, tiene permisos para realizar tareas específicas como se menciona en la tabla siguiente. Por ejemplo, la tarea de publicación solo la puede realizar un editor, pero no un autor o un revisor. Del mismo modo, un autor puede crear un nuevo tema y un revisor solo puede revisar un tema.

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
| Duplicado |   |   | Sí |
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
| Duplicado |   |   | Sí |
| Quitar |   |   | Sí |
| Consola de mapas DITA \(ficha Informes\) | Sí |   | Sí |
| **Funciones disponibles en la consola de mapas DITA \(Ajustes preestablecidos de condición\)** |
| Crear/editar ajuste preestablecido de condición |   |   | Sí |

[1](#fnsrc_1) Si *Autores* y *Editores* están invitados a una revisión.

[2](#fnsrc_2) según los derechos otorgados al usuario en el perfil de estado del documento.
