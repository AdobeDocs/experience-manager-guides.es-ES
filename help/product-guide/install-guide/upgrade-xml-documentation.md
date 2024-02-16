---
title: Actualizar guías de Adobe Experience Manager
description: Obtenga información sobre cómo actualizar las guías de Adobe Experience Manager
exl-id: f058b39f-7408-4874-942b-693e133886cf
feature: Installation
role: Admin
level: Experienced
source-git-commit: 5a444e88b0adba7fa3d498437df39b729b10b5eb
workflow-type: tm+mt
source-wordcount: '5744'
ht-degree: 0%

---

# Actualizar guías de Adobe Experience Manager {#id224MBE0M0XA}

>[!NOTE]
>
> Siga las instrucciones de actualización específicas de la versión con licencia del producto.

Puede actualizar la versión actual de las Guías del Experience Manager a la versión 4.4.0:

- Si utiliza las versiones 4.3.1, 4.3.0 o 4.2.1 (revisión 4.2.1.3), puede actualizar directamente a la versión 4.4.0.
- Si utiliza las versiones 4.2, 4.1 o 4.1.x, debe actualizar a las versiones 4.3.1, 4.3.0 o 4.2.1 (revisión 4.2.1.3) antes de actualizar a la versión 4.4.0.
- Si utiliza la versión 4.0, debe actualizar a la versión 4.2 antes de actualizar a la versión 4.3.x.
- Si utiliza la versión 3.8.5, debe actualizar a la versión 4.0 antes de actualizar a la versión 4.2.
- Si su versión es anterior a la 3.8.5, consulte la sección Guías del Experience Manager de actualización en la guía de instalación específica del producto.


>[!NOTE]
>
> AEM Debe instalar el paquete de servicio de antes de actualizar la versión de las guías del Experience Manager.

Para obtener más información, consulte los siguientes procedimientos:

