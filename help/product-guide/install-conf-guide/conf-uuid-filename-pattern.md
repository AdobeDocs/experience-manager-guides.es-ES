---
title: Configurar patrón de nombre de archivo UUID
description: Obtenga información sobre cómo configurar el patrón de nombres de archivo UUID
feature: Migration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---

# Configurar patrón de nombre de archivo UUID

Al importar contenido, no es necesario que los nombres de archivo estén basados en el UUID. En un sistema que utiliza nombres de archivo basados en UUID, es obligatorio que se haga referencia a todos los archivos utilizando sus UUID en lugar de sus nombres de archivo originales. Si un archivo importado no tiene nombres de archivo basados en UUID, puede configurar el sistema para agregar un UUID a su propiedad de archivo. A continuación, este UUID se utiliza para hacer referencia a estos archivos donde UUID no se utiliza para nombrar los archivos.

## Pasos para configurar el patrón de nombres de archivo UUID

Las siguientes pestañas proporcionan instrucciones para configurar el patrón de nombre de archivo UUID en función de la configuración de Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar el patrón de nombre de archivo UUID:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `uuid.regex` | Cadena que especifica la regex para el patrón de nombre de archivo UUID. <br> Si un archivo no sigue el patrón especificado, se agrega un UUID a la propiedad del archivo y todas las referencias al archivo se actualizan con el UUID asignado al archivo. <br> **Valor predeterminado**: `"^GUID-(?<id>.*)"` |

>[!TAB Local]

Realice los siguientes pasos para comprobar los nombres de archivo con un patrón UUID y asignar UUID a archivos que no tienen un UUID asignado:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y seleccione el paquete *com.adobe.fmdita.config.ConfigManager*.

1. En la propiedad **UUID Filename Patterns**, especifique un motivo para comprobar los nombres de los archivos importados.

   Si un archivo no sigue el patrón especificado, se agrega un UUID a la propiedad del archivo y todas las referencias al archivo se actualizan con el UUID asignado al archivo.

1. Seleccione **Guardar**.

>[!ENDTABS]





