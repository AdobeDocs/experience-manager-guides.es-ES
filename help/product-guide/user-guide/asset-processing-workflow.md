---
title: Preguntas frecuentes sobre el rendimiento y la escalabilidad de la publicación en Adobe Experience Manager Guides
description: Obtenga información acerca de las preguntas más frecuentes sobre Rendimiento y escalabilidad de la publicación en Adobe Experience Manager Guides.
source-git-commit: f188c2827a9e27249d0162c9f9913e090b29672d
workflow-type: tm+mt
source-wordcount: '1654'
ht-degree: 1%

---


# Procesamiento de recursos

El procesamiento de recursos es un flujo de trabajo esencial responsable de garantizar que los recursos de contenido estén estructurados, validados, indexados y sean accesibles dentro de la plataforma. Con la evolución de las demandas de escalabilidad y los requisitos nativos de la nube, la arquitectura ha experimentado una transformación significativa de un modelo de procesamiento jerárquico de un solo hilo a un sistema distribuido, habilitado para gráficos y con varios hilos.

## Flujo de trabajo de procesamiento de recursos actual

### Resumen del procesamiento

Cuando se importa un recurso en las guías de Experience Manager, se ejecutan los siguientes pasos de procesamiento secuenciales:

- Asignación de clave única: a cada documento se le asigna un identificador único para garantizar la trazabilidad y la integridad de la referencia.
- Análisis: El contenido (por ejemplo, DITA XML) se analiza en componentes estructurados para obtener una comprensión a nivel de sistema.
- Validación: la validación estructural y de esquema garantiza el cumplimiento de las normas de los documentos.
- Resolución de referencia: las referencias cruzadas (vínculos, imágenes, dependencias) se resuelven entre recursos.
- Extracción de metadatos: los metadatos, como el título, el autor y los atributos personalizados, se extraen para la indexación y la búsqueda.
- Reprocesamiento en la modificación: el reprocesamiento incremental garantiza la coherencia después de las actualizaciones de contenido.

### Características arquitectónicas

- **Procesamiento de un solo subproceso**: Evita que se dañen las estructuras JCR (repositorio de contenido Java), que dependen de implementaciones de árbol B.Esto garantiza la integridad de los datos, pero introduce cuellos de botella de procesamiento durante la ingesta masiva.

- **Dependencia del mapa principal**: mantiene relaciones jerárquicas entre recursos mediante el recorrido de gráficos. Se trata de una operación intensiva con una alta latencia durante el procesamiento a gran escala, con una mayor sobrecarga de cálculo y una gran tensión debido a las operaciones con gran recorrido.

## Nuevo flujo de procesamiento de recursos

Los pasos principales de procesamiento siguen siendo coherentes desde el punto de vista funcional, pero ahora se ejecutan dentro de un marco de trabajo distribuido y paralelizado, lo que mejora significativamente el rendimiento.

### Mejoras de arquitectura

- **Integración de base de datos de gráficos**:
   - Transición de JCR jerárquico a una base de datos de gráficos nativa
   - Permite una administración eficaz de relaciones y dependencias
   - Elimina la complejidad de simular operaciones de gráficos en un almacenamiento jerárquico
- **Procesamiento distribuido de subprocesos múltiples**:
   - El procesamiento se ejecuta en varios pods en un entorno de nube
   - Elimina la dependencia de un solo nodo maestro
   - Permite la escalabilidad horizontal y la ejecución paralela
- **Eliminación de la dependencia de asignación principal:**
   - Elimina la necesidad de realizar un recorrido de gráficos explícito
   - Reduce las operaciones de E/S y la latencia de procesamiento
   - Simplifica la canalización de procesamiento
- **Asignación de ID único sincronizada**
   - La coordinación centralizada garantiza:
   - Sin duplicación de ID de documento
   - Coherencia entre nodos distribuidos
   - Mantiene la integridad referencial en un entorno simultáneo
- **Base de datos escalable nativa de la nube (alojada en AWS)**
   - Capa de base de datos de alta disponibilidad y solidez
   - Admite escalado elástico según la carga de trabajo
   - Mejora la fiabilidad y el rendimiento generales del sistema

![](images/workflow.png)

