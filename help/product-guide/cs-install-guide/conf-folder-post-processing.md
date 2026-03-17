---
title: Configurar nombres de archivo
description: Obtenga información sobre cómo deshabilitar el posprocesamiento para una carpeta cargada en Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: 42722c6f-1b1c-4a7e-89ef-a373623eb774
source-git-commit: 635206ca34db633a998b0156e2549d86a83f8131
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 0%

---

# Deshabilitar el posprocesamiento de una carpeta

De forma predeterminada, todos los recursos cargados se procesan mediante el flujo de trabajo de recursos de actualización de DAM. Experience Manager Guides ejecuta un procesamiento adicional, denominado posprocesamiento, como parte de este flujo de trabajo. Esto también ayuda a generar los UUID

Al cargar los archivos y carpetas en el servidor *Adobe Experience Manager Assets*, también puede deshabilitar el posprocesamiento y la generación de UUID.

Use las instrucciones de [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles (propiedad) para deshabilitar el posprocesamiento en una ruta determinada o ignorar el posprocesamiento de una carpeta:

>[!NOTE]
>
> También puede utilizar expresiones regulares (regex) para definir reglas que se apliquen a varias carpetas o a una jerarquía de carpetas completa. Para obtener más información, vea la sección [Usar regex para habilitar o deshabilitar el procesamiento posterior](#use-regex-to-enable-or-disable-post-processing).

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `ignored.post.processing.paths` | Valor de cadena para establecer cualquier NODE_OPTIONS estándar (propiedad multivalor, cadenas con ruta que omiten `/` al final o regex) <br> **Valor predeterminado**: `/content/dam/projects/translation_output` |

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `enabled.post.processing.paths` | Valor de cadena para establecer cualquier NODE_OPTIONS estándar (propiedad multivalor, cadenas con ruta que omiten `/` al final o regex) <br> **Valor predeterminado**: `/content/dam` |

## Reglas para habilitar o deshabilitar el posprocesamiento

De forma predeterminada, el posprocesamiento se realiza para cada ruta de carpeta en la carpeta Experience Manager DAM. Las configuraciones se aplican a cualquier carpeta según las siguientes reglas:

* Si el elemento principal se omite para el posprocesamiento pero la carpeta secundaria está habilitada, el elemento secundario y todas sus sucesoras se considerarán habilitadas.
* Si el padre está habilitado para el posprocesamiento pero el hijo se ignora, el hijo y todas sus sucesoras se consideran ignoradas.
* Si existe la misma ruta de carpeta en las configuraciones `ignored.post.processing.paths` y `enabled.post.processing.paths`, se considera ignorada para el posprocesamiento.

## Utilice regex para habilitar o deshabilitar el posprocesamiento

En lugar de especificar rutas de carpeta individuales, puede utilizar expresiones regulares (regex) para definir reglas que se apliquen a varias carpetas o a jerarquías de carpetas completas.

Los patrones regex se evalúan en relación con la ruta completa del recurso durante el posprocesamiento.

Cuando se utilizan expresiones regulares (regex) para configurar rutas de posprocesamiento ignoradas y habilitadas, AEM Guides evalúa ambas configuraciones según la ruta del recurso. Si una ruta coincide con una regla de omisión y una regla de activación, las reglas de omisión siempre tienen prioridad.

Los siguientes ejemplos ilustran cómo se evalúan las reglas de omisión y activación basadas en regex.

## Situaciones de evaluación de regex para el posprocesamiento

### Omitir jerarquía principal, habilitar carpeta específica

**Omitir regex**

`regex:/content/dam/lang-test/.*`

**Habilitar regex**

`regex:/content/dam/lang-test/.*/parent1`

En el ejemplo anterior, el posprocesamiento se deshabilitará para `/content/dam/lang-test/en/parent1`.

Aunque la ruta coincide con la expresión regular habilitada, ya coincide con la expresión regular omitida. Las reglas de omisión tienen prioridad, por lo que el posprocesamiento no está habilitado.

### Ignorar carpeta específica, habilitar jerarquía más amplia

**Omitir regex**

`regex:/content/dam/lang-test/.*/parent1`

**Habilitar regex**

`regex:/content/dam/lang-test/.*`

En el ejemplo anterior, el posprocesamiento se deshabilitará para `/content/dam/lang-test/en/parent1` y se habilitará para `/content/dam/lang-test/en/parent2`.

La ruta `parent1` se omite explícitamente y permanece deshabilitada. Se procesarán otras carpetas que coincidan únicamente con la expresión regular habilitada.

### Omitir carpeta principal, habilitar carpeta secundaria

**Omitir regex**

`regex:/content/dam/lang-test/.*/parent1`

**Habilitar regex**

`regex:/content/dam/lang-test/.*/parent1/child1`

En el ejemplo anterior, el posprocesamiento se deshabilitará para `/content/dam/lang-test/en/parent1` y `/content/dam/lang-test/en/parent1/child2`, y se habilitará para `/content/dam/lang-test/en/parent1/child1`.

Se procesa la carpeta secundaria habilitada explícitamente por regex. Otras carpetas secundarias permanecen deshabilitadas porque su ruta principal coincide con la regex ignorada.

### Omitir carpeta secundaria específica, habilitar jerarquía principal

**Omitir regex**

`regex:/content/dam/lang-test/.*/parent1/child1`

**Habilitar regex**

`regex:/content/dam/lang-test/.*/parent1`

En el ejemplo anterior, el posprocesamiento se deshabilitará para `/content/dam/lang-test/en/parent1/child1` y se habilitará para `/content/dam/lang-test/en/parent1` y `/content/dam/lang-test/en/parent1/child2`.

Solo se omite la carpeta secundaria omitida explícitamente. La carpeta principal y otras carpetas secundarias se procesan porque coinciden con la regex de habilitación y no con la regex de omisión.

