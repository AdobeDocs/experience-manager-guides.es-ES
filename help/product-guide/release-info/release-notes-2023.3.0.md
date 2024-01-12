---
title: Notas de versión | Guías de Adobe Experience Manager as a Cloud Service, versión de marzo de 2023
description: Lanzamiento de marzo de Adobe Experience Manager Guides as a Cloud Service
exl-id: 6a0bba92-7d7d-4b20-ad46-0eacc91268da
feature: Release Notes
role: Leader
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 0%

---

# Lanzamiento de marzo de 2023 de Adobe Experience Manager Guides as a Cloud Service

Esta nota de la versión cubre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en la versión de marzo de 2023 de las guías de Adobe Experience Manager (más adelante denominadas *AEM Guías de as a Cloud Service*).

Para obtener más información sobre las nuevas funciones y mejoras, consulte [AEM Novedades de la versión de marzo de 2023 de Guías de la as a Cloud Service](whats-new-2023.3.0.md).

## Actualizar a la versión de marzo de 2023

AEM Actualice la configuración as a Cloud Service de las guías de usuario actuales realizando los siguientes pasos:
1. Consulte el código Git de los Cloud Service y cambie a la rama configurada en la canalización de Cloud Service correspondiente al entorno que desea actualizar.
2. Actualizar `<dox.version>` propiedad en `/dox/dox.installer/pom.xml` de su código Git de Cloud Service a 2023.3.242.
3. Confirme los cambios y ejecute la canalización de Cloud Service AEM para actualizar a la versión de marzo de 2023 de las guías de la as a Cloud Service.

## AEM Pasos para indexar el contenido existente (solo si se encuentra en una versión anterior a la versión de septiembre de Guías de as a Cloud Service)

Realice los siguientes pasos para indexar el contenido existente y utilizar el nuevo texto de buscar y reemplazar en el nivel de asignación:

* Ejecute una solicitud de POST al servidor (con la autenticación correcta): `http://<server:port>/bin/guides/map-find/indexing`.
(Opcional: puede pasar rutas específicas de los mapas para indexarlas, de forma predeterminada se indexarán todas las asignaciones || Ejemplo : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Por ejemplo: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Una vez completado el trabajo, la solicitud de GET anterior responderá correctamente y mencionará si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.

## Matriz de compatibilidad

AEM En esta sección se muestra la matriz de compatibilidad para las aplicaciones de software compatibles con las guías de la versión de as a Cloud Service para marzo de 2023.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| AEM Versión de Guides as a Cloud de | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.03.0 | No compatible | 2022 o superior |
| | | |


### Conector de oxígeno

| AEM Versión de Guides as a Cloud de | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.03.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |

## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

* El proceso del PDF de descarga no funciona correctamente en el editor web. (11496)
* Salida JSON | Asignar metadatos con valor de propiedad como `"value in spaces and double quotes"` conduce a un error de publicación. (11438)
* La inserción de archivos multimedia de audio y vídeo falla en el formato YouTube en **Insertar multimedia** icono. (11320)
* El error de validación se produce cuando se crea un mapa con la plantilla que tiene un elemento de título especializado. (11212)
* PDF nativo | la nota al pie presente en el encabezado de la tabla lleva a texto en negrita y alineado al centro en el pie de página correspondiente dentro de la salida del PDF. (10610)
>[!NOTE]
>
>Para reflejar el cambio del PDF nativo, elimine la carpeta del PDF ubicada en /content/dam/dita-templates y luego actualice a la última versión. (10610)

### Problema conocido con la solución

El Adobe AEM de ha identificado el siguiente problema conocido para la versión de Guías de as a Cloud Service para marzo de 2023.

* Los usuarios no pueden guardar ni crear la versión de un recurso duplicado.

**Solución**: Antes de realizar cambios en el recurso duplicado, vuelva a procesarlo desde la interfaz de usuario de Assets.
