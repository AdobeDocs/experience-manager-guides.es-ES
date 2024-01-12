---
title: Conversión de contenido no UUID con versiones a contenido UUID
description: Obtenga información sobre cómo migrar contenido que no es UUID con versiones a contenido UUID.
feature: Migration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 0%

---

# Migrar contenido con versiones

Siga estos pasos para migrar el contenido con versiones que no sean UUID al contenido UUID.

>[!NOTE]
>
>Siga las [instrucciones de actualización](./upgrade-xml-documentation.md) específico para la versión con licencia del producto.

## Matriz de compatibilidad

| Versión de las guías del Experience Manager actual (no UUID) | Versión requerida para migrar a UUID | Ruta de actualización admitida |
|---|---|---|
| 3.8.5, 4.0.x o 4.1.x | 4.1 sin UUID | Instale 4.1 (UUID) y ejecute la migración |
| 4.2, 4.2.x o 4.3 | 4.3.0 no UUID | Instale 4.3.1 (UUID) y ejecute la migración |
| 4.3.1. | ND | ND |

## Instalación de paquetes

Descargue los paquetes necesarios desde el Portal de distribución de software de Adobe en función de su versión:
<details>
<summary>  Paquetes para la ruta de actualización a la versión 4.1</summary>

1. **Premigración**: [com.adobe.guides.pre-uuid-migration-1.0.9.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F1-0%2Fcom.adobe.guides.pre-uuid-migration-1.0.9.zip)
1. **Migración**: [com.adobe.guides.uuid-upgrade-1.0.19.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F1-0%2Fcom.adobe.guides.uuid-upgrade-1.0.19.zip)
</details>


<details>
<summary> Ruta de actualización de paquetes para la versión 4.3.1</summary>

1. **Premigración**: [com.adobe.guides.pre-uuid-migration-1.1.3.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2Fcom.adobe.guides.pre-uuid-migration-1.1.3.zip)
1. **Migración**: [com.adobe.guides.uuid-upgrade-1.1.15.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2Fcom.adobe.guides.uuid-upgrade-1.1.15.zip)

</details>

## Premigración

Realice las siguientes comprobaciones en la versión no UUID (4.1 no UUID o 4.3.0 no UUID):

1. Instale el paquete previo a la migración según su versión.

   >[!NOTE]
   >
   >* Necesita permiso de administrador para ejecutar la migración.
   >* Se recomienda corregir los archivos con errores antes de continuar con la migración.

1. (Opcional) Realice la depuración de versiones en el contenido para eliminar versiones innecesarias y acelerar el proceso de migración. Para realizar la depuración de versiones, seleccione la opción **Depuración de versión** en la pantalla de migración y vaya a la interfaz de usuario de con la URL de `http://<server- name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.
   >[!NOTE]
   >
   >Esta utilidad no elimina ninguna versión utilizada en las líneas de base o revisiones, ni tiene etiquetas.

1. Launch `http://<server-name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.
1. Seleccionar **Evaluación de compatibilidad**  en el panel izquierdo y busque una ruta de carpeta.
1. Compruebe la compatibilidad para enumerar la siguiente información:
   * Total de archivos
   * Versiones totales
   * Tiempo estimado para la migración
   * Número de archivos con errores

   ![ficha evaluación de compatibilidad en migración](assets/migration-compatibility-assessment.png){width="800" align="left"}


1. Seleccionar **Configurar validaciones** en el panel izquierdo. A continuación, **Seleccionar mapa** y **Seleccionar ajuste preestablecido** del mapa para configurarlos. La lista de validación de salida actual muestra los archivos de salida presentes antes de la migración y se pueden validar con los archivos de salida generados después de la migración.

   ![Configuración de la pestaña Validaciones en la migración](assets/migration-configure-validation.png){width="800" align="left"}




## Migración

### Paso 1: Actualizar la configuración

