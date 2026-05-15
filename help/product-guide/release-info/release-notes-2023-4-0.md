---
title: Notas de versión | Adobe Experience Manager Guides as a Cloud Service, versión de abril de 2023
description: Lanzamiento de Adobe Experience Manager Guides as a Cloud Service en abril de 2023
exl-id: fa339eab-d3d0-4763-adbf-6411e39aa213
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/tGOV1IcAL8f2B5ziGWPOMfkkPZGPlxcXSerTtAO3LW0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 602
ht-degree: 2%

---

# Lanzamiento de Adobe Experience Manager Guides as a Cloud Service en abril de 2023

Esta nota de la versión cubre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en la versión de abril de 2023 de Adobe Experience Manager Guides (que más adelante se denominará *AEM Guides as a Cloud Service*).

Para obtener más información sobre las nuevas características y mejoras, consulte [Novedades de la versión de abril de 2023 de AEM Guides as a Cloud Service](whats-new-2023-4-0.md).

## Actualización a la versión de abril de 2023

Actualice la configuración actual de AEM Guides as a Cloud Service realizando los siguientes pasos:

1. Consulte el código Git de Cloud Services y cambie a la rama configurada en la canalización de Cloud Services correspondiente al entorno que desea actualizar.
2. Actualice la propiedad `<dox.version>` en el archivo `/dox/dox.installer/pom.xml` de su código Git de Cloud Services a 2023.4.249.
3. Confirme los cambios y ejecute la canalización de Cloud Services para actualizar a la versión de abril de 2023 de AEM Guides as a Cloud Service.

## Pasos para indexar el contenido existente (solo si tiene una versión anterior a la versión de septiembre de AEM Guides as a Cloud Service)

Realice los siguientes pasos para indexar el contenido existente y utilizar el nuevo texto de buscar y reemplazar en el nivel de asignación:

* Ejecute una petición POST en el servidor (con la autenticación correcta): `http://<server:port>/bin/guides/map-find/indexing`.
(Opcional: puede pasar rutas específicas de los mapas para indexarlas, de forma predeterminada se indexarán todas las asignaciones Ejemplo de || : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* La API devolverá un jobId. Para comprobar el estado del trabajo, puede enviar una solicitud de GET con el ID del trabajo al mismo punto final: `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Por ejemplo: http://&lt;_localhost:8080_/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Una vez completado el trabajo, la solicitud de GET anterior responderá correctamente y mencionará si alguna asignación ha fallado. Los mapas indexados correctamente se pueden confirmar desde los registros del servidor.

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con la versión de abril de 2023 de AEM Guides as a Cloud Service.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión de AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.04.0 | No compatible | 2022 o superior |
| | | |


### Conector de oxígeno

| Versión de AEM Guides as a Cloud | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.04.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |  |



## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

* PDF nativo | La publicación de contenido que tiene una clase de salida con paréntesis() provoca la congelación de la publicación. (11596)
* El problema se produce al mover (arrastrar y soltar) un elemento de lista existente con el control de cambios activado. (11570)
* El problema se produce al mover (arrastrar y soltar) un nuevo elemento de lista con el control de cambios activado. (11569)
* La aplicación o anulación de sangría de elementos de lista no funciona según lo esperado con Control de cambios activado. (11568)
* Agregar contenido en una línea con Control de cambios activado y, a continuación, desactivar Control de cambios no lo desactiva. (11567)
* Dificultad para arrastrar y soltar un elemento de lista; el texto se mueve en lugar del elemento de lista. (11566)
* La revisión completada no se abre en modo de solo lectura. (11387)
* El problema se produce en la búsqueda del sitio de AEM (no funciona más allá de 2-3 nodos de nivel). (11352)
* Al crear el elemento mostrado en verde (Control de cambios), el nuevo contenido se muestra como control de cambios aunque el control de cambios esté desactivado. (7021)

### Problema conocido con la solución

Adobe ha identificado el siguiente problema conocido de la versión de abril de 2023 de AEM Guides as a Cloud Service.

* PDF nativo | Los metadatos antiguos no se rellenan hasta que se abre explícitamente el ajuste preestablecido de salida.
