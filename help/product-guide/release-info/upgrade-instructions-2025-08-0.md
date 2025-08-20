---
title: Notas de versión | Instrucciones de actualización y problemas corregidos en la versión 2025.08.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de la matriz de compatibilidad y cómo actualizar a la versión 2025.08.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 3b306a873f3b71078256407d977e8bdd5af1180b
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 3%

---

# Instrucciones de actualización para la versión 2025.08.0

Este artículo describe las instrucciones de actualización y la matriz de compatibilidad para la versión 2025.08.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 2025.08.0](whats-new-2025-08-0.md).

Para ver la lista de problemas corregidos en esta versión, consulte [Problemas solucionados en la versión 2025.08.0](fixed-issues-2025-08-0.md).

## Matriz de compatibilidad

Esta sección indica la matriz de compatibilidad para las aplicaciones de software compatibles con la versión 2025.08.0 de Experience Manager Guides as a Cloud Service.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión de Experience Manager Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2025.08.0 | No compatible | 2022 o superior |


### Conector de oxígeno

| Versión de Experience Manager Guides as a Cloud | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2025.08.0 | 3.8 -uuid 1 | 3.8 -uuid 1 | 2,3 | 2,3 |


### Versión de plantilla de base de conocimiento

| Nombre del paquete de componentes | Versión de componentes | Versión de plantilla |
|---|---|---|
| Paquete de contenido de componentes de Experience Manager Guides para Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |


### Nueva versión de plantilla del sitio AEM

| Versión de componentes | Versión del sitio |
|---|---|
| guides-components.all-1.4.0 | aemg-sites-template-1.3.0 |


## Actualizar a la versión 2025.08.0

Experience Manager Guides se actualiza automáticamente al actualizar la versión actual (la más reciente) de Experience Manager as a Cloud Service.

>[!NOTE]
>
> Una vez que empiece a utilizar la versión actual (la más reciente), compare las configuraciones anuladas con las más recientes para obtener las últimas funciones:
>- ui_config.json (puede haberse configurado en perfiles de carpeta)


Realice los siguientes pasos para Experience Manager Guides as a Cloud Service si no lo ha hecho anteriormente para su versión existente:

### Pasos para activar el déclencheur de una secuencia de comandos mediante un servlet

(Solo si está en una versión anterior a la versión de junio de 2023 de Experience Manager Guides as a Cloud Service)

Una vez finalizada la instalación, puede optar por PULSAR el déclencheur para iniciar el trabajo de traducción:

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

En el JSON de respuesta anterior, la clave `lockNodePath` contiene la ruta al nodo creado en el repositorio que señala al trabajo enviado. Se elimina automáticamente una vez finalizado el trabajo y, a continuación, puede hacer referencia a este nodo para ver el estado del trabajo.

Espere hasta que se complete este trabajo antes de continuar con los siguientes pasos.

>[!NOTE]
>
> Debe comprobar si el nodo sigue presente y el estado del trabajo.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

### Pasos para publicar y procesar el contenido existente a fin de utilizar el informe de vínculos rotos

(Solo si está en una versión anterior a la versión de junio de 2023 de Experience Manager Guides as a Cloud Service)

Realice los siguientes pasos para posprocesar el contenido existente y utilizar el nuevo informe de vínculos rotos:

1. (Opcional) Si hay más de 100 000 archivos DITA en el sistema, actualice `queryLimitReads` y `queryLimitInMemory` en `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valor mayor (cualquier valor mayor que el número de recursos presentes, por ejemplo 200 000) y vuelva a implementar.

   - Siga las instrucciones de la sección *Anulaciones de configuración* en Instalar y configurar Adobe Experience Manager Guides as a Cloud Service para crear el archivo de configuración.
   - En el archivo de configuración, proporcione los siguientes detalles (propiedad) para configurar las opciones `queryLimitReads` y `queryLimitInMemory`:

     | PID | Clave de propiedad | Valor de propiedad |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Value: 200000 Valor predeterminado: 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Value: 200000 Valor predeterminado: 100000 |

1. Ejecute una petición POST en el servidor (con la autenticación correcta): `http://<server>//bin/guides/reports/upgrade`.

1. La API devuelve un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(Por ejemplo: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una vez completado el trabajo, la solicitud de GET anterior responde correctamente. Si el trabajo falla por algún motivo, el error se puede ver en los registros del servidor.

1. Volver al valor predeterminado o anterior existente de `queryLimitReads` si lo ha cambiado en el paso 1.

### Pasos para indexar el contenido existente para utilizar la nueva lista de temas y buscar y reemplazar en la pestaña Informes:

(Solo si está en una versión anterior a la versión de junio de 2023 de Experience Manager Guides as a Cloud Service)

Realice los siguientes pasos para indexar el contenido existente y utilice el nuevo texto de buscar y reemplazar en el nivel de asignación y en la lista de temas de la pestaña Informes:

1. Ejecute una petición POST en el servidor (con la autenticación correcta): `http://<server:port>/bin/guides/map-find/indexing`. (Opcional: puede pasar rutas específicas de las asignaciones para indexarlas; de forma predeterminada, todas las asignaciones están indexadas|| Ejemplo: `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. También se puede pasar una carpeta raíz para indexar las asignaciones DITA de una carpeta específica (y sus subcarpetas). Por ejemplo, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Tenga en cuenta que si se pasan tanto el parámetro de rutas como el parámetro raíz, solo se tendrá en cuenta el parámetro de rutas.

1. La API devuelve un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}` (por ejemplo: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una vez completado el trabajo, la solicitud de GET anterior responde correctamente y menciona si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.

### Pasos para gestionar el conflicto `'fmdita rewriter'`

Experience Manager Guides tiene un módulo [**reescritor de sling personalizado**](../cs-install-guide/conf-output-generation.md#custom-rewriter) para administrar los vínculos generados en caso de mapas cruzados (vínculos entre los temas de dos mapas diferentes).

Si tiene otra reescritura de sling personalizada en la base de código, utilice un valor de `'order'` mayor que 50, ya que la reescritura de sling de Experience Manager Guides utiliza `'order'` 50. Para anular esto, necesita un valor >50. Para obtener más información, vea [Canalizaciones de reescritura de salida](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante esta actualización, dado que el valor `'order'` ha cambiado de 1000 a 50, debe combinar la reescritura personalizada existente, si la hay, con `fmdita-rewriter`.

### Pasos para realizar la migración de árbol B para fragmentos de contenido

Si las referencias no se muestran para los fragmentos de contenido, puede optar por VISITAR el déclencheur para iniciar el trabajo de migración:

PUBLICACIÓN:

```
http://localhost:4503/bin/guides/script/start?jobType=cf-reference-store-btree-migration
```


Respuesta:

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/cf-reference-store-btree-migration/1683190032886",
"status": "SCHEDULED"
}
```

En la respuesta anterior, JSON, la clave `lockNodePath` contiene la ruta de acceso al nodo creado en el repositorio, que apunta al trabajo enviado. Se eliminará automáticamente una vez completado el trabajo. Puede hacer referencia a este nodo para ver el estado del trabajo.

Espere hasta que se complete este trabajo antes de continuar con los siguientes pasos.

>[!NOTE]
>
>Debe comprobar si el nodo sigue presente y el estado del trabajo.

GET:

```
http://<aem_domain>/var/dxml/executor-locks/cf-reference-store-btree-migration/1683190032886.json
```
