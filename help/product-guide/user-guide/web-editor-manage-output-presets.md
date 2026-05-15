---
title: Administrar ajustes preestablecidos de salida del perfil global y de carpeta
description: Obtenga información sobre cómo crear, editar, cambiar el nombre, duplicar y eliminar ajustes preestablecidos de salida de perfil global y de carpeta como usuarios administrativos en AEM Guides.
exl-id: 549c9fe2-77f8-423c-8b3e-b43e56055732
feature: Authoring, Features of Web Editor, Publishing
role: User
TQID: https://experienceleague.adobe.com/FCtMWJZh9bc9sayuHsMWnd-c6mZ0Uvi0ZAgv2lOSu-4
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 478
ht-degree: 0%

---

# Administrar ajustes preestablecidos de salida del perfil global y de carpeta {#id22BLJ0D0V1U}

Los ajustes preestablecidos de Perfil global y de carpeta solo están disponibles para los usuarios administrativos de nivel de carpeta.

Como administrador, Adobe Experience Manager Guides le permite crear y administrar ajustes preestablecidos de salida para los Perfiles global y de carpeta. A continuación, puede utilizar fácilmente estos ajustes preestablecidos de salida para generar resultados para todas las asignaciones relacionadas con ese perfil global o de carpeta.

Realice los siguientes pasos para crear un ajuste preestablecido de salida para los perfiles global y de carpeta:

1. Seleccione el mapa DITA para el que desea crear un ajuste preestablecido de salida.
1. Seleccione la opción **Editar temas** en el menú **Opciones** del archivo de asignación. El archivo de mapa se abre para editarlo en el Editor.
1. Seleccione el icono **Abrir en la consola de mapas** para abrir el archivo de mapa en la consola de mapas.
1. En la consola Mapa, vaya a la pestaña **Ajustes preestablecidos de salida** y, a continuación, seleccione el icono + para crear un ajuste preestablecido de salida para el mapa DITA.

   ![](images/add-global-output-preset.png){width="350"}

1. Escriba los siguientes detalles en el cuadro de diálogo **Agregar ajuste preestablecido**:
   - Tipo
   - Nombre
   - Target \(para ajuste preestablecido de la base de conocimiento\)
1. Seleccione la casilla de verificación **Agregar al perfil de carpeta** para crear un ajuste preestablecido de salida para el perfil de carpeta relacionado y, a continuación, seleccione **Agregar**. El ajuste preestablecido se crea y aparece en la ficha **Ajustes preestablecidos de salida** de todas las asignaciones relacionadas. El icono \( ![](images/global-preset-icon.svg)\) indica un ajuste preestablecido de nivel de perfil de carpeta.
1. Introduzca los detalles de configuración. Para obtener más información sobre los ajustes preestablecidos de salida, vea [Explicación de los ajustes preestablecidos de salida](./generate-output-understand-presets.md).

   >[!NOTE]
   >
   > Estos ajustes preestablecidos añadidos al perfil de carpeta son independientes de las asignaciones, por lo que las configuraciones específicas de asignación no están presentes para estos ajustes preestablecidos.

1. Puede seleccionar el icono **Generar salida** en la esquina superior derecha para generar la salida de los mapas relacionados con el ajuste preestablecido de salida creado. Puede ver el estado del proceso de generación de resultados. Para ver el resultado, seleccione **Ver resultado** en el cuadro de diálogo **Éxito**.

>[!NOTE]
>
> Experience Manager Guides también proporciona un ajuste preestablecido de salida PDF para generar la salida de los mapas DITA.

**Otras operaciones del menú Opciones**

También puede realizar las siguientes operaciones en el ajuste preestablecido desde el menú Opciones:

- **Generar salida**: Permite generar una salida para un ajuste preestablecido existente.
- **Ver salida** y **Ver registro**: vínculos rápidos para ver la salida y los registros generados.
- **Cambiar nombre**, **Duplicar** o **Eliminar** un ajuste preestablecido de salida existente del menú **Opciones**.
- **PDF predeterminado**: permite seleccionar el ajuste preestablecido de PDF existente como ajuste preestablecido de PDF predeterminado. El ajuste preestablecido seleccionado sería, y luego se usaría como el ajuste preestablecido predeterminado para generar la salida de PDF usando la opción **Descargar como PDF** para un mapa.

>[!NOTE]
>
> Cuando se elimina un ajuste preestablecido de salida en Perfiles globales y de carpeta, se reflejará en todas las asignaciones relacionadas y no aparecerá en la pestaña **Ajustes preestablecidos de salida**.

**Tema principal:**&#x200B;[&#x200B; Trabajar con el editor web](web-editor.md)
