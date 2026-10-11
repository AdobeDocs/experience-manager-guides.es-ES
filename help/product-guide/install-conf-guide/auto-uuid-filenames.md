---
title: Configurar nombres de archivo automáticos basados en UUID
description: Aprenda a configurar nombres de archivo automáticos basados en UUID
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: 2b591ddc-173b-484a-995f-1b3322babbbd
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
    internal-label: Filename configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 1%
---
# Configurar nombres de archivo automáticos basados en UUID {#id205QG070D5Z}

De forma predeterminada, cuando se crea un tema o un archivo de asignación, los autores tienen la opción de especificar también el nombre del archivo. Los autores son libres de asignar los nombres de archivo según sus requisitos. Sin embargo, esto puede generar incoherencia y se puede ver una amplia gama de nombres de archivos en un sistema de documentación grande. Como administrador, puede restringir el acceso de los autores a la asignación de nombres de archivo para los archivos que crean en el sistema. Para cada nuevo tema o archivo de asignación, puede elegir asignar automáticamente nombres de archivo basados en UUID.

Las siguientes pestañas proporcionan instrucciones para configurar los nombres de archivo automáticos en función del UUID según la configuración de Experience Manager Guides: Cloud Service o On-Premise.


>[!BEGINTABS]

>[!TAB Cloud Service]

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(propiedad\) para configurar los nombres de archivo automáticos basados en UUID:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uniquefilenames` | Booleano \(true/false\).<br> **Valor predeterminado**: false |

>[!NOTE]
>
> Cuando esta opción está activada, los autores no verán la opción de especificar el nombre del archivo al crear un nuevo tema o archivo de asignación. Se puede crear un nuevo tema o archivo de asignación desde la interfaz de usuario de Assets y el Editor.

>[!TAB Local]

Realice los siguientes pasos para asignar automáticamente el nombre de archivo basado en UUID a todos los archivos nuevos creados en el sistema:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete *com.adobe.fmdita.xmleditor.config.XmlEditorConfig*.

1. Seleccione la opción **Usar nombres de archivo del sistema basados en UUID**.

1. Haga clic en **Guardar**.


>[!NOTE]
>
> Esta opción está desactivada de forma predeterminada. Cuando esta opción está activada, los autores no verán la opción de especificar el nombre del archivo al crear un nuevo tema o archivo de asignación. Se puede crear un nuevo tema o archivo de asignación desde la interfaz de usuario de Assets y el Editor.

>[!ENDTABS]
