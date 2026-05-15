---
title: Configurar nombres de archivo automáticos basados en UUID
description: Aprenda a configurar nombres de archivo automáticos basados en UUID
exl-id: bdbdf119-b928-4ed2-bab3-d99370da8aa9
feature: Filename Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/HxTJaPGbwH31vitQ-Cu6wPyCuzZSWDXtq6xMY4hXEAI
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 197
ht-degree: 1%

---

# Configurar nombres de archivo automáticos basados en UUID {#id205QG070D5Z}

De forma predeterminada, cuando se crea un tema o un archivo de asignación, los autores tienen la opción de especificar también el nombre del archivo. Los autores son libres de asignar los nombres de archivo según sus requisitos. Sin embargo, esto puede generar incoherencia y se puede ver una amplia gama de nombres de archivos en un sistema de documentación grande. Como administrador, puede restringir el acceso de los autores a la asignación de nombres de archivo para los archivos que crean en el sistema. Para cada nuevo tema o archivo de asignación, puede elegir asignar automáticamente nombres de archivo basados en UUID.

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(propiedad\) para configurar los nombres de archivo automáticos basados en UUID:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uniquefilenames` | Booleano \(true/false\).<br> **Valor predeterminado**: false |

>[!NOTE]
>
> Cuando esta opción está activada, los autores no verán la opción de especificar el nombre del archivo al crear un nuevo tema o archivo de asignación. Se puede crear un nuevo tema o archivo de asignación desde la interfaz de usuario de Assets y el editor web.

**Tema principal:**[ Configurar nombres de archivo](conf-file-names.md)
