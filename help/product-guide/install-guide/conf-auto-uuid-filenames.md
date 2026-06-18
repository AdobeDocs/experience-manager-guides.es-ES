---
title: Configurar nombres de archivo automáticos basados en UUID
description: Aprenda a configurar nombres de archivo automáticos basados en UUID
exl-id: 2a599228-6d46-494f-a57a-96c3f30e073a
feature: Filename Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/2oXpOlXt4gZ3GELX7SmwPJoWJYM71f0cZFy2--M6AYM
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 220
ht-degree: 0%

---

# Configurar nombres de archivo automáticos basados en UUID {#id205QG070D5Z}

De forma predeterminada, cuando se crea un tema o un archivo de asignación, los autores tienen la opción de especificar también el nombre del archivo. Los autores son libres de asignar los nombres de archivo según sus requisitos. Sin embargo, esto puede generar incoherencia y se puede ver una amplia gama de nombres de archivos en un sistema de documentación grande. Como administrador, puede restringir el acceso de los autores a la asignación de nombres de archivo para los archivos que crean en el sistema. Para cada nuevo tema o archivo de asignación, puede elegir asignar automáticamente nombres de archivo basados en UUID.

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

**Tema principal:**&#x200B;[&#x200B; Configurar nombres de archivo](conf-file-names.md)
