---
title: Notas de versión | Instrucciones de actualización y problemas corregidos en la versión 4.2.1 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores y cómo actualizar a las versiones 4.2.1 de Adobe Experience Manager Guides
exl-id: a75ec83f-564b-4243-b5c5-341049521adb
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 1%

---

# Versión 4.2.1 de Adobe Experience Manager Guides (mayo de 2023)

Esta nota de la versión cubre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en la versión 4.2.1 de Adobe Experience Manager Guides (más adelante denominada *AEM Guides*).

Para obtener más información sobre las nuevas características y mejoras, consulte [Novedades de la versión 4.2.1 de Adobe Experience Manager Guides](whats-new-4-2-1-release.md).

## Actualización a la versión 4.2.1 de AEM Guides


Puede actualizar fácilmente su versión actual de AEM Guides a la versión 4.2.1. Antes de continuar actualizando a la versión 4.2.1 de AEM Guides, debe tener en cuenta los siguientes puntos:
Puede actualizar su versión actual de AEM Guides a la versión 4.2.1
* Si utiliza las versiones 4.1, 4.1.x o 4.2, puede actualizar directamente a la versión 4.2.1.
* Si está utilizando la versión 4.0, debe actualizar a la versión 4.2 antes de actualizar a la versión 4.2.1.
* Si utiliza la versión 3.8.5, debe actualizar a la versión 4.0 antes de actualizar a la versión 4.2.
* Si su versión es anterior a la 3.8.5, consulte la sección Actualización de AEM Guides en la guía de instalación específica del producto.

>[!NOTE]
>
>AEM Debe instalar el paquete de servicio de antes de actualizar la versión de AEM Guides.

Para obtener más información, consulte [Instrucciones de actualización](../install-guide/upgrade-xml-documentation.md).

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con AEM Guides 4.2. Versión 1 de.

### Adobe Experience Manager

**No UUID**
Paquete de servicio 15, 14, 13 o 12 de la versión 6.5

**UUID**
Paquete de servicio 15, 14, 13 o 12 de la versión 6.5

Para obtener más información, consulte la sección *Requisitos técnicos* en la guía Instalar y configurar Adobe Experience Manager Guides.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.2.1 (no UUID) | 2022 o superior | 2020.2 o superior* | 2022 o superior | 2020.3 o superior |
| 4.2.1 (UUID) | 2022 o superior | 2020.2 o superior* | 2022 o superior | 2020.4 o superior |
| | | | |

AEM *La línea de base y las condiciones creadas en la versión de FMPS a partir de 2020.2 son compatibles con las versiones de FMPS.

### Conector de oxígeno

| Versión | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.2.1 (no UUID) | 2.2-regular-3 | 2.2-regular-3 | 1,6 | 1,6 |
| 4.2.1 (UUID) | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |   |

## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

### Creación

* El Navtitle se elimina del contenido al cambiar de la vista Diseño a la vista Autor o Código fuente. (12174)
* AEM El botón Cerrar del Editor Web no lleva a la página Navegación de la. (11948)
* A veces, se produce un error de aplicación al hacer clic en un mapa DITA. (11842)
* El problema se produce al mover (arrastrar y soltar) un elemento de lista existente con el control de cambios activado. (11570)
* El problema se produce al mover (arrastrar y soltar) un nuevo elemento de lista con el control de cambios activado. (11569)
* La aplicación o anulación de sangría de elementos de lista no funciona según lo esperado con Control de cambios activado. (11568)
* Agregar contenido en una línea con Control de cambios activado y, a continuación, desactivar Control de cambios no lo desactiva. (11567)
* Dificultad para arrastrar y soltar un elemento de lista; el texto se mueve en lugar del elemento de lista. (11566)
* Al crear el elemento mostrado en verde (Control de cambios), el nuevo contenido se muestra como control de cambios aunque el control de cambios esté desactivado. (7021)
* El explorador (editor web) se bloquea al cargar contenido con el esquema personalizado. (11211)
* PDF nativo | Al crear un ajuste preestablecido de salida con la opción &quot;Añadir a perfil de carpeta&quot;, la generación del PDF falla con una excepción de puntero nulo. (10950)
* PDF nativo | La etiqueta de imagen agrega el atributo display-inline a todas las imágenes. (10653)
* La inserción de archivos multimedia de audio y vídeo falla en el formato YouTube bajo el icono **Insertar multimedia**. (11320)
* El error de validación se produce cuando se crea un mapa con la plantilla que tiene un elemento de título especializado. (11212)
* Editor web | Se agrega espacio de no separación en el Editor XML al editar un tema. (11786)

### Administración

* La ficha Informes de la interfaz de usuario del editor web no muestra la lista de temas de los mapas DITA creados antes de la actualización a la versión 4.2. (11708)

* La funcionalidad del botón Cargar archivos de la IU de Assets se interrumpe en la versión 4.2. (11633)


### Publicación

* PDF nativo | La publicación de contenido que tiene una clase de salida con paréntesis() provoca la congelación de la publicación. (11936)
* Salida JSON | La asignación de metadatos con valor de propiedad como `"value in spaces and double quotes"` produce un error de publicación. (11933)
* AEM El problema se produce en la búsqueda del sitio de la (no funciona más allá de 2-3 nodos de nivel). (11352)
* Editor web | AEM La ruta y la plantilla de salida no se pueden seleccionar en el ajuste preestablecido de la. (11530)
* Al actualizar de la versión 4.1.x a la 4.2, el motor de PDF nativo no funciona y genera NullPointerException incluso para el sistema operativo compatible.(11526)
* El proceso del PDF de descarga no funciona correctamente en el editor web. (11496)
* PDF nativo | Los comentarios del borrador están ocultos de forma predeterminada en la salida generada. (10560)
* PDF nativo | el título de navegación no se respeta para topichead. (10509)
* PDF nativo | Agregar `xref` a una imagen no procesa la imagen en el PDF generado. (11346)
* PDF nativo | la nota al pie presente en el encabezado de la tabla lleva a texto en negrita y alineado al centro en el pie de página correspondiente dentro de la salida del PDF. (10610)

### Traducción

* Con la actualización 4.2, todo el contenido de traducción se muestra fuera de sincronización o sin copia. (11834)

### Revisión

* La revisión completada no se abre en modo de solo lectura. (11387)