1. AEM Asegúrese de que el espacio libre disponible sea al menos diez veces el espacio que ocupa el usuario (directorio crx-quickstart) durante la migración. Una vez completada la migración, puede recuperar la mayor parte del espacio en disco ejecutando la compactación (consulte [Limpieza de revisión](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en)).

1. Activar *Activar iniciadores de flujo de trabajo de procesamiento posterior* in `com.adobe.fmdita.config.ConfigManager` y *Habilitar procesamiento posterior de la versión* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Instale la versión UUID de la versión compatible sobre la versión que no es UUID. Por ejemplo, si utiliza la versión 4.1 sin UUID, debe instalar la versión 4.1 de UUID y ejecutar la migración.

1. Instale el nuevo paquete para la migración de uuid.

1. Deshabilite los siguientes flujos de trabajo y cualquier otro flujo de trabajo que se ejecute en `/content/dam` uso de lanzadores en `http://<server-name>/libs/cq/workflow/content/console.html`.

   * Flujo de trabajo de recursos de actualización DAM
   * Flujo de trabajo de reescritura de metadatos DAM

1. Deshabilitar *Activar iniciadores de flujo de trabajo de procesamiento posterior* in `com.adobe.fmdita.config.ConfigManager` y deshabilitar *Habilitar procesamiento posterior de la versión* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`.

1. Deshabilite la propiedad Habilitar validación (`validation.enabled`) en el servicio Day CQ Tagging.

1. Asegúrese de que `uuid.regex` la carpeta de propiedades está correctamente configurada en `com.adobe.fmdita.config.ConfigManager`. Si está en blanco, establézcalo en el valor predeterminado - `^GUID-(?<id>.*)`.
1. Añadir un registrador independiente para `com.adobe.fmdita.uuid` La respuesta del explorador también está disponible en `/content/uuid-upgrade/logs`.

### Paso 2: Ejecute la migración y valide

#### Instalación del paquete de migración

1. Launch `http://<server-name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.

   ![Pestaña Actualización del sistema en la migración](assets/migration-system-upgrade.png){width="800" align="left"}

1. Seleccionar **Actualización del sistema** en el panel izquierdo para ejecutar la migración. Comience en una carpeta con datos más pequeños antes de ejecutarla en `/content/dam`.

1. Seleccionar **Descargar informe** mientras se ejecuta la migración, para comprobar si todos los archivos de la carpeta se han actualizado correctamente y si todas las funciones solo funcionan para esa carpeta.


>[!NOTE]
>
> La migración de contenido se puede ejecutar en un nivel de carpeta, el `/content/dam`o en la misma carpeta (vuelva a ejecutar la migración).

Además, es importante asegurarse de que la migración de contenido se realiza para todos los recursos multimedia, como imágenes y gráficos, que se han utilizado en el contenido DITA.

#### Migración de línea base y revisión

Seleccionar **Actualización de línea base/revisión** en el panel izquierdo para migrar las líneas de base y revisarlas en el nivel de carpeta.

![Pestaña Línea base y revisión en la migración](assets/migration-baseline-review-upgrade.png){width="800" align="left"}


### Paso 3: Restaurar la configuración

Después de migrar el servidor correctamente, habilite el posprocesamiento, el etiquetado y los siguientes flujos de trabajo (incluidos todos los demás flujos de trabajo que se deshabilitaron inicialmente durante la migración) para seguir trabajando en el servidor.

* Flujo de trabajo de recursos de actualización DAM
* Flujo de trabajo de metadatos DAM

>[!NOTE]
>
>Si algunos archivos no se procesan o dañan antes de la migración, se dañarán antes de la migración y permanecerán dañados incluso después de la migración.

## Validación de migración

1. Una vez completada la migración, seleccione **Validar actualización del sistema** en el panel izquierdo y valide los archivos de salida antes y después de la migración para asegurarse de que la migración se realiza correctamente.

   ![Validar la pestaña de actualización del sistema en la migración](assets/migration-validate-system-upgrade.png){width="800" align="left"}


1. Una vez realizada la validación, la mayor parte del espacio en disco se puede recuperar ejecutando la compactación (consulte `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en`).

