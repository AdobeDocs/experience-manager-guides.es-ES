---
title: Actualizar Adobe Experience Manager Guides
description: Obtenga información sobre cómo actualizar Adobe Experience Manager Guides
feature: Installation
role: Admin
level: Experienced
source-git-commit: 453da51a42984b912547570f2e1de70806b41171
workflow-type: tm+mt
source-wordcount: '1661'
ht-degree: 0%

---

# Actualizar Adobe Experience Manager Guides para la versión 4.6.0 o superior

Este artículo contiene instrucciones para actualizar las versiones de Experience Manager Guides para la 4.6.0 y posteriores.

>[!NOTE]
>
> Siga las instrucciones de actualización específicas de la versión con licencia del producto.

Puede actualizar su versión actual de Experience Manager Guides a la versión 5.1.0 Service Pack 3:

- Si utiliza la versión 5.1.0 o 5.1.x , puede actualizar directamente a la versión 5.1.0 Service Pack 3.
- Si utiliza las versiones 4.6.0, 4.6.x, 5.0.0 o 5.0.x, debe actualizar a la versión 5.1.0.
- Si tiene una versión anterior a la 4.6.0, consulte [Actualizar Adobe Experience Manager Guides para la versión 4.4.0 y anteriores](./upgrade-aemg-prev-versions.md) para obtener instrucciones detalladas sobre la actualización.

>[!NOTE]
>
> Debe instalar AEM Service Pack antes de actualizar la versión de Experience Manager Guides.

Para obtener más información, consulte los siguientes procedimientos:

