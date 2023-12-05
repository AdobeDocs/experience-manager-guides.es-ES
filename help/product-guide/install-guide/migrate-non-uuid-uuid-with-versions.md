---
title: Conversión de contenido no UUID con versiones a contenido UUID
description: Obtenga información sobre cómo migrar contenido que no sea UUID con versiones de.
exl-id: 9387e0d1-906c-4e5c-a7a0-0ed1600f5eb6
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1287'
ht-degree: 1%

---

# Migración de contenido que no sea UUID con versiones

Realice estos pasos para migrar el contenido que no es UUID con versiones al contenido UUID.

## Matriz de compatibilidad

| AEM Versión actual de las guías de usuario (no UUID) | Versión requerida para migrar a UUID | Ruta de actualización admitida |
|---|---|---|
| 3.8.5 | 4.0 sin UUID | Instale 4.1 (UUID) y ejecute la migración |
| 4.0, 4.0.x, 4.1 o 4.1.x | Igual que el UUID actual que no es | Instale 4.1 (UUID) y ejecute la migración |
| 4.2 o superior | ND | Aún no es compatible |

## Paquetes necesarios

1. **Depuración de versiones**: `com.adobe.guides.version-purge-1.0.11.zip` (opcional)
1. **Premigración**: `com.adobe.guides.pre-uuid-migration-1.0.7.zip`
1. **Migración**: `com.adobe.guides.uuid-upgrade-1.0.17`
1. **Posterior a migración**: `com.adobe.guides.post-uuid-migration-1.0.2.zip`


## Premigración

1. (Opcional) Realice la depuración de versiones en el contenido para eliminar versiones innecesarias y acelerar el proceso de migración. Para realizar la depuración de la versión 4.1 (NO compatible con la 4.0), instale el paquete `com.adobe.guides.version-purge-1.0.11.zip`y vaya a la interfaz de usuario de con esta dirección URL `http://<server-name> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`.

   >[!NOTE]
   >
   >Esta utilidad no elimina ninguna versión utilizada en las líneas de base o revisiones, ni tiene etiquetas.
1. Instale el paquete previo a la migración (`com.adobe.guides.pre-uuid-migration-1.0.7.zip`).

1. Ejecute la siguiente consulta para obtener un informe con un tiempo estimado (ETA) de cuánto tiempo tardará la migración e informa si hay archivos con problemas de contenido que no se migrarían.

>[!NOTE]
>
>Necesita permiso de administrador para ejecutar la migración.


| URL de extremo | Tipo de solicitud | Parámetro de consulta | Resultados esperados |
|---|---|---|---|
| `/bin/guides/pre_uuid_upgrade` <br> <br>**Por ejemplo**: http://localhost:4502/bin/guides/pre_uuid_upgrade?root=/content/dam | GET | **raíz**: carpeta raíz<br> **Valor**: `/content/dam` para todo el repositorio. | Se creará un informe previo a la migración (.csv) con la cantidad de archivos, las versiones totales y los errores. <br><br> **Salida de ejemplo**:<br>Carpeta raíz: /content/dam <br>Total de archivos: 2697 <br>Total de versiones: 10380 <br>Número de archivos con errores: 28 <br>AEM Se encontrará disponible un informe detallado a través de CRX de la en `/content/uuid-pgrade/UuidMigrationReport_1688400131039.csv` |

Este paso podría fallar si hay muchos archivos DITA en el sistema. Para solucionarlo, aumente el límite del número de archivos atravesados en la consulta aumentando el valor de *Límite de lectura en memoria (queryLimitReads)* en Apache Jackrabbit Query Engine Settings Service de 100000 un número mayor que el número total de recursos DITA presentes en el sistema.

## Migración

### Paso 1: Actualizar la configuración

1. AEM Asegúrese de que el espacio libre disponible sea al menos 10 veces el espacio que ocupa el usuario (directorio crx-quickstart) durante la migración. Una vez completada la migración, puede recuperar la mayor parte del espacio en disco ejecutando la compactación (consulte [Limpieza de revisión](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en)).

1. Activar *Activar iniciadores de flujo de trabajo de procesamiento posterior* in `com.adobe.fmdita.config.ConfigManager` y *Habilitar procesamiento posterior de la versión* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Instale la versión UUID de la versión compatible sobre la versión que no es UUID. Por ejemplo, si utiliza una compilación 4.0 sin UUID o una compilación 4.1 sin UUID, debe instalar la versión 4.1 de UUID.

