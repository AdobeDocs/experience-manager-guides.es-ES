---
title: Notas de versión | Instrucciones de actualización y problemas corregidos en las guías de Adobe Experience Manager, versión de febrero de 2024
description: Obtenga información acerca de las correcciones de errores y cómo actualizar a la versión de febrero de 2024 de las guías de Adobe Experience Manager as a Cloud Service.
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1311'
ht-degree: 0%

---

# Lanzamiento de febrero de 2024 de Adobe Experience Manager Guides as a Cloud Service

Esta nota de la versión cubre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en la versión de febrero de 2024 de Adobe Experience Manager Guides as a Cloud Service (más adelante denominada *Guías del Experience Manager as a Cloud Service*).

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión de febrero de 2024 de Experience Manager Guides as a Cloud Service](whats-new-2024-02-0.md).

## Actualizar a la versión de febrero de 2024

Actualice la configuración as a Cloud Service de las guías del Experience Manager actuales realizando los siguientes pasos:

1. Consulte el código Git de los Cloud Service y cambie a la rama configurada en la canalización de Cloud Service correspondiente al entorno que desea actualizar.
2. Actualizar `<dox.version>` propiedad en `/dox/dox.installer/pom.xml` de su código Git de Cloud Service a 2024.02.0.15.
3. Confirme los cambios y ejecute la canalización de Cloud Service para actualizar a la versión de febrero de 2024 de las guías del Experience Manager as a Cloud Service.

## Pasos para activar el déclencheur de una secuencia de comandos mediante un servlet

(Solo si tiene una versión anterior a la versión as a Cloud Service de las guías del Experience Manager de junio de 2023)

Una vez finalizada la instalación, puede optar por PULSAR el déclencheur para iniciar el trabajo de traducción:

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

En el JSON de respuesta anterior, la clave `lockNodePath` contiene la ruta al nodo creado en el repositorio que señala al trabajo enviado. Se eliminará automáticamente una vez finalizado el trabajo. A continuación, puede hacer referencia a este nodo para ver el estado del trabajo.

Espere hasta que se complete este trabajo antes de continuar con los siguientes pasos.

>[!NOTE]
>
> Debe comprobar si el nodo sigue presente y el estado del trabajo.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Pasos para publicar y procesar el contenido existente a fin de utilizar el informe de vínculos rotos

(Solo si tiene una versión anterior a la versión as a Cloud Service de las guías del Experience Manager de junio de 2023)

Realice los siguientes pasos para posprocesar el contenido existente y utilizar el nuevo informe de vínculos rotos:

1. (Opcional) Si hay más de 100.000 archivos DITA en el sistema, actualice el `queryLimitReads` y `queryLimitInMemory` bajo `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valor mayor (cualquier valor mayor que el número de recursos presentes, por ejemplo 200 000) y, a continuación, vuelva a implementar.

   - Siga las instrucciones de la *Anulaciones de configuración* en Instalar y configurar las guías de Adobe Experience Manager as a Cloud Service para crear el archivo de configuración.
   - En el archivo de configuración, proporcione los siguientes detalles (propiedad) para configurar el `queryLimitReads` y `queryLimitInMemory` opción:

     | PID | Clave de propiedad | Valor de propiedad |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Value: 200000 Valor predeterminado: 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Value: 200000 Valor predeterminado: 100000 |

1. Ejecute una solicitud de POST al servidor (con la autenticación correcta): `http://<server>//bin/guides/reports/upgrade`.

