---
title: Notas de versión | Instrucciones de actualización y problemas corregidos en la versión de Adobe Experience Manager Guides de octubre de 2023
description: Obtenga información acerca de las correcciones de errores y cómo actualizar a la versión de octubre de 2023 de Adobe Experience Manager Guides as a Cloud Service
exl-id: 536d2ec2-31a0-4533-9c29-16a27525acca
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 1%

---

# Versión de octubre de 2023 de Adobe Experience Manager Guides as a Cloud Service

Esta nota de la versión cubre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en la versión de octubre de 2023 de Adobe Experience Manager Guides (que más adelante se denominará *AEM Guides as a Cloud Service*).

Para obtener más información sobre las nuevas características y mejoras, consulte [Novedades de la versión de octubre de 2023 de AEM Guides as a Cloud Service](whats-new-2023-10-0.md).

## Actualizar a la versión de octubre de 2023

Actualice la configuración as a Cloud Service de AEM Guides actual realizando los siguientes pasos:

1. Consulte el código Git de los Cloud Service y cambie a la rama configurada en la canalización de Cloud Service correspondiente al entorno que desea actualizar.
2. Actualice la propiedad `<dox.version>` en el archivo `/dox/dox.installer/pom.xml` de su código Git de Cloud Service a 2023.10.0.373.
3. Confirme los cambios y ejecute la canalización de Cloud Service para actualizar a la versión de octubre de 2023 de AEM Guides as a Cloud Service.

## Pasos para activar el déclencheur de una secuencia de comandos mediante un servlet

(Solo si tiene una versión anterior a la versión de junio de 2023 de AEM Guides as a Cloud Service)

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

(Solo si tiene una versión anterior a la versión de junio de 2023 de AEM Guides as a Cloud Service)

Realice los siguientes pasos para posprocesar el contenido existente y utilizar el nuevo informe de vínculos rotos:

1. (Opcional) Si hay más de 100 000 archivos DITA en el sistema, actualice `queryLimitReads` en `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valor mayor (cualquier valor mayor que el número de recursos presentes, por ejemplo 200 000) y vuelva a implementar.

   - Siga las instrucciones que se indican en la sección *Anulaciones de configuración* de Instalar y configurar Adobe Experience Manager Guides as a Cloud Service para crear el archivo de configuración.
   - En el archivo de configuración, proporcione los siguientes detalles (propiedad) para configurar la opción queryLimitReads:

     | PID | Clave de propiedad | Valor de propiedad |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Value: 200000 Valor predeterminado: 100000 |

1. Ejecute una solicitud de POST al servidor (con la autenticación correcta): `http://<server:port>//bin/guides/reports/upgrade`.

1. La API devuelve un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Por ejemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una vez finalizado el trabajo, la solicitud de GET anterior responde correctamente. Si el trabajo falla por algún motivo, los errores se pueden ver en los registros del servidor.

1. Revertir al valor existente predeterminado o anterior de `queryLimitReads` si lo ha cambiado en el paso 1.

## Pasos para indexar el contenido existente para utilizar la nueva lista de temas y buscar y reemplazar en la pestaña Informes:

(Solo si tiene una versión anterior a la versión de junio de 2023 de AEM Guides as a Cloud Service)

Realice los siguientes pasos para indexar el contenido existente y utilice el nuevo texto de buscar y reemplazar en el nivel de asignación y en la lista de temas de la pestaña Informes:

1. Ejecute una solicitud de POST al servidor \(con la autenticación correcta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: puede pasar rutas específicas de las asignaciones para indexarlas; de forma predeterminada, todas las asignaciones se indexarán \|\| Por ejemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. También se puede pasar una carpeta raíz para indexar las asignaciones DITA de una carpeta específica (y sus subcarpetas). Por ejemplo, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Tenga en cuenta que si se pasan tanto el parámetro de rutas como el parámetro raíz, solo se tendrá en cuenta el parámetro de rutas.

1. La API devuelve un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID de trabajo al mismo punto final: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(por ejemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Una vez finalizado el trabajo, la solicitud de GET anterior responde correctamente y menciona si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con la versión de AEM Guides as a Cloud Service para octubre de 2023.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión de AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.10.0 | No compatible | 2022 o superior |
| | | |


### Conector de oxígeno

| Versión de AEM Guides as a Cloud | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.10.0 | 3.2-uuid 5 | 3.2-uuid 5 | 2,3 | 2,3 |
|  |  |  |  |


### Versión de plantilla de base de conocimiento

| Nombre del paquete de componentes | Versión de componentes | Versión de plantilla |
|---|---|---|
| Paquete de contenido de componentes de AEM Guides para Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

### Creación

- Las horas de la tarde no se establecen en **Date** para la creación de líneas de base. (12712)
- No se puede pegar el código JSON en el elemento `<codeblock>` del editor web. (12326)
- Los cambios de versión no guardados y los indicadores correspondientes no se muestran para los archivos grandes. (11784)
- Al editar en coreano, el primer carácter cambia al predeterminado. (10049)


### Publicación

- PDF nativo | El orden de los temas no se corrige cuando se genera la salida del PDF. (13157)
- PDF nativo| No hay ninguna etiqueta de estilo predeterminada disponible para el elemento `<p>`. (12559)
- PDF nativo | Los estilos en línea aplicados al área de contenido no se aplican a los temas de la materia principal y de la materia secundaria. (13510)
- AEM El atributo `DeliveryTarget` no se propaga al generar la salida del sitio de la.  (13132)
- El flujo de trabajo **Publish AEM** se atasca al generar la salida del sitio de la aplicación para el contenido con ciertos errores. (12000)

### Administración

- El historial de versiones no se muestra aunque la propiedad `dc:format` no esté presente para un recurso. (10463)


### Revisión

- La revisión de un tema muestra comentarios incorrectos. (13453)



### Traducción

- La línea de base exportada desde el panel **Translation** produce un error y no se abre en el idioma de destino. (13466)

- Se crean nuevos proyectos de traducción en lugar de agregar nuevos trabajos a los proyectos de traducción existentes seleccionados.  (10214)

## Problema conocido

El Adobe ha identificado el siguiente problema conocido para la versión de octubre de 2023.

- Error al volver a publicar el fragmento de contenido.
