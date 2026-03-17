---
title: Notas de versión | Novedades de la versión 2026.03.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las funciones nuevas y mejoradas de la versión 2026.03.0 de Adobe Experience Manager Guides
role: Leader
source-git-commit: dedd253dba3d93beed162eb5258125928f6d315c
workflow-type: tm+mt
source-wordcount: '824'
ht-degree: 2%

---

# Novedades de la versión 2026.03.0 (marzo de 2026)

Este artículo cubre las funciones nuevas y mejoradas introducidas con la versión 2026.03.0 de Adobe Experience Manager Guides as a Cloud Service.

Para ver la lista de problemas corregidos en esta versión, consulte [Problemas solucionados en la versión 2026.03.0](fixed-issues-2026-03-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2026.03.0](../release-info/upgrade-instructions-2026-03-0.md).

## Introducción de formación sobre productos y contenido de aprendizaje en Experience Manager Guides

La función de contenido **Aprendizaje y formación sobre productos** de Experience Manager Guides permite a los equipos de formación y a los diseñadores de instrucciones crear cursos interactivos de aprendizaje electrónico directamente desde la interfaz de Experience Manager Guides.

![](assets/lc-overview.png)

Con la creación basada en plantillas, los componentes interactivos de los cursos y el soporte para las evaluaciones, los equipos pueden desarrollar contenido de formación de alta calidad alineado con sus objetivos organizativos.

>[!NOTE]
> 
> La función Aprendizaje y contenido del producto permanece deshabilitada de forma predeterminada para todas las instancias de Experience Manager Guides as a Cloud Service. Los administradores pueden habilitar esta característica en el nivel de perfil de carpeta desde **Configuración de Workspace** > **General**.

Las funciones clave son las siguientes:

- Administración centralizada de contenido de aprendizaje
- Creación basada en plantillas
- Compatibilidad con la reutilización de contenido
- Creación y administración de evaluaciones
- Flujos de trabajo de revisión basados en web
- Administración de traducción líder del sector
- Publicación multicanal mediante los formatos de salida SCORM y PDF predeterminados.

Para obtener más información, consulte [Guía de introducción](../learning-content/course-overview.md) y [Guía de configuración](../lc-config-guide/introduction.md).


## Mejoras del editor

Se han realizado las siguientes mejoras de Editor como parte de esta versión:

### Mejoras en el panel de validación de Schematron

Se han realizado las siguientes mejoras en la interfaz de usuario de Schematron para mejorar la claridad, la facilidad de uso y los resultados de validación:

- En el panel Validación, se muestra un mensaje de estado vacío cuando no se agrega ningún archivo de Schematron, lo que proporciona una mejor claridad y dirección para los pasos siguientes.

  ![](assets/schematron-panel.png){width="350" align="left"}
- Cuando se agregan varios archivos de Schematron, se organizan en un acordeón consolidado, lo que proporciona una mejor visibilidad de los archivos de Schematron configurados.

  ![](assets/schematron-panel-error.png){width="350" align="left"}
- Según el atributo de rol definido en el archivo Schematron, los resultados de validación ahora se clasifican en: `Fatal`, `Error`, `Warn` o `Info`. Cada categoría incluye un recuento visible junto con información sobre herramientas contextuales para una interpretación más clara.

  ![](assets/schematron-validation-errors.png){width="350" align="left"}

Para obtener más información sobre el uso de archivos Schematron en Experience Manager Guides, vea [Compatibilidad con archivos Schematron](../user-guide/support-schematron-file.md).

### Las copias de idioma de traducción ya están disponibles en el panel derecho de la interfaz del editor

Ahora hay disponible una nueva sección **Traducciones** en el panel derecho bajo *Propiedades del archivo* en el editor. Esta sección proporciona acceso directo a todas las copias de idioma disponibles para el recurso abierto actualmente (mapa, tema, imagen, etc.). Ya no es necesario navegar a la interfaz de usuario de Assets para ver o acceder a estas copias de idioma.

![](assets/translations-right-panel.png){width="350" align="left"}

Para cada copia de idioma, puede pasar el ratón sobre el archivo para localizar su ruta en el repositorio o simplemente seleccionarlo para abrirlo en el Editor. Además de abrir archivos, también puede realizar muchas acciones utilizando el menú **Opciones**. Algunas de las acciones que puede realizar son Editar, Vista previa, Copiar UUID, Copiar ruta, Agregar a colecciones y Propiedades.

Para obtener más información, vea [Panel derecho en el editor](../user-guide/web-editor-right-panel.md#file-properties).


### Buscar citas en todos los campos del diario

Ahora puede buscar citas en todos los campos de diario, como *Título*, *Título del diario*, *Autor*, *Año*, *Volumen*, *Número* y *Páginas*, usando la opción **Cualquier campo** en el cuadro de diálogo **Agregar cita**. La búsqueda devuelve la cita coincidente más cercana en función del texto introducido.

Para obtener más información sobre cómo agregar citas en Experience Manager Guides, vea [Agregar y administrar citas en el contenido](../user-guide/web-editor-apply-citations.md).

![](assets/add-citations.png){width="350" align="left"}



## Revisar mejoras

En esta versión están disponibles las siguientes mejoras para la función Revisar:

- La asignación de un revisor a una tarea de revisión ahora depende de la selección de un proyecto activo. El campo **Asignar a** de la página *Crear tarea de revisión* permanece deshabilitado hasta que se seleccione un proyecto activo. Después de seleccionar un proyecto, el campo **Asignar a** se habilita y muestra solamente los usuarios y grupos de usuarios asociados con ese proyecto. Esto garantiza que las tareas de revisión se asignen únicamente a miembros de proyecto válidos y evita que se seleccione un revisor de forma involuntaria.

  ![](assets/create-review-task-023.png)

- El campo **Asignar a** ahora admite la búsqueda de escritura anticipada, lo que le permite localizar rápidamente usuarios o grupos de usuarios escribiendo texto.

En conjunto, estas mejoras hacen que la selección de Revisor sea más precisa, eficiente y esté alineada con los flujos de trabajo de revisión específicos del proyecto.

Para obtener más información, vea [Enviar temas para revisión](../user-guide/review-send-topics-for-review.md).

## Mejoras en la administración de recursos

Esta versión introduce las siguientes mejoras en la administración de recursos:

### Utilice Acoplar jerarquía de archivos para descargar asignaciones con nombres de archivo originales y metadatos asociados

Ahora puede utilizar la opción Acoplar jerarquía de archivos para descargar un mapa con su nombre de archivo original. Además, el paquete descargado incluye un archivo de `metadata.json`, lo que facilita el acceso y la reutilización de los metadatos asociados fuera de Experience Manager Guides.

Para obtener más información sobre cómo descargar archivos en Experience Manager Guides, vea [Descargar archivos](../user-guide/authoring-download-assets.md).

### Usar regex para habilitar o deshabilitar el procesamiento posterior

Ahora puede utilizar regex para habilitar o deshabilitar el posprocesamiento para carpetas. Esta mejora permite a los administradores definir reglas de procesamiento posterior que se aplican a varias carpetas o jerarquías de carpetas completas mediante una sola configuración, en lugar de especificar rutas de carpeta individuales.

Para obtener más información, vea [Use regex para habilitar o deshabilitar el procesamiento posterior](../cs-install-guide/conf-folder-post-processing.md#use-regex-to-enable-or-disable-post-processing).