- [Actualización a la versión 5.1.0](#upgrade-to-version-510)
- [Actualización a la versión 5.0.0](#upgrade-to-version-500)
- [Actualización a la versión 4.6.0](#upgrade-to-version-460)

>[!IMPORTANT]
>
> Antes de comenzar la actualización, realice una copia de seguridad completa del sistema para evitar la pérdida de datos.


## Actualización a la versión 5.1.0


>[!IMPORTANT]
>
> Si actualmente está en AEM 6.5 y planea pasar a AEM 6.5 LTS, asegúrese de completar primero la actualización de AEM antes de continuar con la actualización de Experience Manager Guides 5.1.0. Para obtener más información, vea [Actualización a Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

**Requisitos previos**

>[!NOTE]
>
>Si actualiza al paquete de servicio 3 5.1.0, debe tener la versión 5.1.0 o 5.1.x de Experience Manager Guides. El proceso de actualización para el paquete de servicio 3 de la versión 5.1.0 sigue los mismos pasos que en la versión 5.1.0.

Antes de iniciar el proceso de actualización de Experience Manager Guides 5.1.0, asegúrese de lo siguiente:

1. Se ha actualizado a Experience Manager Guides versión 4.6.3, 4.6.4, 5.0.0 o 5.0.0 Service Pack 1.
1. (Opcional) Cerró todas las tareas de traducción.
1. Se ha cambiado el nivel de registro a **INFO** para la clase `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` y se han anexado estos registros a un nuevo archivo de registro, por ejemplo, `logs/translation_upgrade.log`.

>[!NOTE]
>
> El posprocesamiento y la indexación pueden tardar unas horas. Le recomendamos que inicie el proceso de actualización durante las horas de menor actividad.

**Instalar versión 5.1.0**

Descargue el paquete de la versión 5.1.0 del [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html) y siga las instrucciones que se proporcionan en [Flujo de trabajo de instalación y actualización posterior a la instalación](#installation-and-post-installation-upgrade-workflow) para completar el proceso de actualización.


## Actualización a la versión 5.0.0

>[!TIP]
>
> La actualización a la versión 5.0.0 Service Pack 3 depende de la versión actual de Experience Manager Guides. Si está utilizando la versión 5.0.0 Service Pack 2, 5.0.0 Service Pack 1 o 5.0.0, puede actualizar directamente a la versión 5.0.0 Service Pack 3. Los pasos de actualización son los mismos que para la versión 5.0.0.

>[!NOTE]
>
> El posprocesamiento y la indexación pueden tardar unas horas. Le recomendamos que inicie el proceso de actualización durante las horas de menor actividad.

**Requisitos previos**

Antes de iniciar el proceso de actualización de Experience Manager Guides 5.0.0, asegúrese de lo siguiente:

1. Se ha actualizado a la versión de Experience Manager Guides 4.6.3, 4.6.1, 4.6.0 o 4.4.
1. (Opcional) Cerró todas las tareas de traducción.
1. Se ha cambiado el nivel de registro a **INFO** para la clase `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` y se han anexado estos registros a un nuevo archivo de registro, por ejemplo, `logs/translation_upgrade.log`.


**Instalar versión 5.0.0**

Descargue el paquete de la versión 5.0.0 del [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html) y siga las instrucciones que se proporcionan en [Flujo de trabajo de instalación y actualización posterior a la instalación](#installation-and-post-installation-upgrade-workflow) para completar el proceso de actualización.

## Actualización a la versión 4.6.0

>[!TIP]
>
> Se recomienda instalar el paquete de servicio 4.6.0 sobre la versión 4.6.0, el paquete de servicio 1 4.6.0 o el paquete de servicio 3 4.6.0. El proceso de actualización para el paquete de servicio 4 de la versión 4.6.0 sigue los mismos pasos que en la versión 4.6.0.

La actualización a la versión 4.6.0 depende de la versión actual de Experience Manager Guides. Si utiliza las versiones 4.4.0, 4.3.1, 4.3.0, 4.2 o 4.2.1 (revisión 4.2.1.3), puede actualizar directamente a la versión 4.6.0.

>[!NOTE]
>
> El posprocesamiento y la indexación pueden tardar unas horas. Le recomendamos que inicie el proceso de actualización durante las horas de menor actividad.

**Requisitos previos**

Antes de iniciar el proceso de actualización de Experience Manager Guides 4.6.0, asegúrese de lo siguiente:

1. Se ha actualizado a la versión de Experience Manager Guides 4.3.1, 4.3.0 o 4.2.1 (revisión 4.2.1.3).
1. (Opcional) Cerró todas las tareas de traducción.
1. Se ha cambiado el nivel de registro a **INFO** para la clase `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` y se han anexado estos registros a un nuevo archivo de registro, por ejemplo, `logs/translation_upgrade.log`.

**Instalar versión 4.6.0**

Descargue el paquete de la versión 4.6.0 del [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html) y siga las instrucciones que se proporcionan en [Flujo de trabajo de instalación y actualización posterior a la instalación](#installation-and-post-installation-upgrade-workflow) para completar el proceso de actualización.

## Flujo de trabajo de instalación y actualización posterior a la instalación

### Instalación del paquete de versión

Siga estos pasos para instalar el paquete de la versión:

1. Instale el paquete de la versión en la que desea actualizar.
1. Puede elegir pulsar el déclencheur para iniciar el trabajo de actualización del mapa de traducción. Para obtener más información, consulte [Habilitar el déclencheur del script mediante un servlet](#enable-trigger-of-script-via-a-servlet).

1. Una vez completada la instalación del paquete, espere al siguiente mensaje en los registros:

   `Completed the post deployment setup script`

   El mensaje anterior indica que se han completado todos los pasos de la instalación.

   Si encuentra cualquiera de los siguientes errores, informe de ellos a su equipo de éxito del cliente:

   - Error en el script de configuración posterior a la implementación
   - Excepción al transferir el mapa de traducción
   - No se puede portar el mapa de traducción de v1 a v2 para la propiedad
1. (Opcional) Actualice el complemento Conector de oxígeno lanzado con la versión a la que está actualizando.
1. Borre la caché del explorador después de instalar el paquete.

### Proceso posterior a la instalación

Después de instalar Experience Manager Guides, puede combinar las distintas configuraciones aplicables desde la versión recién instalada con la configuración.

>[!NOTE]
>
> El modelo dam-update-asset se puede personalizar. Por lo tanto, si se ha realizado alguna personalización, es necesario sincronizar las personalizaciones y Experience Manager Guides en la copia de trabajo del modelo.

**Flujo de trabajo del recurso de actualización DAM \(Cambios posteriores al procesamiento\):**

1. Abrir URL:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Seleccione **flujo de trabajo del recurso de actualización DAM**.
1. Seleccione **Editar**.
1. Si el componente **Iniciador de procesamiento posterior DXML** está presente, asegúrese de que las personalizaciones estén sincronizadas.
1. Si el componente **Iniciador de procesamiento posterior DXML** no está presente, realice los siguientes pasos para insertarlo:

   - Seleccione **Insertar componente** \(Responsable del posprocesamiento de Experience Manager Guides como paso final del proceso\).
   - Configure el **paso del proceso** con los siguientes detalles:

     **Ficha común:**

      - **Título:** Iniciador de procesamiento posterior DXML

      - **Descripción**: paso del iniciador posterior del proceso DXML que almacenará en déclencheur un trabajo sling para el posprocesamiento DXML del recurso modificado/creado

     **Ficha de proceso**

      - Seleccione **Iniciador de procesamiento posterior DXML** de la lista desplegable **Proceso**
      - Seleccionar **avance de controlador**
      - Seleccionar **Listo**

1. Seleccione **Sincronizar** en la parte superior derecha después de completar los cambios. Recibirá una notificación de éxito.

   >[!NOTE]
   >
   > Actualice y compruebe que los cambios personalizados y el paso posterior al procesamiento de Experience Manager Guides estén presentes en el modelo final de flujo de trabajo.

1. Una vez validado **flujo de trabajo del recurso de actualización DAM**, compruebe las configuraciones del iniciador correspondientes. Para ello, vaya a la interfaz de flujo de trabajo de AEM y abra los iniciadores.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Busque y realice cambios \(si es necesario\) en los dos iniciadores siguientes \(que deberían estar activos\) correspondientes a **flujo de trabajo de recursos de actualización de DAM**:

1. Lanzador para &quot;*Nodo creado*&quot; para **flujo de trabajo del recurso de actualización DAM**- para la condición `"jcr:content/jcr:mimeType!=video"`, el valor &#39;Globbing&#39; debe ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; debe tener `"event-user-data:changedByWorkflowProcess"`.
   - Lanzador para &quot;*Nodo modificado*&quot; para **flujo de trabajo de recursos de actualización DAM -** para la condición &quot;`jcr:content/jcr:mimeType!=video`&quot;, el valor &#39;Globbing&#39; debe ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` debe tener `"event-user-data:changedByWorkflowProcess"`.

1. Una vez completada la actualización, asegúrese de que cualquiera de las personalizaciones/superposiciones se valide y actualice para que coincida con el nuevo código de la aplicación. A continuación se ofrecen algunos ejemplos:
   - Cualquier componente superpuesto de `/libs/fmditaor/libsshould` debe compararse con el nuevo código de producto y las actualizaciones deben realizarse en archivos superpuestos en /apps.
   - Cualquier categoría `clientlib` utilizada del producto debe revisarse para ver si hay cambios. Cualquier configuración anulada `\(examples below\)` debe compararse con las más recientes para obtener las últimas funciones:
   - elementmapping.xml
   - `ui\_config.json\(may have been set in folder profiles\)`
   - se modificó `com.adobe.fmdita.config.ConfigManager`

1. Si ha añadido personalizaciones en damAssetLucene, es posible que tenga que volver a aplicarlas. Después de realizar estos cambios, establezca reindex como true. Esto reindexará todos los nodos existentes con las personalizaciones. Una vez finalizado, el indicador de reindexación se volverá a establecer en &quot;false&quot;. Esto puede tardar unas horas, según la cantidad de recursos que haya en el sistema.

### Pasos para reindexar los índices de Experience Manager Guides

1. Abra `crx/de` y vaya a la ruta de acceso del índice: `/oak:index/guidesAssetProperties`
2. Establezca la propiedad reindex como `true` (`false` de forma predeterminada) y haga clic en **Guardar todo**.
3. Una vez completado el reíndice, la propiedad reindex se vuelve a establecer en `false` y el recuento de reíndices se incrementa en 1.

   >[!NOTE]
   >
   > Esto puede tardar unos minutos, según la cantidad de datos presentes.
4. Siga los mismos pasos para otros índices agregados o modificados: `guidesBulkActivation`, `guidesPeerLinkIndex` y `guidesKonnectTemplateIndex`.

### Pasos para indexar el contenido existente

Siga estos pasos para indexar el contenido existente:

- Ejecute una petición POST al servidor \(con la autenticación correcta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: puede pasar rutas específicas de las asignaciones para indexarlas; de forma predeterminada, todas las asignaciones se indexarán || Ejemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- La API devolverá un `jobId`. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(por ejemplo: ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

- Una vez completado el trabajo, la solicitud de GET anterior responderá correctamente y mencionará si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.


>[!NOTE]
>
> Si utiliza el esquema personalizado, debe definir la ruta de los archivos DTD y XSD catalog.xml personalizados en el repositorio de AEM en la opción **Integrar catálogos**.

### Pasos para gestionar el conflicto `'fmdita rewriter'`

Experience Manager Guides tiene un módulo [**reescritor de sling personalizado**](../install-conf-guide/conf-output-generation.md#custom-rewriter) para administrar los vínculos generados en caso de mapas cruzados (vínculos entre los temas de dos mapas diferentes).

Si tiene otra reescritura de sling personalizada en la base de código, utilice un valor de `'order'` mayor que 50, ya que la reescritura de sling de Experience Manager Guides utiliza `'order'` 50.  Para anular esto, necesita un valor >50. Para obtener más información, vea [Canalizaciones de reescritura de salida](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante esta actualización, dado que el valor `'order'` ha cambiado de 1000 a 50, debe combinar la reescritura personalizada existente, si la hay, con `'fmdita-rewriter'`.


### Pasos para reindexar damAssetLucene

La definición del índice se actualiza para damAssetLucene con AEM Guides. Después de actualizar a la versión requerida, consulte [este artículo](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-16460) para reindexar damAssetLucene.

>[!NOTE]
>
> Mientras sigue la documentación, asegúrese de que ambas propiedades (`reindex=true` y `reindex-async=true` para `/oak:index/damAssetLucene`) se actualicen simultáneamente mediante la operación Guardar.

