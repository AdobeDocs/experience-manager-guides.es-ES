---
title: Notas de versión | Instrucciones de actualización y problemas corregidos en la versión de Adobe Experience Manager Guides de septiembre de 2023
description: Obtenga información acerca de las correcciones de errores y cómo actualizar a la versión de septiembre de 2023 de Adobe Experience Manager Guides as a Cloud Service
exl-id: 795b86a0-e763-404a-a4bb-35d3d2a42672
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 0%

---

# Versión de septiembre de 2023 de Adobe Experience Manager Guides as a Cloud Service

Esta nota de la versión cubre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en la versión de septiembre de 2023 de Adobe Experience Manager Guides (que más adelante se denominará *AEM Guides as a Cloud Service*).

Para obtener más información sobre las nuevas características y mejoras, consulte [Novedades de la versión de septiembre de 2023 de AEM Guides as a Cloud Service](whats-new-2023-9-0.md).

## Actualizar a la versión de septiembre de 2023

Actualice la configuración as a Cloud Service de AEM Guides actual realizando los siguientes pasos:

1. Consulte el código Git de los Cloud Service y cambie a la rama configurada en la canalización de Cloud Service correspondiente al entorno que desea actualizar.
2. Actualice la propiedad `<dox.version>` en el archivo `/dox/dox.installer/pom.xml` de su código Git de Cloud Service a 2023.9.0.359.
3. Confirme los cambios y ejecute la canalización de Cloud Service para actualizar a la versión de septiembre de 2023 de AEM Guides as a Cloud Service.

## Pasos para activar el déclencheur de una secuencia de comandos mediante un servlet

(Solo si tiene una versión anterior al lanzamiento de junio de 2023 de AEM Guides as a Cloud Service)

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

(Solo si tiene una versión anterior al lanzamiento de junio de 2023 de AEM Guides as a Cloud Service)

Realice los siguientes pasos para posprocesar el contenido existente y utilizar el nuevo informe de vínculos rotos:

1. (Opcional) Si hay más de 100 000 archivos dita en el sistema, actualice `queryLimitReads` en `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valor mayor (cualquier valor mayor que el número de recursos presentes, por ejemplo 200 000) y vuelva a implementar.

   - Siga las instrucciones de la sección *Anulaciones de configuración* en Instalar y configurar Adobe Experience Manager Guides
as a Cloud Service, para crear el archivo de configuración.
   - En el archivo de configuración, proporcione los siguientes detalles (propiedad) para configurar la opción queryLimitReads:

     | PID | Clave de propiedad | Valor de propiedad |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Value: 200000 Valor predeterminado: 100000 |

1. Ejecute una solicitud de POST al servidor (con la autenticación correcta): `http://<server:port>//bin/guides/reports/upgrade`.

1. La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Por ejemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una vez completado el trabajo, la solicitud de GET anterior se responderá correctamente. Si el trabajo falla por algún motivo, los errores se pueden ver en los registros del servidor.

1. Volver al valor predeterminado o anterior existente de `queryLimitReads` si lo ha cambiado en el paso 1.

## Pasos para indexar el contenido existente para utilizar la nueva lista de temas y buscar y reemplazar en la pestaña Informes:

(Solo si tiene una versión anterior al lanzamiento de junio de 2023 de AEM Guides as a Cloud Service)

Realice los siguientes pasos para indexar el contenido existente y utilice el nuevo texto de buscar y reemplazar en el nivel de asignación y en la lista de temas de la pestaña Informes:

