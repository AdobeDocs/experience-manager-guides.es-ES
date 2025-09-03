---
title: Configuración y personalización de flujos de trabajo
description: Obtenga información sobre cómo configurar y personalizar flujos de trabajo
exl-id: 3be387b9-6ac2-4b61-afdf-fbe9d8b6cc1e
feature: Workflow Configuration
role: Admin
level: Experienced
source-git-commit: 439be49e8f4c8cfacb16679257352f4197574365
workflow-type: tm+mt
source-wordcount: '2126'
ht-degree: 2%

---

# Configuración y personalización de flujos de trabajo {#id181AI0OJ0RO}

Los flujos de trabajo permiten automatizar las actividades \(AEM\) de Adobe Experience Manager. Un flujo de trabajo consiste en una serie de pasos que se ejecutan en un orden específico. Puede definir una actividad distinta para ejecutarla en cada paso. Por ejemplo, puede enviar una notificación por correo electrónico a todos los revisores de un grupo cuando se cree una revisión de tema. O bien, envíe una notificación al editor cuando se complete una tarea de generación de resultados.

Para obtener más información sobre los flujos de trabajo en AEM, consulte:

- [Administrar flujos de trabajo](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/workflows.html)

- Aplicando y participando en flujos de trabajo: [Trabajando con flujos de trabajo](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/workflows.html).

- Creando modelos de flujo de trabajo y ampliando la funcionalidad de flujo de trabajo: [Desarrollando y ampliando flujos de trabajo](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/workflows.html).

