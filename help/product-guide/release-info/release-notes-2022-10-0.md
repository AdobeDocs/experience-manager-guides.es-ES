---
title: Notas de versión | Adobe Experience Manager Guides as a Cloud Service, versión de octubre de 2022
description: Versión de Adobe Experience Manager Guides as a Cloud Service de octubre
exl-id: 38638080-625c-49c3-9e54-56cc23831546
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 1%

---

# Versión de Adobe Experience Manager Guides as a Cloud Service de octubre

## Actualización a la versión de octubre

Actualice la configuración actual del as a Cloud Service de Adobe Experience Manager Guides (más adelante denominado *AEM Guides as a Cloud Service*) realizando los siguientes pasos:
1. Consulte el código Git de los Cloud Service y cambie a la rama configurada en la canalización de Cloud Service correspondiente al entorno que desea actualizar.
1. Actualice la propiedad `<dox.version>` en el archivo `/dox/dox.installer/pom.xml` de su código Git de Cloud Service a 2022.10.183.
1. Confirme los cambios y ejecute la canalización de Cloud Service para actualizar a la versión de octubre del as a Cloud Service de AEM Guides.

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con la versión de AEM Guides as a Cloud Service para octubre de 2022.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| No compatible | Actualización 4 de 2020 y posterior |
| | |

AEM *La línea de base y las condiciones creadas en la versión de FMPS a partir de 2020.2 son compatibles con las versiones de FMPS.

### Conector de oxígeno

| Versión de AEM Guides as a Cloud | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2022.10.0 | 2.7.13 | 2.7.13 | 2,3 | 2,3 |
|  |  |  |  |


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

* PDF nativo | Se produce un error al eliminar los temas solo de recursos de la salida del PDF. (10554)
* PDF nativo | Las referencias clave vacías aparecen en la salida del PDF. (10553)
* PDF nativo | `navtitle` de `topichead` no se cumple. (10509)
* PDF nativo | Se necesita compatibilidad con los sabores JDK de amd64. (10465)
* PDF nativo | No se pueden ocultar los temas de front-matter de la tabla de contenido. (10355)
* PDF nativo | Al reiniciar el número de página en el diseño del capítulo, se inicia aleatoriamente la numeración desde el final del capítulo anterior. (10154)
* Explorador de Chrome | La pantalla se queda en blanco al arrastrar y soltar cualquier elemento de la interfaz de usuario. Por ejemplo, al arrastrar una condición desde el panel Condiciones. (10524)
* Las propiedades del nodo se eliminan después de la operación de copiar y pegar de un recurso. (10053)
* AEM Al hacer clic en **Cerrar** usuarios se estaban redirigiendo a los recursos; la experiencia se ha corregido para llevar a los usuarios a la página principal de la página de inicio de la página de inicio. (9654)
