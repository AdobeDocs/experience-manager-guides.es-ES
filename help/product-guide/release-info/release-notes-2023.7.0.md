---
title: Notas de versión | Instrucciones de actualización y problemas corregidos en las guías de Adobe Experience Manager, versión de julio de 2023
description: Obtenga información acerca de las correcciones de errores y cómo actualizar a la versión de julio de 2023 de las guías de Adobe Experience Manager as a Cloud Service
exl-id: f1765c6a-cb8e-4a06-a6f4-f5c225b6bc88
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 1%

---

# Versión de julio de 2023 de Adobe Experience Manager Guides as a Cloud Service

Esta nota de la versión cubre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en la versión de julio de 2023 de las guías de Adobe Experience Manager (más adelante denominados *AEM Guías de as a Cloud Service*).

Para obtener más información sobre las nuevas funciones y mejoras, consulte [AEM Novedades de la versión de julio de 2023 de Guías de la as a Cloud Service](whats-new-2023.7.0.md).

## Actualizar a la versión de julio de 2023

AEM Actualice la configuración as a Cloud Service de las guías de usuario actuales realizando los siguientes pasos:

1. Consulte el código Git de los Cloud Service y cambie a la rama configurada en la canalización de Cloud Service correspondiente al entorno que desea actualizar.
2. Actualizar `<dox.version>` propiedad en `/dox/dox.installer/pom.xml` de su código Git de Cloud Service a 2023.7.0.314.
3. Confirme los cambios y ejecute la canalización de Cloud Service AEM para actualizar a la versión de julio de 2023 de las guías de la aplicación as a Cloud Service de la.

## Pasos para activar el déclencheur de una secuencia de comandos mediante un servlet

AEM (Solo si tiene una versión anterior a la versión as a Cloud Service de junio de 2023 de las Guías de la)

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

AEM (Solo si tiene una versión anterior a la versión as a Cloud Service de junio de 2023 de las Guías de la)

Realice los siguientes pasos para posprocesar el contenido existente y utilizar el nuevo informe de vínculos rotos:

1. (Opcional) Si hay más de 100 000 archivos dita en el sistema, actualice el `queryLimitReads` bajo `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valor mayor (cualquier valor mayor que el número de recursos presentes, por ejemplo 200 000) y, a continuación, vuelva a implementar.

   - Siga las instrucciones que se indican en *Anulaciones de configuración* en Instalar y configurar las guías de Adobe Experience Manager as a Cloud Service para crear el archivo de configuración.
   - En el archivo de configuración, proporcione los siguientes detalles (propiedad) para configurar la opción queryLimitReads:

     | PID | Clave de propiedad | Valor de propiedad |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Value: 200000 Valor predeterminado: 100000 |

1. Ejecute una solicitud de POST al servidor (con la autenticación correcta): `http://<server:port>//bin/guides/reports/upgrade`.

1. La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Por ejemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una vez completado el trabajo, la solicitud de GET anterior se responderá correctamente. Si el trabajo falla por algún motivo, los errores se pueden ver en los registros del servidor.

1. Volver al valor predeterminado o al valor existente anterior de `queryLimitReads` si lo ha cambiado en el paso 1.

## Pasos para indexar el contenido existente para utilizar la nueva lista de temas y buscar y reemplazar en la pestaña Informes:

AEM (Solo si tiene una versión anterior a la versión as a Cloud Service de junio de 2023 de las Guías de la)

Realice los siguientes pasos para indexar el contenido existente y utilice el nuevo texto de buscar y reemplazar en el nivel de asignación y en la lista de temas de la pestaña Informes:

1. Ejecute una solicitud de POST al servidor \(con autenticación correcta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: puede pasar rutas específicas de las asignaciones para indexarlas, de forma predeterminada, todas las asignaciones se indexarán \|\| Por ejemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. También se puede pasar una carpeta raíz para indexar las asignaciones DITA de una carpeta específica (y sus subcarpetas). Por ejemplo, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Tenga en cuenta que si se pasan tanto el parámetro de rutas como el parámetro raíz, solo se tendrá en cuenta el parámetro de rutas.

1. La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Por ejemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Una vez completado el trabajo, la solicitud de GET anterior responderá correctamente y mencionará si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.

## Matriz de compatibilidad

AEM En esta sección se muestra la matriz de compatibilidad para las aplicaciones de software compatibles con las guías de software de la versión as a Cloud Service de julio de 2023 de las Guías de.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| AEM Versión de Guides as a Cloud de | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.07.0 | No compatible | 2022 o superior |
| | | |


### Conector de oxígeno

| AEM Versión de Guides as a Cloud de | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.07.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |


## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

### Creación

- Los atributos en línea/de visualización no aparecen en la vista Presentación del Editor Web. (12498)
- AEM Subir archivos en Oxygen Plugin for Guides no funciona en los servicios en la nube si tiene ! en el nombre del archivo. (12207)
- La publicación de mapas DITA es muy lenta con plantillas editables. (12075)
- La configuración de la interfaz de usuario del perfil global no coincide con el perfil de carpeta. (11970)
- Las referencias de contenido se rompen cuando los ficheros DITA se copian y pegan. (11959)
- AEM No se puede editar el fragmento de contenido en la vista de columna con las Guías de instaladas. (7342)
- El contenido se pierde cuando una referencia xref no ajustada se encuentra bajo etiquetas de subelemento. (12532)

### Publicación

- El flujo de trabajo de aprobación no funciona cuando docstate se cambia a &quot;end state&quot; desde las propiedades de archivo del panel derecho. (11026)