1. La API devuelve un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(Por ejemplo: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una vez finalizado el trabajo, la solicitud de GET anterior responde correctamente. Si el trabajo falla por algún motivo, los errores se pueden ver en los registros del servidor.

1. Volver al valor predeterminado o al valor existente anterior de `queryLimitReads` si lo ha cambiado en el paso 1.

## Pasos para indexar el contenido existente para utilizar la nueva lista de temas y buscar y reemplazar en la pestaña Informes:

(Solo si tiene una versión anterior a la versión as a Cloud Service de las guías del Experience Manager de junio de 2023)

Realice los siguientes pasos para indexar el contenido existente y utilice el nuevo texto de buscar y reemplazar en el nivel de asignación y en la lista de temas de la pestaña Informes:

1. Ejecute una solicitud de POST al servidor (con la autenticación correcta): `http://<server:port>/bin/guides/map-find/indexing`. (Opcional: puede pasar rutas específicas de los mapas para indexarlas, de forma predeterminada se indexarán todas las asignaciones|| Por ejemplo: `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(Por ejemplo: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una vez finalizado el trabajo, la solicitud de GET anterior responde correctamente. Si el trabajo falla por algún motivo, los errores se pueden ver en los registros del servidor.

1. Vuelva al valor predeterminado o al valor existente anterior de queryLimitReads si lo ha cambiado en el paso 1.

## Pasos para gestionar el `'fmdita rewriter'` conflicto

Las guías del Experience Manager tienen un [**reescritura sling personalizada**](../cs-install-guide/conf-output-generation.md#custom-rewriter) módulo para gestionar los enlaces generados en caso de mapas cruzados (enlaces entre los temas de dos mapas diferentes).

Si tiene otra reescritura de sling personalizada en la base de código, utilice una `'order'` valor mayor que 50, ya que el reescritor sling de las Guías del Experience Manager utiliza `'order'` 50.  Para anular esto, necesita un valor >50. Para obtener más información, consulte [Canalizaciones de reescritura de salida](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante esta actualización, dado que el `'order'` Si el valor cambia de 1000 a 50, debe combinar la reescritura personalizada existente, si la hay, con `'fmdita-rewriter'`.


## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con las guías del Experience Manager as a Cloud Service para la versión de febrero de 2024.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión de Experience Manager Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2024.02.0 | No compatible | 2022 o superior |
| | | |


### Conector de oxígeno

| Versión de Experience Manager Guides as a Cloud | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2024.02.0 | 3.1-uuid.17 | 3.1-uuid.17 | 2,3 | 2,3 |
|  |  |  |  |


### Versión de plantilla de base de conocimiento

| Nombre del paquete de componentes | Versión de componentes | Versión de plantilla |
|---|---|---|
| Paquete de contenido de componentes de guías del Experience Manager para Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

### Creación

- La revisión ortográfica en el editor no permite la selección de sugerencias. (15045)
- El botón de navegación global no funciona y el panel no se puede cargar. (14968)
- En el editor web, la función de mapa de descarga no almacena en déclencheur una notificación emergente cuando está lista para descargarse. (14626)
- En el editor web, la función de mapa de descarga no puede descargar un mapa con una línea de base. (14622)
- Error de DTD no válido en la versión as a Cloud Service 2310 de las guías del Experience Manager. (14482)
- Arrastrar un tema del glosario desde el repositorio a un mapa del glosario crea `topicref`. (10767)
- El editor web se desinstala después de volver a instalar la versión 4.3.1 de las guías de Adobe Experience Manager. (14519)
- El instalador de la versión 4.3.1 encuentra un conflicto de filtros, que provoca la anulación de `apps/cq/core/content/projects/properties`. (14517)
- La pantalla de vista previa de los fragmentos de código está inmovilizada. (14840)

### Publicación

- En la publicación de PDF nativos, los atributos personalizados dentro de ajustes preestablecidos de condición no funcionan para la publicación de PDF nativos. (14943)
- No se puede añadir una plantilla personalizada desde el **Salidas** en el Editor. (14846)
- **AEM Sitio web de** el ajuste preestablecido no funciona debido a una ruta de plantilla vacía. (14804)
- AEM La regeneración de sitios falla en los mapas DITA con temas que contienen ecuaciones MathML. (14790)
- En la publicación de PDF nativos, la generación de PDF genera errores al obtener dependencias para `Node.js` publicación. (14445)
- AEM El ajuste preestablecido no permite la selección de una plantilla fuera del `/content` jerarquía en el editor web. (14260)
- En la salida de AEM Sites, el estilo o los saltos de línea se perdieron para la variable `<lines>` elemento con subelementos .(12542)
- Los metadatos personalizados no están disponibles en la salida final. (12116)
- Al actualizar a la versión 4.3.1, se producen algunas excepciones en el nodo PDF nativo. (14492)


### Administración

- **Filtro de línea base** Los archivos no funcionan con Nombre de archivo en el Editor web. (13486)
- Desactivar la indexación del mapa DITA principal para obtener un mejor rendimiento puede afectar a la funcionalidad de determinadas funciones.(12213)
- Etiquetas de la `labels.json` Los archivos aparecen en orden aleatorio en el Editor Web. (10508)

### Revisión

- El menú contextual del botón secundario no funciona para **Aceptar** o **Rechazar** haga un seguimiento de cambios. (14607)
- Cambiar para cerrar los temas de DITA en la pantalla de revisión no funciona en la versión 4.3.1 de Adobe Experience Manager Guides. (14537)
- La personalización de las plantillas de correo electrónico para el flujo de trabajo de revisión no funciona con la superposición. (13954)

## Problema conocido

El Adobe ha identificado el siguiente problema conocido para la versión de febrero de 2024:

- La versión 1.0 no se muestra en la interfaz de usuario del archivo DITA duplicado.
