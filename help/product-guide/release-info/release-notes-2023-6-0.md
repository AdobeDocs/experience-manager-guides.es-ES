---
title: Notas de versión | Instrucciones de actualización y problemas corregidos en la versión de Adobe Experience Manager Guides de junio de 2023
description: Obtenga información acerca de las correcciones de errores y cómo actualizar a la versión de junio de 2023 de Adobe Experience Manager Guides as a Cloud Service
exl-id: df17ee33-9f50-4223-ab9f-a57a31097d22
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1169'
ht-degree: 1%

---

# Lanzamiento de Adobe Experience Manager Guides as a Cloud Service en junio de 2023

Esta nota de la versión cubre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en la versión de junio de 2023 de Adobe Experience Manager Guides (que más adelante se denominará *AEM Guides as a Cloud Service*).

Para obtener más información sobre las nuevas características y mejoras, consulte [Novedades de la versión de junio de 2023 de AEM Guides as a Cloud Service](whats-new-2023-6-0.md).

## Actualización a la versión de junio de 2023

Actualice la configuración actual de AEM Guides as a Cloud Service realizando los siguientes pasos:

1. Consulte el código Git de Cloud Services y cambie a la rama configurada en la canalización de Cloud Services correspondiente al entorno que desea actualizar.
2. Actualice la propiedad `<dox.version>` en el archivo `/dox/dox.installer/pom.xml` de su código Git de Cloud Services a 2023.6.297.
3. Confirme los cambios y ejecute la canalización de Cloud Services para actualizar a la versión de junio de 2023 de AEM Guides as a Cloud Service.

## Pasos para activar el déclencheur de una secuencia de comandos mediante un servlet

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

En el JSON de respuesta anterior, la clave `lockNodePath` contiene la ruta al nodo creado en el repositorio que señala al trabajo enviado. Se eliminará automáticamente una vez finalizado el trabajo y, hasta entonces, puede hacer referencia a este nodo para consultar el estado actual del trabajo.

Espere hasta que se complete este trabajo antes de continuar con los siguientes pasos.

>[!NOTE]
>
> Debe comprobar si el nodo sigue presente y el estado del trabajo.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Pasos para publicar y procesar el contenido existente a fin de utilizar el informe de vínculos rotos

(Solo si tiene una versión anterior al lanzamiento de junio de 2023 de AEM Guides as a Cloud Service)

Realice los siguientes pasos para posprocesar el contenido existente y utilizar el nuevo informe de vínculos rotos:

1. (Opcional) Si hay más de 100 000 archivos dita en el sistema, actualice `queryLimitReads` en `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valor mayor (cualquier valor mayor que el número de recursos presentes, por ejemplo 200 000) y vuelva a implementar.

   - Siga las instrucciones de la sección *Anulaciones de configuración* en Instalar y configurar Adobe Experience Manager Guides
as a Cloud Service, para crear el archivo de configuración.
   - En el archivo de configuración, proporcione los siguientes detalles (propiedad) para configurar la opción queryLimitReads:

     | PID | Clave de propiedad | Valor de propiedad |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Value: 200000 Valor predeterminado: 100000 |

1. Ejecute una petición POST en el servidor (con la autenticación correcta): `http://<server:port>//bin/guides/reports/upgrade`.

1. La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Por ejemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una vez completado el trabajo, la solicitud anterior de GET se responderá correctamente. Si el trabajo falla por algún motivo, los errores se pueden ver en los registros del servidor.

1. Volver al valor predeterminado o anterior existente de `queryLimitReads` si lo ha cambiado en el paso 1.

## Pasos para indexar el contenido existente para utilizar la nueva lista de temas y buscar y reemplazar en la pestaña Informes:

(Solo si tiene una versión anterior al lanzamiento en septiembre de 2022 de AEM Guides as a Cloud Service)

Realice los siguientes pasos para indexar el contenido existente y utilice el nuevo texto de buscar y reemplazar en el nivel de asignación y en la lista de temas de la pestaña Informes:

