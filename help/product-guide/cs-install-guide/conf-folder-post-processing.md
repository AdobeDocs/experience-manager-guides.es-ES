---
title: Configurar nombres de archivo
description: Obtenga información sobre cómo deshabilitar el posprocesamiento para una carpeta cargada en Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: fedd04f4a261ec199f86cb38ecd57e76b9393ae5
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 1%

---


# Deshabilitar el posprocesamiento de una carpeta

De forma predeterminada, todos los recursos cargados se procesan mediante el flujo de trabajo de recursos de actualización de DAM. Guías del Experience Manager ejecuta un procesamiento adicional, denominado posprocesamiento, como parte de este flujo de trabajo. Esto también ayuda a generar los UUID

Al cargar los archivos y carpetas en *Adobe Experience Manager Assets* También puede deshabilitar el posprocesamiento y la generación de UUID.


Siga las instrucciones de [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles (propiedad) para deshabilitar el posprocesamiento en una ruta determinada o ignorar el posprocesamiento de una carpeta:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `ignored.post.processing.paths` | Valor de cadena para establecer cualquier NODE_OPTIONS estándar (propiedad multivalor, cadenas con ruta que omiten `/` al final) <br> **Valor predeterminado**: `/content/dam/projects/translation_output` |


| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `enabled.post.processing.paths` | Valor de cadena para establecer cualquier NODE_OPTIONS estándar (propiedad multivalor, cadenas con ruta que omiten `/` al final) <br> **Valor predeterminado**: `/content/dam` |


## Reglas para habilitar o deshabilitar el posprocesamiento

De forma predeterminada, el posprocesamiento se realiza para cada ruta de carpeta en la carpeta DAM de Experience Manager. Las configuraciones se aplican a cualquier carpeta según las siguientes reglas:

* Si el elemento principal se omite para el posprocesamiento pero la carpeta secundaria está habilitada, el elemento secundario y todas sus sucesoras se considerarán habilitadas.
* Si el padre está habilitado para el posprocesamiento pero el hijo se ignora, el hijo y todas sus sucesoras se consideran ignoradas.
* Si la misma ruta de carpeta existe en las configuraciones ignore.post.processing.paths y enabled.post.processing.paths, se considera ignorada para el posprocesamiento.
