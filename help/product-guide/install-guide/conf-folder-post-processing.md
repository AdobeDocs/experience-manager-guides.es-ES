---
title: Configurar nombres de archivo
description: Obtenga información sobre cómo deshabilitar el posprocesamiento para una carpeta cargada en Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: ff6e1322-9655-42aa-b353-199c70c9de49
source-git-commit: e84a00237e61275c6cd1ddd312883ac4f66b65ff
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 0%

---

# Deshabilitar el posprocesamiento de una carpeta

De forma predeterminada, todos los recursos cargados se procesan mediante el flujo de trabajo de recursos de actualización de DAM. Experience Manager Guides ejecuta un procesamiento adicional, denominado posprocesamiento, como parte de este flujo de trabajo. Esto también ayuda a generar los UUID.

Al cargar los archivos y carpetas en el servidor *Adobe Experience Manager Assets*, también puede deshabilitar el posprocesamiento y la generación de UUID.


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

>[!NOTE]
>
> Además de las rutas ignoradas y habilitadas configuradas mediante la configuración OSGi, el comportamiento posterior al procesamiento también se ve influido por un nodo de nivel de repositorio ubicado en `/var/dxml/postprocess/ignoredPaths`. <br> Si una carpeta se excluye inesperadamente del posprocesamiento y no aparece en la configuración de OSGi, se recomienda comprobar este nodo de repositorio. Si la ruta de acceso aparece allí y está establecida en `true`, se omitirá. Para volver a habilitar el procesamiento, puede quitar la propiedad correspondiente manualmente del nodo.

## Reglas para habilitar o deshabilitar el posprocesamiento

De forma predeterminada, el posprocesamiento se realiza para cada ruta de carpeta en la carpeta Experience Manager DAM. Las configuraciones se aplican a cualquier carpeta según las siguientes reglas:

* Si el elemento principal se omite para el posprocesamiento pero la carpeta secundaria está habilitada, el elemento secundario y todas sus sucesoras se considerarán habilitadas.
* Si el padre está habilitado para el posprocesamiento pero el hijo se ignora, el hijo y todas sus sucesoras se consideran ignoradas.
* Si la misma ruta de carpeta existe en las configuraciones ignore.post.processing.paths y enabled.post.processing.paths, se considera ignorada para el posprocesamiento.
