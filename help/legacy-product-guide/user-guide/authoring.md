---
title: Administrar contenido
description: Administre contenido e identifique sus funciones y permisos en AEM Guides. Conozca los conceptos clave de la administración de contenido y del trabajo con los perfiles globales o de nivel de carpeta.
feature: Content Management
role: User
hide: true
exl-id: 54b960cf-fb00-4d4a-a836-9de4738c49a8
TQID: https://experienceleague.adobe.com/Rko9tfse1l5d-ZKeidb8hCqs1L2RcMlc9o581Xiakk4
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
  - id: b88be3fe-792c-484d-8262-9f667de75c8d
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
  - id: f7774ebe-aec9-42b6-97e4-5002acdc712e
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: da3860b0-d637-47df-bef0-273751180266
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 741
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
| **Estado del documento** |  |  |  |
| Crear/editar perfil de estado del documento |   |   | Sí |
| Cambiar el estado del documento[2](#fntarg_2) | Sí | Sí | Sí |
| **Funciones disponibles en la consola de mapas DITA \(ficha Ajustes preestablecidos de salida\)** |  |  |  |
| Generar |   |   | Sí |
| Editar |   |   | Sí |
| Duplicado |   |   | Sí |
| Crear |   |   | Sí |
| Eliminar ajuste preestablecido |   |   | Sí |
| **Funciones disponibles en la consola de mapas DITA \(ficha Salidas\)** |  |  |  |
| Ver salida generada | Sí |   | Sí |
| **Funciones disponibles en la consola de mapas DITA \(ficha Temas\)** |  |  |  |
| Crear tarea de revisión | Sí |   | Sí |
| Editar | Sí |   | Sí |
| **Funciones disponibles en la consola de mapas DITA \(ficha Líneas bases\)** |  |  |  |
| Crear |   |   | Sí |
| Editar |   |   | Sí |
| Duplicado |   |   | Sí |
| Quitar |   |   | Sí |
| Consola de mapas DITA \(ficha Informes\) | Sí |   | Sí |
| **Funciones disponibles en la consola de mapas DITA \(Ajustes preestablecidos de condición\)** |  |  |  |
| Crear/editar ajuste preestablecido de condición |   |   | Sí |

[1](#fnsrc_1) Si *Autores* y *Editores* están invitados a una revisión.

[2](#fnsrc_2) según los derechos otorgados al usuario en el perfil de estado del documento.

## Requisitos previos para la creación de contenido

**Trabajar con perfiles globales o de nivel de carpeta**

En una empresa, diferentes grupos o productos pueden utilizar diferentes plantillas de creación, plantillas de salida, perfiles de atributos condicionales \(o esquemas de asunto\) y configuraciones del Editor web. La configuración de estos solo a nivel empresarial \(o global\) puede dificultar la experiencia de los autores, ya que verán plantillas o perfiles que no son relevantes para ellos.

AEM Guides permite configurar la creación de plantillas \(topic o map\), plantillas de salida, atributos condicionales y configuraciones del editor web en el nivel \(global\) empresarial, así como en el nivel de carpeta. De este modo, puede separar las configuraciones para diferentes departamentos o productos de la empresa.

Además, puede delegar las configuraciones específicas de la carpeta a un departamento o a administradores de productos para descentralizar la administración.

Para obtener más información sobre la configuración de perfiles globales y de nivel de carpeta, consulte *Configuración de perfiles globales o de nivel de carpeta* en Instalar y configurar Adobe Experience Manager Guides as a Cloud Service.
