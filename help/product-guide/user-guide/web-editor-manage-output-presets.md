---
title: Administrar ajustes preestablecidos de salida del perfil global y de carpeta
description: AEM Obtenga información sobre cómo crear, editar, cambiar el nombre, duplicar y eliminar ajustes preestablecidos de salida de perfil global y de carpeta como usuarios administrativos en las Guías de administración de perfiles.
exl-id: 549c9fe2-77f8-423c-8b3e-b43e56055732
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# Administrar ajustes preestablecidos de salida del perfil global y de carpeta {#id22BLJ0D0V1U}

Los ajustes preestablecidos de Perfil global y de carpeta solo están disponibles para los usuarios administrativos de nivel de carpeta.

AEM Como administrador, las Guías de le permiten crear y administrar ajustes preestablecidos de salida para los Perfiles global y de carpeta. A continuación, puede utilizar fácilmente estos ajustes preestablecidos de salida para generar resultados para todas las asignaciones relacionadas con ese perfil global o de carpeta.

Realice los siguientes pasos para crear un ajuste preestablecido de salida para los perfiles global y de carpeta:

1. Seleccione el mapa DITA para el que desea crear un ajuste preestablecido de salida.
1. Seleccione el **Editar temas** de la opción **Opciones** del archivo de asignación. El archivo de asignación se abre para editarlo en el Editor Web.
1. En el **Output** , seleccione el icono + para crear un ajuste preestablecido de salida para el mapa DITA.

   ![](images/add-global-output-preset.png){width="350" align="left"}

1. Introduzca los siguientes detalles en la **Añadir ajuste preestablecido** diálogo:
   - Tipo
   - Nombre
   - Target \(para ajuste preestablecido de la base de conocimiento\)
1. Seleccione el **Añadir a perfil de carpeta** para crear un ajuste preestablecido de salida para el perfil de carpeta relacionado y haga clic en **Añadir**. El ajuste preestablecido se crea y aparece bajo la etiqueta **Output** de todas las asignaciones relacionadas. \( ![](images/global-preset-icon.svg)El icono \) indica un ajuste preestablecido de nivel de perfil de carpeta.
1. Introduzca los detalles de configuración. Para obtener más información sobre los ajustes preestablecidos de salida, consulte [Explicación de los ajustes preestablecidos de salida](./generate-output-understand-presets.md).

   >[!NOTE]
   >
   > Estos ajustes preestablecidos añadidos al perfil de carpeta son independientes de las asignaciones, por lo que las configuraciones específicas de asignación no están presentes para estos ajustes preestablecidos.

1. Puede seleccionar el **Generar ajuste preestablecido** en la parte superior para generar la salida de las asignaciones relacionadas con el ajuste preestablecido de salida creado. Verá el estado del proceso de generación de resultados. Para ver el resultado, pase el puntero del ratón sobre el tema y haga clic en **Ver salida**.

>[!NOTE]
>
> Guías del PDF también proporciona un ajuste preestablecido de salida de AEM para generar la salida de los mapas DITA.

**Otras operaciones del menú Opciones**

También puede realizar las siguientes operaciones en el ajuste preestablecido desde el menú Opciones:

- Seleccione el ajuste preestablecido como ajuste preestablecido de PDF predeterminado. A continuación, el ajuste preestablecido seleccionado se utilizaría como el ajuste preestablecido predeterminado para generar la salida del PDF utilizando **Descargar como PDF** opción para un mapa.
- **Editar**, **Cambiar nombre**, **Duplicar**, o **Eliminar** un ajuste preestablecido de salida existente del **Opciones** menú.

>[!NOTE]
>
> Cuando se elimina un ajuste preestablecido de salida en Perfiles globales y de carpeta, se reflejará en todas las asignaciones relacionadas y no aparecerá en la **Output** pestaña.

**Tema principal:**[ Trabajar con el editor web](web-editor.md)