- Mejora del rendimiento de los flujos de trabajo que utilizan recursos de servidor significativos: [Procesamiento de flujo de trabajo simultáneo](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/configuring-performance.html#ConfiguringforPerformance).


Las secciones de este tema le guiarán por varias personalizaciones que puede realizar en los flujos de trabajo predeterminados enviados en AEM Guides.

## Personalizar flujo de trabajo de revisión {#id176NE0C00HS}

El equipo de creación de contenido de cada organización trabaja de forma específica para satisfacer sus necesidades empresariales. En algunas organizaciones hay un editor dedicado, mientras que otras organizaciones podrían tener un sistema automatizado de revisión editorial. Por ejemplo, en una organización, un flujo de trabajo típico de creación y publicación podría incluir tareas como: cada vez que un autor termina de crear contenido, va automáticamente a los revisores y, cuando se completa la revisión, va al editor para generar el resultado final. En AEM, las actividades que realiza en el contenido y los recursos se pueden combinar en forma de proceso y asignar a un flujo de trabajo de AEM. Para obtener más información sobre los flujos de trabajo en AEM, consulte [Administración de flujos de trabajo](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/workflows.html) en la documentación de AEM.

AEM Guides permite personalizar el flujo de trabajo de revisión predeterminado. Puede utilizar los cuatro procesos personalizados siguientes relacionados con la revisión con el resto de los flujos de trabajo de creación o publicación.

- **Crear revisión**: este proceso prepara los metadatos necesarios para crear una tarea de revisión. Por ejemplo, asignará permiso de revisión a los revisores, establecerá el estado de los temas como en revisión, establecerá las escalas de tiempo de revisión y mucho más. De los cuatro procesos, este es el único proceso obligatorio que debe incluirse en el flujo de trabajo personalizado. En el flujo de trabajo, puede elegir incluir o excluir los otros tres procesos.

- **Asignar tarea de revisión**: este proceso crea la tarea de revisión y envía la notificación de la tarea al iniciador y a los revisores.

- **Enviar correo electrónico de revisión**: este proceso envía el correo electrónico de revisión al iniciador y a los revisores.

- **Programar trabajo para cerrar revisión**: este proceso garantiza que el proceso de revisión se complete al llegar a la fecha límite.


Al crear un flujo de trabajo de revisión personalizado, la primera tarea consiste en establecer los metadatos requeridos que necesita el proceso Crear revisión. Para ello, puede crear un script ECMA. A continuación, se muestra un ejemplo del script ECMA que asigna los metadatos tanto para el tema como para el mapa.

**Para El Tema**

```json
var workflowdata=workItem.getWorkflowData();
workflowdata.getMetaDataMap().put("initiator","admin");
workflowdata.getMetaDataMap().put("operation","AEM_REVIEW");
workflowdata.getMetaDataMap().put("orgTopics","/content/dam/xml-solution/review.xml");
workflowdata.getMetaDataMap().put("payloadJson","{\"base\":\"/content/dam/xml-solution\",\"asset\":[\"/content/dam/xml-solution/review.xml\"],\"referrer\":\""}");
workflowdata.getMetaDataMap().put("deadline","2017-06-27T13:19:00.000+05:30");
workflowdata.getMetaDataMap().put("title","Review through custom workflow");
workflowdata.getMetaDataMap().put("description","Initiate this review process using the AEM workflow");
workflowdata.getMetaDataMap().put("assignee","user-one", "user-two");
workflowdata.getMetaDataMap().put("status","1");
workflowdata.getMetaDataMap().put("projectPath","/content/projects/review");
workflowdata.getMetaDataMap().put("startTime", System.currentTimeMillis());
workflowdata.getMetaDataMap().put("reviewType", "AEM");
workflowdata.getMetaDataMap().put("versionJson", "[{\"path\":\"GUID-ca6ae229-889a-4d98-a1c6-60b08a820bb3.dita\",\"review\":true,\"version\":\"1.0\",\"reviewers\":[\"projects-samplereviewproject-owner\"]}]");
workflowdata.getMetaDataMap().put("isDitamap","false");
workflowdata.getMetaDataMap().put("reviewVersion","3.0");
```

**Para Mapa**

```json
var workflowdata = workItem.getWorkflowData();
workflowdata.getMetaDataMap().put("initiator", "admin");
workflowdata.getMetaDataMap().put("operation", "AEM_REVIEW");
workflowdata.getMetaDataMap().put("orgTopics", "GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita|GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita|GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita|");
var payloadJson = "{\"referrer\":\"\",\"rootMap\":\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\",\"asset\":[\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\"],\"base\":\"/content/dam\"}";
workflowdata.getMetaDataMap().put("payloadJson", payloadJson);
workflowdata.getMetaDataMap().put("deadline", "2047-06-27T13:19:00.000+05:30");
workflowdata.getMetaDataMap().put("title", "Review task via workflow with map");
workflowdata.getMetaDataMap().put("description", "Review task via workflow with map Description");
workflowdata.getMetaDataMap().put("assignee", "user-one");
workflowdata.getMetaDataMap().put("status", "1");
workflowdata.getMetaDataMap().put("projectPath", "/content/projects/review_project_via_workflow");
workflowdata.getMetaDataMap().put("startTime", new Date().getTime());
var versionJson = "[{\"path\":\"GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]},{\"path\":\"GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]},{\"path\":\"GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]}]";
workflowdata.getMetaDataMap().put("versionJson", versionJson);
workflowdata.getMetaDataMap().put("notifyViaEmail", "true");
workflowdata.getMetaDataMap().put("allowAllReviewers", "false");
workflowdata.getMetaDataMap().put("isDitamap", "true");
workflowdata.getMetaDataMap().put("ditamap", "GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap");
var ditamapHierarchy = "[{\"path\":\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\",\"items\":[{\"path\":\"GUID-db5787bb-5467-4dc3-b3e5-cfde562ee745.ditamap\",\"items\":[{\"path\":\"GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita\",\"items\":[],\"title\":\"\"},{\"path\":\"GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita\",\"items\":[],\"title\":\"\"}],\"title\":\"\"},{\"path\":\"GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita\",\"items\":[],\"title\":\"\"}]}]";
workflowdata.getMetaDataMap().put("ditamapHierarchy", ditamapHierarchy);
workflowdata.getMetaDataMap().put("reviewVersion","3.0");
```

Puede crear este script en el nodo `/etc/workflows/scripts`. En la tabla siguiente se describen las propiedades que asigna este script ECMA:

| Propiedad | Tipo | Descripción |
|--------|----|-----------|
| `initiator` | Cadena | ID del usuario que inicia la tarea de revisión. |
| `operation` | Cadena | Un valor estático establecido como `AEM_REVIEW`. |
| `orgTopics` | Cadena | Ruta de los temas que se comparten para su revisión. Especifique varios temas separados por comas. |
| `payloadJson` | Objeto JSON | Especifique los siguientes valores: <br> - `base`: ruta de acceso de la carpeta principal que contiene el tema enviado para revisión.<br>- `asset`: ruta de acceso del tema enviado para revisión. <br>- `referrer`: déjelo en blanco. |
| `deadline` | Cadena | Especifique la hora en formato `yyyy-MM-dd'T'HH:mm:ss.SSSXXX`. |
| `title` | Cadena | Escriba un título para la tarea de revisión. |
| `description` | Cadena | Escriba una descripción para la tarea de revisión. |
| `assignee` | Cadena | ID de usuario de los usuarios a los que desea enviar el tema para su revisión. |
| `status` | Entero | Un valor estático establecido como 1. |
| `startTime` | Largo | Utilice la función `System.currentTimeMillis()` para obtener la hora actual del sistema. |
| `projectPath` | Cadena | Ruta del proyecto de revisión al que se asignará la tarea de revisión, por ejemplo: /content/projects/samplereviewproject. |
| `reviewType` | Cadena | Valor estático AEM. |
| `versionJson` | Objeto JSON | versionJson es una lista de temas que aparecen en la revisión en la que cada objeto de tema tiene la siguiente estructura [ { &quot;path&quot;: &quot;/content/dam/1-topic.dita&quot;, &quot;version&quot;: &quot;1.1&quot;, &quot;review&quot;: true, &quot;reviewers&quot;: [&quot;projects-we_retail-editor&quot;] } ] |
| `isDitamap` | Booleano | false/true |
| `ditamapHierarchy` | Objeto JSON | En caso de que el mapa se envíe para su revisión, el valor aquí debe ser como:[ { &quot;path&quot;: &quot;GUID-f0df1513-fe07-473f-9960-477d4df29c87.ditamap&quot;, &quot;items&quot;: [ &quot;path&quot;: &quot;GUID-9747e8ab-8cf1-45dd-9e20-d47d482f667d.dita&quot;, &quot;title&quot;: &quot;&quot;, &quot;items&quot;: [] } ]. |
| `ditamap` | Cadena | Especificar la ruta del mapa de dietas de la tarea de revisión |
| `allowAllReviewers` | Booleano | false/true |
| `notifyViaEmail` | Booleano | false/true |
| `reviewVersion` | Cadena | Especifica la versión actual del flujo de trabajo de revisión. El valor predeterminado es `3.0`<br> Para habilitar las nuevas características del flujo de trabajo de revisión para [Autores](../user-guide/review-close-review-task.md) y [Revisores](../user-guide/review-complete-review-tasks.md), asegúrese de que `reviewVersion` esté establecido en `3.0`. |


Una vez creado el script, llámelo antes de llamar al proceso Crear revisión en el flujo de trabajo. A continuación, según sus necesidades, puede llamar a los demás procesos de flujo de trabajo de revisión.

### Quitar el flujo de trabajo de revisión de la configuración de depuración

Para mejorar el rendimiento del motor de flujos de trabajo, puede depurar con regularidad las instancias de flujo de trabajo completadas del repositorio de AEM. Si utiliza las configuraciones de AEM predeterminadas, todas las instancias de flujo de trabajo completadas se limpian después de un período de tiempo específico. Esto también provoca que todos los flujos de trabajo de revisión se eliminen del repositorio de AEM.

Puede evitar que los flujos de trabajo de revisión se depuren automáticamente si elimina el modelo de flujo de trabajo de revisión \(información\) de la configuración de depuración automática. Debe usar la **Configuración de depuración del flujo de trabajo de Adobe Granite** para quitar los modelos de flujo de trabajo de revisión de la lista de depuración automática.

En la **Configuración de depuración del flujo de trabajo de Adobe Granite**, asegúrese de que incluye al menos un flujo de trabajo que pueda purgar con seguridad. Por ejemplo, puede utilizar cualquiera de los siguientes flujos de trabajo creados por AEM Guides:

- /etc/workflow/models/publishditamap/jcr:content/model
- /etc/workflow/models/post-dita-project-creation-tasks/ jcr:content/model

Añadir un flujo de trabajo en la **configuración de depuración del flujo de trabajo de Adobe Granite** garantiza que AEM purgue solo los flujos de trabajo que se enumeran en la configuración. Esto evita que AEM depure la información del flujo de trabajo de revisión.

Para obtener más información sobre la configuración de la **configuración de depuración del flujo de trabajo de Adobe Granite**, consulte *Administración de instancias del flujo de trabajo* en la documentación de AEM.

### Personalizar notificaciones por correo electrónico y AEM

Varios flujos de trabajo de AEM Guides utilizan las notificaciones por correo electrónico. Por ejemplo, si inicia una tarea de revisión, se envía una notificación por correo electrónico a los revisores. Sin embargo, para asegurarse de que se envía la notificación por correo electrónico, debe habilitar esta funcionalidad en AEM. Para habilitar la notificación por correo electrónico en AEM, consulte el artículo [Configuración de la notificación por correo electrónico](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=es) en la documentación de AEM.

AEM Guides contiene un conjunto de notificaciones por correo electrónico y AEM que puede personalizar. Siga estos pasos para personalizar estas notificaciones:

1. Use el Administrador de paquetes para descargar la carpeta `/libs/fmdita/mail/review`.

   >[!NOTE]
   >
   > No realice ninguna personalización en los archivos de configuración predeterminados disponibles en el nodo ``libs``. Debe crear una superposición del nodo ``libs`` en el nodo ``apps`` y actualizar los archivos necesarios solo en el nodo ``apps``.

1. La carpeta `review` contiene las siguientes subcarpetas:

   - `aem-notification`
   - `CSS`
   - `email-notification`

   La descripción detallada de estas subcarpetas se explica a continuación:

   | Revisar subcarpetas | Descripción |
   |-----------------|-----------|
   | `aem-notification` | Contiene diferentes tipos de notificaciones de AEM disponibles para personalizar. <br> `closed` <br> `content-updated` <br> `feedback-addressed` <br> `feedback-provided` <br> `requested` <br> `reviewer-removed` <br> `tag-mention` <br> Dentro de estas subcarpetas, se encuentran `primary.vm` y `secondary.vm` archivos que le permiten personalizar el título y la descripción de las notificaciones de AEM, respectivamente. |
   | `CSS` | Contiene el archivo `email-notification.css` para personalizar el estilo de las notificaciones por correo electrónico. |
   | `email-notification` | Contiene diferentes tipos de notificaciones de correo electrónico disponibles para la personalización. <br> `closed` <br> `content-updated` <br> `feedback-addressed` <br> `feedback-provided` <br> `requested` <br> `reviewer-removed` <br> `tag-mention` <br> Dentro de estas subcarpetas, se encuentran `primary.vm` y `secondary.vm` archivos que le permiten personalizar el asunto y el cuerpo de las notificaciones de correo electrónico, respectivamente. |

A continuación se describe la definición de cada tipo de notificación:

- `closed`: Déclencheur cuando se cierra una tarea de revisión.
- `content-updated`: Déclencheur cuando un autor o iniciador actualiza el contenido.
- `feedback-addressed`: se produce un Déclencheur cuando el autor o el iniciador dirige los comentarios y solicita una nueva revisión al revisor.
- `feedback-provided` Déclencheur cuando el revisor marca la tarea como completada al proporcionar comentarios de nivel de tarea al autor o al iniciador de la tarea de revisión.
- `requested`: Déclencheur cuando un autor o iniciador crea una tarea de revisión.
- `reviewer-removed`: Déclencheur cuando se quita la asignación de un revisor de la tarea de revisión.
- `tag-mention`: Déclencheur cuando se menciona o se etiqueta a un usuario en los comentarios de la revisión.

Al personalizar una notificación por correo electrónico o de AEM, asegúrese de usar solamente el siguiente conjunto predefinido de variables que se usan en `primary.vm` y `secondary.vm` archivos.


| **Nombre de variable** | **Descripción** | **Tipo de datos** |
|-------------------------|---------------------------------------------------------------|---------------|
| `projectPath` | Ruta al proyecto que contiene la tarea de revisión | Cadena |
| `reviewTitle` | Título de la tarea de revisión | Cadena |
| `projectName` | Nombre del proyecto | Cadena |
| `commentator` | Nombre del usuario que ha agregado un comentario | Cadena |
| `commentExcerpt` | Fragmento de comentario añadido | Cadena |
| `taskLink` | Vínculo directo a la tarea de revisión | URL |
| `authorName` | Nombre del autor que creó o actualizó la tarea de revisión | Cadena |
| `dueDate` | Fecha de vencimiento de la tarea de revisión | Fecha |
| `reviewerName` | Nombre del revisor asignado a la tarea | Cadena |
| `user` | Usuario involucrado en la tarea de revisión, como autor, revisor o incluso administrador. | Cadena |
| `recipient` | Usuario específico que recibe la notificación | Cadena |


## Personalizar flujo de trabajo de generación posterior a la salida {#id17A6GI004Y4}

AEM Guides le ofrece la flexibilidad de especificar un flujo de trabajo de generación posterior a la salida. Puede realizar algunas tareas de posprocesamiento en la salida que se genera mediante AEM Guides. Por ejemplo, es posible que desee aplicar algunas etiquetas CQ en la salida generada del sitio de AEM, o establecer ciertas propiedades en la salida de PDF, o puede que desee enviar un correo electrónico a un conjunto de usuarios una vez que se genere la salida.

Puede crear un nuevo modelo de flujo de trabajo para utilizarlo como flujo de trabajo de generación posterior a la salida. Cuando se activa un flujo de trabajo de generación posterior a la salida, este comparte información contextual a través del mapa de metadatos del flujo de trabajo, que puede utilizar para realizar el procesamiento en la salida generada. En la tabla siguiente se describe la información contextual compartida como metadatos:

| Propiedad | Tipo | Descripción |
|--------|----|-----------|
| ``outputName`` | Cadena | Nombre del ajuste preestablecido de salida utilizado para generar la salida. |
| `generatedPath` | Cadena | Ruta de acceso en DAM donde se almacena la salida generada. |
| `outputType` | com.adobe.fmdita.output.OutputType | Tipo de ajuste preestablecido de salida. |
| `outputTitle` | Cadena | Título del ajuste preestablecido de salida. |
| `outputHistoryPath` | Cadena | Ruta de repositorio del nodo de historial. |
| `isSuccess` | Booleano | Un indicador que representa el estado final del proceso de generación de resultados: éxito o error. |
| `logPath` | Cadena | Ruta en DAM donde se guardan los registros de generación de salida. |
| `generatedTime` | Largo | Hora a la que se activó el proceso de generación de resultados. |
| `initiator` | Cadena | El ID del usuario que activó el flujo de trabajo de generación de resultados. |

Para utilizar los metadatos de generación de salida, puede crear un script ECMA o un paquete OSGi. A continuación, se muestra un ejemplo del script ECMA que utiliza los metadatos:

>[!NOTE]
>
> Puede crear este script en el nodo ``/etc/workflows/scripts``.

```json
var session = workflowSession.getSession(); // Obtain session object to read/write the repository.
var payload = workItem.getWorkflowData().getPayload().toString(); // Get the workflow payload (the ditamap file on which the generation was triggered)
var metadata = workItem.getWorkflowData().getMetaDataMap(); // Get the workflow metadata object
var generatedPath = metadata.get("generatedPath"); // supplied by AEM Guides
var username = metadata.get("initiator"); // supplied by AEM Guides
var successful = metadata.get("isSuccess"); // supplied by AEM Guides
var title = metadata.get("outputTitle"); // supplied by AEM Guides
var subject = "Output Generation Finished";
var message = "Generation of output " + title + " just finished " + 
(successful ? "successfully. " : "unsuccessfully. ");
    message += "It was triggered by " + username;    
if (successful) {
    message += "<br/><br/>The path to the generated output is " + 
generatedPath;
}
/*
    MailerAPI.sendMail("dl-docs-authors", subject, message);
*/
```

Una vez creado el script, invoque al script personalizado en el flujo de trabajo. A continuación, según sus necesidades, puede llamar a los demás procesos de flujo de trabajo. Una vez que haya diseñado el flujo de trabajo personalizado, llame a *Finalizar generación de publicaciones* como último paso en el proceso de flujo de trabajo. El paso *Finalizar generación posterior* garantiza que el estado de la tarea de generación de resultados se actualice a *Finalizado* al finalizar el proceso de generación de resultados. Después de crear un flujo de trabajo de generación posterior a la salida personalizado, puede configurarlo con cualquiera de los ajustes preestablecidos de generación de salida. Seleccione el flujo de trabajo necesario en la propiedad *Ejecutar flujo de trabajo de generación posterior* del ajuste preestablecido requerido. Cuando ejecuta una tarea de generación de resultados mediante el ajuste preestablecido de salida configurado, el estado de la tarea \(en la pestaña Salida\) cambia a *Procesamiento posterior*.

## Flujo de trabajo Personalizar actualizar recurso {#id18C3D0I0B5Z}

De manera predeterminada, el flujo de trabajo *Recurso de actualización DAM* déclencheur cada vez que crea o actualiza cualquier Recurso de AEM \(XML o no XML\). Por ejemplo, cuando crea un tema o lo actualiza, se ejecuta el flujo de trabajo *Recurso de actualización DAM*. El flujo de trabajo *DAM Update Asset* intenta extraer metadatos relevantes de Assets. El *Flujo de trabajo de actualización de recursos* de serie no tiene ningún paso para extraer metadatos relevantes de un archivo DITA y el flujo de trabajo *Recurso de actualización DAM* genera muchos registros en el momento de la ejecución. Si desea evitar los registros adicionales, puede configurar el flujo de trabajo para que omita el procesamiento de todos los archivos XML.

Realice los siguientes pasos para personalizar el flujo de trabajo *Recurso de actualización DAM*:

1. abra la página **Iniciadores de flujo de trabajo**.

   La URL predeterminada para acceder a la página Iniciadores de flujo de trabajo es:

   ```http
   http://<server name>:<port>/libs/cq/workflow/admin/console/content/launchers.html
   ```

1. En la lista de iniciadores de flujo de trabajo, abra las propiedades del flujo de trabajo **DAM Update Asset**.

1. Añada una condición con la siguiente expresión:

   ```json
   jcr:content/metadata/dc:format!=application/xml
   ```

1. Hacer clic en **Guardar y cerrar**


## Configurar el flujo de trabajo XML posterior al procesamiento {#id18CJB03J0Y4}

AEM Guides crea un conjunto de flujos de trabajo que le permiten trabajar con contenido DITA en AEM. Por ejemplo, hay flujos de trabajo que se ejecutan al cargar contenido DITA o al actualizar contenido existente. Estos flujos de trabajo analizan documentos DITA y realizan diversas tareas, como configurar los metadatos, añadir ajustes preestablecidos de salida predeterminados a nuevas asignaciones DITA y otras tareas relacionadas.

>[!NOTE]
>
> Para personalizar o ampliar los flujos de trabajo posteriores al procesamiento predeterminados, puede usar el controlador de eventos posteriores al procesamiento descrito en la *referencia de API para Adobe Experience Manager Guides*.

Las siguientes propiedades rigen la forma en que AEM Guides ejecuta los flujos de trabajo posteriores al procesamiento:

>[!NOTE]
>
> Se puede acceder a las siguientes propiedades a través de la consola web: http://&lt;server name\>:&lt;port\>/system/console/configMgr.

| Propiedad | Nombre de paquete | Descripción |
|--------|-----------|-----------|
| Salidas dinámicas | `com.adobe.fmdita.postprocess.PostProcessObservation` | Para todos los archivos en los que no se ha realizado el posprocesamiento, recupera las referencias salientes analizando los archivos de tema. Se recomienda mantener esta opción desactivada, ya que tiene la posibilidad de sobrecargar el sistema si el número de archivos que se van a procesar es grande. |
| Threads de procesamiento posterior | `com.adobe.fmdita.config.ConfigManager` | Establece el número de subprocesos de posprocesamiento que se utilizarán para el flujo de trabajo de posprocesamiento. <br>El valor predeterminado es 1. |
