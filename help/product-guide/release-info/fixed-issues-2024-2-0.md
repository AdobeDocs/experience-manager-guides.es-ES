---
title: Notas de versión | Se han corregido problemas en la versión 2024.2.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2024.2.0 de Adobe Experience Manager Guides as a Cloud Service.
exl-id: fae1ff07-6232-4e9a-a89e-5e760e807b9d
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 4%

---

# Se han corregido problemas en la versión 2024.2.0

Este artículo cubre los errores corregidos en varias áreas de la versión 2024.2.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 2024.2.0](whats-new-2024-2-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2024.2.0](upgrade-instructions-2024-2-0.md).



## Creación

- La revisión ortográfica en el editor no permite la selección de sugerencias. (15045)
- El botón de navegación global no funciona y el panel no se puede cargar. (14968)
- En el editor web, la función de mapa de descarga no almacena en déclencheur una notificación emergente cuando está lista para descargarse. (14626)
- En el editor web, la función de mapa de descarga no puede descargar un mapa con una línea de base. (14622)
- Error de DTD no válido en la versión de octubre de 2023 de Experience Manager Guides as a Cloud Service. (14482)
- Si arrastra un tema del glosario desde el repositorio a un mapa del glosario, se creará `topicref`. (10767)
- La pantalla de vista previa de los fragmentos de código está inmovilizada. (14840)
- Las etiquetas del archivo `labels.json` aparecen en orden aleatorio en el Editor Web. (10508)

## Publicación

- En la publicación en PDF nativo, los atributos personalizados dentro de ajustes preestablecidos de condición no funcionan para la publicación en PDF nativo. (14943)
- En la publicación de PDF nativos, las referencias clave no se resuelven para la versión de diciembre de 2023 de Adobe Experience Manager Guides. (15085)
- La publicación de AEM Sites falla y causa errores de ámbito para los archivos que tienen `xref` en el archivo DITA que comienza con &quot;HTTP&quot;. (15154)
- No se puede agregar una plantilla personalizada desde la ficha **Salidas** del Editor. (14846)
- AEM El ajuste preestablecido **Site** no funciona debido a una ruta de acceso de plantilla vacía. (14804)
- AEM La regeneración de sitios falla en los mapas DITA con temas que contienen ecuaciones MathML. (14790)
- En la publicación de PDF nativo, la generación de PDF genera errores al obtener dependencias para la publicación `Node.js`. (14445)
- AEM El ajuste preestablecido no permite la selección de una plantilla fuera de la jerarquía de `/content` en el editor web. (14260)
- En la salida de AEM Sites, el estilo o los saltos de línea se perdieron para el elemento `<lines>` que tiene subelementos. (12542)
- Los metadatos personalizados no están disponibles en la salida final. (12116)
- En la publicación de PDF nativo, las propiedades de metadatos de mapa DITA no se pueden utilizar para rellenar los metadatos de salida de archivo de PDF. (15159)



## Administración

- Los archivos de **Filtro de línea de base** no funcionan con Nombre de archivo en el Editor web. (13486)
- Desactivar la indexación del mapa DITA principal para obtener un mejor rendimiento puede afectar a la funcionalidad de determinadas funciones.(12213)


## Revisión

- El menú contextual del botón secundario no funciona para que **Accept** o **Reject** realice un seguimiento de los cambios. (14607)
- Cambiar para cerrar los temas de DITA en la pantalla de revisión no funciona en la versión de diciembre de 2023 de Adobe Experience Manager Guides. (14537)
- La personalización de las plantillas de correo electrónico para el flujo de trabajo de revisión no funciona con la superposición. (13954)

## Problema conocido

El Adobe ha identificado el siguiente problema conocido para la versión 2024.2.0:

- La versión 1.0 no se muestra en la interfaz de usuario del archivo DITA duplicado.
- La propagación de los metadatos de recursos no funciona para la versión 2024.2.0 con el microservicio habilitado para cualquier ajuste preestablecido.
