---
title: Notas de versión | Instrucciones de actualización y problemas corregidos en la versión 4.3.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores y cómo actualizar a las versiones 4.3.0 de Adobe Experience Manager Guides
exl-id: 7fb568a0-0b88-4ea0-9b79-2625336348ff
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1085'
ht-degree: 1%

---

# Versión 4.3.0 de Adobe Experience Manager Guides (julio de 2023)

Esta nota de la versión cubre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en la versión 4.3.0 de Adobe Experience Manager Guides (más adelante denominada *AEM Guides*).

Para obtener más información sobre las nuevas características y mejoras, consulte [Novedades de la versión 4.3.0 de Adobe Experience Manager Guides](./whats-new-4-3-release.md).

## Actualización a la versión 4.3.0 de AEM Guides


Puede actualizar fácilmente su versión actual de AEM Guides a la versión 4.3.0. Antes de continuar actualizando a la versión 4.3.0 de AEM Guides, debe tener en cuenta los siguientes puntos:
Puede actualizar su versión actual de AEM Guides a la versión 4.3.0

- Si utiliza la versión 4.2 o 4.2.x, puede actualizar directamente a la versión 4.3.0.
- Si utiliza la versión 4.1 o 4.1.x, debe actualizar a la versión 4.2 o 4.2.x antes de actualizar a la versión 4.3.0.
- Si está utilizando la versión 4.0, debe actualizar a la versión 4.2 antes de actualizar a la versión 4.3.0.
- Si utiliza la versión 3.8.5, debe actualizar a la versión 4.0 antes de actualizar a la versión 4.2.
- Si su versión es anterior a la 3.8.5, consulte la sección Actualización de AEM Guides en la guía de instalación específica del producto.



>[!NOTE]
>
>Debe instalar AEM Service Pack antes de actualizar la versión de AEM Guides.

Para obtener más información, consulte [Instrucciones de actualización](../install-guide/upgrade-xml-documentation.md).

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con la versión 4.3.0 de AEM Guides.

### Adobe Experience Manager

**4.3.0 sin UUID**
Paquete de servicio 18, 17, 16, 15 o 14 de la versión 6.5

**UUID 4.3.0**
Paquete de servicio 18, 17, 16, 15 o 14 de la versión 6.5

Para obtener más información, consulte la sección *Requisitos técnicos* en la guía Instalar y configurar Adobe Experience Manager Guides.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.3.0 (no UUID) | 2022 o superior | 2020.2 o superior* | 2022 o superior | 2020.3 o superior |
| 4.3.0 (UUID) | 2022 o superior | 2020.2 o superior* | 2022 o superior | 2020.4 o superior |
| | | | | |

*Las condiciones y de línea de base creadas en AEM son compatibles con las versiones de FMPS a partir de 2020.2.

### Conector de oxígeno

| Versión | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.3.0 (no UUID) | 2.3-regular-5 | 2.3-regular-5 | 1,6 | 1,6 |
| 4.3.0 (UUID) | 3.0-uuid-4 | 3.0-uuid-3 | 2,3 | 2,3 |
|  |  |   |  |  |

## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

### Creación

