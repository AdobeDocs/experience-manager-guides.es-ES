---
title: Configurar nombres de archivo
description: Obtenga información sobre cómo deshabilitar el posprocesamiento para una carpeta cargada en Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# Deshabilitar el posprocesamiento de una carpeta

De forma predeterminada, todos los recursos cargados se procesan mediante el flujo de trabajo de recursos de actualización de DAM. Experience Manager Guides ejecuta un procesamiento adicional, denominado posprocesamiento, como parte de este flujo de trabajo. Esto también ayuda a generar los UUID

Al cargar los archivos y carpetas en el servidor *Adobe Experience Manager Assets*, también puede deshabilitar el posprocesamiento y la generación de UUID.

Las siguientes pestañas proporcionan instrucciones para deshabilitar el posprocesamiento para una carpeta en función de su configuración de Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Use las instrucciones de [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles (propiedad) para deshabilitar el posprocesamiento en una ruta determinada o ignorar el posprocesamiento de una carpeta:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `ignored.post.processing.paths` | Valor de cadena para establecer cualquier NODE_OPTIONS estándar (propiedad multivalor, cadenas con ruta que omiten `/` al final) <br> **Valor predeterminado**: `/content/dam/projects/translation_output` |
| `com.adobe.fmdita.config.ConfigManager` | `enabled.post.processing.paths` | Valor de cadena para establecer cualquier NODE_OPTIONS estándar (propiedad multivalor, cadenas con ruta que omiten `/` al final) <br> **Valor predeterminado**: `/content/dam` |

>[!TAB Local]

Realice los siguientes pasos para deshabilitar el posprocesamiento en una ruta determinada o ignorar el posprocesamiento de una carpeta:


1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.config.ConfigManager**.

1. Seleccione la opción **Rutas ignoradas para el procesamiento posterior** para ignorar una carpeta para el procesamiento posterior.

   Valor de cadena para establecer cualquier NODE_OPTIONS estándar (propiedad multivalor, cadenas con ruta que omiten `/` al final)

   **Valor predeterminado**: `/content/dam/projects/translation_output`

   >[!NOTE]
   >
   > Esta propiedad está desactivada de forma predeterminada y la pestaña Traducción está disponible en el panel de mapas.

1. Seleccione la opción **Rutas habilitadas para el procesamiento posterior** para habilitar una ruta para el procesamiento posterior.

   Valor de cadena para establecer cualquier NODE_OPTIONS estándar (propiedad multivalor, cadenas con ruta que omiten `/` al final)

   **Valor predeterminado**: `/content/dam/`

   >[!NOTE]
   >
   > Esta propiedad está desactivada de forma predeterminada y la pestaña Traducción está disponible en el panel de mapas.


1. Haga clic en **Guardar**.

>[!ENDTABS]

## Reglas para habilitar o deshabilitar el posprocesamiento

De forma predeterminada, el posprocesamiento se realiza para cada ruta de carpeta en la carpeta Experience Manager DAM. Las configuraciones se aplican a cualquier carpeta según las siguientes reglas:

* Si el elemento principal se omite para el posprocesamiento pero la carpeta secundaria está habilitada, el elemento secundario y todas sus sucesoras se considerarán habilitadas.
* Si el padre está habilitado para el posprocesamiento pero el hijo se ignora, el hijo y todas sus sucesoras se consideran ignoradas.
* Si la misma ruta de carpeta existe en las configuraciones ignore.post.processing.paths y enabled.post.processing.paths, se considera ignorada para el posprocesamiento.