## Ventajas de la nueva arquitectura

- Mejoras de rendimiento:
   - La ejecución en paralelo reduce significativamente el tiempo de procesamiento
   - La eliminación de las operaciones de gran recorrido reduce la latencia
   - La administración optimizada de gráficos mejora la velocidad de resolución de dependencias
- Escalabilidad:
   - El escalado horizontal entre pods permite administrar grandes volúmenes de ingesta
   - La infraestructura nativa de la nube se adapta dinámicamente a las demandas de carga de trabajo
- Fiabilidad y disponibilidad:
   - El procesamiento distribuido elimina el único punto de error
   - La base de datos alojada en AWS garantiza una alta disponibilidad y tolerancia a fallos
- Aumento de la eficiencia:
   - Reducción de la sobrecarga de E/S debido a la eliminación de la inversión del mapa principal
   - Mejor utilización de los recursos en los nodos de computación
- Integridad de los datos:
   - La asignación de ID sincronizada mantiene la coherencia en todos los sistemas distribuidos
   - Mantiene la solidez y permite la concurrencia

## Configurar base de datos

Experience Manager Guides permite una configuración de base de datos optimizada para entornos de AEM Cloud. Para configurar la base de datos para la instancia de AEM Cloud, realice los siguientes pasos:

1. Acceda a AEM Cloud Manager: vaya a Adobe Experience Cloud Manager mediante la dirección URL siguiente y reemplace los marcadores de posición por los detalles de su organización, programa y entorno: `https://experience.adobe.com/#/${orgName}/cloud-manager/environments.html/program/${programId}/environment/${envId}`

1. Configure el entorno: después de abrir la página de configuración del entorno a través de Cloud Manager, podrá ajustar la configuración específica de la instancia, incluida la configuración de la base de datos necesaria.

Este enfoque optimizado garantiza un acceso y una configuración sencillos para los entornos de AEM dentro de la infraestructura en la nube de Adobe.

1. Configure las siguientes propiedades:


| Nombre de la propiedad | Valor | Servicio aplicado | Tipo |
|----------------------------------|--------------------------------|-----------------|----------|
| DATABASE_URL | `<host>:<port>/<db_name>` | Autor | Variable |
| GUIDES_ENABLE_DATABASE | `true` | Autor | Variable |
| DATABASE_PASSWORD | `password` | Autor | Secreto |
| DATABASE_USERNAME | `username` | Autor | Variable |
| RUN_POSTPROCESS_IN_PHASES | `true` | Autor | Variable |
| DATABASE_CONNECTION_POOL_SIZE | `10` | Autor | Variable |


![](images/environment-config.png){width="350"}

1. Guardar cambios: después de realizar los cambios de configuración, asegúrese de **guardarlos** en la interfaz de Cloud Manager.

1. Disponibilidad del sistema: una vez que las configuraciones se hayan aplicado completamente, abra GET `http://host/bin/guides/v1/system/status` y compruebe las siguientes propiedades:
   - `<isDatabase>`: debe ser verdadero
   - `<databaseConnectionCheck>`: se debe pasar

   Si los valores anteriores son correctos en la respuesta, el sistema está disponible para utilizarse con la base de datos recién configurada.

Si sigue este proceso, tendrá un entorno de nube de AEM correctamente configurado y listo para usar.

>[!NOTE]
>
> Si está migrando a un entorno existente con contenido preexistente, primero debe ejecutar la Fase 2 (Migrar contenido existente) antes de ingerir cualquier contenido nuevo. Esto sirve para garantizar que las GUID temporales se asignan correctamente al nuevo contenido.

## Ingesta de datos en AEM DAM (entorno de nube) (fase 1)

Para configurar una carpeta nueva en AEM DAM (Digital Asset Manager), ingerir datos y compararlos con un entorno basado en JCR, siga los siguientes pasos.

1. Cree una nueva carpeta en DAM.

2. Ingesta de datos mediante la herramienta de carga de datos: para obtener más información, consulte **Carga de Assets a AEM Cloud**.