- El archivo de tema no está desbloqueado en el Editor Web, aunque las opciones Desbloquear el archivo y No guardar están seleccionadas. (12558)
- No se puede desproteger un archivo en el Editor Web, a pesar de que se ha elegido la opción NO para descartar los cambios antes de protegerlo. (12557)
- La información sobre herramientas de los iconos Bloquear y desbloquear archivo de la barra de herramientas principal del Editor Web no es coherente con los iconos mostrados en la Vista de repositorio.(12555)
- La opción Cancelar desprotección y Desbloquear se muestra para un archivo del Editor Web que aún no se ha desprotegido en la Vista de mapa. (12556)
- No se pueden seleccionar los recursos de PDF en los vínculos &quot;topicref&quot; existentes. (12477).
- Al realizar una combinación y una división en las tablas, AEM Guides 4.2 genera celdas de tabla adicionales. (11793)
- En la vista de repositorio, los temas o imágenes no se pueden arrastrar después de usar la funcionalidad Buscar/Filtrar. (12396)
- Los resultados de búsqueda se desactivan en el panel Buscar y reemplazar después de abrir un archivo buscado. (12142)
- La tecla numérica &quot;8&quot; del teclado lateral no funciona en el editor de AEM Guides. (12106)
- Los atributos en línea/de visualización no aparecen en la vista Presentación del Editor Web. (12498)
- La configuración de la interfaz de usuario del perfil global no coincide con el perfil de carpeta. (11970)
- Las referencias de contenido se rompen cuando los ficheros DITA se copian y pegan. (11959)
- No se puede editar el fragmento de contenido en la vista de columna con AEM Guides instalado. (7342)
- El contenido se pierde cuando una referencia xref no ajustada se encuentra bajo etiquetas de subelemento. (12532)
- El flujo de trabajo de aprobación no funciona cuando docstate se cambia a &quot;end state&quot; desde las propiedades de archivo del panel derecho. (11026)
- IU de recursos | En la vista de lista, las columnas disponibles superpuestas no se pueden combinar. (11528)
- Keyref no se resuelve en la vista de mapa. (11490)
- El menú superior no aparece al navegar por el editor XML. (10868)
- `conref` en etiqueta ph | El cuadro de diálogo de exploración mostrado es incorrecto. (9481)
- Los vínculos locales a otros elementos no se resuelven en el Editor web. (8790)
- La función Matches() no funciona en la función schematron. (11224)



### Administración

- El campo &quot;title&quot; en las propiedades de metadatos de mapa DITA se sobrescribe con el elemento `<title>` para el mapa. (10702)
- Al intentar abrir o actualizar la versión de los temas en la línea de base, el cargador &quot;Recuperando información del servidor&quot; se ejecuta indefinidamente.(12478)


### Revisión

- Nueva IU de revisión | Las condiciones de resaltar y mostrar u ocultar funcionan de forma diferente a como funcionan en el Editor web. (11628)

### Publicación

- La publicación falla al cambiar el nombre de un ajuste preestablecido nativo de PDF. (12564)
- Al duplicar una plantilla de PDF nativa, se duplica la ubicación de la plantilla predeterminada en lugar de la ubicación de la plantilla personalizada proporcionada. (12563)
- PDF nativo | Los metadatos de idioma no se pueden establecer en el PDF generado para cumplir con WCAG 2.0. (12407)
- La publicación en el sitio de AEM falla al leer archivos temporales del pod que pueden haberse actualizado o reiniciado. (12113)
- PDF nativo | Los atributos personalizados no se propagan al motor temporal HTML o PDF. (DXML-12005)
- PDF nativo |  Java OutOfMemoryError se produce al publicar contenido grande. (11789)
- PDF nativo | Xref está imprimiendo el contenido del título del tema href en lugar de la etiqueta Xref. (11322)
- PDF nativo | No se puede guardar la configuración de la plantilla de PDF. (10751)
- PDF nativo | El texto se extiende más allá del ancho de la columna al incluir varias referencias x. (10876)
- PDF nativo | El elemento `<note>` `</note>` no genera un título de espacio adicional de su tipo. (10549)
- Salida JSON | La propiedad `fmUuid` del nodo jcr:content de JSON es diferente del &quot;id&quot; dentro de JSON. (11564)
- Salida JSON | Si el mapa y el tema con el mismo nombre de archivo están presentes, se elimina JSON para el mapa. (11524)

## Problema conocido

Adobe ha identificado el siguiente problema conocido de la versión 4.3.0 de AEM Guides:

- El diseño de página común definido en la plantilla básica no se aplica como plantilla predeterminada.

  Solución alternativa:
Agregue el diseño de página común como portada y contraportada y, a continuación, comenzará a llegar para cada página.
- El problema se produce en la búsqueda del sitio al buscar en la página de salida del sitio de AEM en el paquete de servicio 16 o 17 de AEM.

  Solución alternativa:

   1. Abrir archivo con la ruta: `/libs/foundation/components/search/search.jsp` en `crx/de`
   1. Reemplace el número de línea 234 por el siguiente código:

      ```
      <a href="<c:url value="${hit.URL}" context="/"/>" onclick="trackSelectedResult(this, ${status.index + 1})"><%= xssAPI.filterHTML(((Search.Hit) pageContext.getAttribute("hit")).getTitle()) %></a>
      
      *(Add the missing closing anchor tag at the end).
      ```

   1. Guarde el archivo.
