---
title: Barra de fichas en el editor
description: Conozca la barra de pestañas del editor. Obtenga información acerca de la interfaz y las funciones de Editor en Adobe Experience Manager Guides.
feature: Authoring, Features of Web Editor
role: User
exl-id: 02e45d34-898f-411c-bd80-bd4f2364b7d7
TQID: https://experienceleague.adobe.com/sqNExkYi3iIqIxC7mdlhWw-59-LcAXCOU8w7GD63d8Q
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
    internal-label: Web Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: bd5be58a284c64f021af0fa97beca5e57514a5ab
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 0%
---
# Barra de pestañas del editor

>[!INFO]
>
> Este tema se aplica tanto al Editor nuevo como al Editor antiguo. Aunque la funcionalidad principal sigue siendo coherente, las diferencias en la interfaz de usuario, la terminología y las interacciones se indican dentro del contenido mediante pestañas y llamadas, según corresponda.

La barra de fichas se encuentra en la parte superior de la interfaz del Editor y proporciona acceso a las distintas funciones de nivel de archivo.

>[!BEGINTABS]

>[!TAB Nuevo editor]

![](./images/web-editor-tab-bar-editor-2-0.png)

>[!TAB Editor antiguo]

![](./images/web-editor-tab-bar.png)

>[!ENDTABS]

**Pestañas**

Muestra los temas abiertos actualmente en el Editor como fichas de archivo. Puede tener varios temas abiertos al mismo tiempo, que se muestran en sus respectivas pestañas en la barra de pestañas. De forma predeterminada, puede ver los títulos de los archivos en las pestañas. Al pasar el ratón por encima de un archivo, puede ver el título y la ruta del archivo como información sobre herramientas.

>[!NOTE]
>
> Como administrador, también puede elegir ver la lista de archivos por nombres de archivo en las pestañas. Seleccione la opción **Filename** en la sección **Configuración de visualización de archivos del editor** en [Preferencias de usuario](./intro-home-page.md#user-preferences).

Al seleccionar la pestaña Archivo, se abre un menú contextual con las opciones Guardar como nueva versión, Copiar, Buscar en, Añadir a, Propiedades, Dividir, Descargar como PDF y Cerrar.

**Guardar todo**

Guarda los cambios realizados en todos los temas abiertos. Si tiene varios temas abiertos en el editor, al seleccionar **Guardar todo** o al usar las teclas de método abreviado **Ctrl**+**S** se guardan todos los documentos con un solo clic. No es necesario guardar cada documento individualmente.

>[!NOTE]
>
> La operación **Guardar todo** no crea una nueva versión de los temas. Para crear una nueva versión, usa la opción **Guardar como nueva versión**.

**Asistente de IA**: el Asistente de IA está disponible en dos modos: **Agente** y **Estándar**.

>[!NOTE]
>
> Para utilizar el modo automático de la función Asistente de IA en su entorno, póngase en contacto con el equipo de éxito del cliente. Una vez habilitada la función, los administradores pueden activarla o desactivarla desde la Configuración de Workspace. Solo se puede habilitar un modo de asistente de IA a la vez; ya sea agéntico o estándar.

- **Agnetic**: aporta al editor la habilidad inteligente y auténtica de etiquetado inteligente de Adobe CX Enterprise Coworker, lo que permite un etiquetado de contenido natural y conversacional. Analiza el contenido, recomienda las etiquetas relevantes y le ayuda a aplicar metadatos coherentes y precisos con un esfuerzo mínimo. Puede revisar las etiquetas sugeridas y elegir aplicarlas o rechazarlas antes de confirmar la selección. [Use el Asistente de IA en el modo agente](../user-guide/ai-assistant-agentic.md) para optimizar el proceso de etiquetado y mejorar la organización y la detección del contenido.

- **Estándar**: Una potente herramienta impulsada por IA diseñada para mejorar su productividad mediante características de ayuda inteligentes. Además, cuando trabaje en la interfaz del editor, puede aprovechar las capacidades de creación inteligente del asistente de IA, que hace que su proceso de creación sea más inteligente y rápido mediante sugerencias inteligentes para la reutilización y optimización de contenido.

La característica [AI Assistant](./ai-assistant.md) solo está disponible actualmente para Adobe Experience Manager as a Cloud Service.

**Expandir vista**: permite expandir la vista de página mediante el icono **Expandir**. En esta vista, la barra de encabezado que contiene el logotipo de Adobe Experience Manager está oculta. Esto maximiza el espacio de contenido para editar. Para volver a la vista estándar, usa el icono **Salir de la vista expandida**.

**Más acciones**: Proporciona acceso a opciones adicionales. Al seleccionar este botón, se abre un menú con las siguientes opciones:

- **Assets**: lo lleva a un destino basado en su configuración.
  - **Cloud Services**: Si usas Cloud Services, al seleccionar la opción **Assets** accederás a la página Navegación de AEM.

  - **Software On-Premise**: Si utiliza Adobe Experience Manager Guides (4.2.1 y versiones posteriores), al seleccionar la opción **Assets**, se le redirigirá a la ruta de archivo actual en la interfaz de usuario de Assets.
- **Configuración de Workspace**: lo lleva al cuadro de diálogo Configuración de Workspace. Para obtener más información, vea [Configurar las opciones de Workspace](../install-conf-guide/workspace-settings.md).

>[!NOTE]
>
>Si usa Adobe Experience Manager Guides en una configuración local anterior a la versión 5.2, la opción de configuración de Workspace seguirá apareciendo como **Configuración** en el menú Más acciones.

- **Configuración del editor**: lo lleva al cuadro de diálogo Configuración del editor, donde puede personalizar el comportamiento del editor a nivel de autor individual. Permite controlar la visibilidad y el comportamiento de las etiquetas, los comentarios y otras configuraciones de nivel de editor durante la creación. Para obtener más información, vea [Configuración del editor](../user-guide/config-editor-settings.md).

**Tema principal:**&#x200B;[&#x200B; Introducción al editor](web-editor.md)
