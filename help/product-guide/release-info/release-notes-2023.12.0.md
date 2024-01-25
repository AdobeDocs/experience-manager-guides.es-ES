---
title: Notas de versión | Instrucciones de actualización y problemas corregidos en las guías de Adobe Experience Manager, versión de diciembre de 2023
description: Obtenga información acerca de las correcciones de errores y cómo actualizar a la versión de diciembre de 2023 de las guías de Adobe Experience Manager as a Cloud Service.
feature: Release Notes
role: Leader
source-git-commit: 110a358ce6c0525f7b1eae075d89d78f8014ceff
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 1%

---

# Versión de diciembre de 2023 de Adobe Experience Manager Guides as a Cloud Service

Esta nota de la versión cubre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en la versión de diciembre de 2023 de las guías de Adobe Experience Manager as a Cloud Service (más adelante denominadas *Guías del Experience Manager as a Cloud Service*).

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión de diciembre de 2023 de Experience Manager Guides as a Cloud Service](whats-new-2023.12.0.md).

## Actualización a la versión de diciembre de 2023

Actualice la configuración as a Cloud Service de las guías del Experience Manager actuales realizando los siguientes pasos:

1. Consulte el código Git de los Cloud Service y cambie a la rama configurada en la canalización de Cloud Service correspondiente al entorno que desea actualizar.
2. Actualizar `<dox.version>` propiedad en `/dox/dox.installer/pom.xml` de su código Git de Cloud Service a 2023.12.0.16.
3. Confirme los cambios y ejecute la canalización de Cloud Service para actualizar a la versión de diciembre de 2023 de las guías del Experience Manager as a Cloud Service.

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

1. Revertir al valor existente predeterminado o anterior de `queryLimitReads` si lo ha cambiado en el paso 1.

## Pasos para indexar el contenido existente para utilizar la nueva lista de temas y buscar y reemplazar en la pestaña Informes:

(Solo si tiene una versión anterior a la versión as a Cloud Service de las guías del Experience Manager de junio de 2023)

Realice los siguientes pasos para indexar el contenido existente y utilice el nuevo texto de buscar y reemplazar en el nivel de asignación y en la lista de temas de la pestaña Informes:

1. Ejecute una solicitud de POST al servidor (con la autenticación correcta): `http://<server:port>/bin/guides/map-find/indexing`. (Opcional: puede pasar rutas específicas de los mapas para indexarlas, de forma predeterminada se indexarán todas las asignaciones|| Por ejemplo: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

1. También se puede pasar una carpeta raíz para indexar las asignaciones DITA de una carpeta específica (y sus subcarpetas). Por ejemplo, `http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test`. Tenga en cuenta que si se pasan tanto el parámetro de rutas como el parámetro raíz, solo se tendrá en cuenta el parámetro de rutas.

1. La API devuelve un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(Por ejemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)


1. Una vez finalizado el trabajo, la solicitud de GET anterior responde correctamente y menciona si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.

## Pasos para gestionar el `'fmdita rewriter'` conflicto

Las guías del Experience Manager tienen un [**reescritura sling personalizada**](../cs-install-guide/conf-output-generation.md#custom-rewriter) módulo para gestionar los enlaces generados en caso de mapas cruzados (enlaces entre los temas de dos mapas diferentes).

Si tiene otra reescritura de sling personalizada en la base de código, utilice una `'order'` valor mayor que 50, ya que el reescritor sling de las Guías del Experience Manager utiliza `'order'` 50.  Para anular esto, necesita un valor >50. Para obtener más información, consulte [Canalizaciones de reescritura de salida](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante esta actualización, dado que el `'order'` Si el valor cambia de 1000 a 50, debe combinar la reescritura personalizada existente, si la hay, con `'fmdita-rewriter'`.


## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con las guías del Experience Manager as a Cloud Service para la versión de diciembre de 2023.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión de Experience Manager Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.12.0 | No compatible | 2022 o superior |
| | | |


### Conector de oxígeno

| Versión de Experience Manager Guides as a Cloud | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.12.0 | 3.3-uuid.5 | 3.3-uuid.5 | 2,3 | 2,3 |
|  |  |  |  |


### Versión de plantilla de base de conocimiento

| Nombre del paquete de componentes | Versión de componentes | Versión de plantilla |
|---|---|---|
| Paquete de contenido de componentes de guías del Experience Manager para Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:



### Creación

- El **Título** en la pestaña Editor web se trunca después de un punto (.) extra. (14372)
- No se ha actualizado la mensajería de error para nombres de asignaciones duplicados en la interfaz de usuario de Assets. (14320)
- Se produce un error en la lógica de creación de versiones al arrastrar y soltar recursos. (14291)
- El contenido reutilizable omite los ID de elemento. (14213)
- El control de configuración que se va a ocultar **Variables de idioma** panel debajo de **Output** falta la pestaña. (14194)
- El Editor Web genera errores de aplicación al agregar una nueva referencia o tema mediante un esquema especializado en la vista Presentación. (14094)
- Un vínculo de anclaje a `<dlentry>` o `<dt>` El elemento no muestra el texto del vínculo. (13543)
- El **Favoritos** La colección del Editor Web no se puede cargar. (13495)
- Las citas muestran vínculos en los que no se puede hacer clic cuando se crean con un ID único con espacios. (13447)
- En el **Diseño** vista de un mapa de libros, usando **Mover a la derecha** para convertir un capítulo seleccionado en un subelemento no funciona. (12567)
- La ventana de vista previa del Editor XML se trunca en los exploradores Google Chrome y Microsoft Edge. (10755)
- El editor web carece de la capacidad de envolver un elemento dentro de los posibles elementos principales. (8791)

### Publicación

- Los componentes de Famidia tienen una ruta codificada de `delegator.jsp`, evitando la superposición de componentes de AEM Sites. (13993)
- La vista etiquetada del reactor de PDF en la salida de publicación del PDF nativo no funciona como se esperaba. (13622)
- AEM La publicación de sitios encuentra un problema al comprometerse con el almacén de datos para mapas grandes con vínculos de igual a igual de ámbito. (13531)
- No se puede activar un sitio mediante el panel de publicación en masa de las guías del Experience Manager. (13439)
- La localización de las etiquetas de elementos no funciona correctamente en la salida de AEM Sites. (12144)
- Falta **ditaval** en los ajustes preestablecidos de salida del nivel de perfil de carpeta creados mediante la interfaz de usuario del editor web. (11903)

### Administración

- AEM Los entornos de nube de se encuentran con la excepción MongoWrite debido a nodos de gran tamaño. (13509)

### Traducción

- El **Aceptar/Rechazar** aparecen erróneamente botones para la traducción humana aprobada automáticamente. (14318)
- AEM Los problemas de internacionalización (i18n) se producen durante la transformación de archivos DITA que no están en inglés a páginas de. (14286)
- El contenido traducido no se puede sincronizar desde proyectos de traducción temporales y el asistente de traducción del editor XML DITA muestra incorrectamente **En curso** estado de los trabajos aprobados. (9938)

### Accesibilidad

- No se puede navegar por la interfaz de usuario del lienzo de creación, ya que el enfoque queda atrapado en el editor de temas. (13517)

## Problema conocido

El Adobe ha identificado el siguiente problema conocido para la versión de diciembre de 2023:
- &quot;Error de DTD no válido&quot; se produce de forma intermitente al actualizar a la versión de diciembre de 2023.