3. Verifique el sistema
   - Una vez finalizada la carga, compruebe que los recursos estén presentes en DAM.
   - Asegúrese de que los metadatos (como tipos de archivo, descripciones y etiquetas) se hayan extraído y asociado a los recursos.
   - Compruebe el procesamiento de Experience Manager Guides (multiproceso) para confirmar que todas las referencias, extracción de metadatos y validaciones se han realizado correctamente.
   - Pruebe a acceder y editar un documento para confirmar la integridad del sistema.

4. Comparación con un entorno basado en JCR
   - Compare resultados en varios casos de prueba.
   - Evalúe la velocidad de ingesta.


Para migrar el contenido que se ha cargado y procesado antes de cambiar Experience Manager Guides a una configuración basada en la base de datos, se puede utilizar un script de migración. El script aprovecha un conjunto de API para iniciar y supervisar el proceso de migración. Los siguientes pasos describen el enfoque recomendado.

## Migración de contenido de JCR a base de datos (Fase 2)

Para migrar contenido que se haya cargado y procesado antes de cambiar a Experience Manager Guides a una configuración basada en bases de datos, debe utilizar un script de migración. El script aprovecha un conjunto de API para iniciar y supervisar el proceso de migración. Los siguientes pasos describen el enfoque recomendado.

1. Almacene en déclencheur la API de migración con cualquier cliente REST.
2. Compruebe el progreso de la migración.
3. Monitorice la migración hasta la finalización: continúe monitorizando hasta que la API de progreso notifique la finalización del 100 %. Una vez finalizado, todo el contenido cargado y procesado anteriormente desde el repositorio JCR se migra a la base de datos.

   >[!NOTE]
   >
   > - Asegúrese de que los encabezados de autorización necesarios (como tokens de OAuth, claves de API o tokens de acceso de Developer Console) estén incluidos para autenticar solicitudes con AEM.
   > - La duración de la migración depende del tamaño del repositorio de contenido. Se recomiendan comprobaciones periódicas del progreso, junto con la monitorización de errores o interrupciones.
   > - Revise los registros de migración, si están disponibles, para evaluar el rendimiento de la migración e identificar cualquier problema.

4. Para admitir la migración para tamaños de repositorio grandes, siga la configuración a continuación

   >[!NOTE]
   >
   > Aplique esta configuración solo si se encuentran errores de recorrido del repositorio durante la migración.

   `file name: `org.apache.jackrabbit.oak.query.QueryEngineSettingsService.xml&quot;

   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0"
         xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
         jcr:primaryType="sling:OsgiConfig"
         queryLimitInMemory="5000000"
         queryLimitReads="1000000"
   />
   ```


## API de migración

### Iniciar migración

- extremo: `POST /bin/guides/v1/assets/process`
- cuerpo de solicitud: (`application/json`):

```json
  {
    "path": "/content/dam/dita-templates",
    "excludedPaths": [
      "/content/dam/demo",
      "/content/dam/demo1"
    ],
    "type": "ASSET_PROCESSING"
  }
