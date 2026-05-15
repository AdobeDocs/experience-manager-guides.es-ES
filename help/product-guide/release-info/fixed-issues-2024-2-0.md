---
title: Notas de versión | Se han corregido problemas en la versión 2024.2.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2024.2.0 de Adobe Experience Manager Guides as a Cloud Service.
exl-id: fae1ff07-6232-4e9a-a89e-5e760e807b9d
TQID: https://experienceleague.adobe.com/z-L0sZ2HH720nI3LyDjiIqujxSBP-QLdPqvEInNNRnE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 504
ht-degree: 8%

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

- En la publicación nativa de PDF, los atributos personalizados dentro de ajustes preestablecidos de condición no funcionan para la publicación nativa de PDF. (14943)
- En la publicación nativa de PDF, las referencias clave no se resuelven para la versión de diciembre de 2023 de Adobe Experience Manager Guides. (15085)
- La publicación de AEM Sites falla y causa errores de ámbito para los archivos que tienen `xref` en el archivo DITA que comienza con &quot;HTTP&quot;. (15154)
- No se puede agregar una plantilla personalizada desde la ficha **Salidas** del Editor. (14846)
- El ajuste preestablecido **AEM Site** no funciona debido a una ruta de acceso de plantilla vacía. (14804)
- La regeneración del sitio de AEM falla en los mapas DITA con temas que contienen ecuaciones de MathML. (14790)
- En la publicación nativa de PDF, la generación de PDF genera errores al obtener dependencias para la publicación de `Node.js`. (14445)
- El ajuste preestablecido de AEM no permite la selección de una plantilla fuera de la jerarquía `/content` en el editor web. (14260)
- En la salida de AEM Sites, el estilo o los saltos de línea se perdieron para el elemento `<lines>` que tiene subelementos. (12542)
- Los metadatos personalizados no están disponibles en la salida final. (12116)
- En la publicación nativa de PDF, las propiedades de metadatos de mapa DITA no se pueden usar para rellenar los metadatos de salida de archivo PDF. (15159)



## Administración

- Los archivos de **Filtro de línea de base** no funcionan con Nombre de archivo en el Editor web. (13486)
- Desactivar la indexación del mapa DITA principal para obtener un mejor rendimiento puede afectar a la funcionalidad de determinadas funciones.(12213)


## Revisión

- El menú contextual del botón secundario no funciona para que **Accept** o **Reject** realice un seguimiento de los cambios. (14607)
- Cambiar para cerrar los temas de DITA en la pantalla de revisión no funciona en la versión de diciembre de 2023 de Adobe Experience Manager Guides. (14537)
- La personalización de las plantillas de correo electrónico para el flujo de trabajo de revisión no funciona con la superposición. (13954)

## Problema conocido

Adobe ha identificado el siguiente problema conocido para la versión 2024.2.0:

- La versión 1.0 no se muestra en la interfaz de usuario del archivo DITA duplicado.
- La propagación de los metadatos de recursos no funciona para la versión 2024.2.0 con el microservicio habilitado para cualquier ajuste preestablecido.
