---
title: Administrar contenido
description: Administre contenido e identifique sus funciones y permisos en AEM Guides. Conozca los conceptos clave de la administración de contenido y del trabajo con los perfiles globales o de nivel de carpeta.
feature: Content Management
role: User
hide: true
exl-id: 54b960cf-fb00-4d4a-a836-9de4738c49a8
source-git-commit: 7286c3fb36695caa08157296fd6e0de722078c2b
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 10%

---

# Administrar contenido {#id164JBG0M0T1}

Antes de empezar a crear contenido, debe familiarizarse con algunos conceptos básicos de administración de contenido en AEM Guides. A continuación, comience con la creación de diferentes grupos de usuarios y la organización de sus recursos.

## Conceptos clave

Algunos conceptos clave de la administración de contenido en AEM son los siguientes:

**Administración de recursos**

AEM Guides utiliza la administración de recursos digitales \(DAM\) de AEM para administrar los archivos DITA. Los archivos que carga o registra en DAM se almacenan como recursos digitales. Puede administrar y editar sus recursos en AEM Assets. Para obtener más información sobre la administración de recursos, consulte [Administrar recursos](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html?lang=en).

**Administración de vínculos**

Mueva o cambie el nombre de los archivos o la estructura de carpetas en el repositorio de contenido, sin preocuparse por las referencias rotas. Todas las referencias hacia y desde el contenido afectado se actualizan automáticamente. Obtenga advertencias al eliminar contenido al que se hace referencia desde cualquier otra parte para evitar roturas no intencionadas.

**Administración de versiones**

AEM Guides proporciona administración de versiones para sus recursos digitales. Puede activar fácilmente esta funcionalidad desde la aplicación de creación DITA que desee. Permite a los escritores realizar las funciones estándar de control de versiones, como el registro y la desprotección.

Para obtener más información sobre cómo crear versiones o revertir a una versión específica, vea [Ramificar, revertir y versiones posteriores](web-editor-preview-topics.md#id193PG0Y051X).

**Administración DITA nativa**

Aunque AEM Guides mantiene la estructura de los ficheros DITA, también permite a AEM gestionar DITA de forma nativa mediante la asignación de elementos para asignar los elementos DITA a los componentes de AEM. El tratamiento nativo de DITA se utiliza en funciones como la previsualización de temas, la publicación en AEM Sites y los flujos de trabajo de revisión.

## Identificación de la función y los permisos {#id181TF0K0MHT}

AEM Guides proporciona tres grupos listos para usar. Estos grupos son: *Autores*, *Revisores* y *Editores*. Según el grupo con el que esté asociado, tiene permisos para realizar tareas específicas como se menciona en la tabla siguiente. Por ejemplo, la tarea de publicación solo la puede realizar un editor, pero no un autor o un revisor. Del mismo modo, un autor puede crear un nuevo tema y un revisor solo puede revisar un tema.

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

[1](#fnsrc_1) Si *Autores* y *Editores* están invitados a una revisión.

[2](#fnsrc_2) según los derechos otorgados al usuario en el perfil de estado del documento.

## Requisitos previos para la creación de contenido

**Trabajar con perfiles globales o de nivel de carpeta**

En una empresa, diferentes grupos o productos pueden utilizar diferentes plantillas de creación, plantillas de salida, perfiles de atributos condicionales \(o esquemas de asunto\) y configuraciones del Editor web. La configuración de estos solo a nivel empresarial \(o global\) puede dificultar la experiencia de los autores, ya que verán plantillas o perfiles que no son relevantes para ellos.

AEM Guides permite configurar la creación de plantillas \(topic o map\), plantillas de salida, atributos condicionales y configuraciones del editor web en el nivel \(global\) empresarial, así como en el nivel de carpeta. De este modo, puede separar las configuraciones para diferentes departamentos o productos de la empresa.

Además, puede delegar las configuraciones específicas de la carpeta a un departamento o a administradores de productos para descentralizar la administración.

Para obtener más información sobre la configuración de perfiles globales y de nivel de carpeta, consulte *Configuración de perfiles globales o de nivel de carpeta* en Instalar y configurar Adobe Experience Manager Guides as a Cloud Service.
