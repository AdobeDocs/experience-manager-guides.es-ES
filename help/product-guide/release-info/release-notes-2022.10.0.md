---
title: Notas de versión | Versión as a Cloud Service de las guías de Adobe Experience Manager, octubre de 2022
description: Versión de octubre de Adobe Experience Manager Guides as a Cloud Service
exl-id: 38638080-625c-49c3-9e54-56cc23831546
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 1%

---

# Versión de octubre de Adobe Experience Manager Guides as a Cloud Service

## Actualización a la versión de octubre

Actualice las guías de Adobe Experience Manager actuales as a Cloud Service (más adelante denominadas *AEM Guías de as a Cloud Service*) realizando los siguientes pasos:
1. Consulte el código Git de los Cloud Service y cambie a la rama configurada en la canalización de Cloud Service correspondiente al entorno que desea actualizar.
1. Actualizar `<dox.version>` propiedad en `/dox/dox.installer/pom.xml` de su código Git de Cloud Service a 2022.10.183.
1. Confirme los cambios y ejecute la canalización de Cloud Service AEM para actualizar a la versión de octubre de las guías de la aplicación as a Cloud Service de la.

## Matriz de compatibilidad

AEM En esta sección se muestra la matriz de compatibilidad para las aplicaciones de software compatibles con las guías de la aplicación de la versión de octubre de 2022 as a Cloud Service por las Guías de.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| No compatible | Actualización 4 de 2020 y posterior |
| | |

AEM *La línea de base y las condiciones creadas en la versión de FMPS a partir de 2020.2 son compatibles con las versiones de FMPS.

### Conector de oxígeno

| AEM Versión de Guides as a Cloud de | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2022.10.0 | 2.7.13 | 2.7.13 | 2,3 | 2,3 |
|  |  |  |  |


## Nuevas funciones y mejoras

AEM En la versión de octubre de se incluyen mejoras y nuevas funciones en el as a Cloud Service de Guías de:


### Panel Generación rápida

AEM Ahora, Guías de proporciona el **Generación rápida** panel que ayuda a generar y ver rápidamente la salida de los ajustes preestablecidos creados para el mapa DITA.

![Icono Generar rápidamente](assets/quick-generate-icon.png)

En el **Generación rápida** , puede ver la lista de todos los ajustes preestablecidos de salida creados para el mapa DITA.

![Panel Generación rápida](assets/quick-generate-panel.png)

Seleccione uno o más ajustes preestablecidos y genere rápidamente la salida. También puede ver rápidamente el resultado generado para los ajustes preestablecidos. Se muestra un mensaje de éxito en la generación de la salida. Se muestra un mensaje de error si falla la generación de salida. También puede ver el registro de errores para ver los detalles del error que se produjo en el proceso de generación.


## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

* PDF nativo | Se produce un error al eliminar temas solo de recursos de la salida del PDF. (10554)
* PDF nativo | Las referencias clave vacías aparecen en la salida del PDF. (10553)
* PDF nativo | `navtitle` para `topichead` no se cumple. (10509)
* PDF nativo | Se necesita soporte para los sabores JDK de amd64. (10465)
* PDF nativo | No se pueden ocultar los temas de front-matter de la tabla de contenido. (10355)
* PDF nativo | Al reiniciar el número de página en el diseño del capítulo, la numeración se inicia aleatoriamente desde el final del capítulo anterior. (10154)
* Navegador Chrome | La pantalla se queda en blanco al arrastrar y soltar cualquier elemento de la interfaz de usuario. Por ejemplo, al arrastrar una condición desde el panel Condiciones. (10524)
* Las propiedades del nodo se eliminan después de la operación de copiar y pegar de un recurso. (10053)
* Al hacer clic  **Cerrar** AEM los usuarios se redirigían a los recursos: la experiencia se ha corregido para llevar a los usuarios a la página principal de la página de la aplicación de la. (9654)
