---
title: Notas de versión | Se han corregido problemas en la versión 2025.06.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2025.06.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 78d8896982ff73e954de6d6daa9832faf30ed3b3
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 4%

---

# Se han corregido problemas en la versión 2025.06.0

Este artículo cubre los errores corregidos en varias áreas de la versión 2025.06.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas funciones y mejoras, consulte [Novedades de la versión 2025.06.0](whats-new-2025-06-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2025.06.0](upgrade-instructions-2025-06-0.md).

## Creación

- Al abrir un mapa DITA con el shell unificado habilitado, el editor se actualiza de forma intermitente. (GUIDES-26919)
- Si no se cierran las conexiones de sesión JCR al actualizar o crear temas, se producen pérdidas de memoria y tiempo de inactividad del servicio. (GUIDES-26282)
- Al arrastrar las columnas, su anchura cambia de valores de porcentaje a valores de píxel, lo que da como resultado tablas distorsionadas o mal alineadas.(GUIDES-23128)
- Cuando el contenido se pega en `code block` o cuando se agregan espacios en `code block` y se cambia la vista, se pierde el espaciado. (GUIDES-27478)
- Al agregar un mapa a `bookmap`, se almacena en `fmditatopicrefs` en lugar de en `fmditamaprefs`. (GUIDES-25480)
- El cuadro de diálogo **Insertar imagen** no se representa correctamente en una pantalla de alta resolución o con zoom ampliado, lo que hace que desaparezcan el título de la figura y los campos de texto alternativo. (GUIDES-26459)


## Publicación

- La publicación nativa de PDF continúa indefinidamente si el contenido DITA tiene un vínculo web sin tener el ámbito `external`. (GUIDES-26434)
- La publicación de PDF nativos y sitios de AEM se detiene y se pone en cola cuando hay errores en el contenido. (GUIDES-26516)
- Al crear una nueva línea base con un gran número de etiquetas, se evita que se recuperen todas las etiquetas. (GUIDES-16232)
- Al generar páginas de sitio de AEM con títulos que incluyen varias palabras separadas por espacios, el título del mapa muestra guiones en lugar de espacios. (GUIDES-27903)
- Para PDF nativo, no se está resolviendo un nombre de propiedad de metadatos no válido y se muestra como `unresolved property name` en **propiedades de documento**. (GUIDES-25680)
- El texto multilínea dentro de `codeblock` causa problemas de desbordamiento de texto durante la generación de PDF. (GUIDES-15541)
- Al añadir mapas a la colección de mapas, se muestran recursos que no sean mapas (le gustan los temas, etc.) y los idiomas de mapa traducidos tampoco se ordenan correctamente.(GUIDES-25085)


## Revisión

- La vista de documento de la IU de revisión no ajusta el contenido para algunos tamaños de pantalla, lo que requiere que los usuarios se desplacen horizontalmente para ver el contenido completo. (GUIDES-25292)


## Problemas conocidos

Adobe ha identificado el siguiente problema conocido para la versión 2025.06.0:

- Cuando se utiliza la opción Buscar y reemplazar, después de aplicar la operación Reemplazar una sola incidencia en un archivo, no se pueden realizar más acciones en el panel Buscar y reemplazar. (GUIDES-28930)

- En un perfil de carpeta, cuando se elimina un recurso ya indexado de la interfaz de usuario, la ruta indexada correspondiente no se elimina y un intento de reindexación falla con un mensaje de error. (GUIDES-29147) <br>**Solución alternativa:** Debe quitar la ruta obsoleta que ya no existe antes de iniciar la reindexación.

- Si un mapa contiene dependencias cíclicas y se abre la Vista previa del mapa, las vistas Source, Autor y Diseño dejarán de ser accesibles hasta que se actualice la página. (GUIDES-28334) <br>**Solución alternativa:** Debe actualizar la página para restaurar el acceso a estas vistas.
