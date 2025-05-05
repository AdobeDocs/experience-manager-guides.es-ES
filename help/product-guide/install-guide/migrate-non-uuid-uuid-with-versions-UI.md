---
title: Conversión de contenido no UUID con versiones a contenido UUID desde la interfaz de usuario
description: Obtenga información sobre cómo migrar contenido que no sea UUID con versiones 4.3.x.
source-git-commit: f18c19eb493cd4d2003f68b082e71ebe7b3e6b7a
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 0%

---

# Migración de contenido que no sea UUID con versiones desde la interfaz de usuario

Si utiliza la versión 4.3.x o posterior de, realice estos pasos para migrar el contenido que no es UUID con versiones de a contenido UUID.

## Matriz de compatibilidad

| Versión actual de AEM Guides (no UUID) | Versión requerida para migrar a UUID | Ruta de actualización admitida |
|---|---|---|
| 4.3.x o superior | 4.3.0 no UUID | Instalación de 4.3.1 (UUID) |

## Paquetes necesarios

1. **Depuración de versiones**: `com.adobe.guides.version-purge-1.0.11.zip` (opcional)
1. **Antes de la migración**: `com.adobe.guides.pre-uuid-migration-1.1.2 .zip`
1. **Migración**: `com.adobe.guides.uuid-upgrade-1.1.13.zip`



## Premigración

1. (Opcional) Realice la depuración de versiones en el contenido para eliminar versiones innecesarias y acelerar el proceso de migración. Para realizar la depuración de la versión 4.1 (NO compatible con la versión 4.0), instale el paquete `com.adobe.guides.version-purge-1.0.11.zip` y vaya a la interfaz de usuario con esta dirección URL `http://<server-name> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`.

   >[!NOTE]
   >
   >Esta utilidad no elimina ninguna versión utilizada en las líneas de base o revisiones, ni tiene etiquetas.
1. Instale el paquete previo a la migración (`ccom.adobe.guides.pre-uuid-migration-1.1.2 .zip`).

   >[!NOTE]
   >
   >* Necesita permiso de administrador para ejecutar la migración.
   >* Se recomienda corregir los archivos con errores antes de continuar con la migración.

1. Seleccione **Evaluación de compatibilidad** en el panel izquierdo y busque una ruta de carpeta.
1. Compruebe la compatibilidad para enumerar la siguiente información:
   * Total de archivos
   * Versiones totales
   * Tiempo estimado para la migración
   * Número de archivos con errores



![ficha de evaluación de compatibilidad en la migración](assets/migration-compatibility-assessment.png){width="800" align="left"}


1. Seleccione **Configurar validaciones** en el panel izquierdo. A continuación, **seleccione el mapa** y **seleccione el ajuste preestablecido** del mapa para configurarlos. La lista de validación de salida actual mostrará los archivos de salida presentes antes de la migración y se pueden validar con los archivos de salida generados después de la migración.

![Configurar validaciones en la ficha de migración](assets/migration-configure-validation.png){width="800" align="left"}




## Migración

### Paso 1: Actualizar la configuración

1. AEM Asegúrese de que el espacio libre disponible sea al menos 10 veces el espacio que ocupa el usuario (directorio crx-quickstart) durante la migración. Una vez completada la migración, puede recuperar la mayor parte del espacio en disco ejecutando la compactación (consulte [Limpieza de revisión](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=es)).

1. Habilitar *Habilitar iniciadores de flujo de trabajo de procesamiento de Post* en `com.adobe.fmdita.config.ConfigManager` y *Habilitar procesamiento posterior de versiones* en `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Instale la versión UUID de la versión compatible sobre la versión que no es UUID. Por ejemplo, si utiliza una compilación 4.0 sin UUID o una compilación 4.1 sin UUID, debe instalar la versión 4.1 de UUID.

1. Instale el nuevo paquete para la migración de uuid (`com.adobe.guides.uuid-upgrade-1.1.13`).

1. Deshabilite los siguientes flujos de trabajo y cualquier otro flujo de trabajo que se ejecute en `/content/dam` mediante iniciadores en `http://localhost:4502/libs/cq/workflow/content/console.html`.

   * Flujo de trabajo de recursos de actualización DAM
   * Flujo de trabajo de reescritura de metadatos DAM

1. Deshabilite *Habilitar los iniciadores del flujo de trabajo de procesamiento de Post* en `com.adobe.fmdita.config.ConfigManager` y deshabilite *Habilitar procesamiento posterior de versiones* en `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`.

1. Deshabilite la propiedad Habilitar validación (`validation.enabled`) en el servicio de etiquetado CQ por día.

1. Asegúrese de que la carpeta de propiedades `uuid.regex` esté establecida correctamente en `com.adobe.fmdita.config.ConfigManager`. Si está en blanco, establézcalo en el valor predeterminado: `^GUID-(?<id>.*)`.
1. Agregar un registrador independiente para `com.adobe.fmdita.uuid.upgrade.UuidUpgrade` La respuesta del explorador también está disponible en `/content/uuid-upgrade/logs`.

### Paso 2: Ejecute la migración y valide

#### Instalación del paquete de migración

![Ficha de actualización del sistema en la migración](assets/migration-system-upgrade.png){width="800" align="left"}

* Seleccione **Actualización del sistema** en el panel izquierdo para ejecutar la migración. Comience en una carpeta con datos más pequeños antes de ejecutarla en `/content/dam`.

* Seleccione **Descargar informe** mientras se ejecuta la migración para comprobar si todos los archivos de la carpeta se han actualizado correctamente y si todas las características funcionan únicamente para esa carpeta.


>[!NOTE]
>
> La migración de contenido se puede ejecutar en el nivel de carpeta o en la carpeta completa `/content/dam` o en la misma carpeta (volver a ejecutar la migración).

Además, es importante asegurarse de que la migración de contenido también se realiza para todos los recursos multimedia, como imágenes y gráficos, que se han utilizado en el contenido DITA.

#### Migración de línea base y revisión

Seleccione **Actualización de línea de base/revisión** en el panel izquierdo para migrar las líneas de base y revisarlas en el nivel de carpeta.

![Ficha de línea de base y revisión en la migración](assets/migration-baseline-review-upgrade.png){width="800" align="left"}


### Paso 3: Restaurar la configuración

Una vez que el servidor se haya migrado correctamente, habilite el posprocesamiento, el etiquetado y los siguientes flujos de trabajo (incluidos todos los demás flujos de trabajo que están desactivados inicialmente durante la migración) para seguir trabajando en el servidor.

* Flujo de trabajo de recursos de actualización DAM
* Flujo de trabajo de metadatos DAM

>[!NOTE]
>
>Si algunos archivos no se procesan o se dañan antes de la migración y se dañan antes de la migración y se dañan incluso después de la migración.

## Validación de migración

Una vez completada la migración, seleccione **Validar la actualización del sistema** en el panel izquierdo y valide los archivos de salida antes y después de la migración para garantizar que la migración se realice correctamente.

![Validar ficha de actualización del sistema en la migración](assets/migration-validate-system-upgrade.png){width="800" align="left"}


1. Una vez completada la migración, la mayor parte del espacio en disco se puede recuperar ejecutando compactación (consulte `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=es`).

