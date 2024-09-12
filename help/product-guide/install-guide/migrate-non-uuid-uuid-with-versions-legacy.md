---
title: Conversión de contenido no UUID con versiones a contenido UUID
description: Obtenga información sobre cómo migrar contenido que no es UUID con versiones a contenido UUID.
feature: Migration
role: Admin
level: Experienced
exl-id: 8f3a89fc-7d18-453d-909d-6dff5e275cab
source-git-commit: f86d8f2d2e6aa48941cf16526e608df4845420fd
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 0%

---

# Migrar contenido con versiones

>[!NOTE]
>
> Puede migrar el contenido que no sea UUID al contenido UUID en Experience Manager Guides. Este artículo se archivará en noviembre de 2024.
>Vea [**Migración de contenido que no es UUID a UUID**](./migrate-non-uuid-uuid.md) para obtener la documentación más reciente y detallada.

Siga estos pasos para migrar el contenido con versiones que no sean UUID al contenido UUID.

>[!NOTE]
>
>Siga las [instrucciones de actualización](./upgrade-xml-documentation.md) específicas de la versión con licencia del producto.

## Matriz de compatibilidad

| Versión actual de Experience Manager Guides (no UUID) | Versión requerida para migrar a UUID | Ruta de actualización admitida |
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

1. (Opcional) Realice la depuración de versiones en el contenido para eliminar versiones innecesarias y acelerar el proceso de migración. Para realizar la depuración de versiones, seleccione la opción **Depuración de versiones** en la pantalla de migración y vaya a la interfaz de usuario mediante la dirección URL `http://<server- name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.
   >[!NOTE]
   >
   >Esta utilidad no elimina ninguna versión utilizada en las líneas de base o revisiones, ni tiene etiquetas.

1. Iniciar `http://<server-name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.
1. Seleccione **Evaluación de compatibilidad** en el panel izquierdo y busque una ruta de carpeta.
1. Compruebe la compatibilidad para enumerar la siguiente información:
   * Total de archivos
   * Versiones totales
   * Tiempo estimado para la migración
   * Número de archivos con errores

   ![ficha de evaluación de compatibilidad en la migración](assets/migration-compatibility-assessment.png){width="800" align="left"}


1. Seleccione **Configurar validaciones** en el panel izquierdo. A continuación, **seleccione el mapa** y **seleccione el ajuste preestablecido** del mapa para configurarlos. La lista de validación de salida actual muestra los archivos de salida presentes antes de la migración y se pueden validar con los archivos de salida generados después de la migración.

   ![Configurar validaciones en la ficha de migración](assets/migration-configure-validation.png){width="800" align="left"}




## Migración

### Paso 1: Actualizar la configuración

1. AEM Asegúrese de que el espacio libre disponible sea al menos diez veces el espacio que ocupa el usuario (directorio crx-quickstart) durante la migración. Una vez completada la migración, puede recuperar la mayor parte del espacio en disco ejecutando compactación (consulte [Limpieza de revisión](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en)).

1. Habilitar *Habilitar iniciadores de flujo de trabajo de procesamiento posterior* en `com.adobe.fmdita.config.ConfigManager` y *Habilitar procesamiento posterior de la versión* en `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Instale la versión UUID de la versión compatible sobre la versión que no es UUID. Por ejemplo, si utiliza la versión 4.1 sin UUID, debe instalar la versión 4.1 de UUID y ejecutar la migración.

1. Instale el nuevo paquete para la migración de uuid.

1. Deshabilite los siguientes flujos de trabajo y cualquier otro flujo de trabajo que se ejecute en `/content/dam` mediante iniciadores en `http://<server-name>/libs/cq/workflow/content/console.html`.

   * Flujo de trabajo de recursos de actualización DAM
   * Flujo de trabajo de reescritura de metadatos DAM

1. Deshabilite *Habilitar iniciadores de flujo de trabajo de procesamiento posterior* en `com.adobe.fmdita.config.ConfigManager` y deshabilite *Habilitar procesamiento posterior de versión* en `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`.

1. Deshabilite la propiedad Habilitar validación (`validation.enabled`) en el servicio de etiquetado CQ por día.

1. Asegúrese de que la carpeta de propiedades `uuid.regex` esté establecida correctamente en `com.adobe.fmdita.config.ConfigManager`. Si está en blanco, establézcalo en el valor predeterminado: `^GUID-(?<id>.*)`.
1. Agregar un registrador independiente para `com.adobe.fmdita.uuid` La respuesta del explorador también está disponible en `/content/uuid-upgrade/logs`.

### Paso 2: Ejecute la migración y valide

#### Instalación del paquete de migración

1. Iniciar `http://<server-name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.

   ![Ficha de actualización del sistema en la migración](assets/migration-system-upgrade.png){width="800" align="left"}

1. Seleccione **Actualización del sistema** en el panel izquierdo para ejecutar la migración. Comience en una carpeta con datos más pequeños antes de ejecutarla en `/content/dam`.

1. Seleccione **Descargar informe** mientras se ejecuta la migración para comprobar si todos los archivos de la carpeta se han actualizado correctamente y si todas las características funcionan únicamente para esa carpeta.


>[!NOTE]
>
> La migración de contenido se puede ejecutar en un nivel de carpeta, en la carpeta completa `/content/dam` o en la misma carpeta (volver a ejecutar la migración).

Además, es importante asegurarse de que la migración de contenido se realiza para todos los recursos multimedia, como imágenes y gráficos, que se han utilizado en el contenido DITA.

#### Migración de línea base y revisión

Seleccione **Actualización de línea de base/revisión** en el panel izquierdo para migrar las líneas de base y revisarlas en el nivel de carpeta.

![Ficha de línea de base y revisión en la migración](assets/migration-baseline-review-upgrade.png){width="800" align="left"}


### Paso 3: Restaurar la configuración

Después de migrar el servidor correctamente, habilite el posprocesamiento, el etiquetado y los siguientes flujos de trabajo (incluidos todos los demás flujos de trabajo que se deshabilitaron inicialmente durante la migración) para seguir trabajando en el servidor.

* Flujo de trabajo de recursos de actualización DAM
* Flujo de trabajo de metadatos DAM

>[!NOTE]
>
>Si algunos archivos no se procesan o dañan antes de la migración, se dañarán antes de la migración y permanecerán dañados incluso después de la migración.

## Validación de migración

1. Una vez completada la migración, seleccione **Validar la actualización del sistema** en el panel izquierdo y valide los archivos de salida antes y después de la migración para garantizar que la migración se realice correctamente.

   ![Validar ficha de actualización del sistema en la migración](assets/migration-validate-system-upgrade.png){width="800" align="left"}


1. Una vez completada la validación, se puede recuperar la mayor parte del espacio en disco ejecutando la compactación (consulte `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en`).
