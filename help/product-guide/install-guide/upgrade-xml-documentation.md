---
title: Actualizar Adobe Experience Manager Guides
description: Obtenga información sobre cómo actualizar Adobe Experience Manager Guides
exl-id: f058b39f-7408-4874-942b-693e133886cf
feature: Installation
role: Admin
level: Experienced
source-git-commit: f43d8d01a9c3b29328641680f3ba7d96ce7ecd79
workflow-type: tm+mt
source-wordcount: '8023'
ht-degree: 0%

---

# Actualizar Adobe Experience Manager Guides {#id224MBE0M0XA}

>[!NOTE]
>
> Siga las instrucciones de actualización específicas de la versión con licencia del producto.

Puede actualizar su versión actual de Experience Manager Guides a la versión 5.0.0:


- Si está utilizando la versión 4.6.x, 4.6 o 4.4, puede actualizar directamente a la versión 5.0.0.
- Si está utilizando la versión 4.3.x, 4.2, 4.2.1 (revisión 4.2.1.3), 4.1 o 4.1.x, debe actualizar a la versión 4.4 antes de actualizar a la versión 5.0.0.
- Si utiliza la versión 4.0, debe actualizar a la versión 4.2 antes de actualizar a la versión 4.3.x.
- Si utiliza la versión 3.8.5, debe actualizar a la versión 4.0 antes de actualizar a la versión 4.2.
- Si tiene una versión anterior a 3.8.5, consulte la sección Guías para la actualización Experience Manager en el guía de instalación específico del producto disponible en [el archivo](https://helpx.adobe.com/es/xml-documentation-for-experience-manager/archive.html) PDF de ayuda de Adobe Experience Manager Guías.


>[!NOTE]
>
> Debe instalar AEM Service Pack antes de actualizar la versión de Experience Manager Guides.

Para obtener más información, consulte los siguientes procedimientos:

- [Actualización de 3.8.5 a la versión 4.0](#upgrade-from-version-385-to-version-40)
- [Actualizar a la versión 4.2](#upgrade-to-version-42)
- [Actualizar a la versión 4.2.1](#upgrade-to-version-421)
- [Actualizar a la versión 4.3.0](#upgrade-to-version-430)
- [Actualización a la versión 4.3.1](#upgrade-to-version-431)
- [Actualizar a la versión 4.3.1.5](#upgrade-to-version-4315)
- [Actualización a la versión 4.4.0](#upgrade-to-version-440)
- [Actualización a la versión 4.6.0](#upgrade-to-version-460)
- [Actualización a la versión 5.0.0](#upgrade-to-version-500)



>[!IMPORTANT]
>
> Antes de comenzar la actualización, realice una copia de seguridad completa del sistema para evitar la pérdida de datos.

## Actualice de la versión 3.8.5 a la versión 4.0

Si utiliza la versión 3.8.5 de Experience Manager Guides, puede actualizar a la versión 4.0 de Experience Manager Guides. Con la función de actualización, no es necesario desinstalar la versión anterior de Experience Manager Guides.

Antes de ejecutar el proceso, hay ciertas tareas que debe completar. Las siguientes subsecciones le guiarán por los requisitos previos, la generación de informes y el proceso de migración. Además, después de instalar la versión 4.0 de Experience Manager Guides, puede personalizar varias configuraciones en función de la configuración del cliente.

>[!NOTE]
>
> Este proceso de actualización solo es aplicable de la versión 3.8.5 a la versión 4.0. Para el proceso de actualización de la versión 3.4 o superior a la 3.8.5, consulte la sección *Actualizar Experience Manager Guides* en la guía de instalación específica del producto disponible en [Archivo de PDF de ayuda de Adobe Experience Manager Guides](https://helpx.adobe.com/es/xml-documentation-for-experience-manager/archive.html).



**&#x200B;**&#x200B;Requisitos previos&#x200B;**&#x200B;**

Antes de inicio el proceso de actualización de las Guías Experience Manager, asegúrese de que:

1. Se importó el comentarios de revisión en temas abiertos para revisión.
1. Se cerraron todas las revisiones activas.
1. Se cerraron todas las tareas de traducción.
1. Desinstale cualquier revisión de Experience Manager Guides instalada sobre la versión anterior \(versión principal o de parche\) de Experience Manager Guides.

**Antes de instalar la versión 4.0**

Antes de instalar la versión 4.0, realice los siguientes pasos:

1. Asegúrese de que en este momento Experience Manager Guides esté en la versión 3.8.5.
1. Descargue el paquete del script de actualización. Para ello, busque &quot;Paquete de actualización de la solución XML Documentation 4.0&quot; en [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html), que descargará un archivo zip.
1. Cargue este paquete en AEM a través de Administrador de paquetes e instálelo.
1. Una vez instalado el paquete de actualización, ejecute los scripts dados a continuación en el mismo orden y seguir las instrucciones dadas:

**Comprobar la API de compatibilidad de actualización**

Esta API está diseñada para evaluar el estado actual del sistema e informar si la actualización es posible o no. Para ejecutar este script, active el punto final especificado a continuación:

| Punto final | /bin/dxml/upgrade/3xto4x/report |
| --- | --- |
| Tipo de solicitud | **GET** Puede usar un explorador web en el que haya iniciado sesión como administrador en la instancia de AEM. |
| Respuesta esperada | -   Si se pueden mover todos los nodos requeridos, se le aprobará una comprobación. <br>-   Si un nodo está presente en la ubicación de destino, se producirá un error relevante. Limpie el repositorio \(elimine el nodo /var/xml\), vuelva a instalar el paquete de actualización y, a continuación, almacene en déclencheur este extremo de nuevo. <br>**Nota:** Este no es un error común porque 3.x Experience Manager Guides no usa anteriormente la ubicación de destino. <br> -   Si este script no se ejecuta correctamente, no continúe y genere un informe para el equipo de éxito del cliente. |

**API de migración de datos del sistema**

Esta API está diseñada para migrar los datos del sistema como se menciona en la sección Asignación **de** migración.

1. No ejecute esta secuencia de comandos si se produce un error en la API Comprobar compatibilidad de actualización \(no continuar\).
1. Una vez que la API Comprobar compatibilidad de actualización se realice correctamente, puede ejecutar el script de actualización.

| Punto final | /bin/dxml/upgrade/3xto4x |
| --- | --- |
| Tipo de solicitud | **POST** Este script es una petición POST por lo tanto debe ejecutarse a través de agentes como Postman. |
| Respuesta esperada | -   Una vez completada la migración, puede instalar la solución de XML Documentation versión 4.0.<br>-   En caso de errores, restaure al último punto de comprobación y comparta los registros de errores junto con la salida de la API con el equipo de éxito del cliente. |

**Asignación de migración**: la API anterior migra todos los datos de la ubicación de origen a la ubicación de destino.

| Origen | Público destinatario |
|------|------|
| /content/fmdita | /var/dxml |
| /contenido/dxml | /var/dxml |
| /etc/fmdita | /libs/fmdita |

## Instalar la versión 4.0 {#id23598G006XA}

1. Instale la versión 4.0 solo si los pasos de actualización se realizaron correctamente.
1. Descargar el paquete de la versión 4.0 del [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html):

   - Si está utilizando la versión de software de UUID, busque &quot;Versión 4.0 de UUID para la solución XML Documentation para AEM 6.5&quot;.
   - Si está utilizando una versión de software que no es de UUID, búsqueda para &quot;4.0 Non-UUID release for XML Documentación solution for AEM 6.5&quot;.
Cargue el paquete en el servidor AEM existente instancia\(s\) utilizando el Administrador de paquetes CRX e instálelo.

   >[!NOTE]
   >
   > Espere a que todos los componentes del sistema se inicio.

1. Borre la Caché del explorador después de instalar el paquete.
1. Si Dispatcher está configurado en la instancia de autor de AEM, realice los siguientes pasos:
   - Asegúrese de que se gestionan las siguientes opciones en las reglas de Dispatcher:
   - El patrón de URL /home/users/\*/preferences está en la lista blanca.
   - El patrón de URL /libs/cq/security/userinfo.json no se almacena en caché.
1. Borrar caché de Dispatcher \(para borrar cualquier `clientlibs` almacenado en caché\).

## Actualización a la versión 4.2

La actualización a la versión 4.2 depende de la versión actual de Experience Manager Guides.

Si utiliza las versiones 4.0, 4.1 o 4.1.x, puede actualizar directamente a la versión 4.2.

**&#x200B;**&#x200B;Requisitos previos&#x200B;**&#x200B;**

Antes de inicio el proceso de actualización de las Guías de Experience Manager 4.2, asegúrese de lo siguiente:

1. Actualizado a las versiones 4.0, 4.1 o 4.1.x de Experience Manager Guides.
1. Se cerraron todas las tareas de traducción.
1. Se ha cambiado el nivel de registro a **INFO** para la clase `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` y se han anexado estos registros a un nuevo archivo de registro, por ejemplo, `logs/translation_upgrade.log.`

>[!NOTE]
>
> Debe cerrar todas las revisiones activas. Si las tareas de revisión no se cierran al actualizar a la versión 4.2, las tareas de revisión en curso más antiguas siguen llevando a los usuarios a las páginas de revisión más antiguas y las tareas de revisión creadas después de la actualización mostrarán las actualizaciones más recientes en la funcionalidad.

## Instalar versión 4.2 {#id2245IK0E0EV}

1. Descargue el paquete de la versión 4.2 del [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html).
1. Instale el paquete de la versión 4.2.
1. Después de completar la instalación del paquete, espere a que aparezca el siguiente mensaje en los registros:

   `Completed the post deployment setup script`

   El mensaje anterior indica que se han completado todos los pasos de la instalación.

   Si encuentra cualquiera de los siguientes prefijos ERROR, informe de ellos a su equipo de éxito del cliente:

   - Error en el script de configuración posterior a la implementación
   - Excepción al portar el MAP de traducción
   - No se puede puerto asignación de traducción de v1 a v2 para Propiedad
1. Actualice el conector de oxígeno plug-in lanzado con la versión 4.2 \(si es necesario\).
1. Borre la Caché del explorador después de instalar el paquete.
1. Continuar actualizar las personalizaciones como se detalla en la siguiente sección.

## Después de instalar la versión 4.2 {#id2326F02004K}

>[!IMPORTANT]
>
> El plantilla de alta tecnología no se muestra en el servidor actualizado. Para incluir la plantilla de alta tecnología en el servidor, puede copiarla: Source: /libs/fmdita/pdf/Hi-Tech Destino: /content/dam/dita-templates/pdf

Después de instalar Experience Manager Guides, puede combinar las distintas configuraciones aplicables desde la versión recién instalada con la configuración.

>[!NOTE]
>
> El modelo dam-update-asset se puede personalizar. Por lo tanto, si se ha realizado alguna personalización, es necesario sincronizar las personalizaciones y Experience Manager Guides en la copia de trabajo del modelo.

1. **Flujo de trabajo del recurso de actualización DAM \(Cambios posteriores al procesamiento\):**

1. Abrir URL:

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Seleccione **DAM flujo de trabajo** de actualización de recursos.
1. Haga clic en **Editar**.
1. Si el **componente DXML Post Process Initiator** está presente, asegúrese de que las personalizaciones están sincronizadas.
1. Si el **componente DXML Post Process Initiator** está ausente, realice los siguientes pasos para insertarlo:

1. Haga clic en **Insertar componente** \(Responsable de Experience Manager guías entrada procesamiento como paso final del proceso\).
1. Configure el **paso del proceso** con los siguientes detalles:

   **Ficha común**

   **Título:** Iniciador de procesamiento posterior DXML

   **Descripción**: paso del iniciador posterior del proceso DXML que almacenará en déclencheur un trabajo sling para el posprocesamiento DXML del recurso modificado/creado

   **Ficha de proceso**

   - Seleccione **Iniciador de procesamiento posterior DXML** de la lista desplegable **Proceso**

   - Seleccionar **avance de controlador**

   - Seleccionar **Listo**

1. Haga clic en **Sincronizar** en la parte superior derecha después de completar los cambios. Recibirá una notificación de éxito.

   >[!NOTE]
   >
   > Actualice y compruebe que los cambios personalizados y el paso posterior al procesamiento de Experience Manager Guides estén presentes en el modelo final de flujo de trabajo.

1. Una vez **validada DAM flujo de trabajo** de Update Asset , compruebe las configuraciones de lanzador correspondientes. Para ello, vaya a AEM interfaz de flujo de trabajo y abra los iniciadores.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Busque y realice cambios \(si es necesario\) en los dos iniciadores siguientes \(que deben estar activos\) correspondientes a **DAM flujo de trabajo** de actualización de recursos:

1. Lanzador para &quot;*Nodo creado*&quot; para **DAM Actualizar recurso flujo de trabajo**- para la condición `"jcr:content/jcr:mimeType!=video"`, el valor &#39;Globbing&#39; debería ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; debe tener `"event-user-data:changedByWorkflowProcess"`.
   - Lanzador para &quot;*Nodo modificado*&quot; para **flujo de trabajo de recursos de actualización DAM -** para la condición &quot;`jcr:content/jcr:mimeType!=video`&quot;,
   - el valor &quot;Globbing&quot; debe ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; debe tener `"event-user-data:changedByWorkflowProcess"`.
1. Una vez completada la actualización, asegúrese de que cualquiera de las personalizaciones o superposiciones se validan y actualizan para que coincidan con el nuevo código aplicación. A continuación se muestran algunos ejemplos:
   - Cualquier componente superpuesto de /libs/fmditaor/libs debe compararse con el nuevo código de producto y las actualizaciones deben realizarse en archivos superpuestos en /apps.
   - Cualquier categoría clientlib utilizada desde el producto debe revisarse para ver si hay cambios. Cualquier configuración anulada \(ejemplos abajo\) debe compararse con las más recientes para obtener las últimas funciones:
   - elementmapping.xml
   - UI\_config.json\(puede haberse configurado en perfiles de carpeta\)
   - irreparable `com.adobe.fmdita.config.ConfigManager`
   - Compruebe si alguno de los códigos personalizados utilizaba rutas antiguas \(como se menciona en la [sección Asignación](#id2244LE040XA) de migración\)\: debe actualizarse a las nuevas rutas para que las personalizaciones también funcionen como se espera.
1. Lea acerca de las nuevas configuraciones introducidas en la versión actual \(consulte [las Notas](../release-info/release-notes-4-3.md) de la versión\) y vea si alguna funcionalidad se ve afectada, luego tome las medidas adecuadas. Un ejemplo podría ser hacer uso de &quot;Manejo mejorado de archivos y versiones&quot; introducido en la versión 4.0, para lo cual necesita habilitar una configuración.

## Pasos para indexar el contenido existente y utilizar la nueva función de buscar y reemplazar:

Realice los siguientes pasos para indexar el contenido existente y utilice el nuevo texto de búsqueda y reemplazo a nivel de mapa:

- Ejecute una petición POST al servidor \(con la autenticación correcta\) - `http://<server:port\>/bin/guides/map-find/indexing`. \(Opcional: Puede pasar rutas específicas de los mapas para indexarlos, de forma predeterminada todos los mapas se indexarán \|\| Por ejemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`\)

- La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar un petición GET con ID de trabajo al mismo extremo:

`http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Por ejemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)

- Una vez completado el trabajo, la solicitud de GET anterior responderá correctamente y mencionará si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.

Si el trabajo de actualización falla y el registro de errores muestra el siguiente error:

&quot;La *consulta* leyó o atravesó más de *100000 nodos*. Para evitar que afectara a otras tareas, el procesamiento se detuvo&quot;.

Esto podría suceder porque el índice no está configurado correctamente para la consulta utilizada en la actualización. Puede probar la siguiente solución:

1. En el índice damAssetLucene oak, agregue la propiedad booleana `indexNodeName` como `true` en el nodo.
   `/oak:index/damAssetLucene/indexRules/dam:Asset`
1. Agregue un nuevo nodo con el extracto de nombre bajo el nodo.

   `/oak:index/damAssetLucene/indexRules/dam:Asset/properties`
y establezca las siguientes propiedades en el nodo:

   ```
   name - rep:excerpt
   propertyIndex - {Boolean}true
   notNullCheckEnabled - {Boolean}true
   ```

   La estructura de `damAssetLucene` debería tener un aspecto similar al siguiente:

   ```
   <damAssetLucene compatVersion="{Long}2" async="async, nrt" jcr:primaryType="oak:QueryIndexDefinition" evaluatePathRestrictions="{Boolean}true" type="lucene">
   <indexRules jcr:primaryType="nt:unstructured">
     <dam:Asset indexNodeName="{Boolean}true" jcr:primaryType="nt:unstructured">
       <properties jcr:primaryType="nt:unstructured">
         <excerpt name="rep:excerpt" propertyIndex="{Boolean}true" jcr:primaryType="nt:unstructured" notNullCheckEnabled="{Boolean}true"/>
       </properties>
       </dam:Asset>
     </indexRules>
   </damAssetLucene>    
   ```


   (junto con otros nodos y propiedades existentes)

1. Vuelva a indexar el `damAssetLucene` índice (configurando el indicador de reindexación como `true` se muestra en
y esperar a que vuelva a estar `false` (esto indica que la reindexación se ha completado). Tenga en cuenta que puede tardar algunas horas dependiendo del tamaño del índice.
1. Ejecute la secuencia de comandos de indexación de nuevo realizando los pasos anteriores.


## Actualizar a la versión 4.2.1

>[!TIP]
>
>Se recomienda instalar Hotfix sobre la 4.2.1.3 versión 4.2.1.

La actualización a la versión 4.2.1 depende de la versión actual de Experience Manager guías. Si utiliza la versión 4.1, 4.1.x o 4.2, puede actualizar directamente a la versión 4.2.1.

>[!NOTE]
>
>El posprocesamiento y la indexación pueden tardar unas horas. Le recomendamos que inicie el proceso de actualización durante las horas de menor actividad.

**&#x200B;**&#x200B;Requisitos previos&#x200B;**&#x200B;**

Antes de iniciar el proceso de actualización de Experience Manager Guides 4.2.1, asegúrese de lo siguiente:

1. Se ha actualizado a la versión de Experience Manager Guides 4.1, 4.1.x o 4.2.
1. Se cerraron todas las tareas de traducción.
1. Se ha cambiado el nivel de registro a **INFO** para `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` la clase y se añaden estos registros en una nueva archivo de registro, por ejemplo: `logs/translation_upgrade.log.`

>[!NOTE]
>
> Debe cerrar todas las revisiones activas. Si las tareas de revisión no se cierran durante la actualización a 4.2, las tareas de revisión en curso más antiguas siguen llevando a los usuarios a las páginas de revisión más antiguas, y las tareas de revisión creadas después de la actualización mostrarán las últimas actualizaciones en el funcionalidad.

## Instale la versión 4.2.1

1. Descargue el paquete de la versión 4.2.1 Adobe Systems Portal[&#128279;](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html) de distribución de software.
1. Instale el paquete de la versión 4.2.1.
1. Puede elegir ENTRAR en el déclencheur para iniciar el trabajo de actualización del mapa de traducción. Para obtener más información, consulte [Habilitar el déclencheur del script mediante un servlet](#enable-trigger-of-script-via-a-servlet-for-421).


1. Después de completar la instalación del paquete, espere a que aparezca el siguiente mensaje en los registros:

   `Completed the post deployment setup script`

   El mensaje anterior indica que se han completado todos los pasos de la instalación.

   Si encuentra cualquiera de los siguientes prefijos ERROR, informe de ellos a su equipo de éxito del cliente:

   - Error en el script de configuración posterior a la implementación
   - Excepción al transferir el mapa de traducción
   - No se puede puerto asignación de traducción de v1 a v2 para Propiedad
1. Actualice el conector de oxígeno plug-in lanzado con la versión 4.2 \(si es necesario\).
1. Borre la Caché del explorador después de instalar el paquete.
1. Continuar actualizar las personalizaciones como se detalla en la siguiente sección.

### Habilitar el activador de secuencia de comandos mediante un servlet (para 4.2.1)

EXPONER:

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

En el JSON de respuesta anterior, la clave `lockNodePath` contiene la ruta al nodo creado en el repositorio que apunta al trabajo enviado. Se eliminará automáticamente una vez que se complete el trabajo, hasta entonces, puede consultar este nodo para conocer el estado actual del trabajo.

Registro de muestra:
El siguiente es un ejemplo de registros que aparecerán en la archivo de registro después de desencadenar el script.

```
04.05.2023 14:17:12.876 *INFO* [[0:0:0:0:0:0:0:1] [1683190032736] POST /bin/guides/script/start HTTP/1.1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Acquiring lock for job : translation-map-upgrade
04.05.2023 14:17:12.897 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Starting the thread to upgrade translation map from V1 to V2
04.05.2023 14:17:12.899 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Initiating lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.901 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Starting porting of translation map from V1 to V2
04.05.2023 14:17:12.904 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Memory increase is of : 764 kB
04.05.2023 14:17:12.906 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2
04.05.2023 14:17:12.907 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Releasing lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.909 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2
```

Look para y `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` antes `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` de continuar con los pasos siguientes.



## Después de instalar la versión 4.2.1

>[!IMPORTANT]
>
> El plantilla de alta tecnología no se muestra en el servidor actualizado. Para incluir la plantilla de alta tecnología en el servidor, puede copiarla: Source: /libs/fmdita/pdf/Hi-Tech Destino: /content/dam/dita-templates/pdf

Después de instalar Experience Manager Guides, puede combinar las distintas configuraciones aplicables desde la versión recién instalada con la configuración.

>[!NOTE]
>
> El modelo dam-update-asset se puede personalizar. Por lo tanto, si se ha realizado alguna personalización, es necesario sincronizar las personalizaciones y Experience Manager Guides en la copia de trabajo del modelo.

1. **DAM flujo de trabajo de actualización de recursos \(cambios Post procesamiento electrónico\):**

1. Abrir URL:

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Seleccione **DAM flujo de trabajo** de actualización de recursos.
1. Haga clic en **Editar**.
1. Si el **componente DXML Post Process Initiator** está presente, asegúrese de que las personalizaciones están sincronizadas.
1. Si el componente **Iniciador de procesamiento posterior DXML** no está presente, realice los siguientes pasos para insertarlo:

1. Haga clic en **Insertar componente** \(Responsable del posprocesamiento de Experience Manager Guides como paso final del proceso\).
1. Configure el **paso del proceso** con los siguientes detalles:

   **Ficha común**

   **Título:** DXML Post Process Initiator

   **Descripción**: paso del iniciador posterior del proceso DXML que almacenará en déclencheur un trabajo sling para el posprocesamiento DXML del recurso modificado/creado

   **Ficha de proceso**

   - Seleccione **Iniciador de procesamiento posterior DXML** de la lista desplegable **Proceso**

   - Seleccionar **avance de controlador**

   - Seleccionar **Listo**

1. Haga clic en **Sincronizar** en la parte superior derecha después de completar los cambios. Recibirá una notificación de éxito.

   >[!NOTE]
   >
   > Actualice y compruebe que los cambios personalizados y el paso posterior al procesamiento de Experience Manager Guides estén presentes en el modelo final de flujo de trabajo.

1. Una vez validado **flujo de trabajo del recurso de actualización DAM**, compruebe las configuraciones del iniciador correspondientes. Para ello, vaya a la interfaz de flujo de trabajo de AEM y abra los iniciadores.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Busque y realice cambios \(si es necesario\) en los dos iniciadores siguientes \(que deberían estar activos\) correspondientes a **flujo de trabajo de recursos de actualización de DAM**:

1. Lanzador para &quot;*Nodo creado*&quot; para **DAM Actualizar recurso flujo de trabajo**- para la condición `"jcr:content/jcr:mimeType!=video"`, el valor &#39;Globbing&#39; debería ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; debería tener `"event-user-data:changedByWorkflowProcess"`.
   - Lanzador para &quot;*Nodo modificado*&quot; para **DAM Update flujo de trabajo de recurso** : para la condición &quot;`jcr:content/jcr:mimeType!=video`&quot;, el valor &quot;Globbing&quot; debería ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` debería tener `"event-user-data:changedByWorkflowProcess"`.

1. Una vez completada la actualización, asegúrese de que cualquiera de las personalizaciones o superposiciones se validan y actualizan para que coincidan con el nuevo código aplicación. A continuación se muestran algunos ejemplos:
   - Cualquier componente superpuesto de /libs/fmditaor/libs debe compararse con el nuevo código de producto y las actualizaciones deben realizarse en archivos superpuestos en /apps.
   - Cualquier categoría clientlib utilizada desde el producto debe revisarse para ver si hay cambios. Las configuraciones anuladas \(ejemplos a continuación\) deben compararse con las más recientes para obtener las últimas funciones:
   - elementmapping.xml
   - ui\_config.json\(puede haberse configurado en perfiles de carpeta\)
   - se modificó `com.adobe.fmdita.config.ConfigManager`
   - Compruebe si alguno de los códigos personalizados estaba usando rutas antiguas \(como se menciona en la sección [Asignación de migración](#id2244LE040XA)\) - debe actualizarse a las nuevas rutas para que las personalizaciones también funcionen según lo esperado.
1. Obtenga información sobre las nuevas configuraciones que se introdujeron en la versión actual \(compruebe [Notas de la versión](../release-info/release-notes-4-2-1.md)\) y vea si alguna funcionalidad se ve afectada y, a continuación, tome las medidas adecuadas. Un ejemplo podría ser utilizar el &quot;Control de archivos y versiones mejorado&quot; introducido en la versión 4.0, para el cual necesita habilitar una configuración.

## Pasos para indexar el contenido existente y utilizar la nueva función de buscar y reemplazar:

Realice los siguientes pasos para indexar el contenido existente y utilice el nuevo texto de búsqueda y reemplazo a nivel de mapa:

- Asegúrese de que se ha completado la indexación `damAssetLucene`. Puede tardar hasta unas horas, según la cantidad de datos presentes en el servidor. Puede confirmar que la reindexación se ha completado comprobando que el campo de reindexación está configurado como falso en
  `http://<server:port>/oak:index/damAssetLucene`.  Además, si ha agregado personalizaciones en `damAssetLucene`, es posible que tenga que volver a aplicarlas.

- Ejecute una petición POST al servidor \(con la autenticación correcta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: puede pasar rutas específicas de las asignaciones para indexarlas; de forma predeterminada, todas las asignaciones se indexarán \|\| Por ejemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- También se puede pasar una carpeta raíz para indexar las asignaciones DITA de una carpeta específica (y sus subcarpetas). Por ejemplo, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Tenga en cuenta que si se pasan tanto el parámetro de rutas como el parámetro raíz, solo se tendrá en cuenta el parámetro de rutas.

- La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(por ejemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


- Una vez completado el trabajo, la solicitud de GET anterior responderá correctamente y mencionará si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.


## Actualizar a la versión 4.3.0

La actualización a la versión 4.3.0 depende de la versión actual de Experience Manager guías. Si está utilizando la versión 4.2 o 4.2.x, puede actualizar directamente a la versión 4.3.0.

>[!NOTE]
>
>El procesamiento electrónico de la entrada y la indexación pueden tardar unas horas. Le recomendamos que inicio el proceso de actualización durante las horas de menor actividad.

**&#x200B;**&#x200B;Requisitos previos&#x200B;**&#x200B;**

Antes de inicio el proceso de actualización de las guías Experience Manager 4.3.0, asegúrese de que:

1. Se han actualizado a la versión 4.2 o 4.2.x de Experience Manager Guides y han completado su respectivo paso de instalación.
1. Se han cerrado todas las tareas de traducción.



## Instalar la versión 4.3.0

1. Descargue el paquete de la versión 4.3.0 de Adobe Systems Portal[&#128279;](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html) de distribución de software.
1. Instale el paquete de la versión 4.3.0.
1. Borre la Caché del explorador después de instalar el paquete.
1. Actualice el `ui_config.json` archivo desde el **pestaña Configuración** del Editor XML del perfil Carpeta.


## Después de instalar la versión 4.3.0

Después de instalar Experience Manager guías, puede combinar las diversas configuraciones aplicables de la versión recién instalada a su configuración.

## Pasos para procesar entrada el contenido existente utilizar el informe de vincular interrumpido


Realice los siguientes pasos para entrada el procesamiento de los contenido existentes y el uso del nuevo informe de vincular roto:

1. (Opcional) Si hay más de 100.000 archivos dita en el sistema, actualice el `queryLimitReads` bajo `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valor mayor (cualquier valor mayor que el número de activos presente, por ejemplo, 200.000) y, a continuación, vuelva a implementarlo.

   | PID | Clave de propiedad | Valor de propiedad |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valor: 200000 <br> Valor predeterminado: 100000 |

1. Ejecute las siguientes API para ejecutar el procesamiento entrada en todos los archivos:

   | Punto final | /bin/guides/reports/upgrade |
   |---|---|
   | Tipo de solicitud | **POST** Este script es una petición POST por lo tanto debe ejecutarse a través de agentes como Postman. |
   | Respuesta esperada | La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID de trabajo al mismo punto final.<br> Ejemplo de URL: `http://<server:port>/bin/guides/reports/upgrade` |

   | Punto final | /bin/guides/reports/upgrade |
   |---|---|
   | Tipo de solicitud | **OBTENER** |
   | Parámetro | jobId: Pasa el jobId recibido del solicitud de entrada anterior. |
   | Respuesta esperada | - Una vez completado el trabajo, la solicitud de GET responde correctamente. <br>: en caso de que haya errores, comparta los registros de errores junto con la salida de la API con el equipo de éxito del cliente.  <br>URL de ejemplo: `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |


1. Volver al valor predeterminado o anterior existente de `queryLimitReads` si lo ha cambiado en el paso 1.



## Actualización a la versión 4.3.1

La actualización a la versión 4.3.1 depende de la versión actual de Experience Manager Guides. Si utiliza las versiones 4.3.0, 4.2 o 4.2.1, puede actualizar directamente a la versión 4.3.1.

>[!NOTE]
>
>El posprocesamiento y la indexación pueden tardar unas horas. Le recomendamos que inicie el proceso de actualización durante las horas de menor actividad.

**&#x200B;**&#x200B;Requisitos previos&#x200B;**&#x200B;**

Antes de iniciar el proceso de actualización de Experience Manager Guides 4.3.1, asegúrese de lo siguiente:

1. Se ha actualizado a la versión de Experience Manager Guides 4.3.0, 4.2 o 4.2.1 y se han completado los pasos de instalación correspondientes.
1. (Opcional) Cerró todas las tareas de traducción.
1. Se ha cambiado el nivel de registro a **INFO** para la clase `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` y se han anexado estos registros a un nuevo archivo de registro, por ejemplo, `logs/translation_upgrade.log`.


## Instalar versión 4.3.1

1. Descargue el paquete de la versión 4.3.1 del [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html).
1. Instale el paquete de la versión 4.3.1.
1. Puede elegir ENTRAR en el déclencheur para iniciar el trabajo de actualización del mapa de traducción. Para obtener más información, consulte [Habilitar el déclencheur del script mediante un servlet](#enable-trigger-of-script-via-a-servlet-for-431).


1. Después de completar la instalación del paquete, espere a que aparezca el siguiente mensaje en los registros:

   `Completed the post deployment setup script`

   El mensaje anterior indica que se han completado todos los pasos de la instalación.

   Si encuentra cualquiera de los siguientes prefijos ERROR, informe de ellos a su equipo de éxito del cliente:

   - Error en el script de configuración posterior a la implementación
   - Excepción al portar el MAP de traducción
   - No se puede puerto asignación de traducción de v1 a v2 para Propiedad
1. Actualice el conector de oxígeno plug-in lanzado con la versión 4.2 \(si es necesario\).
1. Borre la Caché del explorador después de instalar el paquete.
1. Continuar actualizar las personalizaciones como se detalla en la siguiente sección.

### Habilitar el activador de secuencia de comandos mediante un servlet (para 4.3.1)

EXPONER:

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

En el JSON de respuesta anterior, la clave `lockNodePath` contiene la ruta al nodo creado en el repositorio que apunta al trabajo enviado. Se eliminará automáticamente una vez que se complete el trabajo, hasta entonces, puede consultar este nodo para conocer el estado actual del trabajo.

Registro de muestra:
El siguiente es un ejemplo de registros que aparecerán en la archivo de registro después de desencadenar el script.

```
04.05.2023 14:17:12.876 *INFO* [[0:0:0:0:0:0:0:1] [1683190032736] POST /bin/guides/script/start HTTP/1.1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Acquiring lock for job : translation-map-upgrade
04.05.2023 14:17:12.897 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Starting the thread to upgrade translation map from V1 to V2
04.05.2023 14:17:12.899 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Initiating lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.901 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Starting porting of translation map from V1 to V2
04.05.2023 14:17:12.904 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Memory increase is of : 764 kB
04.05.2023 14:17:12.906 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2
04.05.2023 14:17:12.907 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Releasing lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.909 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2
```

Look para y `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` antes `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` de continuar con los pasos siguientes.

## Después de instalar la versión 4.3.1



Después de instalar Experience Manager Guides, puede combinar las distintas configuraciones aplicables desde la versión recién instalada con la configuración.

>[!NOTE]
>
> El modelo dam-update-asset se puede personalizar. Por lo tanto, si se ha realizado alguna personalización, es necesario sincronizar las personalizaciones y Experience Manager Guides en la copia de trabajo del modelo.

1. **DAM flujo de trabajo de actualización de recursos \(cambios Post procesamiento electrónico\):**

1. Abrir URL:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Seleccione **DAM flujo de trabajo** de actualización de recursos.
1. Haga clic en **Editar**.
1. Si el **componente DXML Post Process Initiator** está presente, asegúrese de que las personalizaciones están sincronizadas.
1. Si el **componente DXML Post Process Initiator** está ausente, realice los siguientes pasos para insertarlo:

1. Haga clic en **Insertar componente** \(Responsable del posprocesamiento de Experience Manager Guides como paso final del proceso\).
1. Configure el **paso del proceso** con los siguientes detalles:

   **Ficha común**

   **Título:** Iniciador de procesamiento posterior DXML

   **Descripción**: DXML entrada proceso iniciador paso que activará un trabajo de sling para el procesamiento entrada DXML del recurso modificado/creado

   **Ficha de proceso**

   - Seleccione **Iniciador de procesamiento posterior DXML** de la lista desplegable **Proceso**

   - Seleccionar **avance de controlador**

   - Seleccionar **Listo**

1. Haga clic en **Sincronizar** en la parte superior derecha después de completar los cambios. Recibirá una notificación de éxito.

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
   - Cualquier componente superpuesto de /libs/fmidator/libs debe compararse con el nuevo código de producto y las actualizaciones deben realizarse en archivos superpuestos en /apps.
   - Cualquier categoría clientlib utilizada desde el producto debe revisarse para ver si hay cambios. Cualquier configuración anulada \(ejemplos abajo\) debe compararse con las más recientes para obtener las últimas funciones:
   - elementmapping.xml
   - ui\_config.json\(puede haberse configurado en perfiles de carpeta\)
   - se modificó `com.adobe.fmdita.config.ConfigManager`


## Pasos para indexar el contenido existente

>[!NOTE]
>
> No es necesario que realice estos pasos si actualiza desde la versión 4.3.0 o 4.2.1.

Realice los siguientes pasos para indexar el contenido existente y utilice el nuevo texto de búsqueda y reemplazo a nivel de mapa:


- Ejecute una petición POST al servidor \(con la autenticación correcta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: puede pasar rutas específicas de las asignaciones para indexarlas; de forma predeterminada, todas las asignaciones se indexarán \|\| Por ejemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)


- La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(por ejemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


- Una vez completado el trabajo, la solicitud de GET anterior responderá correctamente y mencionará si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.

## Pasos para publicar y procesar el contenido existente a fin de utilizar el informe de vínculos rotos

>[!NOTE]
>
> No es necesario que realice estos pasos si actualiza desde la versión 4.3.0

Realice los siguientes pasos para posprocesar el contenido existente y utilizar el nuevo informe de vínculos rotos:

1. (Opcional) Si hay más de 100 000 archivos dita en el sistema, actualice `queryLimitReads` en `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valor mayor (cualquier valor mayor que el número de recursos presentes, por ejemplo 200 000) y vuelva a implementar.

   | PID | Clave de propiedad | Valor de propiedad |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valor: 200000 <br> Valor predeterminado: 100000 |

1. Ejecute las siguientes API para ejecutar el procesamiento entrada en todos los archivos:

   | Punto final | /bin/guides/reports/upgrade |
   |---|---|
   | Tipo de solicitud | **&#x200B;**&#x200B;POST Este script es un petición POST por lo tanto, debe ejecutarse a través de agentes gustar Postman. |
   | Respuesta esperada | La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar un petición GET con ID de trabajo al mismo extremo.<br> Ejemplo de URL: `http://<server:port>/bin/guides/reports/upgrade` |

   | Punto final | /bin/guides/reports/upgrade |
   |---|---|
   | Tipo de solicitud | **GET** |
   | Parámetro | jobId: Pasa el jobId recibido del solicitud de entrada anterior. |
   | Respuesta esperada | - Una vez completado el trabajo, el petición GET responde con éxito. <br> - En caso de que haya errores, comparta los registros de errores junto con la salida de la API con su equipo de éxito del cliente.  <br>URL de ejemplo: `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |


1. Volver al valor predeterminado o anterior existente de `queryLimitReads` si lo ha cambiado en el paso 1.



## Actualizar a la versión 4.3.1.5

La actualización a la versión 4.3.1.5 depende de la versión actual de Experience Manager Guides. Si utiliza la versión 4.3.1, puede actualizar directamente a la versión 4.3.1.5.



## Instalar versión 4.3.1.5

1. Descargue el paquete de la versión 4.3.1.5 del [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html).
1. Instale el paquete de la versión 4.3.1.5.

1. Espere a que el proceso de instalación se complete correctamente.
1. Continúe actualizando las personalizaciones como se detalla en la siguiente sección.


## Después de instalar la versión 4.3.1.5


>[!NOTE]
>
>Si desea utilizar el paquete org.apache.velocity, realice los siguientes pasos antes de cargar el paquete:
> 1. Vaya a `<server>:<port>/system/console/bundles`.
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

La actualización a la versión 4.4.0 depende de la versión actual de Experience Manager Guides. Si utiliza las versiones 4.3.1, 4.3.0, 4.2 o 4.2.1 (revisión 4.2.1.3), puede actualizar directamente a la versión 4.4.0

>[!NOTE]
>
>El posprocesamiento y la indexación pueden tardar unas horas. Le recomendamos que inicie el proceso de actualización durante las horas de menor actividad.

**&#x200B;**&#x200B;Requisitos previos&#x200B;**&#x200B;**

Antes de iniciar el proceso de actualización de Experience Manager Guides 4.4.0, asegúrese de lo siguiente:

1. Se ha actualizado a la versión de Experience Manager Guides 4.3.1, 4.3.0 o 4.2.1 (revisión 4.2.1.3) y se han completado los pasos de instalación correspondientes.
1. (Opcional) Cerró todas las tareas de traducción.
1. Se ha cambiado el nivel de registro a **INFO** para la clase `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` y se han anexado estos registros a un nuevo archivo de registro, por ejemplo, `logs/translation_upgrade.log`.


## Instalar versión 4.4.0

1. Descargue el paquete de la versión 4.4.0 del [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html).
1. Instale el paquete de la versión 4.4.0.
1. Puede elegir ENTRAR en el déclencheur para iniciar el trabajo de actualización del mapa de traducción. Para obtener más información, consulte [Habilitar el déclencheur del script mediante un servlet](#enable-trigger-of-script-via-a-servlet).

1. Después de completar la instalación del paquete, espere a que aparezca el siguiente mensaje en los registros:

   `Completed the post deployment setup script`

   El mensaje anterior indica que se han completado todos los pasos de la instalación.

   Si encuentra cualquiera de los siguientes prefijos ERROR, informe de ellos a su equipo de éxito del cliente:

   - Error en el script de configuración posterior a la implementación
   - Excepción al transferir el mapa de traducción
   - No se puede puerto asignación de traducción de v1 a v2 para Propiedad
1. Actualice el conector de oxígeno plug-in lanzado con la versión 4.4.0 \(si es necesario\).
1. Borre la Caché del explorador después de instalar el paquete.
1. Continuar actualizar las personalizaciones como se detalla en la siguiente sección.


## Después de instalar la versión 4.4.0

Después de instalar Experience Manager guías, puede combinar las diversas configuraciones aplicables de la versión recién instalada a su configuración.

>[!NOTE]
>
> El modelo dam-update-recurso puede personalizarse. Por lo tanto, si se han realizado personalizaciones, debemos sincronizar las personalizaciones y las guías de Experience Manager en la copia de trabajo del modelo.

1. **DAM flujo de trabajo de actualización de recursos \(cambios Post procesamiento electrónico\):**

1. Abrir URL:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Seleccione **DAM flujo de trabajo** de actualización de recursos.
1. Haz clic en **Editar**.
1. Si el componente **Iniciador de procesamiento posterior DXML** está presente, asegúrese de que las personalizaciones estén sincronizadas.
1. Si el componente **Iniciador de procesamiento posterior DXML** no está presente, realice los siguientes pasos para insertarlo:

1. Haga clic en **Insertar componente** \(Responsable del posprocesamiento de Experience Manager Guides como paso final del proceso\).
1. Configure el **paso del proceso** con los siguientes detalles:

   **Ficha común**

   **Título:** Iniciador de procesamiento posterior DXML

   **Descripción**: paso del iniciador posterior del proceso DXML que almacenará en déclencheur un trabajo sling para el posprocesamiento DXML del recurso modificado/creado

   **Ficha de proceso**

   - Seleccione **Iniciador de procesamiento posterior DXML** de la lista desplegable **Proceso**

   - Seleccionar **avance de controlador**

   - Seleccionar **Listo**

1. Haga clic en **Sincronizar** en la parte superior derecha después de completar los cambios. Recibirá una notificación de éxito.

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
   - Cualquier componente superpuesto de /libs/fmidator/libs debe compararse con el nuevo código de producto y las actualizaciones deben realizarse en archivos superpuestos en /apps.
   - Cualquier categoría clientlib utilizada desde el producto debe revisarse para ver si hay cambios. Cualquier configuración anulada \(ejemplos abajo\) debe compararse con las más recientes para obtener las últimas funciones:
   - elementmapping.xml
   - ui\_config.json\(puede haberse configurado en perfiles de carpeta\)
   - se modificó `com.adobe.fmdita.config.ConfigManager`

1. Si ha añadido personalizaciones en damAssetLucene, es posible que tenga que volver a aplicarlas. Después de realizar estos cambios, establezca reindex como true. Esto reindexará todos los nodos existentes con las personalizaciones. Una vez finalizado, el indicador de reindexación se volverá a establecer en &quot;false&quot;. Esto puede tardar unas horas, según la cantidad de recursos que haya en el sistema.

## Pasos para indexar el contenido existente

>[!NOTE]
>
> No es necesario que realice estos pasos si actualiza desde la versión 4.3.0 o 4.3.1.

Realice los siguientes pasos para indexar el contenido existente y utilice el nuevo texto de búsqueda y reemplazo a nivel de mapa:

- Ejecute una petición POST al servidor \(con la autenticación correcta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: puede pasar rutas específicas de las asignaciones para indexarlas; de forma predeterminada, todas las asignaciones se indexarán \|\| Por ejemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(por ejemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)

- Una vez completado el trabajo, la solicitud de GET anterior responderá correctamente y mencionará si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.

## Pasos para publicar y procesar el contenido existente a fin de utilizar el informe de vínculos rotos

>[!NOTE]
>
> No es necesario que realice estos pasos si actualiza desde la versión 4.3.0 o 4.3.1.

Realice los siguientes pasos para posprocesar el contenido existente y utilizar el nuevo informe de vínculos rotos:

1. (Opcional) Si hay más de 100 000 archivos dita en el sistema, actualice `queryLimitReads` en `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valor mayor (cualquier valor mayor que el número de recursos presentes, por ejemplo 200 000) y vuelva a implementar.

   | PID | Clave de propiedad | Valor de propiedad |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valor: 200000 <br> Valor predeterminado: 100000 |

1. Ejecute las siguientes API para ejecutar el posprocesamiento en todos los archivos:

   | Punto final | /bin/guides/reports/upgrade |
   |---|---|
   | Tipo de solicitud | **POST** Este script es una petición POST por lo tanto debe ejecutarse a través de agentes como Postman. |
   | Respuesta esperada | La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID de trabajo al mismo punto final.<br> Ejemplo de URL: `http://<server:port>/bin/guides/reports/upgrade` |

   | Punto final | /bin/guides/reports/upgrade |
   |---|---|
   | Tipo de solicitud | **OBTENER** |
   | Parámetro | jobId: pase el jobId recibido de la solicitud de publicación anterior. |
   | Respuesta esperada | - Una vez completado el trabajo, la solicitud de GET responde correctamente. <br> - En caso de que haya errores, comparta los registros de errores junto con la salida de la API con su equipo de éxito del cliente.  <br>Ejemplo de URL: `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |

1. Vuelva al valor predeterminado o al valor existente anterior de `queryLimitReads` si lo ha cambiado en el paso 1.

### Habilitar el déclencheur del script mediante un servlet

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



## Pasos para gestionar el conflicto `'fmdita rewriter'`

Experience Manager Guides tiene un módulo [**reescritor de sling personalizado**](../cs-install-guide/conf-output-generation.md#custom-rewriter) para administrar los vínculos generados en caso de mapas cruzados (vínculos entre los temas de dos mapas diferentes).

Si tiene otra reescritura de sling personalizada en la base de código, utilice un valor de `'order'` mayor que 50, ya que la reescritura de sling de Experience Manager Guides utiliza `'order'` 50.  Para anular esto, necesita un valor >50. Para obtener más información, vista [Output Reescritura de canalizaciones](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante esta actualización, dado que el `'order'` valor se ha cambiado de 1000 a 50, debe combinar el reescritor personalizado existente, si lo hay, con `'fmdita-rewriter'`.


**Tema principal:**&#x200B;[ Descargar e instalar](download-install.md)


## Actualizar a la versión 4.6.0

>[!TIP]
>
> Se recomienda instalar el paquete de servicio 4.6.0 sobre la versión 4.6.0, el paquete de servicio 1 4.6.0 o el paquete de servicio 3 4.6.0. El proceso de actualización de la versión 4.6.0 Service Pack 4 sigue los mismos pasos que la versión 4.6.0.

La actualización a la versión 4.6.0 depende de la versión actual de Experience Manager Guides. Si está utilizando la versión 4.4.0, 4.3.1, 4.3.0, 4.2 o 4.2.1 (Hotfix 4.2.1.3), puede actualizar directamente a la versión 4.6.0.

>[!NOTE]
>
> El procesamiento electrónico de la entrada y la indexación pueden tardar unas horas. Le recomendamos que inicio el proceso de actualización durante las horas de menor actividad.

**&#x200B;**&#x200B;Requisitos previos&#x200B;**&#x200B;**

Antes de inicio el proceso de actualización de las guías de Experience Manager 4.6.0, asegúrese de:

1. Se ha actualizado a la versión de Experience Manager Guides 4.3.1, 4.3.0 o 4.2.1 (revisión 4.2.1.3) y se han completado los pasos de instalación correspondientes.
1. (Opcional) Cerró todas las tareas de traducción.
1. Se ha cambiado el nivel de registro a **INFO** para la clase `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` y se han anexado estos registros a un nuevo archivo de registro, por ejemplo, `logs/translation_upgrade.log`.


## Instalar versión 4.6.0

1. Descargue el paquete de la versión 4.6.0 desde el [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html).
1. Instale el paquete de la versión 4.6.0.
1. Puede elegir ENTRAR en el déclencheur para iniciar el trabajo de actualización del mapa de traducción. Para obtener más información, consulte [Habilitar el déclencheur del script mediante un servlet](#enable-trigger-of-script-via-a-servlet).

1. Después de completar la instalación del paquete, espere a que aparezca el siguiente mensaje en los registros:

   `Completed the post deployment setup script`

   El mensaje anterior indica que se han completado todos los pasos de la instalación.

   Si encuentra cualquiera de los siguientes prefijos ERROR, informe de ellos a su equipo de éxito del cliente:

   - Error en el script de configuración posterior a la implementación
   - Excepción al transferir el mapa de traducción
   - No se puede portar el mapa de traducción de v1 a v2 para la propiedad
1. Actualice el conector de oxígeno plug-in lanzado con la versión 4.6.0 \(si es necesario\).
1. Borre la Caché del explorador después de instalar el paquete.

## Después de instalar la versión 4.6.0

Después de instalar Experience Manager Guides, puede combinar las distintas configuraciones aplicables desde la versión recién instalada con la configuración.

>[!NOTE]
>
> El modelo dam-update-asset se puede personalizar. Por lo tanto, si se ha realizado alguna personalización, es necesario sincronizar las personalizaciones y Experience Manager Guides en la copia de trabajo del modelo.

1. **Flujo de trabajo del recurso de actualización DAM \(Cambios posteriores al procesamiento\):**

1. Abrir URL:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Seleccione **flujo de trabajo del recurso de actualización DAM**.
1. Haz clic en **Editar**.
1. Si el componente **Iniciador de procesamiento posterior DXML** está presente, asegúrese de que las personalizaciones estén sincronizadas.
1. Si el componente **Iniciador de procesamiento posterior DXML** no está presente, realice los siguientes pasos para insertarlo:

1. Haga clic en **Insertar componente** \(Responsable del posprocesamiento de Experience Manager Guides como paso final del proceso\).
1. Configure el **paso del proceso** con los siguientes detalles:

   **Ficha común**

   **Título:** DXML Post Process Initiator

   **Descripción**: DXML entrada proceso iniciador paso que activará un trabajo de sling para el procesamiento entrada DXML del recurso modificado/creado

   **Procesar pestaña**

   - Seleccione **Iniciador de procesamiento posterior DXML** de la lista desplegable **Proceso**

   - Seleccionar **avance de controlador**

   - Seleccionar **Listo**

1. Haga clic en **Sincronizar** en la parte superior derecha después de completar los cambios. Recibirá una notificación de éxito.

   >[!NOTE]
   >
   > Actualizar y verificar que los cambios personalizados y el paso de procesamiento entrada de las guías de Experience Manager estén presentes en el modelo de flujo de trabajo final.

1. Una vez **validada DAM flujo de trabajo** de Update Asset , compruebe las configuraciones de lanzador correspondientes. Para ello, vaya a AEM interfaz de flujo de trabajo y abra los iniciadores.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Busque y realice cambios \(si es necesario\) en los dos iniciadores siguientes \(que deben estar activos\) correspondientes a **DAM flujo de trabajo** de actualización de recursos:

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
   - Cualquier componente superpuesto de /libs/fmidator/libs debe compararse con el nuevo código de producto y las actualizaciones deben realizarse en archivos superpuestos en /apps.
   - Cualquier categoría clientlib utilizada desde el producto debe revisarse para ver si hay cambios. Cualquier configuración anulada \(ejemplos abajo\) debe compararse con las más recientes para obtener las últimas funciones:
   - elementmapping.xml
   - ui\_config.json\(puede haberse configurado en perfiles de carpeta\)
   - se modificó `com.adobe.fmdita.config.ConfigManager`

1. Si ha añadido personalizaciones en damAssetLucene, puede que tenga que aplicarlas de nuevo. Después de realizar esos cambios, establezca el reindex como true. Esto reindexará todos los nodos existentes con las personalizaciones. Una vez finalizado, la indicador de reindexación se volverá a establecer en false. Esto puede tardar algunas horas dependiendo del número de activos en el sistema.

## Pasos para reindexar los índices de las Guías de Experience Manager

1. Abra `crx/de` y vaya a la ruta de acceso del índice: `/oak:index/guidesAssetProperties`
2. Establezca la propiedad reindex como `true` (`false` de forma predeterminada) y haga clic en **Guardar todo**.
3. Una vez completado el reindexado, el Propiedad de reindexación se establece de `false` nuevo y el recuento de reindexación se incrementa en 1.

   >[!NOTE]
   >
   > Esto puede tardar unos minutos, dependiendo de la cantidad de datos presentes.
4. Siga los mismos pasos para otros índices agregados o modificados: `guidesBulkActivation`, `guidesPeerLinkIndex`, y `guidesKonnectTemplateIndex`.

## Pasos para indexar el contenido existente



Realice los pasos siguientes para indexar los contenido existentes:

- Ejecute un petición POST al servidor \(con la autenticación correcta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: Puede pasar rutas específicas de los mapas para indexarlos, por defecto todos los mapas serán indexados || Ejemplo : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar un petición GET con el ID del trabajo al mismo punto final: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(por ejemplo: ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

- Una vez que se complete el trabajo, los petición GET anteriores responderán con éxito y mencionarán si algún mapa falló. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.


>[!NOTE]
>
> Si utiliza el esquema personalizado, debe definir la ruta de acceso de los archivos de catalog.xml DTD y XSD personalizados en la AEM repositorio en la **opción Integrar catálogos** .




## Pasos para gestionar el conflicto `'fmdita rewriter'`

Experience Manager Guides tiene un módulo [**reescritor de sling personalizado**](../cs-install-guide/conf-output-generation.md#custom-rewriter) para administrar los vínculos generados en caso de mapas cruzados (vínculos entre los temas de dos mapas diferentes).

Si tiene otra reescritura de sling personalizada en la base de código, utilice un valor de `'order'` mayor que 50, ya que la reescritura de sling de Experience Manager Guides utiliza `'order'` 50.  Para anular esto, necesita un valor >50. Para obtener más información, vea [Canalizaciones de reescritura de salida](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante esta actualización, dado que el valor `'order'` ha cambiado de 1000 a 50, debe combinar la reescritura personalizada existente, si la hay, con `'fmdita-rewriter'`.


## Actualización a la versión 5.0.0

>[!TIP]
>
> La actualización a la versión 5.0.0 depende de la versión actual de Experience Manager Guides. Si utiliza las versiones 4.6.3, 4.6.1, 4.6.0 o 4.4, puede actualizar directamente a la versión 5.0.0.

>[!NOTE]
>
> El procesamiento electrónico de la entrada y la indexación pueden tardar unas horas. Le recomendamos que inicio el proceso de actualización durante las horas de menor actividad.

**&#x200B;**&#x200B;Requisitos previos&#x200B;**&#x200B;**

Antes de inicio el proceso de actualización de las Guías de Experience Manager 5.0.0, asegúrese de que tiene:

1. Se ha actualizado a la versión de Experience Manager Guides 4.6.3, 4.6.1, 4.6.0 o 4.4 y se han completado los pasos de instalación correspondientes.
1. (Opcional) Cerró todas las tareas de traducción.
1. Se ha cambiado el nivel de registro a **INFO** para la clase `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` y se han anexado estos registros a un nuevo archivo de registro, por ejemplo, `logs/translation_upgrade.log`.


## Instalar versión 5.0.0

1. Descargue el paquete de la versión 5.0.0 desde el [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html).
1. Instale el paquete de la versión 5.0.0.
1. Puede elegir ENTRAR en el déclencheur para iniciar el trabajo de actualización del mapa de traducción. Para obtener más información, consulte [Habilitar el déclencheur del script mediante un servlet](#enable-trigger-of-script-via-a-servlet).

1. Después de completar la instalación del paquete, espere a que aparezca el siguiente mensaje en los registros:

   `Completed the post deployment setup script`

   El mensaje anterior indica que se han completado todos los pasos de la instalación.

   Si encuentra cualquiera de los siguientes prefijos ERROR, informe de ellos a su equipo de éxito del cliente:

   - Error en entrada implementación script de configuración
   - Excepción al portar el MAP de traducción
   - No se puede puerto asignación de traducción de v1 a v2 para Propiedad
1. Actualice el conector de oxígeno plug-in lanzado con la versión 5.0.0 \(si es necesario\).
1. Borre la Caché del explorador después de instalar el paquete.

## Después de instalar la versión 5.0.0

Después de instalar Experience Manager Guides, puede combinar las distintas configuraciones aplicables desde la versión recién instalada con la configuración.

>[!NOTE]
>
> El modelo dam-update-asset se puede personalizar. Por lo tanto, si se han realizado personalizaciones, debemos sincronizar las personalizaciones y las guías de Experience Manager en la copia de trabajo del modelo.

1. **DAM flujo de trabajo de actualización de recursos \(cambios Post procesamiento electrónico\):**

1. Abrir URL:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Seleccione **DAM flujo de trabajo** de actualización de recursos.
1. Haz clic en **Editar**.
1. Si el componente **Iniciador de procesamiento posterior DXML** está presente, asegúrese de que las personalizaciones estén sincronizadas.
1. Si el componente **Iniciador de procesamiento posterior DXML** no está presente, realice los siguientes pasos para insertarlo:

1. Haga clic en **Insertar componente** \(Responsable del posprocesamiento de Experience Manager Guides como paso final del proceso\).
1. Configure el **paso del proceso** con los siguientes detalles:

   **Ficha común**

   **Título:** Iniciador de procesamiento posterior DXML

   **Descripción**: paso del iniciador posterior del proceso DXML que almacenará en déclencheur un trabajo sling para el posprocesamiento DXML del recurso modificado/creado

   **Ficha de proceso**

   - Seleccione **Iniciador de procesamiento posterior DXML** de la lista desplegable **Proceso**

   - Seleccionar **avance de controlador**

   - Seleccione **Listo**

1. Haga clic en **Sincronizar** en la parte superior derecha después de completar los cambios. Recibirá una notificación de éxito.

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

1. Una vez completada la actualización, asegúrese de que cualquiera de las personalizaciones o superposiciones se validan y actualizan para que coincidan con el nuevo código aplicación. A continuación se muestran algunos ejemplos:
   - Cualquier componente superpuesto de /libs/fmditaor/libs debe compararse con el nuevo código de producto y las actualizaciones deben realizarse en archivos superpuestos en /apps.
   - Cualquier categoría de clientlib utilizada desde el producto debe revisarse para ver si hay cambios. Las configuraciones anuladas \(ejemplos a continuación\) deben compararse con las más recientes para obtener las últimas funciones:
   - elementmapping.xml
   - UI\_config.json\(puede haberse configurado en perfiles de carpeta\)
   - se modificó `com.adobe.fmdita.config.ConfigManager`

1. Si ha añadido personalizaciones en damAssetLucene, es posible que tenga que volver a aplicarlas. Después de realizar estos cambios, establezca reindex como true. Esto reindexará todos los nodos existentes con las personalizaciones. Una vez finalizado, el indicador de reindexación se volverá a establecer en &quot;false&quot;. Esto puede tardar unas horas, según la cantidad de recursos que haya en el sistema.

## Pasos para reindexar los índices de Experience Manager Guides

1. Abra `crx/de` y vaya a la ruta de acceso del índice: `/oak:index/guidesAssetProperties`
2. Establezca la propiedad reindex como `true` (`false` de forma predeterminada) y haga clic en **Guardar todo**.
3. Una vez completado el reíndice, la propiedad reindex se vuelve a establecer en `false` y el recuento de reíndices se incrementa en 1.

   >[!NOTE]
   >
   > Esto puede tardar unos minutos, dependiendo de la cantidad de datos presentes.
4. Siga los mismos pasos para otros índices agregados o modificados: `guidesBulkActivation`, `guidesPeerLinkIndex`, y `guidesKonnectTemplateIndex`.

## Pasos para indexar el contenido existente



Siga estos pasos para indexar el contenido existente:

- Ejecute una petición POST al servidor \(con la autenticación correcta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: puede pasar rutas específicas de los mapas para indexarlas, de forma predeterminada se indexarán todas las asignaciones || Ejemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(por ejemplo: ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

- Una vez completado el trabajo, la solicitud de GET anterior responderá correctamente y mencionará si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.


>[!NOTE]
>
> Si utiliza el esquema personalizado, debe definir la ruta de los archivos DTD y XSD catalog.xml personalizados en el repositorio de AEM en la opción **Integrar catálogos**.




## Pasos para gestionar el conflicto `'fmdita rewriter'`

Experience Manager Guides tiene un módulo [**reescritor de sling personalizado**](../cs-install-guide/conf-output-generation.md#custom-rewriter) para administrar los vínculos generados en caso de mapas cruzados (vínculos entre los temas de dos mapas diferentes).

Si tiene otra reescritura de sling personalizada en la base de código, utilice un valor de `'order'` mayor que 50, ya que la reescritura de sling de Experience Manager Guides utiliza `'order'` 50.  Para anular esto, necesita un valor >50. Para obtener más información, vea [Canalizaciones de reescritura de salida](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante esta actualización, dado que el valor `'order'` ha cambiado de 1000 a 50, debe combinar la reescritura personalizada existente, si la hay, con `'fmdita-rewriter'`.



## Pasos para reindexar damAssetLucene

Index definición de damAssetLucene se actualiza con guías. Consulte este [artículo](https://experienceleague.adobe.com/es/docs/experience-cloud-kcs/kbarticles/ka-16460) para volver a indexar damAssetLucene después de actualizar a la versión 5.0.0.

>[!NOTE]
>
> Mientras sigue la documentación, asegúrese de que ambas propiedades (reindex=true y reindex-async=true para /oak:index/damAssetLucene) se actualizan simultáneamente mediante la operación de guardado.


**Tema principal:** [Descargar e instalar](download-install.md)