1. Instale el nuevo paquete para la migración de uuid (`com.adobe.guides.uuid-upgrade-1.0.17`).

1. Deshabilite los siguientes flujos de trabajo y cualquier otro flujo de trabajo que se ejecute en `/content/dam` uso de lanzadores en `http://localhost:4502/libs/cq/workflow/content/console.html`.

   * Flujo de trabajo de recursos de actualización DAM
   * Flujo de trabajo de reescritura de metadatos DAM

1. Deshabilitar *Activar iniciadores de flujo de trabajo de procesamiento posterior* in `com.adobe.fmdita.config.ConfigManager` y deshabilitar *Habilitar procesamiento posterior de la versión* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`.

1. Deshabilite la propiedad Habilitar validación (`validation.enabled`) en el servicio Day CQ Tagging.

1. Asegúrese de que `uuid.regex` la carpeta de propiedades está correctamente configurada en `com.adobe.fmdita.config.ConfigManager`. Si está en blanco, establézcalo en el valor predeterminado - `^GUID-(?<id>.*)`.
1. Añadir un registrador independiente para `com.adobe.fmdita.uuid.upgrade.UuidUpgrade` La respuesta del explorador también está disponible en `/content/uuid-upgrade/logs`.

### Paso 2: Ejecutar el script y validar

Ejecute la consulta determinada en una carpeta con datos más pequeños antes de ejecutarla en `/content/dam`.

>[!TIP]
>
>Puede comprobar si todos los archivos de la carpeta se han actualizado correctamente y si todas las características funcionan únicamente para esa carpeta.

| URL de extremo | Tipo de solicitud | Parámetro de consulta | Resultados esperados |
|---|---|---|---|
| `/bin/guides/uuid_upgrade`<br><br> **Por ejemplo**: `http://localhost:4502/bin/guides/uuid_upgrade?root=/content/dam/test` | GET | **raíz**: carpeta raíz <br>**Valor**: /content/dam para todo el repositorio.<br><br>**ignoreImageVersions**<br> **Valor**: true/false (ignora el procesamiento de las versiones de la imagen. El valor predeterminado es false) | Informe de migración con Lista de archivos migrados correctamente, no se pudo actualizar, se actualizó con errores y el tiempo total empleado. <br><br> **Salida de ejemplo**: <br> [INFORMACIÓN] Error en la lista de archivos:0 <br>[INFORMACIÓN] No. de archivos actualizados correctamente: 2241 <br>[INFORMACIÓN] No. Número de archivos actualizados con errores: 28 <br>[INFORMACIÓN] No. No se pudo actualizar el número de archivos: 0 <br> [INFORMACIÓN] Tiempo total empleado: 0:37:03,131 |

>[!NOTE]
>
> La migración de contenido se puede ejecutar en el nivel de carpeta o en el modo completo `/content/dam` o en la misma carpeta (volver a ejecutar la migración).

Además, es importante asegurarse de que la migración de contenido también se realiza para todos los recursos multimedia, como imágenes y gráficos, que se han utilizado en el contenido DITA.

#### Migración de línea base

Ejecute la consulta en la carpeta que ya ha migrado para migrar las líneas de base que contiene.

| URL de extremo | Tipo de solicitud | Parámetro de consulta | Resultados esperados |
|---|---|---|---|
| `/bin/guides/baseline_uuid_upgrade`<br><br> **Por ejemplo**: ` http://localhost:4502/bin/guides/baseline_uuid_upgrade?root=/content/dam/test` | GET | **raíz**: carpeta raíz <br> **Valor**: /content/dam para todo el repositorio. <br><br> **ignoreImageVersions**<br> **Valor**: true/false <br>(Omite el procesamiento de las versiones de la imagen. El valor predeterminado es false) <br><br> **doReviews** <br> **Valor**: true/false <br> (Si las revisiones deben actualizarse o no. El valor predeterminado es false). Informe de migración con Lista de archivos migrados correctamente, no se pudo actualizar, se actualizó con errores y el tiempo total empleado. <br> <br> **Salida de ejemplo**:<br>[INFORMACIÓN] Error en la lista de archivos <br> [INFORMACIÓN] No. de archivos actualizados correctamente 2241<br> [INFORMACIÓN] No. de archivos actualizados con errores 28<br>[INFORMACIÓN] No. de archivos no se pudo actualizar 0<br>[INFORMACIÓN] Tiempo total empleado: 0:37:03,131 |


### Paso 3: Restaurar la configuración