1. Ejecute una petición POST al servidor \(con la autenticación correcta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: puede pasar rutas específicas de las asignaciones para indexarlas; de forma predeterminada, todas las asignaciones se indexarán \|\| Por ejemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. También se puede pasar una carpeta raíz para indexar las asignaciones DITA de una carpeta específica (y sus subcarpetas). Por ejemplo, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Tenga en cuenta que si se pasan tanto el parámetro de rutas como el parámetro raíz, solo se tendrá en cuenta el parámetro de rutas.

1. La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(por ejemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Una vez completado el trabajo, la solicitud de GET anterior responderá correctamente y mencionará si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con la versión de junio de 2023 de AEM Guides as a Cloud Service.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión de AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.06.0 | No compatible | 2022 o superior |
| | | |


### Conector de oxígeno

| Versión de AEM Guides as a Cloud | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.06.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |  |


## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

### Creación

- Navtitle se elimina del contenido33 al cambiar de la vista Diseño a la vista Autor o Código fuente. (12174)
- A veces, se produce un error de aplicación al hacer clic en un mapa DITA. (11842)
- Editor web | Se agrega espacio de no separación en el Editor XML al editar un tema. (11786)
- IU de recursos | En la vista de lista, las columnas disponibles superpuestas no se pueden combinar. (11528)
- Keyref no se resuelve en la vista de mapa. (11490)
- El menú superior no aparece al navegar por el editor XML. (10868)
- `conref` en etiqueta ph | El cuadro de diálogo de exploración mostrado es incorrecto. (9481)
- Los vínculos locales a otros elementos no se resuelven en el Editor web. (8790)
- La función Matches() no funciona en la función schematron. (11224)


### Administración

- La ficha Informes de la interfaz de usuario del editor web no muestra la lista de temas de los mapas DITA creados antes de la actualización a la versión 4.2. (11708)

- La funcionalidad del botón Cargar archivos de la IU de Assets se interrumpe en la versión 4.2. (11633)

### Publicación

- La publicación en el sitio de AEM falla al leer archivos temporales del pod que pueden haberse actualizado o reiniciado. (12113)
- PDF nativo | La publicación de contenido que tiene una clase de salida con paréntesis() provoca la congelación de la publicación. (11936)
- Salida JSON | La asignación de metadatos con valor de propiedad como `"value in spaces and double quotes"` produce un error de publicación. (11933)
- Editor web | No se pueden seleccionar la ruta y la plantilla de salida en el ajuste preestablecido de AEM. (11530)
- PDF nativo | Los atributos personalizados no se propagan al motor temporal HTML o PDF. (DXML-12005)
- PDF nativo |  Java OutOfMemoryError se produce al publicar contenido grande. (11789)
- Salida JSON | La propiedad `fmUuid` del nodo jcr:content de JSON es diferente del &quot;id&quot; dentro de JSON. (11564)
- Salida JSON | Si el mapa y el tema con el mismo nombre de archivo están presentes, se elimina JSON para el mapa. (11524)
- PDF nativo | Xref está imprimiendo el contenido del título del tema href en lugar de la etiqueta Xref. (11322)
- PDF nativo | No se puede guardar la configuración de la plantilla de PDF. (10751)
- PDF nativo | El texto se extiende más allá del ancho de la columna al incluir varias referencias x. (10876)
- PDF nativo | El elemento `<note>``</note>` no genera un título de espacio adicional de su tipo. (10549)
- PDF nativo | Los metadatos de idioma no se pueden establecer en el PDF generado para cumplir con WCAG 2.0. (12296)



### Traducción

- Después de la versión en la nube de febrero (2302), todo el contenido de traducción muestra Fuera de sincronización o Falta de copia. (11834)

### Revisión

- Nueva IU de revisión | Las condiciones de resaltar y mostrar u ocultar funcionan de forma diferente a como funcionan en el Editor web. (11628)
