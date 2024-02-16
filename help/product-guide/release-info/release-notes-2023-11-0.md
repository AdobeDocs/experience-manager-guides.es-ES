---
title: Notas de versión | Instrucciones de actualización y problemas corregidos en las guías de Adobe Experience Manager, versión de noviembre de 2023
description: Obtenga información acerca de las correcciones de errores y cómo actualizar a la versión de noviembre de 2023 de las guías de Adobe Experience Manager as a Cloud Service
exl-id: 80839890-075f-4187-a167-444c73215496
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1673'
ht-degree: 0%

---

# Versión de noviembre de 2023 de Adobe Experience Manager Guides as a Cloud Service

Esta nota de la versión cubre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en la versión de noviembre de 2023 de Adobe Experience Manager Guides as a Cloud Service (más adelante denominada *Guías del Experience Manager as a Cloud Service*).

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión de noviembre de 2023 de Experience Manager Guides as a Cloud Service](whats-new-2023-11-0.md).

## Actualizar a la versión de noviembre de 2023

Actualice la configuración as a Cloud Service de las guías del Experience Manager actuales realizando los siguientes pasos:

1. Consulte el código Git de los Cloud Service y cambie a la rama configurada en la canalización de Cloud Service correspondiente al entorno que desea actualizar.
2. Actualizar `<dox.version>` propiedad en `/dox/dox.installer/pom.xml` de su código Git de Cloud Service a 2023.11.0.406.
3. Confirme los cambios y ejecute la canalización de Cloud Service para actualizar a la versión de noviembre de 2023 de las guías del Experience Manager as a Cloud Service.

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

En el JSON de respuesta anterior, la clave `lockNodePath` contiene la ruta al nodo creado en el repositorio que señala al trabajo enviado. Se eliminará automáticamente una vez completado el trabajo. A continuación, puede hacer referencia a este nodo para ver el estado del trabajo.

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

1. Ejecute una solicitud de POST al servidor (con la autenticación correcta): `http://<server:port>//bin/guides/reports/upgrade`.

1. La API devuelve un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Por ejemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una vez finalizado el trabajo, la solicitud de GET anterior responde correctamente. Si el trabajo falla por algún motivo, los errores se pueden ver en los registros del servidor.

1. Revertir al valor existente predeterminado o anterior de `queryLimitReads` si lo ha cambiado en el paso 1.

## Pasos para indexar el contenido existente para utilizar la nueva lista de temas y buscar y reemplazar en la pestaña Informes:

(Solo si tiene una versión anterior a la versión as a Cloud Service de las guías del Experience Manager de junio de 2023)

Realice los siguientes pasos para indexar el contenido existente y utilice el nuevo texto de buscar y reemplazar en el nivel de asignación y en la lista de temas de la pestaña Informes:

1. Ejecute una solicitud de POST al servidor (con la autenticación correcta): `http://<server:port>/bin/guides/map-find/indexing`. (Opcional: puede pasar rutas específicas de los mapas para indexarlas, de forma predeterminada se indexarán todas las asignaciones || Por ejemplo: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

1. También se puede pasar una carpeta raíz para indexar las asignaciones DITA de una carpeta específica (y sus subcarpetas). Por ejemplo, `http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test`. Tenga en cuenta que si se pasan tanto el parámetro de rutas como el parámetro raíz, solo se tendrá en cuenta el parámetro de rutas.

1. La API devuelve un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(Por ejemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`)


1. Una vez finalizado el trabajo, la solicitud de GET anterior responde correctamente y menciona si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.

## Pasos para gestionar el `'fmdita rewriter'` conflicto

Las guías del Experience Manager tienen un [**reescritura sling personalizada**](../cs-install-guide/conf-output-generation.md#custom-rewriter) módulo para gestionar los enlaces generados en caso de mapas cruzados (enlaces entre los temas de dos mapas diferentes).

Si tiene otra reescritura de sling personalizada en la base de código, utilice una `'order'` valor mayor que 50, ya que el reescritor sling de las Guías del Experience Manager utiliza `'order'` 50.  Para anular esto, necesita un valor >50. Para obtener más información, consulte [Canalizaciones de reescritura de salida](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante esta actualización, dado que el `'order'` Si el valor cambia de 1000 a 50, debe combinar la reescritura personalizada existente, si la hay, con `'fmdita-rewriter'`.


## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con las guías del Experience Manager as a Cloud Service para la versión de noviembre de 2023.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Guías de Experience Manager Guides as a Cloud Release | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.11.0 | No compatible | 2022 o superior |
| | | |


### Conector de oxígeno

| Versión de Experience Manager Guides as a Cloud | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.11.0 | 3.2-uuid 5 | 3.2-uuid 5 | 2,3 | 2,3 |
|  |  |  |  |


### Versión de plantilla de base de conocimiento

| Nombre del paquete de componentes | Versión de componentes | Versión de plantilla |
|---|---|---|
| Paquete de contenido de componentes de guías del Experience Manager para Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:



### Creación

- Espacio después de la conref `<ph>` desaparece al guardar el tema. (13642)
- Se produce un error de aplicación al intentar guardar archivos DITA antes de que finalice el posprocesamiento. (13571)
- Si el título de un tema contiene una barra diagonal `/`, la pestaña del editor solo muestra las cartas que le siguen. (13455)
- La previsualización de la imagen no desaparece después de mostrarla en el Editor. (13454)
- La ventana emergente Insertar palabra clave no aparece al utilizar claves definidas por mapa raíz en otros temas. (12950)
- Los iconos de cierre no son visibles cuando se obtiene una vista previa de gráficos muy altos en el panel Historial de versiones. (12867)
- No se puede modificar la zona horaria de **Versión creada el** para las líneas de base. (12711)
- El **Historial de versiones** en la IU de Assets muestra una marca de tiempo incorrecta para **Actual** field. (12624)
- La creación de un fichero DITA a partir de una plantilla con un nombre de fichero que empieza por caracteres numéricos da lugar a un error de espacio de nombres. (12188)
- En el Editor Web, la variable **Referencias clave** se abre al insertar el `varname` etiqueta. (10940)
- Los archivos Zip no se reconocen en el Editor Web y no se pueden arrastrar y soltar. (12709)
- El contenido con algunos atributos aplicados no se resalta en el modo Autor o Vista previa. (11063)
- AEM Al cerrar un tema después de editarlo, se le redirige a la página de inicio de la página de inicio de la página de en lugar de volver a la vista de carpeta. (13306)
- Se produce un retraso en el posprocesamiento de los archivos que se han copiado y pegado en los servicios en la nube. (12457)
- La configuración de mapa de raíz persiste en el editor web aunque el usuario no la haya establecido explícitamente desde las preferencias de usuario. (11551)


### Publicación

- La funcionalidad Publicar como fragmento de contenido no funciona para los archivos enumerados en los resultados de búsqueda. (14090)
- En la publicación nativa en PDF, la selección del color de fondo en el diseño de la plantilla requiere volver a cargar la página al volver a `None`. (13621)
- AEM Problema al comprometerse con el almacén de datos para un mapa DITA grande con vínculos de igual a igual de ámbito en la publicación del sitio de la. (13530)
- En la publicación nativa en PDF, la accesibilidad se ve comprometida, ya que las imágenes del encabezado y del pie de página no muestran texto alternativo. (12829)
- La duplicación del diseño de página en el PDF nativo no funciona sin que se agregue ninguna extensión automáticamente. (12534)
- Al generar la salida del PDF con la publicación del PDF nativo, el nombre del archivo se trunca después de un punto. (13620)
- Se muestran iconos e información de objeto incorrectos para  **Editar contenido** de la barra de herramientas Diseños de página de las plantillas utilizadas en la publicación nativa de PDF. (13492)
- Los metadatos personalizados no están disponibles en la salida final. (12116)
- la reescritura de fmidita entra en conflicto con la configuración de reescritura del usuario y conduce a la visualización de direcciones URL largas en lugar de los vínculos. (12076)
- AEM En el ajuste preestablecido del sitio de la, la opción para **Generar un PDF independiente para cada tema** no funciona. (11555)
- La publicación en PDF nativo no es compatible con la conversión del espacio de color CMYK. (10754)
- Las llamadas de línea de base dinámicas utilizan el nombre en lugar del título, lo que provoca el fallo de la API Exportar mapa DITA. (14268)

### Administración

- La referencia de contenido se interrumpe al copiar y pegar los archivos DITA con vínculos de referencia automática sin GUID. (13540)
- En el Editor Web, la instantánea muestra el título de la versión anterior en lugar de la versión seleccionada del fichero DITA. (13444)
- El **Informes** La pestaña de la interfaz de usuario del editor web no muestra la lista de temas para los mapas DITA antiguos creados antes de la actualización en julio de 2023 del as a Cloud Service de las guías del Experience Manager. (11852)
- No se crean los ajustes preestablecidos de condición para un mapa DITA grande. (10936)
- Aparecerá un vínculo de referencia en la lista de Vínculos rotos de los informes. (13539)

### Revisión

- Los paneles de revisión en paralelo de las versiones anterior y actual en el Editor web no son correctos en la versión de octubre de 2023 de Guías del Experience Manager as a Cloud Service. (14156)
- Personalización de plantillas de correo electrónico para **Revisar** el flujo de trabajo no funciona con la superposición de nodos. (13954)
- El **Cerrar** en la página Revisar de las guías del Experience Manager AEM lleva a los usuarios a la página principal de la página de la página de inicio de la. (13535)
- Aparecen caracteres rotos al crear los fragmentos en coreano. (13489)
- Los archivos adjuntos coreanos de la pantalla Revisión de las guías del Experience Manager no se pueden seleccionar. (13436)
- El título del mapa se corta en la pantalla de revisión y colaboración, sin opción de ver el título completo. (13012)

### Traducción

- La aprobación automática no funciona a veces y se producen excepciones si se establece un valor incorrecto en **Estado de traducción**. (13607)
- La línea de base exportada desde el panel de traducción produce un error y no se abre en el idioma de destino. (12993)

## Problema conocido

El Adobe ha identificado el siguiente problema conocido para la versión de noviembre de 2023.

- AEM La regeneración selectiva de temas para la salida del sitio de la falla.