Una vez que el servidor se haya migrado correctamente, habilite el posprocesamiento, el etiquetado y los siguientes flujos de trabajo (incluidos todos los demás flujos de trabajo que están desactivados inicialmente durante la migración) para seguir trabajando en el servidor.

* Flujo de trabajo de recursos de actualización DAM
* Flujo de trabajo de metadatos DAM

>[!NOTE]
>
>Si algunos archivos no se procesan o se dañan antes de la migración y se dañan antes de la migración y se dañan incluso después de la migración.

## Validación de migración

1. Instale el paquete de migración posterior a uuid (`com.adobe.guides.post-uuid-migration-1.0.2.zip`).

1. Ejecute la siguiente consulta para comprobar que no se han producido errores durante la migración que hayan provocado la rotura de ningún vínculo. Esta secuencia de comandos identificará si había algún vínculo que no se hubiera roto antes, pero que se haya roto ahora por algún motivo.

   | URL de extremo | Tipo de solicitud | Parámetro de consulta | Resultados esperados |
   |---|---|---|---|
   | `/bin/guides/get_broken_links` <br> <br> **Por ejemplo**:<br>`http://localhost:4502/bin/guides/get_broken_links` | GET | ND | Informe de migración con el número total de archivos que tienen UUID rotos y sus respectivas rutas de archivo. <br> <br> **Salida de ejemplo**:<br>[DEPURAR] Comprobando si todas estas GUID se utilizan en el contenido.<br>[DEPURAR] Número total de archivos que pueden tener UUID rotos: 0 <br>[DEPURAR] Rutas que potencialmente tienen UUID rotos:0 |

1. Una vez completada la migración, la mayor parte del espacio en disco se puede recuperar ejecutando compactación (consulte `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en`).

## Migración de contenido delta

1. Para migrar el contenido delta del servidor activo (que no sea UUID) al servidor uuid actual, instale el script de premigración en el servidor que no sea UUID.

1. Ejecute la siguiente consulta en todo el conjunto de datos (o subcarpeta) para identificar y exportar todos los archivos modificados después de la marca de tiempo determinada: La marca de tiempo utiliza el formato ISO8601 para las fechas y horas ( AAAA-MM-DDTHH:mm:ss.SSSZ) y también permite representaciones parciales, como AAAA-MM-DD.

   | URL de extremo | Tipo de solicitud | Parámetro de consulta | Resultados esperados |
   |---|---|---|---|
   | `/bin/guides/data_export`<br><br>**Por ejemplo**: <br> `http://localhost:4502/bin/guides/data_export?timestamp=2023-07-11&root=/content/dam` | GET | **timestamp** <br> **Valor**: AAAA-MM-DD<br><br> **raíz**: carpeta raíz <br> **Valor**: `/content/dam` para todo el repositorio. | Se crea un archivo zip con contenido delta en /var/xml/exports. <br> <br>**Muestra**: dataexport_1689761491218.zip (se creará el archivo) |

1. Descargue el archivo zip exportado por el script. La última línea de la respuesta debe proporcionar la ruta del archivo zip generado (almacenado en /var/xml/exports en el sistema).

1. Cargue el archivo zip al servidor uuid en la ruta deseada en la interfaz de usuario de Assets.

1. Asegúrese de que el paquete posterior a la migración esté instalado en el servidor uuid.

1. Ejecute la siguiente consulta para importar el contenido delta del archivo zip cargado en el sistema. La consulta debe incluir la ruta del archivo zip cargado para identificar y procesar correctamente los datos.

   | URL de extremo | Tipo de solicitud | Parámetro de consulta | Resultados esperados |
   |---|---|---|---|
   | `/bin/guides/data_import`<br> **Por ejemplo**:`http://localhost:4502/bin/guides/data_import?path=/content/dam/dataexport_1689344927551.zip&createVersion=true` | POST | **ruta**<br> **Valor**: `/content/dam/filename.zip`(Ubicación del archivo cargado) **createVersion** <br> **Valor**: true/false<br>(El valor predeterminado de createVersion es false). | El archivo se cargará en la ruta de contenido deseada.<br><br>**Muestra**: `dataexport_1689761491218.zip`<br><br> (El mismo archivo que se exportó en el paso anterior se carga en la ruta deseada en `/content/dam`). |

1. El script creará un nuevo archivo si no existe o anulará el archivo existente si se modificó.

>[!NOTE]
>
> El historial de versiones y cualquier otro cambio realizado en el servidor (como flujos de trabajo y revisiones ) deben actualizarse manualmente.