```

- devuelve el valor de processingId para la migración.
- déclencheur el flujo de trabajo de procesamiento de recursos integrado en el producto.

### Comprobación del estado de migración

extremo: `GET /bin/guides/v1/assets/process/status?processingId=<processingId>`

### Cancelar una migración en ejecución

- extremo: `POST /bin/guides/v1/assets/process/cancel`
- cuerpo de la solicitud (application/json):

  ```
  {
   "processingId": "processingId"
  }
  ```

### Reanudar una migración fallida o cancelada

- extremo: `POST /bin/guides/v1/assets/process/resume`
- cuerpo de la solicitud (application/json):

  ```
  {
   "processingId": "processingId"
  }
  ```

## Cargar recursos a la nube de AEM

Adobe Experience Manager (AEM) as a Cloud Service proporciona varios enfoques para la ingesta masiva de contenido. Para garantizar un rendimiento óptimo, especialmente para el posprocesamiento de Experience Manager Guides, es esencial adoptar una estrategia de ingesta compatible y escalable.

### Ingesta masiva mediante integraciones de almacenamiento en la nube

AEM admite la ingesta masiva de contenido a través de proveedores de almacenamiento en la nube admitidos, lo que permite a las organizaciones conectar su solución de almacenamiento preferida e importar contenido directamente en AEM. Este enfoque se recomienda para la ingesta a gran escala y con sensibilidad de rendimiento debido a las siguientes ventajas:

- Infraestructura escalable: el proceso de ingesta se ejecuta en una infraestructura en la nube administrada por Adobe, lo que permite un escalado automático basado en la carga y el volumen de contenido. Esto garantiza un rendimiento de ingesta uniforme, incluso para conjuntos de datos grandes.

- Planificación de ingesta predecible: los usuarios pueden estimar la duración de la ingesta por adelantado, lo que ayuda a planificar la versión, programar y coordinar con los equipos dependientes.

  ![](images/ingestion-time.png){width="350"}

- Registro y seguimiento completos: el flujo de trabajo de ingesta incluye funciones detalladas de registro y seguimiento, lo que proporciona visibilidad sobre el progreso, los estados de éxito y los problemas potenciales a lo largo del proceso de importación.

  ![](images/bulk-import-job.png){width="350"}

- Ingesta programada: la ingesta de contenido puede programarse para que se produzca durante ventanas de tiempo predefinidas, lo que garantiza un impacto mínimo o nulo en los usuarios finales y las operaciones en curso.

Para obtener más información, vea [Uso de la importación en lotes](https://experienceleague.adobe.com/en/docs/experience-manager-learn/cloud-service/migration/bulk-import).

## Ingesta masiva mediante carga de AEM

AEM también proporciona [carga de AEM](https://github.com/adobe/aem-uploa), una biblioteca e interfaz de línea de comandos (CLI) que permite a los usuarios ingerir contenido directamente desde un sistema de archivos local. Esta opción se puede integrar en soluciones personalizadas o utilizarse como herramienta CLI independiente para cargar contenido.

Dado que este método se ejecuta en el equipo local del usuario, requiere una conexión de red estable e ininterrumpida para garantizar una experiencia de ingesta fiable y sin problemas.


## Comprobación de estado de la conectividad de base de datos Experience Manager Guides

Las implementaciones de Experience Manager Guides configuradas para utilizar una base de datos requieren una conectividad de base de datos estable y coherente para funcionar de forma fiable. La comprobación del estado de conexión de la base de datos es un paso clave de comprobación de estado para descartar problemas relacionados con la conectividad que puedan afectar a la funcionalidad del sistema.

Esta comprobación de estado permite a los usuarios confirmar si la base de datos está configurada, si está accesible y si funciona según lo esperado. Para comprobar el estado de la conexión DB, siga los siguientes pasos.

1. Abra cualquier explorador o cliente REST
2. Almacenar en déclencheur una llamada GET mediante esta [URL](https://host:port/bin/guides/v1/system/status)
3. Los campos siguientes se pueden utilizar para determinar la configuración del sistema y el estado
   1. isDatabase:
      - true: el entorno está configurado con la base de datos.
      - false: el entorno no utiliza la base de datos

   2. databaseConnectionCheck:
      - pasado: Experience Manager Guides comprobará el estado de la conexión y, si Guides puede conectarse con la base de datos, devolverá el estado como pasado.
      - error: el entorno no puede comunicarse con la base de datos. Los clientes deben dejar de utilizar el sistema inmediatamente y ponerse en contacto con el servicio de asistencia de Adobe.

## Monitorización de registros

Experience Manager Guides con base de datos registra de forma eficaz los detalles para proporcionar una insight en el estado del sistema.
Utilice las siguientes consultas en Splunk para obtener registros para diferentes escenarios.

1. Registros de migración:
   - `index IN ("dx_aem_engineering") aem_service=cm-${programid}-${environmentId} sourcetype=aemerror "AssetProcessingJob" OR "AssetJobProducerDb" NOT "ServiceEvent"`
2. Registros de procesamiento posterior:
   - `index IN ("dx_aem_engineering") aem_service= cm-${programid}-${environmentId} sourcetype=aemerror com.adobe.fmdita.uuid.concrete.Cor*`


>[!NOTE]
>
> Obtenga más información sobre las [funciones de consultas de Splunk](https://www.splunk.com/en_us/blog/learn/splunk-cheat-sheet-query-spl-regex-commands.html) para filtrar estos registros según la duración del tiempo, el nivel de registro o para buscar algunos patrones específicos.










