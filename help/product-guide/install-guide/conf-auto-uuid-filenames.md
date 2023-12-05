---
title: Configurar nombres de archivo automáticos basados en UUID
description: Aprenda a configurar nombres de archivo automáticos basados en UUID
exl-id: 2a599228-6d46-494f-a57a-96c3f30e073a
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '217'
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

1. Busque y haga clic en *com.adobe.fmdita.xmleditor.config.XmlEditorConfig* paquete.

1. Seleccione el **Usar nombres de archivo de sistema basados en UUID** opción.

1. Haga clic en **Guardar**.


>[!NOTE]
>
> Esta opción está desactivada de forma predeterminada. Cuando esta opción está activada, los autores no verán la opción de especificar el nombre del archivo al crear un nuevo tema o archivo de asignación. Se puede crear un nuevo tema o archivo de asignación desde la interfaz de usuario de Assets y el editor web.

**Tema principal:**[ Configurar nombres de archivo](conf-file-names.md)
