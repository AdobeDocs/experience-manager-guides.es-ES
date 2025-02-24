---
title: Consola de mapas en Adobe Experience Manager Guides
description: Obtenga información acerca de la consola Mapa y las distintas funciones disponibles que le permiten publicar y administrar mapas en Adobe Experience Manager Guides.
feature: Publishing
role: User
source-git-commit: 4c13d0dab23c19fe2340128aaa05803bb711a486
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 0%

---


# Información general de la consola Mapa

Adobe Experience Manager Guides ofrece una consola específica, conocida como **consola de mapas**, para optimizar la administración de mapas y las tareas de publicación. Esta interfaz centralizada mejora la productividad y la precisión de las actividades relacionadas con los mapas al proporcionarle opciones para generar resultados, traducir contenido, acceder a informes y mucho más, todo en un solo lugar.

![ficha de opciones de propiedades de archivo](./images/map-console-screen.png){width="800" align="left"}

La interfaz de la consola Mapa se divide principalmente en dos secciones: **Barra de navegación** y **Panel izquierdo**.

![Nuevo](images/map-console-sections.png){width="800" align="left"}

- (**A**) **Barra de navegación**: La barra de navegación muestra las herramientas para cambiar la navegación, ajustar la vista de página y muestra el nombre del archivo de mapa seleccionado.

  Las funciones disponibles en la barra de navegación se explican de la siguiente manera:

   - **Conmutador de navegación**: permite una navegación perfecta a otras páginas - Editor o Página de inicio:
   - **Archivo de asignación seleccionado**: Muestra el nombre del archivo de asignación seleccionado actualmente. Puede abrirlo en el Editor o elegir un archivo de asignación diferente para la consola Mapa.
   - **Más acciones**: Proporciona opciones para navegar a la **IU de Assets** y a la **configuración**. Para obtener más información, consulte la sección **Más acciones** del documento [Conocer las características del editor](./web-editor-features.md#tab-bar).
   - **Expandir vista**: permite expandir la vista de página mediante el icono **Expandir**. En esta vista, la barra de encabezado está oculta, lo que maximiza el espacio de contenido. Para volver a la vista estándar, usa el icono **Salir de la vista expandida**.

  >[!NOTE]
  >
  > Si usas el as a Cloud Service de Adobe Experience Manager Guides, se mostrará una característica adicional [Asistente de IA](./ai-assistant.md) en la barra de navegación.

- (**B**) **Panel izquierdo**: el panel izquierdo le proporciona acceso rápido a las funciones de generación de salida, creación y administración de informes, línea de base, ajustes preestablecidos de condición, traducción de contenido y Workfront (solo si están configuradas).

  Para obtener más información, consulte la sección [Características de la consola de mapas](#map-console-features) a continuación.

## Funciones de consola de mapas

Las siguientes funciones están disponibles en el panel izquierdo al [abrir un archivo de mapa DITA en la consola de mapas](./open-files-map-console.md).

**Generación de resultados**

Con la consola Mapa, puede generar salidas de forma eficaz en varios formatos, incluidos AEM Sites, PDF, HTML5, EPUB, JSON y salida personalizada a través de DITA-OT, publicación nativa de PDF y FMPS. Puede generar resultados para un mapa DITA completo o publicar selectivamente sólo algunos temas que haya actualizado. También se puede utilizar la función de publicación Línea base para publicar selectivamente una versión específica del tema o mapa DITA.

Para obtener más información, vea [Generación de resultados](./generate-output.md).

**Creación y administración de informes**

En una configuración organizativa, debe verificar la integridad general de la documentación técnica antes de empezar a trabajar en ella o publicar los documentos. Esta necesidad se vuelve aún más esencial en entornos multiusuario y a gran escala. Con la consola Mapa, puede acceder a informes de Experience Manager Guides que ofrecen una perspectiva útil del estado general del contenido del repositorio y de cómo se utiliza el contenido en el proceso de documentación.

Para obtener más información, vea [Informes en Experience Manager Guides](./reports-intro.md).

**Línea base**

Experience Manager Guides proporciona la función Línea de base que le permite crear una versión de los temas y recursos que luego se puede utilizar para publicar o traducir. También se pueden publicar varios ajustes preestablecidos de salida del mismo mapa DITA en paralelo.

Aprenda a [crear y administrar líneas de base en Experience Manager Guides](./web-editor-baseline.md).

**Ajustes preestablecidos de condición**

Experience Manager Guides permite definir atributos en los temas DITA y utilizar el ajuste preestablecido de condición para especificar qué sucede con el atributo en la salida final. Por ejemplo, puede agregar atributos como la versión 1.0 y la versión 2.0 en el contenido y utilizar un ajuste preestablecido de condición para incluir la versión 1.0 para la versión 1.0 y excluir la versión 2.0. Del mismo modo, puede añadir atributos como SO Windows y OS Linux al contenido y, a continuación, incluir o excluir el contenido relevante para la salida final según el sistema operativo.

Más información sobre [Ajustes preestablecidos de condición](./generate-output-use-condition-presets.md).

**Traducción de contenido**

Experience Manager Guides incluye potentes funcionalidades que le permiten traducir el contenido a varios idiomas. Experience Manager Guides admite los flujos de trabajo de traducción automática y humana.

En la consola Mapa, puede acceder a todas las opciones necesarias para comenzar a utilizar los flujos de trabajo de traducción. Para obtener más información, vea [Traducir contenido](./translation.md).


**Workfront**

La función Workfront también está presente en la consola Mapa, que le permite trabajar con tareas de Adobe Workfront directamente desde Experience Manager Guides.

Obtenga información acerca de la integración de [Adobe Workfront en Experience Manager Guides](./workfront-integration.md).

Solo puedes acceder a esta función si el administrador ha configurado la integración de **Adobe Workfront** en tu instancia de Experience Manager Guides.