---
title: Configuración y personalización de flujos de trabajo
description: Obtenga información sobre cómo configurar y personalizar flujos de trabajo
exl-id: 3be387b9-6ac2-4b61-afdf-fbe9d8b6cc1e
feature: Workflow Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1744'
ht-degree: 1%

---

# Configuración y personalización de flujos de trabajo {#id181AI0OJ0RO}

Los flujos de trabajo permiten automatizar las actividades \(\) de Adobe Experience Manager AEM. Un flujo de trabajo consiste en una serie de pasos que se ejecutan en un orden específico. Puede definir una actividad distinta para ejecutarla en cada paso. Por ejemplo, puede enviar una notificación por correo electrónico a todos los revisores de un grupo cuando se cree una revisión de tema. O bien, envíe una notificación al editor cuando se complete una tarea de generación de resultados.

AEM Para obtener más información sobre los flujos de trabajo en la, consulte:

- [Administrar flujos de trabajo](https://helpx.adobe.com/es/experience-manager/6-5/sites/administering/using/workflows.html)

- Aplicando y participando en flujos de trabajo: [Trabajando con flujos de trabajo](https://helpx.adobe.com/es/experience-manager/6-5/sites/authoring/using/workflows.html).

- Creando modelos de flujo de trabajo y ampliando la funcionalidad de flujo de trabajo: [Desarrollando y ampliando flujos de trabajo](https://helpx.adobe.com/es/experience-manager/6-5/sites/developing/using/workflows.html).

- Mejora del rendimiento de los flujos de trabajo que utilizan recursos de servidor significativos: [Procesamiento de flujo de trabajo simultáneo](https://helpx.adobe.com/es/experience-manager/6-5/sites/deploying/using/configuring-performance.html#ConfiguringforPerformance).


Las secciones de este tema le guiarán por varias personalizaciones que puede realizar en los flujos de trabajo predeterminados enviados en AEM Guides.

## Personalizar flujo de trabajo de revisión {#id176NE0C00HS}

El equipo de creación de contenido de cada organización trabaja de forma específica para satisfacer sus necesidades empresariales. En algunas organizaciones hay un editor dedicado, mientras que otras organizaciones podrían tener un sistema automatizado de revisión editorial. Por ejemplo, en una organización, un flujo de trabajo típico de creación y publicación podría incluir tareas como: cada vez que un autor termina de crear contenido, va automáticamente a los revisores y, cuando se completa la revisión, va al editor para generar el resultado final. AEM AEM En la práctica, las actividades que realice en el contenido y los recursos se pueden combinar en forma de proceso y asignarse a un flujo de trabajo de. AEM AEM Para obtener más información acerca de los flujos de trabajo en la, consulte [Administración de flujos de trabajo](https://helpx.adobe.com/es/experience-manager/6-5/sites/administering/using/workflows.html) en la documentación de la aplicación de la.

AEM Guides permite personalizar el flujo de trabajo de revisión predeterminado. Puede utilizar los cuatro procesos personalizados siguientes relacionados con la revisión con el resto de los flujos de trabajo de creación o publicación.

- **Crear revisión**: este proceso prepara los metadatos necesarios para crear una tarea de revisión. Por ejemplo, asignará permiso de revisión a los revisores, establecerá el estado de los temas como en revisión, establecerá las escalas de tiempo de revisión y mucho más. De los cuatro procesos, este es el único proceso obligatorio que debe incluirse en el flujo de trabajo personalizado. En el flujo de trabajo, puede elegir incluir o excluir los otros tres procesos.

- **Asignar tarea de revisión**: este proceso crea la tarea de revisión y envía la notificación de la tarea al iniciador y a los revisores.

- **Enviar correo electrónico de revisión**: este proceso envía el correo electrónico de revisión al iniciador y a los revisores.

- **Programar trabajo para cerrar revisión**: este proceso garantiza que el proceso de revisión se complete al llegar a la fecha límite.


Al crear un flujo de trabajo de revisión personalizado, la primera tarea consiste en establecer los metadatos requeridos que necesita el proceso Crear revisión. Para ello, puede crear un script ECMA. A continuación, se muestra un ejemplo del script ECMA que asigna los metadatos:

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

Una vez creado el script, llámelo antes de llamar al proceso Crear revisión en el flujo de trabajo. A continuación, según sus necesidades, puede llamar a los demás procesos de flujo de trabajo de revisión.

### Quitar el flujo de trabajo de revisión de la configuración de depuración

AEM Para mejorar el rendimiento del motor de flujo de trabajo, puede depurar con regularidad las instancias de flujo de trabajo completadas del repositorio de la. AEM Si utiliza las configuraciones de flujo de trabajo predeterminadas, todas las instancias de flujo de trabajo completadas se limpian después de un período de tiempo específico. AEM Esto también provoca que todos los flujos de trabajo de revisión se eliminen del repositorio de la.

Puede evitar que los flujos de trabajo de revisión se depuren automáticamente si elimina el modelo de flujo de trabajo de revisión \(información\) de la configuración de depuración automática. Debe usar la **Configuración de depuración del flujo de trabajo de Granite de Adobe** para quitar los modelos de flujo de trabajo de revisión de la lista de depuración automática.

En la **Configuración de depuración del flujo de trabajo de Granite de Adobe**, asegúrese de que incluye al menos un flujo de trabajo que pueda purgar con seguridad. Por ejemplo, puede utilizar cualquiera de los siguientes flujos de trabajo creados por AEM Guides:

- /etc/workflow/models/publishditamap/jcr:content/model
- /etc/workflow/models/post-dita-project-creation-tasks/ jcr:content/model

Añadir un flujo de trabajo en la **configuración de depuración del flujo de trabajo de Granite de Adobe AEM** garantiza que las depuraciones solo se realicen en los flujos de trabajo enumerados en la configuración. AEM Esto evita que la información del flujo de trabajo de revisión se depure.

Para obtener más información sobre la configuración de la configuración de depuración de flujo de trabajo de **Adobe AEM Granite**, consulte *Administración de instancias de flujo de trabajo* en la documentación de.

### Personalizar plantillas de correo electrónico

Varios flujos de trabajo de AEM Guides utilizan las notificaciones por correo electrónico. Por ejemplo, si inicia una tarea de revisión, se envía una notificación por correo electrónico a los revisores. AEM Sin embargo, para asegurarse de que se envía la notificación por correo electrónico, debe habilitar esta funcionalidad en la aplicación de. AEM AEM Para habilitar la notificación por correo electrónico en los mensajes de correo electrónico en la documentación, consulte el artículo [Configuración de la notificación por correo electrónico](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=es) en la documentación de la.

AEM Guides contiene un conjunto de plantillas de correo electrónico que puede personalizar. Siga estos pasos para personalizar estas plantillas:

1. AEM Inicie sesión en la aplicación y abra el modo CRXDE Lite.

1. En la pestaña Navegador, vaya a la siguiente ubicación:

   `/libs/fmdita/mail`

   >[!NOTE]
   >
   > No realice ninguna personalización en los archivos de configuración predeterminados disponibles en el nodo ``libs``. Debe crear una superposición del nodo ``libs`` en el nodo ``apps`` y actualizar los archivos necesarios solo en el nodo ``apps``.

1. La carpeta de correo contiene las siguientes plantillas personalizables:

   | Nombre de archivo de plantilla | Descripción |
   |-----------------|-----------|
   | closereview.html | Esta plantilla de correo electrónico se utiliza cuando se cierra una tarea de revisión. |
   | createreview.html | Esta plantilla de correo electrónico se utiliza cuando se crea una nueva tarea de revisión. |
   | reviewapproval.css | Este archivo CSS contiene el estilo de las plantillas de correo electrónico. |


## Personalizar flujo de trabajo de generación posterior a la salida {#id17A6GI004Y4}

AEM Guides le ofrece la flexibilidad de especificar un flujo de trabajo de generación posterior a la salida. Puede realizar algunas tareas de posprocesamiento en la salida que se genera mediante AEM Guides. AEM Por ejemplo, es posible que desee aplicar algunas etiquetas CQ a la salida del sitio generada, o establecer ciertas propiedades en la salida del PDF, o puede que desee enviar un correo electrónico a un conjunto de usuarios una vez generada la salida.

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

Una vez creado el script, invoque al script personalizado en el flujo de trabajo. A continuación, según sus necesidades, puede llamar a los demás procesos de flujo de trabajo. Una vez que haya diseñado el flujo de trabajo personalizado, llame a *Finalizar generación de Post* como último paso en el proceso de flujo de trabajo. El paso *Finalizar generación de Post* garantiza que el estado de la tarea de generación de resultados se actualice a *Finalizado* al finalizar el proceso de generación de resultados. Después de crear un flujo de trabajo de generación posterior a la salida personalizado, puede configurarlo con cualquiera de los ajustes preestablecidos de generación de salida. Seleccione el flujo de trabajo necesario en la propiedad *Ejecutar flujo de trabajo de generación de Post* del ajuste preestablecido requerido. Cuando ejecuta una tarea de generación de resultados mediante el ajuste preestablecido de salida configurado, el estado de la tarea \(en la pestaña Salida\) cambia a *Post-Processing*.

## Flujo de trabajo Personalizar actualizar recurso {#id18C3D0I0B5Z}

De manera predeterminada, el flujo de trabajo *Recurso de actualización DAM* déclencheur AEM cada vez que crea o actualiza cualquier Recurso de la \(XML o no XML\). Por ejemplo, cuando crea un tema o lo actualiza, se ejecuta el flujo de trabajo *Recurso de actualización DAM*. El flujo de trabajo *DAM Update Asset* intenta extraer metadatos relevantes de Assets. El *Flujo de trabajo de actualización de recursos* de serie no tiene ningún paso para extraer metadatos relevantes de un archivo DITA y el flujo de trabajo *Recurso de actualización DAM* genera muchos registros en el momento de la ejecución. Si desea evitar los registros adicionales, puede configurar el flujo de trabajo para que omita el procesamiento de todos los archivos XML.

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

1. Haga clic en **Guardar y cerrar**


## Configurar el flujo de trabajo XML posterior al procesamiento {#id18CJB03J0Y4}

AEM Guides AEM crea un conjunto de flujos de trabajo que le permiten trabajar con contenido DITA en la creación de flujos de trabajo en el entorno de trabajo de la interfaz de usuario de. Por ejemplo, hay flujos de trabajo que se ejecutan al cargar contenido DITA o al actualizar contenido existente. Estos flujos de trabajo analizan documentos DITA y realizan diversas tareas, como configurar los metadatos, añadir ajustes preestablecidos de salida predeterminados a nuevas asignaciones DITA y otras tareas relacionadas.

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
| Post Process Threads | `com.adobe.fmdita.config.ConfigManager` | Establece el número de subprocesos de posprocesamiento que se utilizarán para el flujo de trabajo de posprocesamiento. <br>El valor predeterminado es 1. |
