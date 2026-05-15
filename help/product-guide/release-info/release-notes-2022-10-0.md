---
title: Notas de versión | Adobe Experience Manager Guides as a Cloud Service, versión de octubre de 2022
description: Versión de octubre de Adobe Experience Manager Guides as a Cloud Service
exl-id: 38638080-625c-49c3-9e54-56cc23831546
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/w-fw81jYGDRDrmn98Dzn-hYIkOZzT0B3-4-y-bcxdz4
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2:
  - id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 489
ht-degree: 3%

---

# Versión de octubre de Adobe Experience Manager Guides as a Cloud Service

## Actualización a la versión de octubre

Actualice la configuración actual de Adobe Experience Manager Guides as a Cloud Service (más adelante denominada *AEM Guides as a Cloud Service*) siguiendo estos pasos:
1. Consulte el código Git de Cloud Services y cambie a la rama configurada en la canalización de Cloud Services correspondiente al entorno que desea actualizar.
1. Actualice la propiedad `<dox.version>` en el archivo `/dox/dox.installer/pom.xml` de su código Git de Cloud Services a 2022.10.183.
1. Confirme los cambios y ejecute la canalización de Cloud Services para actualizar a la versión de octubre de AEM Guides as a Cloud Service.

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con la versión de octubre de 2022 de AEM Guides as a Cloud Service.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| No compatible | Actualización 4 de 2020 y posterior |
| | |

*Las condiciones y de línea de base creadas en AEM son compatibles con las versiones de FMPS a partir de 2020.2.

### Conector de oxígeno

| Versión de AEM Guides as a Cloud | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2022.10.0 | 2.7.13 | 2.7.13 | 2,3 | 2,3 |
|  |  |  |  |  |


## Nuevas funciones y mejoras

AEM Guides as a Cloud Service proporciona mejoras y nuevas funciones en la versión de octubre:


### Panel Generación rápida

Ahora, AEM Guides proporciona el panel **Generación rápida**, que le ayuda a generar y ver rápidamente la salida de los ajustes preestablecidos creados para su mapa DITA.

![Icono de generación rápida](assets/quick-generate-icon.png)

En el panel **Generación rápida**, puede ver la lista de todos los ajustes preestablecidos de salida creados para su mapa DITA.

![Panel de generación rápida](assets/quick-generate-panel.png)

Seleccione uno o más ajustes preestablecidos y genere rápidamente la salida. También puede ver rápidamente el resultado generado para los ajustes preestablecidos. Se muestra un mensaje de éxito en la generación de la salida. Se muestra un mensaje de error si falla la generación de salida. También puede ver el registro de errores para ver los detalles del error que se produjo en el proceso de generación.


## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

* PDF nativo | Error al eliminar temas solo de recursos de la salida de PDF. (10554)
* PDF nativo | Las referencias clave vacías aparecen en la salida de PDF. (10553)
* PDF nativo No se cumple | `navtitle` para `topichead`. (10509)
* PDF nativo | Se necesita soporte para los sabores JDK de amd64. (10465)
* PDF nativo | No se pueden ocultar los temas de front-matter de la tabla de contenido. (10355)
* PDF nativo | Al reiniciar el número de página en el diseño del capítulo, la numeración se inicia aleatoriamente desde el final del capítulo anterior. (10154)
* Explorador de Chrome | La pantalla se queda en blanco al arrastrar y soltar cualquier elemento de la interfaz de usuario. Por ejemplo, al arrastrar una condición desde el panel Condiciones. (10524)
* Las propiedades del nodo se eliminan después de la operación de copiar y pegar de un recurso. (10053)
* Al hacer clic en **Cerrar** usuarios se estaban redirigiendo a los recursos; la experiencia se ha corregido para llevar a los usuarios a la página principal de AEM. (9654)
