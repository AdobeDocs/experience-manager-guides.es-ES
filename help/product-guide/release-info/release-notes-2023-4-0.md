---
title: Notas de versión | Guías de Adobe Experience Manager as a Cloud Service, versión de abril de 2023
description: Lanzamiento de abril de 2023 de Adobe Experience Manager Guides as a Cloud Service
exl-id: fa339eab-d3d0-4763-adbf-6411e39aa213
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 0%

---

# Lanzamiento de abril de 2023 de Adobe Experience Manager Guides as a Cloud Service

Esta nota de la versión cubre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en la versión de abril de 2023 de las guías de Adobe Experience Manager (más adelante denominados *AEM Guías de as a Cloud Service*).

Para obtener más información sobre las nuevas funciones y mejoras, consulte [AEM Novedades de la versión de abril de 2023 de Guías de la comunidad de la as a Cloud Service](whats-new-2023-4-0.md).

## Actualización a la versión de abril de 2023

AEM Actualice la configuración as a Cloud Service de las guías de usuario actuales realizando los siguientes pasos:

1. Consulte el código Git de los Cloud Service y cambie a la rama configurada en la canalización de Cloud Service correspondiente al entorno que desea actualizar.
2. Actualizar `<dox.version>` propiedad en `/dox/dox.installer/pom.xml` de su código Git de Cloud Service a 2023.4.249.
3. Confirme los cambios y ejecute la canalización de Cloud Service AEM para actualizar a la versión de abril de 2023 de las guías de la as a Cloud Service.

## AEM Pasos para indexar el contenido existente (solo si se encuentra en una versión anterior a la versión de septiembre de Guías de as a Cloud Service)

Realice los siguientes pasos para indexar el contenido existente y utilizar el nuevo texto de buscar y reemplazar en el nivel de asignación:

* Ejecute una solicitud de POST al servidor (con la autenticación correcta): `http://<server:port>/bin/guides/map-find/indexing`.
(Opcional: puede pasar rutas específicas de los mapas para indexarlas, de forma predeterminada se indexarán todas las asignaciones || Ejemplo : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Por ejemplo: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Una vez completado el trabajo, la solicitud de GET anterior responderá correctamente y mencionará si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.

## Matriz de compatibilidad

AEM En esta sección se enumera la matriz de compatibilidad para las aplicaciones de software compatibles con las guías de la aplicación as a Cloud Service para la versión de abril de 2023 de las Guías de la.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| AEM Versión de Guides as a Cloud de | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.04.0 | No compatible | 2022 o superior |
| | | |


### Conector de oxígeno

| AEM Versión de Guides as a Cloud de | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.04.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |



## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

* PDF nativo | La publicación de contenido que tiene una clase de salida con paréntesis() provoca la congelación de la publicación. (11596)
* El problema se produce al mover (arrastrar y soltar) un elemento de lista existente con el control de cambios activado. (11570)
* El problema se produce al mover (arrastrar y soltar) un nuevo elemento de lista con el control de cambios activado. (11569)
* La aplicación o anulación de sangría de elementos de lista no funciona según lo esperado con Control de cambios activado. (11568)
* Agregar contenido en una línea con Control de cambios activado y, a continuación, desactivar Control de cambios no lo desactiva. (11567)
* Dificultad para arrastrar y soltar un elemento de lista; el texto se mueve en lugar del elemento de lista. (11566)
* La revisión completada no se abre en modo de solo lectura. (11387)
* AEM El problema se produce en la búsqueda del sitio de la (no funciona más allá de 2-3 nodos de nivel). (11352)
* Al crear el elemento mostrado en verde (Control de cambios), el nuevo contenido se muestra como control de cambios aunque el control de cambios esté desactivado. (7021)

### Problema conocido con la solución

El Adobe AEM de ha identificado el siguiente problema conocido para la versión de Guías de as a Cloud Service para abril de 2023.

* PDF nativo | Los metadatos antiguos no se rellenan hasta que se abre explícitamente el ajuste preestablecido de salida.
