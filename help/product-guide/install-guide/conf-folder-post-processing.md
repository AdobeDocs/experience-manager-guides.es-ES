---
title: Configurar nombres de archivo
description: Obtenga información sobre cómo deshabilitar el posprocesamiento para una carpeta cargada en Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 532e7c562a233619a8c4b7cbdbaef44bc73eb4b2
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---


# Deshabilitar el posprocesamiento de una carpeta

De forma predeterminada, todos los recursos cargados se procesan mediante el flujo de trabajo de recursos de actualización de DAM. Guías del Experience Manager ejecuta un procesamiento adicional, denominado posprocesamiento, como parte de este flujo de trabajo. Esto también ayuda a generar los UUID

Al cargar los archivos y carpetas en *Adobe Experience Manager Assets* También puede deshabilitar el posprocesamiento y la generación de UUID.


Realice los siguientes pasos para deshabilitar el posprocesamiento en una ruta determinada o ignorar el posprocesamiento de una carpeta:


1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en **com.adobe.fmdita.config.ConfigManager** paquete.

1. Seleccione el **Rutas ignoradas para el procesamiento posterior** para ignorar una carpeta para el procesamiento posterior.

   Valor de cadena para establecer cualquier NODE_OPTIONS estándar (propiedad multivalor, cadenas con ruta que omiten `/` al final)

   **Valor predeterminado**: `/content/dam/projects/translation_output`

   >[!NOTE]
   >
   > Esta propiedad está desactivada de forma predeterminada y la pestaña Traducción está disponible en el panel de mapas.

1. Seleccione el **Rutas habilitadas para el procesamiento posterior** , para habilitar una ruta para el posprocesamiento.

   Valor de cadena para establecer cualquier NODE_OPTIONS estándar (propiedad multivalor, cadenas con ruta que omiten `/` al final)

   **Valor predeterminado**: `/content/dam/`

   >[!NOTE]
   >
   > Esta propiedad está desactivada de forma predeterminada y la pestaña Traducción está disponible en el panel de mapas.


1. Haga clic en **Guardar**.



## Reglas para habilitar o deshabilitar el posprocesamiento

De forma predeterminada, el posprocesamiento se realiza para cada ruta de carpeta en la carpeta DAM de Experience Manager. Las configuraciones se aplican a cualquier carpeta según las siguientes reglas:

* Si el elemento principal se omite para el posprocesamiento pero la carpeta secundaria está habilitada, el elemento secundario y todas sus sucesoras se considerarán habilitadas.
* Si el padre está habilitado para el posprocesamiento pero el hijo se ignora, el hijo y todas sus sucesoras se consideran ignoradas.
* Si la misma ruta de carpeta existe en las configuraciones ignore.post.processing.paths y enabled.post.processing.paths, se considera ignorada para el posprocesamiento.
