---
title: Notas de versión | Se han corregido problemas en las guías de Adobe Experience Manager, versión 2024.2.0
description: Obtenga información acerca de las correcciones de errores en la versión 2024.2.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 3da78dd90bd219809d0a47bcdc2775b2c5ba29e1
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 0%

---

# Se han corregido problemas en la versión 2024.2.0

Este artículo cubre los errores corregidos en varias áreas de la versión 2024.2.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 2024.2.0](whats-new-2024-2-0.md).

Más información [instrucciones de actualización para la versión 2024.2.0](upgrade-instructions-2024-2-0.md).



## Creación

- La revisión ortográfica en el editor no permite la selección de sugerencias. (15045)
- El botón de navegación global no funciona y el panel no se puede cargar. (14968)
- En el editor web, la función de mapa de descarga no almacena en déclencheur una notificación emergente cuando está lista para descargarse. (14626)
- En el editor web, la función de mapa de descarga no puede descargar un mapa con una línea de base. (14622)
- Error de DTD no válido en la versión de octubre de 2023 de las guías del Experience Manager as a Cloud Service. (14482)
- Arrastrar un tema del glosario desde el repositorio a un mapa del glosario crea `topicref`. (10767)
- La pantalla de vista previa de los fragmentos de código está inmovilizada. (14840)
- Etiquetas de la `labels.json` Los archivos aparecen en orden aleatorio en el Editor Web. (10508)

## Publicación

- En la publicación en PDF nativo, los atributos personalizados dentro de ajustes preestablecidos de condición no funcionan para la publicación en PDF nativo. (14943)
- En la publicación de PDF nativos, las referencias clave no se resuelven para la versión de diciembre de 2023 de las guías de Adobe Experience Manager. (15085)
- La publicación de AEM Sites falla y provoca errores de ámbito en los archivos que tienen `xref` al fichero DITA que empieza por &quot;HTTP&quot;. (15154)
- No se puede añadir una plantilla personalizada desde el **Salidas** en el Editor. (14846)
- **AEM Sitio web de** el ajuste preestablecido no funciona debido a una ruta de plantilla vacía. (14804)
- AEM La regeneración de sitios falla en los mapas DITA con temas que contienen ecuaciones MathML. (14790)
- En la publicación de PDF nativos, la generación de PDF genera errores al obtener dependencias para `Node.js` publicación. (14445)
- AEM El ajuste preestablecido no permite la selección de una plantilla fuera del `/content` jerarquía en el editor web. (14260)
- En la salida de AEM Sites, el estilo o los saltos de línea se perdieron para la variable `<lines>` elemento con subelementos. (12542)
- Los metadatos personalizados no están disponibles en la salida final. (12116)
- En la publicación de PDF nativo, las propiedades de metadatos de mapa DITA no se pueden utilizar para rellenar los metadatos de salida de archivo de PDF. (15159)



## Administración

- **Filtro de línea base** Los archivos no funcionan con Nombre de archivo en el Editor web. (13486)
- Desactivar la indexación del mapa DITA principal para obtener un mejor rendimiento puede afectar a la funcionalidad de determinadas funciones.(12213)


## Revisión

- El menú contextual del botón secundario no funciona para **Aceptar** o **Rechazar** haga un seguimiento de cambios. (14607)
- Cambiar para cerrar los temas de DITA en la pantalla de revisión no funciona en la versión de diciembre de 2023 de las guías de Adobe Experience Manager. (14537)
- La personalización de las plantillas de correo electrónico para el flujo de trabajo de revisión no funciona con la superposición. (13954)

## Problema conocido

El Adobe ha identificado el siguiente problema conocido para la versión 2024.2.0:

- La versión 1.0 no se muestra en la interfaz de usuario del archivo DITA duplicado.
- La propagación de los metadatos de recursos no funciona para la versión 2024.2.0 con el microservicio habilitado para cualquier ajuste preestablecido.

