---
title: Actualizar Adobe Experience Manager Guides On Premise Versiones Anteriores
description: Obtenga información sobre cómo actualizar Adobe Experience Manager Guides
feature: Installation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '3159'
ht-degree: 0%

---

# Actualizar Adobe Experience Manager Guides On Premise (versión 4.4.0 y anteriores)

Este artículo proporciona instrucciones para actualizar **Adobe Experience Manager Guides** versiones **anteriores a la 4.6.0** (hasta la **4.4.0** inclusive).

Si tiene una versión **anterior a la 3.8.5**, consulte la sección **Actualizar Experience Manager Guides** en la guía de instalación específica del producto, disponible en [Archivo de PDF de ayuda de Adobe Experience Manager Guides](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

Para obtener instrucciones de actualización para las versiones más recientes, consulte [Actualizar Adobe Experience Manager Guides para la versión 4.6.0 y superior](./upgrade-aemg-latest-version.md).

## Antes de empezar

>[!NOTE]
>
> Debe actualizar las instrucciones específicas de la versión con licencia del producto e instalar AEM Service Pack antes de actualizar la versión de Experience Manager Guides.

>[!IMPORTANT]
>
> Antes de comenzar la actualización, realice una **copia de seguridad completa del sistema** para evitar la pérdida de datos.

## Rutas de actualización tratadas en este artículo

Este artículo incluye procedimientos para:

- [Actualización a la versión 4.4.0](#upgrade-to-version-440)
- [Actualizar a la versión 4.3.1.5](#upgrade-to-version-4315)
- [Actualización a la versión 4.3.1](#upgrade-to-version-431)
- [Actualización a la versión 4.3.0](#upgrade-to-version-430)
- [Actualización a la versión 4.2.1](#upgrade-to-version-421)
- [Actualización a la versión 4.2](#upgrade-to-version-42)
- [Actualización de 3.8.5 a la versión 4.0](#upgrade-from-version-385-to-version-40)


## Requisitos previos globales (se aplica a todas las actualizaciones a menos que un procedimiento indique lo contrario)

Antes de ejecutar el proceso de actualización, complete estas tareas:

1. Importar comentarios de revisión en temas abiertos para revisión.
2. Cerrar todas las críticas activas.
3. Cierre todas las tareas de traducción.
4. Desinstale cualquier revisión de Experience Manager Guides instalada sobre la versión anterior (versión principal o de parche).

Algunas actualizaciones también requieren la configuración del nivel de registro en `INFO` para una clase de actualización de traducción y el registro en un archivo independiente; estos requisitos se indican en los procedimientos de actualización correspondientes.

## Actualice de la versión 3.8.5 a la versión 4.0

>[!NOTE]
>
> Este proceso de actualización es aplicable **solamente** de **3.8.5** a **4.0**. Para actualizaciones de **3.4 o superior** a **3.8.5**, consulte la guía de instalación específica del producto disponible en [Adobe Experience Manager Guides help PDF archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

Si usa la versión de Experience Manager Guides **3.8.5**, puede actualizar a la versión **4.0** sin desinstalar la versión anterior.

### Antes de instalar la versión 4.0

1. Asegúrese de que Experience Manager Guides está en la versión **3.8.5**.
2. Descargar el paquete del script de actualización: busque **&quot;Paquete de actualización de la solución XML Documentation 4.0&quot;** en el portal de distribución de software de Adobe (descarga un `.zip`).
3. Cargue el paquete en AEM a través de **Administrador de paquetes** e instálelo.
4. Una vez instalado el paquete de actualización, ejecute los scripts en el orden descrito a continuación.

**Comprobar API de compatibilidad de actualización**

Esta API está diseñada para evaluar el estado actual del sistema e informar si la actualización es posible o no. Para ejecutar este script, almacene en déclencheur el siguiente extremo dado:

| Punto final | /bin/dxml/upgrade/3xto4x/report |
| --- | --- |
| Tipo de solicitud | **GET** <br> **Nota**: puede usar un explorador web en el que haya iniciado sesión en la instancia de AEM como administrador. |
| Respuesta esperada | -   Si se pueden mover todos los nodos requeridos, se le aprobará una comprobación. <br>-   Si un nodo está presente en la ubicación de destino, se producirá un error relevante. Limpie el repositorio \(elimine el nodo /var/xml\), vuelva a instalar el paquete de actualización y, a continuación, almacene en déclencheur este extremo de nuevo. <br>**Nota:** Este no es un error común porque 3.x Experience Manager Guides no usa anteriormente la ubicación de destino. <br> -   Si este script no se ejecuta correctamente, no continúe y genere un informe para el equipo de éxito del cliente. |

**API de migración de datos del sistema**

Esta API está diseñada para migrar los datos del sistema como se menciona en la sección **Asignación de migración**.

1. No ejecute este script si la API Comprobar compatibilidad de actualización falla \(no continuar\).
1. Una vez que la API de comprobación de compatibilidad de actualización devuelva un resultado correcto, puede ejecutar el script de actualización.

| Punto final | /bin/dxml/upgrade/3xto4x |
| --- | --- |
| Tipo de solicitud | **POST** <br>**Nota**: este script es una petición POST por lo tanto debe ejecutarse a través de agentes como Postman. |
| Respuesta esperada | -   Una vez completada la migración, puede instalar la solución de XML Documentation versión 4.0.<br>-   En caso de errores, restaure al último punto de comprobación y comparta los registros de errores junto con la salida de la API con el equipo de éxito del cliente. |


**Asignación de migración**

Esta API migra todos los datos de la ubicación de origen a la ubicación de destino.

| Origen | Público destinatario |
|------|------|
| /content/fmdita | /var/dxml |
| /content/dxml | /var/dxml |
| /etc/fmdita | /libs/fmdita |

### Instalar versión 4.0

1. Instale la versión 4.0 solo si los pasos de actualización se realizaron correctamente.
1. Descargar el paquete de la versión 4.0 del [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html):

   - Si está utilizando la versión de software de UUID, busque &quot;Versión 4.0 de UUID para la solución XML Documentation para AEM 6.5&quot;.
   - Si está utilizando una versión de software que no sea UUID, busque &quot;Versión 4.0 que no sea UUID para la solución XML Documentation para AEM 6.5&quot;.
Cargue el paquete en las instancias de servidor de AEM existentes mediante el administrador de paquetes de CRX e instálelo.

     >[!NOTE]
     >
     > Espere a que se inicien todos los componentes del sistema.

1. Borre la caché del explorador después de instalar el paquete.
1. Si Dispatcher está configurado en la instancia de autor de AEM, realice los siguientes pasos:
   - Asegúrese de que se gestionan las siguientes opciones en las reglas de Dispatcher:
   - El patrón de URL /home/users/\*/preferences está en la lista blanca.
   - El patrón de URL /libs/cq/security/userinfo.json no se almacena en caché.
1. Borrar caché de Dispatcher \(para borrar cualquier `clientlibs` almacenado en caché\).

## Actualización a la versión 4.2

Puede actualizar a la versión **4.2** directamente si usa la versión **4.0**, **4.1** o **4.1.x**.

### Antes de instalar la versión 4.2

Antes de iniciar el proceso de actualización de Experience Manager Guides 4.2, asegúrese de lo siguiente:

1. Se ha actualizado a Experience Manager Guides **4.0**, **4.1** o **4.1.x**.
2. Se cerraron todas las tareas de traducción.
3. Establezca el nivel de registro en `INFO` para `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` y registre en un nuevo archivo de registro (por ejemplo, `logs/translation_upgrade.log`).

   >[!NOTE]
   > 
   > Debe cerrar todas las revisiones activas. Si las revisiones no están cerradas al actualizar a la versión 4.2, las tareas de revisión en curso más antiguas pueden seguir abriendo páginas de revisión antiguas; las nuevas tareas de revisión creadas después de la actualización muestran las actualizaciones de funcionalidad más recientes.

### Instalar versión 4.2

1. Descargue el paquete **4.2** del [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html).
2. Instale el paquete 4.2.
3. Después de la instalación, espere a que aparezca el siguiente mensaje en los registros:

   `Completed the post deployment setup script`

   El mensaje anterior indica que se han completado todos los pasos de instalación.

   Si encuentra cualquiera de los siguientes errores, informe de ellos al éxito del cliente:

   - `Error in post deployment setup script`
   - `Exception while porting the translation MAP`
   - `Unable to port translation map from v1 to v2 for property`

4. (Opcional) Actualice el complemento Conector de oxígeno lanzado con la versión 4.2.
5. Borre la caché del explorador después de instalar el paquete.
6. Continúe actualizando las personalizaciones como se detalla en la siguiente sección.

### Después de instalar la versión 4.2

>[!IMPORTANT]
>
> La plantilla de alta tecnología no se muestra en el servidor actualizado. Para incluir la plantilla de alta tecnología en el servidor, puede copiarla: Source: `/libs/fmdita/pdf/Hi-Tech` Destino: `/content/dam/dita-templates/pdf`.

A continuación, continúe con las tareas compartidas posteriores a la actualización en [Tareas comunes posteriores a la actualización (todas las versiones)](#common-postupgrade-tasks-all-versions).

## Actualización a la versión 4.2.1

>[!TIP]
>
> Se recomienda instalar **revisión4.2.1.3** sobre la versión **4.2.1**.

Puede actualizar a la versión **4.2.1** directamente si usa **4.1**, **4.1.x** o **4.2**.

>[!NOTE]
>
> El posprocesamiento y la indexación pueden tardar unas horas. Inicie la actualización durante las horas de menor actividad.

### Antes de instalar la versión 4.2.1

1. Actualice a Experience Manager Guides **4.1**, **4.1.x** o **4.2**.
2. Cierre todas las tareas de traducción.
3. Establezca el nivel de registro en `INFO` para `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` y registre en un nuevo archivo (por ejemplo, `logs/translation_upgrade.log`).

>[!NOTE]
>
> Debe cerrar todas las revisiones activas (con el mismo comportamiento que la 4.2).

### Instalar versión 4.2.1

1. Descargue el paquete **4.2.1** del [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html).
2. Instale el paquete 4.2.1.
3. De forma opcional, almacene en déclencheur el trabajo de actualización del mapa de traducción. Para obtener más información, consulte [Habilitar el déclencheur del script mediante un servlet](#enable-trigger-of-script-via-a-servlet).

4. Después de la instalación, espere: `Completed the post deployment setup script` en los registros.

   Informar de estos errores al éxito del cliente:

   - `Error in post deployment setup script`
   - `Exception while porting the translation MAP`
   - `Unable to port translation map from v1 to v2 for property`
5. (Opcional) Actualizar el complemento Conector de oxígeno lanzado con la versión **4.2**
6. Borre la caché del explorador.
7. Continuar con [Tareas comunes posteriores a la actualización (todas las versiones)](#common-postupgrade-tasks-all-versions).

### Después de instalar la versión 4.2.1

>[!IMPORTANT]
>
> La plantilla de alta tecnología no se muestra en el servidor actualizado. Para incluir la plantilla de alta tecnología en el servidor, puede copiarla: Source: `/libs/fmdita/pdf/Hi-Tech` Destino: `/content/dam/dita-templates/pdf`.

Continúe con [Tareas comunes posteriores a la actualización (todas las versiones)](#common-postupgrade-tasks-all-versions) y (si es necesario) [Indexe el contenido existente para buscar y reemplazar mapas](#index-existing-content-for-map-find-and-replace).


## Actualización a la versión 4.3.0

La actualización a la versión 4.3.0 depende de la versión actual de Experience Manager Guides. Si utiliza la versión 4.2 o 4.2.x, puede actualizar directamente a la versión 4.3.0.

>[!NOTE]
>
>El posprocesamiento y la indexación pueden tardar unas horas. Le recomendamos que inicie el proceso de actualización durante las horas de menor actividad.

### Antes de instalar la versión 4.3.0

Antes de iniciar el proceso de actualización de Experience Manager Guides 4.3.0, asegúrese de lo siguiente:

1. Se ha actualizado a la versión de Experience Manager Guides 4.2 o 4.2.x y se han completado sus respectivos pasos de instalación.
1. Se cerraron todas las tareas de traducción.

### Instalar versión 4.3.0

1. Descargue el paquete de la versión 4.3.0 desde el [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html).
1. Instale el paquete de la versión 4.3.0.
1. Borre la caché del explorador después de instalar el paquete.
1. Actualice el archivo `ui_config.json` desde la ficha **Configuración del editor XML** del perfil de carpeta.

### Después de instalar la versión 4.3.0

Continúe con:

- [Tareas comunes posteriores a la actualización (todas las versiones)](#common-postupgrade-tasks-all-versions)
- Si corresponde: [Procesar el contenido existente para el informe de vínculos rotos](#post-process-existing-content-for-broken-link-report)

## Actualización a la versión 4.3.1

La actualización a la versión 4.3.1 depende de la versión actual de Experience Manager Guides. Si utiliza las versiones 4.3.0, 4.2 o 4.2.1, puede actualizar directamente a la versión 4.3.1.

>[!NOTE]
>
>El posprocesamiento y la indexación pueden tardar unas horas. Le recomendamos que inicie el proceso de actualización durante las horas de menor actividad.

### Antes de instalar la versión 4.3.1

Antes de iniciar el proceso de actualización de Experience Manager Guides 4.3.1, asegúrese de lo siguiente:

1. Se ha actualizado a la versión de Experience Manager Guides 4.3.0, 4.2 o 4.2.1 y se han completado los pasos de instalación correspondientes.
1. (Opcional) Cerró todas las tareas de traducción.
1. Se ha cambiado el nivel de registro a **INFO** para la clase `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` y se han anexado estos registros a un nuevo archivo de registro, por ejemplo, `logs/translation_upgrade.log`.

### Instalar versión 4.3.1

1. Descargue el paquete de la versión 4.3.1 del [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html).
1. Instale el paquete de la versión 4.3.1.
1. De forma opcional, almacene en déclencheur el trabajo de actualización del mapa de traducción. Para obtener más información, consulte [Habilitar el déclencheur del script mediante un servlet](#enable-trigger-of-script-via-a-servlet).
1. Después de la instalación, espere: `Completed the post deployment setup script` en los registros.
Informar de estos errores al éxito del cliente:\
   `Error in post deployment setup script`, `Exception while porting the translation MAP`, `Unable to port translation map from v1 to v2 for property`
1. (Opcional) Actualice el complemento Conector de oxígeno lanzado con la versión **4.2**.
1. Borre la caché del explorador.

### Después de instalar la versión 4.3.1

Continúe con:

- [Tareas comunes posteriores a la actualización (todas las versiones)](#common-postupgrade-tasks-all-versions)
- Si corresponde: [Indizar el contenido existente para buscar y reemplazar asignaciones](#index-existing-content-for-map-find-and-replace)
- Si corresponde: [Procesar el contenido existente para el informe de vínculos rotos](#post-process-existing-content-for-broken-link-report)


## Actualizar a la versión 4.3.1.5

Puede actualizar a **4.3.1.5** directamente si usa la versión **4.3.1**.

### Instalar versión 4.3.1.5

1. Descargue el paquete **4.3.1.5** del [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html).
2. Instale el paquete 4.3.1.5.
3. Espere a que el proceso de instalación se complete correctamente.
4. Continúe actualizando las personalizaciones como se detalla en la siguiente sección.

## Después de instalar la versión 4.3.1.5

>[!NOTE]
>
>Si desea utilizar el paquete org.apache.velocity, realice los siguientes pasos antes de cargar el paquete:
> 1. Vaya a `<server>:<port>/system/console/bundles`
> 1. Busque org.apache.velocity.
> 1. Desinstale el paquete buscado.
> 1. Instale el paquete Velocity requerido.

1. Una vez completada la actualización, asegúrese de que cualquiera de las personalizaciones/superposiciones se valide y actualice para que coincida con el nuevo código de la aplicación. A continuación se ofrecen algunos ejemplos:
   - Cualquier componente superpuesto de `/libs/fmdita` o ` /libs` debe compararse con el nuevo código de producto y las actualizaciones deben realizarse en archivos superpuestos bajo `/apps`
   - Cualquier categoría clientlib utilizada desde el producto debe revisarse para ver si hay cambios. Cualquier configuración anulada \(ejemplos abajo\) debe compararse con las más recientes para obtener las últimas funciones:
   - `elementmapping.xml`
   - `ui\_config.json\` (puede haberse configurado en perfiles de carpeta\)
   - se modificó `com.adobe.fmdita.config.ConfigManager`


## Actualización a la versión 4.4.0

Puede actualizar a **4.4.0** directamente si usa: **4.3.1**, **4.3.0**, **4.2** o **4.2.1 (Revisión 4.2.1.3)**.

>[!NOTE]
>
>El posprocesamiento y la indexación pueden tardar unas horas. Le recomendamos que inicie el proceso de actualización durante las horas de menor actividad.

### Antes de instalar la versión 4.4.0

Antes de iniciar el proceso de actualización de Experience Manager Guides 4.4.0, asegúrese de lo siguiente:

1. Se ha actualizado a la versión de Experience Manager Guides 4.3.1, 4.3.0 o 4.2.1 (revisión 4.2.1.3) y se han completado los pasos de instalación correspondientes.
1. (Opcional) Cerró todas las tareas de traducción.
1. Se ha cambiado el nivel de registro a **INFO** para la clase `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` y se han anexado estos registros a un nuevo archivo de registro, por ejemplo, `logs/translation_upgrade.log`.

### Instalar versión 4.4.0

1. Descargue el paquete de la versión 4.4.0 del [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html).
2. Instale el paquete 4.4.0.
3. De forma opcional, almacene en déclencheur el trabajo de actualización del mapa de traducción. Para obtener más información, consulte [Habilitar el déclencheur del script mediante un servlet](#enable-trigger-of-script-via-a-servlet).
4. Una vez completada la instalación del paquete, espere al siguiente mensaje en los registros:

   `Completed the post deployment setup script`

   El mensaje anterior indica que se han completado todos los pasos de la instalación.

   Si encuentra cualquiera de los siguientes prefijos ERROR, informe de ellos a su equipo de éxito del cliente:

   - `Error in post deployment setup script`
   - `Exception while porting the translation MAP`
   - `Unable to port translation map from v1 to v2 for property`
5. (Opcional) Actualice el complemento Conector de oxígeno lanzado con la versión **4.4.0**.
6. Borre la caché del explorador.
7. Continúe con:

   - [Tareas comunes posteriores a la actualización (todas las versiones)](#common-ppostupgrade-tasks-all-versions)
   - [Indexe el contenido existente para buscar y reemplazar asignaciones](#index-existing-content-for-map-find-and-replace) (solo si corresponde)
   - [Procesar posteriormente el contenido existente para el informe de vínculos rotos](#post-process-existing-content-for-broken-link-report) (solo si corresponde)
   - [Actualización del mapa de traducción (déclencheur de servlet)](#translation-map-upgrade-servlet-trigger) (solo si corresponde)


## Tareas comunes posteriores a la actualización (todas las versiones)

Después de instalar Experience Manager Guides, es posible que tenga que combinar las configuraciones aplicables desde la versión recién instalada con la configuración.

>[!NOTE]
>
> El modelo de flujo de trabajo **DAM Update Asset** se puede personalizar. Si tiene personalizaciones, sincronícelas con los cambios de Experience Manager Guides en la copia de trabajo del modelo.

### Validar el flujo de trabajo de recursos de actualización de DAM (cambios posteriores al procesamiento)

1. Abra la interfaz de usuario de modelos de flujo de trabajo de AEM (ejemplo mostrado en la fuente):\
   `http://<host>:4502/libs/cq/workflow/admin/console/content/models.html`
2. Seleccione **flujo de trabajo del recurso de actualización DAM**.
3. Seleccione **Editar**.
4. Si el componente **Iniciador de procesamiento posterior DXML** está presente, asegúrese de que las personalizaciones estén sincronizadas.
5. Si el componente está ausente, insértelo:
   1. Haga clic en **Insertar componente** (responsable del posprocesamiento de las guías como paso final).
   2. Configurar el **paso de proceso**:
      **Ficha común**
- Título: `DXML Post Process Initiator`
- Descripción: `DXML post process initiator step which will trigger a sling job for DXML post-processing of the modified/created asset`
      **Ficha de proceso**
- Proceso: seleccionar `DXML Post Process Initiator`
- Seleccionar `Handler Advance`
- Seleccionar `Done`
   3. Haga clic en **Sincronizar** en la parte superior derecha después de completar los cambios. Recibirá una notificación de éxito.

>[!NOTE]
>
> Actualice y compruebe que los cambios personalizados y el paso posterior al procesamiento de Experience Manager Guides estén presentes en el modelo final de flujo de trabajo.

### Validar configuraciones del lanzador

1. Vaya a la interfaz del flujo de trabajo de AEM y abra **Iniciadores**.

```http
    http://localhost:4502/libs/cq/workflow/content/console.html
```

1. Busque y realice cambios \(si es necesario\) en los dos iniciadores siguientes \(que deberían estar activos\) correspondientes a **flujo de trabajo de recursos de actualización de DAM**:

1. Lanzador para &quot;*Nodo creado*&quot; para **flujo de trabajo del recurso de actualización DAM**- para la condición `"jcr:content/jcr:mimeType!=video"`, el valor &#39;Globbing&#39; debe ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` debe tener `"event-user-data:changedByWorkflowProcess"`.
   - Lanzador para *nodo modificado* para **flujo de trabajo de recursos de actualización DAM -** para la condición &quot;`jcr:content/jcr:mimeType!=video`&quot;, el valor &#39;Globbing&#39; debe ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` debe tener `"event-user-data:changedByWorkflowProcess"`.

### Validación de superposiciones y personalizaciones

Una vez completada la actualización:

1. Una vez completada la actualización, asegúrese de que cualquiera de las personalizaciones/superposiciones se valide y actualice para que coincida con el nuevo código de la aplicación. A continuación se ofrecen algunos ejemplos:
   - Cualquier componente superpuesto de /libs/fmidator/libs debe compararse con el nuevo código de producto y las actualizaciones deben realizarse en archivos superpuestos en /apps.
   - Cualquier categoría clientlib utilizada desde el producto debe revisarse para ver si hay cambios. Cualquier configuración anulada \(ejemplos abajo\) debe compararse con las más recientes para obtener las últimas funciones:
   - elementmapping.xml
   - ui\_config.json\(puede haberse configurado en perfiles de carpeta\)
   - se modificó `com.adobe.fmdita.config.ConfigManager`

1. Si ha añadido personalizaciones en damAssetLucene, es posible que tenga que volver a aplicarlas. Después de realizar estos cambios, establezca reindex como true. Esto reindexará todos los nodos existentes con las personalizaciones. Una vez finalizado, el indicador de reindexación se volverá a establecer en &quot;false&quot;. Esto puede tardar unas horas, según la cantidad de recursos que haya en el sistema.

## Indexar contenido existente para buscar y reemplazar mapas

Esta sección consolida el procedimiento repetido **indexación** utilizado para habilitar las nuevas funciones de **buscar y reemplazar** a nivel de mapa.

**Cuándo puede omitir la indexación**

El origen incluye notas de &quot;omisión&quot; según la ruta de actualización (por ejemplo, &quot;No es necesario realizar estos pasos si actualiza de la versión 4.3.0 o 4.3.1&quot; y notas similares). Siga la nota de omisión indicada en la sección de actualización.

Realice los siguientes pasos para indexar el contenido existente y utilice el nuevo texto de búsqueda y reemplazo a nivel de mapa:

1. Ejecute una petición POST (con autenticación):

```http
POST http://<server:port>/bin/guides/map-find/indexing
```

Parámetros opcionales admitidos en el origen:

- Rutas de asignaciones específicas del índice (de forma predeterminada se indizan todas las asignaciones):

  ```http
  POST http://<server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>
  ```

- Asignaciones de índice DITA en una carpeta raíz (y sus subcarpetas):

  ```http
  POST http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test
  ```

  >[!NOTE]
  >
  > Si se aprueban `paths` y `root`, solo se considerará `paths`.

1. La API devuelve un `jobId`. Para comprobar el estado, envíe una solicitud de GET:

   ```http
   GET http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}
   ```

   Comportamiento de finalización esperado:

   - Una vez finalizada, GET responde correctamente e indica si alguna de las asignaciones ha fallado.
   - Confirme las asignaciones indexadas correctamente en los registros del servidor.

### Asegúrese de que la indexación de damAssetLucene esté completa (cuando corresponda).

La fuente observa que la indexación de damAssetLucene puede tardar horas en función del tamaño de los datos y puede confirmar la finalización cuando `reindex` tenga `false` en:

`http://<server:port>/oak:index/damAssetLucene`

Si agregó personalizaciones en `damAssetLucene`, es posible que tenga que aplicarlas de nuevo una vez que se complete el reindexado.

### Solución alternativa para &quot;consulta leída o atravesada más de 100000 nodos&quot; (si el trabajo falla)

Si el trabajo de indexación falla y se muestra el error:

&quot;La consulta leyó o atravesó más de 100000 nodos. Para evitar que afectara a otras tareas, el procesamiento se detuvo&quot;.

Pruebe esta solución desde el origen:

1. En el índice Oak `damAssetLucene`, agregue la propiedad booleana `indexNodeName=true` en `/oak:index/damAssetLucene/indexRules/dam:Asset`.
2. Agregue un nuevo nodo denominado `excerpt` en `/oak:index/damAssetLucene/indexRules/dam:Asset/properties` y establezca las propiedades como se muestra en el origen:
   - `name=rep:excerpt`
   - `propertyIndex=true`
   - `notNullCheckEnabled=true`
3. Reindexe `damAssetLucene` estableciendo `reindex=true` y espere hasta que se convierta en `false` de nuevo (puede tomar horas).
4. Vuelva a ejecutar el script de indexación (repita el POST y el seguimiento de trabajos).

## Publicar el contenido existente en el proceso del informe de vínculos rotos

Esta sección consolida el procedimiento repetido **posterior al procesamiento** utilizado para habilitar el **informe de vínculos rotos**.

**Si puede omitir el procesamiento posterior**

El origen incluye notas de &quot;omisión&quot; según la ruta de actualización (por ejemplo, &quot;No es necesario realizar estos pasos si actualiza de la versión 4.3.0&quot; o &quot;de la versión 4.3.0 o 4.3.1&quot;). Siga la nota de omisión indicada en la sección de actualización.

Siga estos pasos para habilitar el informe de vínculos rotos:

1. (Opcional) Aumente Oak queryLimitReads para repositorios grandes

   Si hay más de **100 000 archivos DITA**, actualice `queryLimitReads` en `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valor mayor que el número de recursos (ejemplo: `200000`), vuelva a implementar y continúe.

   | PID | Clave de propiedad | Valor de propiedad |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valor: 200000 <br> Valor predeterminado: 100000 |

1. Ejecute las siguientes API para ejecutar el posprocesamiento en todos los archivos:

   | Punto final | /bin/guides/reports/upgrade |
   |---|---|
   | Tipo de solicitud | **POST** Este script es una petición POST por lo tanto debe ejecutarse a través de agentes como Postman. |
   | Respuesta esperada | La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID de trabajo al mismo punto final.<br> URL de ejemplo: `http://<server:port>/bin/guides/reports/upgrade` |

   | Punto final | /bin/guides/reports/upgrade |
   |---|---|
   | Tipo de solicitud | **GET** |
   | Parámetro | jobId: pase el jobId recibido de la solicitud de publicación anterior. |
   | Respuesta esperada | - Una vez completado el trabajo, la solicitud de GET responde correctamente. <br>: en caso de que haya errores, comparta los registros de errores junto con la salida de la API con el equipo de éxito del cliente.  <br>URL de ejemplo: `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |

1. Volver al valor predeterminado o anterior existente de `queryLimitReads` si lo ha cambiado en el paso 1.

## Habilitar el déclencheur del script mediante un servlet

Varias versiones incluyen un paso opcional para almacenar en déclencheur un trabajo de actualización de mapa de traducción a través de un servlet. Esta sección consolida ese procedimiento repetido e incluye todos los detalles proporcionados en el origen.


>[!NOTE]
>
> No es necesario que realice estos pasos si actualiza desde la versión 4.3.0 o 4.3.1.

PUBLICACIÓN:

```
http://localhost:4503/bin/guides/script/start?jobType=translation-map-upgrade
```

Respuesta:

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/translation-map-upgrade/1683190032886",
"status": "SCHEDULED"
}
```

En el JSON de respuesta anterior, la clave `lockNodePath` contiene la ruta al nodo creado en el repositorio que señala al trabajo enviado. Se eliminará automáticamente una vez finalizado el trabajo y, hasta entonces, puede hacer referencia a este nodo para consultar el estado actual del trabajo.

Busque `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` y `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` antes de continuar con los siguientes pasos.

>[!NOTE]
>
> Debe comprobar si el nodo sigue presente y el estado del trabajo.

**GET**: `http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json`


### Pasos para gestionar el conflicto de &quot;reescritura de multimedia&quot;

Experience Manager Guides incluye un módulo de reescritura de Sling personalizado (`fmditarewriter`) para administrar los vínculos generados para la vinculación entre mapas.

Si tiene otra reescritura de Sling personalizada en la base de código:

- Use un valor `order` **mayor que 50** porque las guías usan `order=50`.
- Durante esta actualización, el valor `order` cambia de `1000` a `50`, por lo que debe combinar la reescritura personalizada existente (si existe) con `fmditarewriter`.