1. Ejecute una solicitud de POST al servidor \(con la autenticación correcta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Opcional: puede pasar rutas específicas de las asignaciones para indexarlas; de forma predeterminada, todas las asignaciones se indexarán \|\| Por ejemplo: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. También se puede pasar una carpeta raíz para indexar las asignaciones DITA de una carpeta específica (y sus subcarpetas). Por ejemplo, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Tenga en cuenta que si se pasan tanto el parámetro de rutas como el parámetro raíz, solo se tendrá en cuenta el parámetro de rutas.

1. La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID de trabajo al mismo punto final: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(por ejemplo: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Una vez completado el trabajo, la solicitud de GET anterior responderá correctamente y mencionará si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con la versión de septiembre de 2023 de AEM Guides as a Cloud Service.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión de AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.09.0 | No compatible | 2022 o superior |
| | | |


### Conector de oxígeno

| Versión de AEM Guides as a Cloud | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.09.0 | 3.1-uuid 17 | 3.1-uuid 17 | 2,3 | 2,3 |
|  |  |  |  |


### Versión de plantilla de base de conocimiento

| Nombre del paquete de componentes | Versión de componentes | Versión de plantilla |
|---|---|---|
| Paquete de contenido de componentes de AEM Guides para Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

### Creación

- El archivo de tema no está desbloqueado en el Editor Web, aunque las opciones Desbloquear el archivo y No guardar están seleccionadas. (12558)
- No se puede desproteger un archivo en el Editor Web, a pesar de que se ha elegido la opción NO para descartar los cambios antes de protegerlo. (12557)
- La información sobre herramientas de los iconos Bloquear y desbloquear archivo de la barra de herramientas principal del Editor Web no es coherente con los iconos mostrados en la Vista de repositorio.(12555)
- La opción Cancelar desprotección y Desbloquear se muestra para un archivo del Editor Web que aún no se ha desprotegido en la Vista de mapa. (12556)
- No se pueden seleccionar los recursos de PDF en los vínculos &quot;topicref&quot; existentes. (12477).
- En la vista de repositorio, los temas o imágenes no se pueden arrastrar después de usar la funcionalidad Buscar/Filtrar. (12396)
- Los resultados de búsqueda se desactivan en el panel Buscar y reemplazar después de abrir un archivo buscado. (12142)
- La tecla numérica &quot;8&quot; del teclado lateral no funciona en el editor de AEM Guides. (12106)

- El prefijo se duplica en el modo de vista previa del editor web. (13133)
- `Choicetable` filas no se muestran o no se pueden seleccionar. (12616)
- El editor web genera errores de validación en escenarios específicos al crear un tema mediante un esquema personalizado. (12576)
- Las referencias a la plantilla de tema ditaval no crean una copia en la carpeta de contenido al crear un mapa a partir de la plantilla de mapa. (12150)
- El cuadro de búsqueda de los mapas DITA no tiene un botón de cierre. (11867)
- Al guardar archivos largos en el Editor Web, `DirtyChecker` genera una excepción con un seguimiento de pila largo y rellena los archivos de registro. (11860)
- La creación de temas DITA requiere permiso de eliminación en el nodo de carpeta correspondiente, aunque el mapa se puede crear con permiso de escritura. (11706)
- El editor web muestra un título incorrecto cuando hay una barra diagonal. (10949)


### Administración

- El campo &quot;title&quot; en las propiedades de metadatos de mapa DITA se sobrescribe con el elemento `<title>` para el mapa. (10702)
- La referencia de contenido se interrumpe al copiar y pegar archivos DITA cuando el ID del tema no es el mismo que el GUID. (12614)
- En las líneas de base dinámicas, la lista de etiquetas no se extrae de las referencias directas de la copia de trabajo de un mapa DITA. (11917)

### Publicación

- La publicación falla al cambiar el nombre de un ajuste preestablecido de PDF nativo. (12564)
- Al duplicar una plantilla de PDF nativa, se duplica la ubicación de plantilla predeterminada en lugar de la ubicación de plantilla personalizada proporcionada. (12563)

- PDF nativo | La inclusión de varias expresiones XFR extiende el texto más allá del ancho de columna. (13004)
- PDF nativo | Cuando el tema y el título tienen el mismo ID, se produce una generación incorrecta de la salida del PDF. (12644)
- PDF nativo | Al agregar una clase de salida a un elemento `<topicref>` principal en un mapa DITA y aplicar un estilo personalizado a la clase de salida, el estilo se aplica a los elementos dentro del cuerpo del tema, incluidos los títulos de sección.(12166)
- La publicación incremental no funciona si un mapa DITA tiene varios ditavalrefs. (12117)
- AEM Sitio web de | Al crear un mapa con keydef apuntando a un tema como variable y agregar processing-role=resource-only, se crean algunas páginas inesperadas. (12099)
- AEM AEM Si alguno de los recursos de DAM de la creación se utiliza en cualquier salida que no sea el sitio de la, entonces los metadatos &quot;jcr:createdBy&quot; no reflejan el nombre del editor ni el nombre del usuario que modificó por última vez el mapa o tema de DITA. (12090)
- AEM Sites | El mapa DITA con el encabezado del tema en el título de navegación (con caracteres no compatibles) conduce a direcciones URL de página incorrectas. (11978)
- PDF nativo | Se producen problemas en la compatibilidad de topichead / topicmeta / navtitle en Frontmatter y Backmatter. (11969)
- PDF nativo | La generación de PDF para documentos grandes requiere mucho tiempo. (11955)
- PDF nativo | Al cambiar el nombre de un ajuste preestablecido, se produce una NullPointerException mientras se genera una salida de PDF. (11889)
- El contenido `<conref>` no se muestra en la salida del PDF. (11131)
- Se agrega un espacio adicional dentro de los elementos `<div>` al alternar entre la vista Autor y Source en el editor de diseño de página. (10750)
- AEM El contenido replicado en el administrador de nube de no es visible en la instancia de Publish. (9564)

### Traducción

- El proceso para exportar una línea base con el nombre cambiado para una traducción falla. (12993)
- El título del archivo traducido se muestra en lugar del título del archivo de origen. (11630)