- [Actualización de 3.8.5 a la versión 4.0](#id2256DK003E1)
- [Actualización a la versión 4.2](#id22A3F500SXA)
- [Actualización a la versión 4.2.1](#upgrade-version-4-2-1)
- [Actualización a la versión 4.3.0](#upgrade-version-4-3)
- [Actualización a la versión 4.3.1](#upgrade-version-4-3-1)
- [Actualización a la versión 4.4.0](#upgrade-version-4-4-0)


>[!IMPORTANT]
>
> Antes de comenzar la actualización, realice una copia de seguridad completa del sistema para evitar la pérdida de datos.

## Actualice de la versión 3.8.5 a la versión 4.0 {#id2256DK003E1}

Si utiliza la versión 3.8.5 de las guías del Experience Manager, puede actualizar a la versión 4.0 de las guías del Experience Manager. Con la función de actualización, no es necesario desinstalar la versión anterior de las guías del Experience Manager.

Antes de ejecutar el proceso, hay ciertas tareas que debe completar. Las siguientes subsecciones le guiarán por los requisitos previos, la generación de informes y el proceso de migración. Además, después de instalar las guías del Experience Manager versión 4.0, puede personalizar varias configuraciones en función de la configuración del cliente.

>[!NOTE]
>
> Este proceso de actualización solo es aplicable de la versión 3.8.5 a la versión 4.0. Para ver el proceso de actualización de la versión 3.4 o superior a la 3.8.5, consulte la *Guías del Experience Manager de actualización* de la guía de instalación específica del producto, disponible en la [Página de archivado de ayuda](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

****Requisitos previos****

Antes de iniciar el proceso de actualización de las Guías del Experience Manager, asegúrese de lo siguiente:

1. Se han importado los comentarios de revisión en los temas abiertos para su revisión.
1. Se cerraron todas las revisiones activas.
1. Se cerraron todas las tareas de traducción.
1. Desinstale las revisiones de las guías del Experience Manager instaladas sobre la versión anterior \(versión principal o de revisión\) de las guías del Experience Manager.

**Antes de instalar la versión 4.0**

Antes de instalar la versión 4.0, realice los siguientes pasos:

1. Asegúrese de que en este punto las Guías del Experience Manager estén en la versión 3.8.5.
1. Descargue el paquete del script de actualización. Para ello, busque &quot;Paquete de actualización de la solución XML Documentation 4.0&quot; en [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html) que descargará un archivo zip.
1. AEM Cargue este paquete en mediante el Administrador de paquetes e instálelo.
1. Una vez instalado el paquete de actualización, ejecute los siguientes scripts en el mismo orden y siga las instrucciones dadas:

**Comprobar API de compatibilidad de actualización**

Esta API está diseñada para evaluar el estado actual del sistema e informar si la actualización es posible o no. Para ejecutar este script, almacene en déclencheur el siguiente extremo dado:

| Punto final | /bin/dxml/upgrade/3xto4x/report |
| --- | --- |
| Tipo de solicitud | **GET** AEM Puede utilizar un explorador web en el que haya iniciado sesión en la instancia de la como administrador. |
| Respuesta esperada | - En caso de que se puedan mover todos los nodos requeridos, obtendrá una comprobación superada. <br>: Si un nodo está presente en la ubicación de destino, se obtiene un error relevante. Limpie el repositorio \(elimine el nodo /var/xml\), vuelva a instalar el paquete de actualización y, a continuación, almacene en déclencheur este extremo de nuevo. <br>**Nota:** Este no es un error común, ya que las guías del Experience Manager 3.x no utilizan anteriormente la ubicación de destino. <br> : Si este script no se ejecuta correctamente, no continúe y genere un informe para el equipo de éxito del cliente. |

**API de migración de datos del sistema**

Esta API está diseñada para migrar los datos del sistema como se menciona en la **Asignación de migración** sección.

1. No ejecute este script si la API Comprobar compatibilidad de actualización falla \(no continuar\).
1. Una vez que la API de comprobación de compatibilidad de actualización devuelva un resultado correcto, puede ejecutar el script de actualización.

| Punto final | /bin/dxml/upgrade/3xto4x |
| --- | --- |
| Tipo de solicitud | **POST** Esta secuencia de comandos es una solicitud de POST, por lo que debe ejecutarse a través de agentes como Postman. |
| Respuesta esperada | - Una vez completada la migración, puede instalar la solución de XML Documentation versión 4.0.<br>: En caso de errores, restaure al último punto de comprobación y comparta los registros de errores junto con la salida de la API con el equipo de éxito del cliente. |

**Asignación de migración**: la API anterior migra todos los datos de la ubicación de origen a la ubicación de destino.

| Origen | Público destinatario |
|------|------|
| /content/fmdita | /var/dxml |
| /content/dxml | /var/dxml |
| /etc/fmdita | /libs/fmdita |

## Instalar versión 4.0 {#id23598G006XA}

1. Instale la versión 4.0 solo si los pasos de actualización se realizaron correctamente.
1. Descargar paquete de versión 4.0 de [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html):

   - Si está utilizando la versión de software de UUID, busque &quot;Versión 4.0 de UUID para la solución de XML Documentation AEM para la versión 6.5 de&quot;.
   - Si está utilizando una versión de software que no sea UUID, busque &quot;Versión 4.0 que no sea UUID para la solución XML Documentation AEM para la versión 6.5 de&quot;.
AEM Cargue el paquete en la instancia de servidor de la existente mediante el Administrador de paquetes CRX e instálelo.

   >[!NOTE]
   >
   > Espere a que se inicien todos los componentes del sistema.

1. Borre la caché del explorador después de instalar el paquete.
1. AEM Si Dispatcher está configurado en una instancia de autor de la aplicación, realice los siguientes pasos:
   - Asegúrese de que se gestionan las siguientes opciones en las reglas de Dispatcher:
   - El patrón de URL /home/users/\*/preferences está en la lista blanca.
   - El patrón de URL /libs/cq/security/userinfo.json no se almacena en caché.
1. Borrar caché de Dispatcher \(para borrar cualquier `clientlibs` en caché\).

## Actualización a la versión 4.2 {#id22A3F500SXA}

La actualización a la versión 4.2 depende de la versión actual de las Guías del Experience Manager.

Si utiliza las versiones 4.0, 4.1 o 4.1.x, puede actualizar directamente a la versión 4.2.

****Requisitos previos****

Antes de iniciar el proceso de actualización de las Guías de Experience Manager 4.2, asegúrese de lo siguiente:

1. Se ha actualizado a las versiones 4.0, 4.1 o 4.1.x de las Guías del Experience Manager.
1. Se cerraron todas las tareas de traducción.
1. Se ha cambiado el nivel de registro a **INFORMACIÓN** para `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` y anexar estos registros a un nuevo archivo de registro, por ejemplo, `logs/translation_upgrade.log.`

>[!NOTE]
>
> Debe cerrar todas las revisiones activas. Si las tareas de revisión no se cierran al actualizar a la versión 4.2, las tareas de revisión en curso más antiguas siguen llevando a los usuarios a las páginas de revisión más antiguas y las tareas de revisión creadas después de la actualización mostrarán las actualizaciones más recientes en la funcionalidad.

## Instalar versión 4.2 {#id2245IK0E0EV}

1. Descargar paquete de la versión 4.2 de [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html).
1. Instale el paquete de la versión 4.2.
1. Después de completar la instalación del paquete, espere a que aparezca el siguiente mensaje en los registros:

   `Completed the post deployment setup script`

   El mensaje anterior indica que se han completado todos los pasos de la instalación.

   Si encuentra cualquiera de los siguientes prefijos ERROR, informe de ellos a su equipo de éxito del cliente:

   - Error en el script de configuración posterior a la implementación
   - Excepción al transferir el mapa de traducción
   - No se puede portar el mapa de traducción de v1 a v2 para la propiedad
1. Actualice el complemento Conector de oxígeno lanzado con la versión 4.2 \(si es necesario\).
1. Borre la caché del explorador después de instalar el paquete.
1. Continúe actualizando las personalizaciones como se detalla en la siguiente sección.

## Después de instalar la versión 4.2 {#id2326F02004K}

>[!IMPORTANT]
>
> La plantilla de alta tecnología no se muestra en el servidor actualizado. Para incluir la plantilla de alta tecnología en el servidor, puede copiarla: Fuente: /libs/fmdita/pdf/Hi-Tech Destino: /content/dam/dita-templates/pdf

Después de instalar las guías del Experience Manager, puede combinar las distintas configuraciones aplicables desde la versión recién instalada con la configuración.

>[!NOTE]
>
> El modelo dam-update-asset se puede personalizar. Por lo tanto, si se ha realizado alguna personalización, es necesario sincronizar las personalizaciones y las guías del Experience Manager en la copia de trabajo del modelo.

1. **Flujo de trabajo del recurso de actualización DAM \(Cambios posteriores al procesamiento\):**

1. Abrir URL:

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Seleccionar **Flujo de trabajo de recursos de actualización DAM**.
1. Haga clic en **Editar**.
1. Si la variable **Iniciador de procesamiento posterior DXML** está presente, asegúrese de que las personalizaciones estén sincronizadas.
1. Si la variable **Iniciador de procesamiento posterior DXML** Si el componente está ausente, realice los siguientes pasos para insertarlo:

1. Clic **Insertar componente** \(Responsable del posprocesamiento de las guías del Experience Manager como paso final del proceso\).
1. Configure las variables **Etapa del proceso** con los siguientes detalles:

   **Pestaña Común**

   **Título:** Iniciador de procesamiento posterior DXML

   **Descripción**: Paso del iniciador posterior del proceso DXML que almacenará en déclencheur un trabajo sling para el posprocesamiento DXML del recurso modificado/creado

   **Pestaña Proceso**

   - Seleccionar **Iniciador de procesamiento posterior DXML** desde el **Proceso** menú desplegable

   - Seleccionar **Avance del controlador**

   - Seleccionar **Listo**

1. Clic **Sincronización** en la parte superior derecha después de completar los cambios. Recibirá una notificación de éxito.

   >[!NOTE]
   >
   > Actualice y compruebe que los cambios personalizados y el paso posterior al procesamiento de las guías del Experience Manager estén presentes en el modelo final de flujo de trabajo.

1. Una **Flujo de trabajo de recursos de actualización DAM** se ha validado, compruebe las configuraciones del lanzador correspondientes. AEM Para ello, vaya a la interfaz de flujo de trabajo de la y abra los iniciadores.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Busque y realice cambios \(si es necesario\) en los dos lanzadores \(que deberían estar activos\) siguientes correspondientes a **Flujo de trabajo de recursos de actualización DAM**:

1. Lanzador para &quot;*Nodo creado*&quot; para **Flujo de trabajo de recursos de actualización DAM**- para la condición `"jcr:content/jcr:mimeType!=video"`, el valor &quot;Globbing&quot; debe ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; debería tener `"event-user-data:changedByWorkflowProcess"`.
   - Lanzador para &quot;*Nodo modificado*&quot; para **Flujo de trabajo de recursos de actualización DAM -** para la condición &quot;`jcr:content/jcr:mimeType!=video`&quot;,
   - el valor &quot;Globbing&quot; debe ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; debería tener `"event-user-data:changedByWorkflowProcess"`.
1. Una vez completada la actualización, asegúrese de que cualquiera de las personalizaciones/superposiciones se valide y actualice para que coincida con el nuevo código de la aplicación. A continuación se ofrecen algunos ejemplos:
   - Cualquier componente superpuesto de /libs/fmidator/libs debe compararse con el nuevo código de producto y las actualizaciones deben realizarse en archivos superpuestos en /apps.
   - Cualquier categoría clientlib utilizada desde el producto debe revisarse para ver si hay cambios. Cualquier configuración anulada \(ejemplos abajo\) debe compararse con las más recientes para obtener las últimas funciones:
   - elementmapping.xml
   - ui\_config.json\(puede haberse configurado en perfiles de carpeta\)
   - enmendado `com.adobe.fmdita.config.ConfigManager`
   - Compruebe si alguno de los códigos personalizados estaba utilizando rutas antiguas \(como se menciona en la [Asignación de migración](#id2244LE040XA) section\): debe actualizarse a las nuevas rutas para que las personalizaciones también funcionen según lo esperado.
1. Obtenga información acerca de las nuevas configuraciones incluidas en la versión actual \(comprobar [Notas de versión](../release-info/release-notes-4-3.md)\) y compruebe si alguna funcionalidad se ve afectada y, a continuación, tome las medidas adecuadas. Un ejemplo podría ser utilizar el &quot;Control de archivos y versiones mejorado&quot; introducido en la versión 4.0, para el cual necesita habilitar una configuración.

## Pasos para indexar el contenido existente y utilizar la nueva función de buscar y reemplazar:

Realice los siguientes pasos para indexar el contenido existente y utilice el nuevo texto de búsqueda y reemplazo a nivel de mapa:

- Ejecute una solicitud de POST al servidor \(con autenticación correcta\) - `http://<server:port\>/bin/guides/map-find/indexing`. \(Opcional: puede pasar rutas específicas de las asignaciones para indexarlas; de forma predeterminada, todas las asignaciones se indexarán \|\| Por ejemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`\)

- La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final:

`http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Por ejemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)

- Una vez completado el trabajo, la solicitud de GET anterior responderá correctamente y mencionará si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.

Si el trabajo de actualización falla y el registro de errores muestra el siguiente error:

&quot;La *query* leídos o atravesados más de *100000 nodos*. Para evitar que afectara a otras tareas, el procesamiento se detuvo&quot;.

Esto podría suceder porque el índice no está configurado correctamente para la consulta utilizada en la actualización. Puede probar la siguiente solución:

1. En el índice oak damAssetLucene, añada la propiedad booleana `indexNodeName` as `true` en el nodo.
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

1. Reindexe el `damAssetLucene` indexar (estableciendo el indicador de reindexación como `true` debajo de y espere a que se `false` de nuevo (esto indica que se ha completado la reindexación). Tenga en cuenta que puede tardar unas horas según el tamaño del índice.
1. Ejecute de nuevo el script de indexación realizando los pasos anteriores.


## Actualización a la versión 4.2.1 {#upgrade-version-4-2-1}

>[!TIP]
>
>Se recomienda instalar la revisión 4.2.1.3 sobre la versión 4.2.1.

La actualización a la versión 4.2.1 depende de la versión actual de las Guías del Experience Manager. Si utiliza la versión 4.1, 4.1.x o 4.2, puede actualizar directamente a la versión 4.2.1.

>[!NOTE]
>
>El posprocesamiento y la indexación pueden tardar unas horas. Le recomendamos que inicie el proceso de actualización durante las horas de menor actividad.

****Requisitos previos****

Antes de iniciar el proceso de actualización de las Guías de Experience Manager 4.2.1, asegúrese de que dispone de lo siguiente:

1. Se ha actualizado a las Guías del Experience Manager versión 4.1, 4.1.x o 4.2.
1. Se cerraron todas las tareas de traducción.
1. Se ha cambiado el nivel de registro a **INFORMACIÓN** para `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` y anexar estos registros a un nuevo archivo de registro, por ejemplo, `logs/translation_upgrade.log.`

>[!NOTE]
>
> Debe cerrar todas las revisiones activas. Si las tareas de revisión no se cierran al actualizar a la versión 4.2, las tareas de revisión en curso más antiguas siguen llevando a los usuarios a las páginas de revisión más antiguas y las tareas de revisión creadas después de la actualización mostrarán las actualizaciones más recientes en la funcionalidad.

## Instalar versión 4.2.1

1. Descargue el paquete de la versión 4.2.1 desde [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html).
1. Instale el paquete de la versión 4.2.1.
1. Puede elegir ENTRAR en el déclencheur para iniciar el trabajo de actualización del mapa de traducción. Para obtener más información, consulte [Habilitar el déclencheur del script mediante un servlet](#enable-trigger-serverlet).


1. Después de completar la instalación del paquete, espere a que aparezca el siguiente mensaje en los registros:

   `Completed the post deployment setup script`

   El mensaje anterior indica que se han completado todos los pasos de la instalación.

   Si encuentra cualquiera de los siguientes prefijos ERROR, informe de ellos a su equipo de éxito del cliente:

   - Error en el script de configuración posterior a la implementación
   - Excepción al transferir el mapa de traducción
   - No se puede portar el mapa de traducción de v1 a v2 para la propiedad
1. Actualice el complemento Conector de oxígeno lanzado con la versión 4.2 \(si es necesario\).
1. Borre la caché del explorador después de instalar el paquete.
1. Continúe actualizando las personalizaciones como se detalla en la siguiente sección.

### Habilitar el déclencheur del script mediante un servlet{#enable-trigger-serverlet}

POST:

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

Registro de muestra: a continuación se muestra un ejemplo de registros que aparecerán en el archivo de registro después de almacenar en déclencheur la secuencia de comandos.

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

Buscar: `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` y `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` antes de continuar con los siguientes pasos.



## Después de instalar la versión 4.2.1

>[!IMPORTANT]
>
> La plantilla de alta tecnología no se muestra en el servidor actualizado. Para incluir la plantilla de alta tecnología en el servidor, puede copiarla: Fuente: /libs/fmdita/pdf/Hi-Tech Destino: /content/dam/dita-templates/pdf

Después de instalar las guías del Experience Manager, puede combinar las distintas configuraciones aplicables desde la versión recién instalada con la configuración.

>[!NOTE]
>
> El modelo dam-update-asset se puede personalizar. Por lo tanto, si se ha realizado alguna personalización, es necesario sincronizar las personalizaciones y las guías del Experience Manager en la copia de trabajo del modelo.

1. **Flujo de trabajo del recurso de actualización DAM \(Cambios posteriores al procesamiento\):**

1. Abrir URL:

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Seleccionar **Flujo de trabajo de recursos de actualización DAM**.
1. Haga clic en **Editar**.
1. Si la variable **Iniciador de procesamiento posterior DXML** está presente, asegúrese de que las personalizaciones estén sincronizadas.
1. Si la variable **Iniciador de procesamiento posterior DXML** Si el componente está ausente, realice los siguientes pasos para insertarlo:

1. Clic **Insertar componente** \(Responsable del posprocesamiento de las guías del Experience Manager como paso final del proceso\).
1. Configure las variables **Etapa del proceso** con los siguientes detalles:

   **Pestaña Común**

   **Título:** Iniciador de procesamiento posterior DXML

   **Descripción**: Paso del iniciador posterior del proceso DXML que almacenará en déclencheur un trabajo sling para el posprocesamiento DXML del recurso modificado/creado

   **Pestaña Proceso**

   - Seleccionar **Iniciador de procesamiento posterior DXML** desde el **Proceso** menú desplegable

   - Seleccionar **Avance del controlador**

   - Seleccionar **Listo**

1. Clic **Sincronización** en la parte superior derecha después de completar los cambios. Recibirá una notificación de éxito.

   >[!NOTE]
   >
   > Actualice y compruebe que los cambios personalizados y el paso posterior al procesamiento de las guías del Experience Manager estén presentes en el modelo final de flujo de trabajo.

1. Una **Flujo de trabajo de recursos de actualización DAM** se ha validado, compruebe las configuraciones del lanzador correspondientes. AEM Para ello, vaya a la interfaz de flujo de trabajo de la y abra los iniciadores.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Busque y realice cambios \(si es necesario\) en los dos lanzadores \(que deberían estar activos\) siguientes correspondientes a **Flujo de trabajo de recursos de actualización DAM**:

1. Lanzador para &quot;*Nodo creado*&quot; para **Flujo de trabajo de recursos de actualización DAM**- para la condición `"jcr:content/jcr:mimeType!=video"`, el valor &quot;Globbing&quot; debe ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; debería tener `"event-user-data:changedByWorkflowProcess"`.
   - Lanzador para &quot;*Nodo modificado*&quot; para **Flujo de trabajo de recursos de actualización DAM -** para la condición &quot;`jcr:content/jcr:mimeType!=video`&quot;, el valor &#39;Globbing&#39; debe ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` debería tener `"event-user-data:changedByWorkflowProcess"`.

1. Una vez completada la actualización, asegúrese de que cualquiera de las personalizaciones/superposiciones se valide y actualice para que coincida con el nuevo código de la aplicación. A continuación se ofrecen algunos ejemplos:
   - Cualquier componente superpuesto de /libs/fmidator/libs debe compararse con el nuevo código de producto y las actualizaciones deben realizarse en archivos superpuestos en /apps.
   - Cualquier categoría clientlib utilizada desde el producto debe revisarse para ver si hay cambios. Cualquier configuración anulada \(ejemplos abajo\) debe compararse con las más recientes para obtener las últimas funciones:
   - elementmapping.xml
   - ui\_config.json\(puede haberse configurado en perfiles de carpeta\)
   - enmendado `com.adobe.fmdita.config.ConfigManager`
   - Compruebe si alguno de los códigos personalizados estaba utilizando rutas antiguas \(como se menciona en la [Asignación de migración](#id2244LE040XA) section\): debe actualizarse a las nuevas rutas para que las personalizaciones también funcionen según lo esperado.
1. Obtenga información acerca de las nuevas configuraciones incluidas en la versión actual \(comprobar [Notas de versión](../release-info/release-notes-4-2-1.md)\) y compruebe si alguna funcionalidad se ve afectada y, a continuación, tome las medidas adecuadas. Un ejemplo podría ser utilizar el &quot;Control de archivos y versiones mejorado&quot; introducido en la versión 4.0, para el cual necesita habilitar una configuración.

## Pasos para indexar el contenido existente y utilizar la nueva función de buscar y reemplazar:

Realice los siguientes pasos para indexar el contenido existente y utilice el nuevo texto de búsqueda y reemplazo a nivel de mapa:

- Asegúrese de que la variable `damAssetLucene` se ha completado la indexación. Puede tardar hasta unas horas, según la cantidad de datos presentes en el servidor. Puede confirmar que la reindexación se ha completado comprobando que el campo de reindexación está configurado como falso en
  `http://<server:port>/oak:index/damAssetLucene`.  Además, si ha añadido personalizaciones en `damAssetLucene`, es posible que tenga que volver a aplicarlos.

- Ejecute una solicitud de POST al servidor \(con autenticación correcta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: puede pasar rutas específicas de las asignaciones para indexarlas; de forma predeterminada, todas las asignaciones se indexarán \|\| Por ejemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- También se puede pasar una carpeta raíz para indexar las asignaciones DITA de una carpeta específica (y sus subcarpetas). Por ejemplo, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Tenga en cuenta que si se pasan tanto el parámetro de rutas como el parámetro raíz, solo se tendrá en cuenta el parámetro de rutas.

- La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Por ejemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


- Una vez completado el trabajo, la solicitud de GET anterior responderá correctamente y mencionará si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.


## Actualización a la versión 4.3.0 {#upgrade-version-4-3}

La actualización a la versión 4.3.0 depende de la versión actual de las Guías del Experience Manager. Si utiliza la versión 4.2 o 4.2.x, puede actualizar directamente a la versión 4.3.0.

>[!NOTE]
>
>El posprocesamiento y la indexación pueden tardar unas horas. Le recomendamos que inicie el proceso de actualización durante las horas de menor actividad.

****Requisitos previos****

Antes de iniciar el proceso de actualización de las Guías de Experience Manager 4.3.0, asegúrese de que dispone de lo siguiente:

1. Se ha actualizado a las Guías del Experience Manager versión 4.2 o 4.2.x y se han completado sus respectivos pasos de instalación.
1. Se cerraron todas las tareas de traducción.



## Instalar versión 4.3.0

1. Descargue el paquete de la versión 4.3.0 desde [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html).
1. Instale el paquete de la versión 4.3.0.
1. Borre la caché del explorador después de instalar el paquete.
1. Actualice el `ui_config.json` desde el **Configuración del editor XML** en el Perfil de carpeta.


## Después de instalar la versión 4.3.0

Después de instalar las guías del Experience Manager, puede combinar las distintas configuraciones aplicables desde la versión recién instalada con la configuración.

## Pasos para publicar y procesar el contenido existente a fin de utilizar el informe de vínculos rotos


Realice los siguientes pasos para posprocesar el contenido existente y utilizar el nuevo informe de vínculos rotos:

1. (Opcional) Si hay más de 100 000 archivos dita en el sistema, actualice el `queryLimitReads` bajo `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valor mayor (cualquier valor mayor que el número de recursos presentes, por ejemplo 200 000) y, a continuación, vuelva a implementar.

   | PID | Clave de propiedad | Valor de propiedad |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valor: 200000 <br> Valor predeterminado: 100000 |

1. Ejecute las siguientes API para ejecutar el posprocesamiento en todos los archivos:

   | Punto final | /bin/guides/reports/upgrade |
   |---|---|
   | Tipo de solicitud | **POST**  Esta secuencia de comandos es una solicitud de POST, por lo que debe ejecutarse a través de agentes como Postman. |
   | Respuesta esperada | La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID de trabajo al mismo punto final.<br> URL de ejemplo: `http://<server:port>/bin/guides/reports/upgrade` |

   | Punto final | /bin/guides/reports/upgrade |
   |---|---|
   | Tipo de solicitud | **GET** |
   | Parámetro | jobId: pase el jobId recibido de la solicitud de publicación anterior. |
   | Respuesta esperada | - Una vez completado el trabajo, la solicitud de GET responde correctamente. <br> - En caso de errores, comparta los registros de errores junto con la salida de la API con el equipo de éxito del cliente.  <br>URL de ejemplo: `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |


1. Volver al valor predeterminado o al valor existente anterior de `queryLimitReads` si lo ha cambiado en el paso 1.



## Actualización a la versión 4.3.1 {#upgrade-version-4-3-1}

La actualización a la versión 4.3.1 depende de la versión actual de las Guías del Experience Manager. Si utiliza las versiones 4.3.0, 4.2 o 4.2.1, puede actualizar directamente a la versión 4.3.1.

>[!NOTE]
>
>El posprocesamiento y la indexación pueden tardar unas horas. Le recomendamos que inicie el proceso de actualización durante las horas de menor actividad.

****Requisitos previos****

Antes de iniciar el proceso de actualización de las Guías de Experience Manager 4.3.1, asegúrese de que dispone de lo siguiente:

1. Se ha actualizado a las Guías del Experience Manager versión 4.3.0, 4.2 o 4.2.1 y se han completado los pasos de instalación correspondientes.
1. (Opcional) Cerró todas las tareas de traducción.
1. Se ha cambiado el nivel de registro a **INFORMACIÓN** para `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` y anexar estos registros a un nuevo archivo de registro, por ejemplo, `logs/translation_upgrade.log`.


## Instalar versión 4.3.1

1. Descargue el paquete de la versión 4.3.1 desde [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html).
1. Instale el paquete de la versión 4.3.1.
1. Puede elegir ENTRAR en el déclencheur para iniciar el trabajo de actualización del mapa de traducción. Para obtener más información, consulte [Habilitar el déclencheur del script mediante un servlet](#enable-trigger-serverlet-4-3-1).


1. Después de completar la instalación del paquete, espere a que aparezca el siguiente mensaje en los registros:

   `Completed the post deployment setup script`

   El mensaje anterior indica que se han completado todos los pasos de la instalación.

   Si encuentra cualquiera de los siguientes prefijos ERROR, informe de ellos a su equipo de éxito del cliente:

   - Error en el script de configuración posterior a la implementación
   - Excepción al transferir el mapa de traducción
   - No se puede portar el mapa de traducción de v1 a v2 para la propiedad
1. Actualice el complemento Conector de oxígeno lanzado con la versión 4.2 \(si es necesario\).
1. Borre la caché del explorador después de instalar el paquete.
1. Continúe actualizando las personalizaciones como se detalla en la siguiente sección.

### Habilitar el déclencheur del script mediante un servlet{#enable-trigger-serverlet-4-3-1}

POST:

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

Registro de muestra: a continuación se muestra un ejemplo de registros que aparecerán en el archivo de registro después de almacenar en déclencheur la secuencia de comandos.

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

Buscar: `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` y `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` antes de continuar con los siguientes pasos.

## Después de instalar la versión 4.3.1



Después de instalar las guías del Experience Manager, puede combinar las distintas configuraciones aplicables desde la versión recién instalada con la configuración.

>[!NOTE]
>
> El modelo dam-update-asset se puede personalizar. Por lo tanto, si se ha realizado alguna personalización, es necesario sincronizar las personalizaciones y las guías del Experience Manager en la copia de trabajo del modelo.

1. **Flujo de trabajo del recurso de actualización DAM \(Cambios posteriores al procesamiento\):**

1. Abrir URL:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Seleccionar **Flujo de trabajo de recursos de actualización DAM**.
1. Haga clic en **Editar**.
1. Si la variable **Iniciador de procesamiento posterior DXML** está presente, asegúrese de que las personalizaciones estén sincronizadas.
1. Si la variable **Iniciador de procesamiento posterior DXML** Si el componente está ausente, realice los siguientes pasos para insertarlo:

1. Clic **Insertar componente** \(Responsable del posprocesamiento de las guías del Experience Manager como paso final del proceso\).
1. Configure las variables **Etapa del proceso** con los siguientes detalles:

   **Pestaña Común**

   **Título:** Iniciador de procesamiento posterior DXML

   **Descripción**: Paso del iniciador posterior del proceso DXML que almacenará en déclencheur un trabajo sling para el posprocesamiento DXML del recurso modificado/creado

   **Pestaña Proceso**

   - Seleccionar **Iniciador de procesamiento posterior DXML** desde el **Proceso** menú desplegable

   - Seleccionar **Avance del controlador**

   - Seleccionar **Listo**

1. Clic **Sincronización** en la parte superior derecha después de completar los cambios. Recibirá una notificación de éxito.

   >[!NOTE]
   >
   > Actualice y compruebe que los cambios personalizados y el paso posterior al procesamiento de las guías del Experience Manager estén presentes en el modelo final de flujo de trabajo.

1. Una **Flujo de trabajo de recursos de actualización DAM** se ha validado, compruebe las configuraciones del lanzador correspondientes. AEM Para ello, vaya a la interfaz de flujo de trabajo de la y abra los iniciadores.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Busque y realice cambios \(si es necesario\) en los dos lanzadores \(que deberían estar activos\) siguientes correspondientes a **Flujo de trabajo de recursos de actualización DAM**:

1. Lanzador para &quot;*Nodo creado*&quot; para **Flujo de trabajo de recursos de actualización DAM**- para la condición `"jcr:content/jcr:mimeType!=video"`, el valor &quot;Globbing&quot; debe ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; debería tener `"event-user-data:changedByWorkflowProcess"`.
   - Lanzador para &quot;*Nodo modificado*&quot; para **Flujo de trabajo de recursos de actualización DAM -** para la condición &quot;`jcr:content/jcr:mimeType!=video`&quot;, el valor &#39;Globbing&#39; debe ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` debería tener `"event-user-data:changedByWorkflowProcess"`.

1. Una vez completada la actualización, asegúrese de que cualquiera de las personalizaciones/superposiciones se valide y actualice para que coincida con el nuevo código de la aplicación. A continuación se ofrecen algunos ejemplos:
   - Cualquier componente superpuesto de /libs/fmidator/libs debe compararse con el nuevo código de producto y las actualizaciones deben realizarse en archivos superpuestos en /apps.
   - Cualquier categoría clientlib utilizada desde el producto debe revisarse para ver si hay cambios. Cualquier configuración anulada \(ejemplos abajo\) debe compararse con las más recientes para obtener las últimas funciones:
   - elementmapping.xml
   - ui\_config.json\(puede haberse configurado en perfiles de carpeta\)
   - enmendado `com.adobe.fmdita.config.ConfigManager`


## Pasos para indexar el contenido existente

>[!NOTE]
>
> No es necesario que realice estos pasos si actualiza desde la versión 4.3.0 o 4.2.1.

Realice los siguientes pasos para indexar el contenido existente y utilice el nuevo texto de búsqueda y reemplazo a nivel de mapa:


- Ejecute una solicitud de POST al servidor \(con autenticación correcta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: puede pasar rutas específicas de las asignaciones para indexarlas; de forma predeterminada, todas las asignaciones se indexarán \|\| Por ejemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)


- La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Por ejemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


- Una vez completado el trabajo, la solicitud de GET anterior responderá correctamente y mencionará si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.

## Pasos para publicar y procesar el contenido existente a fin de utilizar el informe de vínculos rotos

>[!NOTE]
>
> No es necesario que realice estos pasos si actualiza desde la versión 4.3.0

Realice los siguientes pasos para posprocesar el contenido existente y utilizar el nuevo informe de vínculos rotos:

1. (Opcional) Si hay más de 100 000 archivos dita en el sistema, actualice el `queryLimitReads` bajo `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valor mayor (cualquier valor mayor que el número de recursos presentes, por ejemplo 200 000) y, a continuación, vuelva a implementar.

   | PID | Clave de propiedad | Valor de propiedad |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valor: 200000 <br> Valor predeterminado: 100000 |

1. Ejecute las siguientes API para ejecutar el posprocesamiento en todos los archivos:

   | Punto final | /bin/guides/reports/upgrade |
   |---|---|
   | Tipo de solicitud | **POST**  Esta secuencia de comandos es una solicitud de POST, por lo que debe ejecutarse a través de agentes como Postman. |
   | Respuesta esperada | La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID de trabajo al mismo punto final.<br> URL de ejemplo: `http://<server:port>/bin/guides/reports/upgrade` |

   | Punto final | /bin/guides/reports/upgrade |
   |---|---|
   | Tipo de solicitud | **GET** |
   | Parámetro | jobId: pase el jobId recibido de la solicitud de publicación anterior. |
   | Respuesta esperada | - Una vez completado el trabajo, la solicitud de GET responde correctamente. <br> - En caso de errores, comparta los registros de errores junto con la salida de la API con el equipo de éxito del cliente.  <br>URL de ejemplo: `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |


1. Volver al valor predeterminado o al valor existente anterior de `queryLimitReads` si lo ha cambiado en el paso 1.

## Actualización a la versión 4.4.0 {#upgrade-version-4-4-0}

La actualización a la versión 4.4.0 depende de la versión actual de las Guías del Experience Manager. Si utiliza las versiones 4.3.1, 4.3.0, 4.2 o 4.2.1 (revisión 4.2.1.3), puede actualizar directamente a la versión 4.4.0

>[!NOTE]
>
>El posprocesamiento y la indexación pueden tardar unas horas. Le recomendamos que inicie el proceso de actualización durante las horas de menor actividad.

****Requisitos previos****

Antes de iniciar el proceso de actualización de las Guías de Experience Manager 4.4.0, asegúrese de que dispone de lo siguiente:

1. Se ha actualizado a las Guías del Experience Manager versión 4.3.1, 4.3.0 o 4.2.1 (revisión 4.2.1.3) y se han completado los pasos de instalación correspondientes.
1. (Opcional) Cerró todas las tareas de traducción.
1. Se ha cambiado el nivel de registro a **INFORMACIÓN** para `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` y anexar estos registros a un nuevo archivo de registro, por ejemplo, `logs/translation_upgrade.log`.


## Instalar versión 4.4.0

1. Descargue el paquete de la versión 4.4.0 desde [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/aem.html).
1. Instale el paquete de la versión 4.4.0.
1. Puede elegir ENTRAR en el déclencheur para iniciar el trabajo de actualización del mapa de traducción. Para obtener más información, consulte [Habilitar el déclencheur del script mediante un servlet](#enable-trigger-serverlet-4-4-0).

1. Después de completar la instalación del paquete, espere a que aparezca el siguiente mensaje en los registros:

   `Completed the post deployment setup script`

   El mensaje anterior indica que se han completado todos los pasos de la instalación.

   Si encuentra cualquiera de los siguientes prefijos ERROR, informe de ellos a su equipo de éxito del cliente:

   - Error en el script de configuración posterior a la implementación
   - Excepción al transferir el mapa de traducción
   - No se puede portar el mapa de traducción de v1 a v2 para la propiedad
1. Actualice el complemento Conector de oxígeno lanzado con la versión 4.4.0 \(si es necesario\).
1. Borre la caché del explorador después de instalar el paquete.
1. Continúe actualizando las personalizaciones como se detalla en la siguiente sección.


## Después de instalar la versión 4.4.0

Después de instalar las guías del Experience Manager, puede combinar las distintas configuraciones aplicables desde la versión recién instalada con la configuración.

>[!NOTE]
>
> El modelo dam-update-asset se puede personalizar. Por lo tanto, si se ha realizado alguna personalización, es necesario sincronizar las personalizaciones y las guías del Experience Manager en la copia de trabajo del modelo.

1. **Flujo de trabajo del recurso de actualización DAM \(Cambios posteriores al procesamiento\):**

1. Abrir URL:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Seleccionar **Flujo de trabajo de recursos de actualización DAM**.
1. Haga clic en **Editar**.
1. Si la variable **Iniciador de procesamiento posterior DXML** está presente, asegúrese de que las personalizaciones estén sincronizadas.
1. Si la variable **Iniciador de procesamiento posterior DXML** Si el componente está ausente, realice los siguientes pasos para insertarlo:

1. Clic **Insertar componente** \(Responsable del posprocesamiento de las guías del Experience Manager como paso final del proceso\).
1. Configure las variables **Etapa del proceso** con los siguientes detalles:

   **Pestaña Común**

   **Título:** Iniciador de procesamiento posterior DXML

   **Descripción**: Paso del iniciador posterior del proceso DXML que almacenará en déclencheur un trabajo sling para el posprocesamiento DXML del recurso modificado/creado

   **Pestaña Proceso**

   - Seleccionar **Iniciador de procesamiento posterior DXML** desde el **Proceso** menú desplegable

   - Seleccionar **Avance del controlador**

   - Seleccionar **Listo**

1. Clic **Sincronización** en la parte superior derecha después de completar los cambios. Recibirá una notificación de éxito.

   >[!NOTE]
   >
   > Actualice y compruebe que los cambios personalizados y el paso posterior al procesamiento de las guías del Experience Manager estén presentes en el modelo final de flujo de trabajo.

1. Una **Flujo de trabajo de recursos de actualización DAM** se ha validado, compruebe las configuraciones del lanzador correspondientes. AEM Para ello, vaya a la interfaz de flujo de trabajo de la y abra los iniciadores.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Busque y realice cambios \(si es necesario\) en los dos lanzadores \(que deberían estar activos\) siguientes correspondientes a **Flujo de trabajo de recursos de actualización DAM**:

1. Lanzador para &quot;*Nodo creado*&quot; para **Flujo de trabajo de recursos de actualización DAM**- para la condición `"jcr:content/jcr:mimeType!=video"`, el valor &quot;Globbing&quot; debe ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; debería tener `"event-user-data:changedByWorkflowProcess"`.
   - Lanzador para &quot;*Nodo modificado*&quot; para **Flujo de trabajo de recursos de actualización DAM -** para la condición &quot;`jcr:content/jcr:mimeType!=video`&quot;, el valor &#39;Globbing&#39; debe ser:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` debería tener `"event-user-data:changedByWorkflowProcess"`.

1. Una vez completada la actualización, asegúrese de que cualquiera de las personalizaciones/superposiciones se valide y actualice para que coincida con el nuevo código de la aplicación. A continuación se ofrecen algunos ejemplos:
   - Cualquier componente superpuesto de /libs/fmidator/libs debe compararse con el nuevo código de producto y las actualizaciones deben realizarse en archivos superpuestos en /apps.
   - Cualquier categoría clientlib utilizada desde el producto debe revisarse para ver si hay cambios. Cualquier configuración anulada \(ejemplos abajo\) debe compararse con las más recientes para obtener las últimas funciones:
   - elementmapping.xml
   - ui\_config.json\(puede haberse configurado en perfiles de carpeta\)
   - enmendado `com.adobe.fmdita.config.ConfigManager`

1. Si ha añadido personalizaciones en damAssetLucene, es posible que tenga que volver a aplicarlas. Después de realizar estos cambios, establezca reindex como true. Esto reindexará todos los nodos existentes con las personalizaciones. Una vez finalizado, el indicador de reindexación se volverá a establecer en &quot;false&quot;. Esto puede tardar unas horas, según la cantidad de recursos que haya en el sistema.

## Pasos para indexar el contenido existente

>[!NOTE]
>
> No es necesario que realice estos pasos si actualiza desde la versión 4.3.0 o 4.3.1.

Realice los siguientes pasos para indexar el contenido existente y utilice el nuevo texto de búsqueda y reemplazo a nivel de mapa:

- Ejecute una solicitud de POST al servidor \(con autenticación correcta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: puede pasar rutas específicas de las asignaciones para indexarlas; de forma predeterminada, todas las asignaciones se indexarán \|\| Por ejemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Por ejemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)

- Una vez completado el trabajo, la solicitud de GET anterior responderá correctamente y mencionará si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.

## Pasos para publicar y procesar el contenido existente a fin de utilizar el informe de vínculos rotos

>[!NOTE]
>
> No es necesario que realice estos pasos si actualiza desde la versión 4.3.0 o 4.3.1.

Realice los siguientes pasos para posprocesar el contenido existente y utilizar el nuevo informe de vínculos rotos:

1. (Opcional) Si hay más de 100 000 archivos dita en el sistema, actualice el `queryLimitReads` bajo `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valor mayor (cualquier valor mayor que el número de recursos presentes, por ejemplo 200 000) y, a continuación, vuelva a implementar.

   | PID | Clave de propiedad | Valor de propiedad |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valor: 200000 <br> Valor predeterminado: 100000 |

1. Ejecute las siguientes API para ejecutar el posprocesamiento en todos los archivos:

   | Punto final | /bin/guides/reports/upgrade |
   |---|---|
   | Tipo de solicitud | **POST**  Esta secuencia de comandos es una solicitud de POST, por lo que debe ejecutarse a través de agentes como Postman. |
   | Respuesta esperada | La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID de trabajo al mismo punto final.<br> URL de ejemplo: `http://<server:port>/bin/guides/reports/upgrade` |

   | Punto final | /bin/guides/reports/upgrade |
   |---|---|
   | Tipo de solicitud | **GET** |
   | Parámetro | jobId: pase el jobId recibido de la solicitud de publicación anterior. |
   | Respuesta esperada | - Una vez completado el trabajo, la solicitud de GET responde correctamente. <br> - En caso de errores, comparta los registros de errores junto con la salida de la API con el equipo de éxito del cliente.  <br>URL de ejemplo: `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |

1. Volver al valor predeterminado o al valor existente anterior de `queryLimitReads` si lo ha cambiado en el paso 1.

### Habilitar el déclencheur del script mediante un servlet{#enable-trigger-serverlet-4-4-0}

>[!NOTE]
>
> No es necesario que realice estos pasos si actualiza desde la versión 4.3.0 o 4.3.1.

POST:

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

Buscar: `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` y `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` antes de continuar con los siguientes pasos.

>[!NOTE]
>
> Debe comprobar si el nodo sigue presente y el estado del trabajo.

**GET**: `http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json`



## Pasos para gestionar el `'fmdita rewriter'` conflicto

Las guías del Experience Manager tienen un [**reescritura sling personalizada**](../cs-install-guide/conf-output-generation.md#custom-rewriter) módulo para gestionar los enlaces generados en caso de mapas cruzados (enlaces entre los temas de dos mapas diferentes).

Si tiene otra reescritura de sling personalizada en la base de código, utilice una `'order'` valor mayor que 50, ya que el reescritor sling de las Guías del Experience Manager utiliza `'order'` 50.  Para anular esto, necesita un valor >50. Para obtener más información, consulte [Canalizaciones de reescritura de salida](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante esta actualización, dado que el `'order'` Si el valor cambia de 1000 a 50, debe combinar la reescritura personalizada existente, si la hay, con `'fmdita-rewriter'`.


**Tema principal:**[ Descargar e instalar](download-install.md)
